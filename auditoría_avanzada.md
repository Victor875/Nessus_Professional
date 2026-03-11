## Caso Práctico: Auditoría con Credenciales y Cumplimiento (Compliance)

Para elevar el nivel de este laboratorio, decido no limitarme a un escaneo de red básico. Ejecuto una **Auditoría de Caja Blanca** (con credenciales) para obtener una visibilidad total sobre las debilidades de configuración del sistema operativo.

## 1. Preparación del Entorno (Windows 11)

Para que el escaneo sea exitoso y Nessus pueda "entrar" en el sistema operativo, realizo las siguientes configuraciones críticas en el host objetivo:

### A. Configuración de Servicios
* **Remote Registry:** establezco el servicio en modo **Automático** e **Iniciado**. Esto permite a Nessus realizar consultas sobre el registro del sistema para verificar parches y configuraciones.

Para permitir que Nessus consulte el registro del sistema, sigo estos pasos:
1. Presiono la combinación de teclas Win + R, escribo services.msc y pulso Enter.
2. Localizo el servicio llamado Registro remoto (Remote Registry).
3. Hago clic derecho sobre él y selecciono Propiedades.
4. Establezco el Tipo de inicio en Automático y hago clic en el botón Iniciar.
5. Comando de verificación: también puedo validarlo rápidamente desde PowerShell: `Get-Service RemoteRegistry`

![Estado del servicio Remote Registry](Deshabilitar_UAC.jpg)

### B. Reglas de Firewall (SMB)
Habilito el tráfico a través del puerto **445 (TCP)**. Este puerto es esencial para la comunicación **SMB (Server Message Block)**, que es el túnel por el cual Nessus inyectará las credenciales.

### C. Bypass de UAC para Cuentas Locales
Como utilizo una cuenta de administrador local, aplico este cambio en el registro mediante PowerShell para permitir que la cuenta administrativa local gestione las consultas remotas de Nessus:

```powershell
New-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System" -Name "LocalAccountTokenFilterPolicy" -Value 1 -PropertyType DWord -Force
```
![Estado del servicio Remote Registry](Deshabilitar_UAC.jpg)

### 2. Auditoría basada en el Estándar CIS
En lugar de un escaneo genérico, cargo una política de cumplimiento basada en el **CIS Windows 11 Enterprise Benchmark**. 
* **Objetivo:** evaluar el nivel de *Hardening* del equipo frente a un estándar de la industria.
* **Proceso:** Nessus verifica automáticamente cientos de configuraciones, como la longitud mínima de contraseñas, servicios innecesarios activos y políticas de auditoría de eventos.



### 3. Análisis de Resultados Avanzados
A diferencia del escaneo básico, esta prueba revela vulnerabilidades críticas que no son detectables a través de la red, como:
* Parches de seguridad (KBs) faltantes en el sistema operativo.
* Configuraciones de red inseguras a nivel de protocolo (ej. NetBIOS activo).
* Software de terceros desactualizado con exploits conocidos.
