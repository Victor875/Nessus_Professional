# Nessus Expert
En esta sección detallo los motivos por los cuales he seleccionado Nessus Expert para este laboratorio, destacando sus capacidades de visibilidad sobre la superficie de ataque moderna

## Introducción

En este proyecto, realizo una auditoría de seguridad utilizando Nessus Expert sobre un entorno controlado en Windows 11. Mi objetivo es demostrar la capacidad de identificar, clasificar y priorizar vulnerabilidades tanto en activos internos como en la superficie de ataque externa. Esta práctica simula un flujo de trabajo real de un analista de ciberseguridad, desde la fase de reconocimiento hasta la propuesta de remediación.

## ¿Por qué utilizar Nessus Expert?

He seleccionado la versión Expert frente a la Professional o Essentials por su capacidad de ir más allá de la red tradicional. Como estoy documentando una auditoría integral, necesito las funciones exclusivas que esta versión ofrece:

### Comparativa Técnica: Nessus Expert

| Característica | Ventajas (Pros) | Desventajas (Contras) |
| :--- | :--- | :--- |
| **Visibilidad Externa** | **EASM:** permite descubrir activos en internet que no están inventariados. | Requiere configuración DNS precisa; si no, los resultados son limitados. |
| **Infraestructura Cloud** | **Escaneo de IaC:** audita plantillas de Terraform o CloudFormation antes del despliegue. | La versión de prueba limita la profundidad de análisis en la nube. |
| **Priorización de Riesgos** | **Métrica VPR:** prioriza vulnerabilidades según la probabilidad real de explotación. | Requiere conexión constante a Tenable para actualizar inteligencia de amenazas. |
| **Escalabilidad** | Permite gestionar hasta 32 hosts en la versión Trial, ideal para auditorías específicas. | El límite de 32 hosts es insuficiente para redes corporativas medianas. |
| **Facilidad de Uso** | Interfaz intuitiva sobre Windows 11 con reportes ejecutivos profesionales. | El consumo de RAM de `nessusd.exe` es elevado durante escaneos intensivos. |

## Guía de Instalación y Configuración

Para replicar este entorno de auditoría en **Windows 11**, sigo estos pasos de manera secuencial:

1. **Descarga de software:** obtengo el instalador oficial de **Nessus Expert** directamente desde el portal de descargas de Tenable, seleccionando la arquitectura compatible con mi sistema.
2. **Ejecución del instalador:** ejecuto el archivo `.msi` y sigo las instrucciones del asistente de instalación. Durante este proceso, verifico que el servicio `nessusd` se inicie correctamente en el sistema.
3. **Activación de la instancia:** accedo a la interfaz web a través de la dirección `https://localhost:8834`. Utilizo mi clave de licencia **Trial** (limitada a 32 hosts) para completar el registro y activar todas las capacidades de la versión Expert.
4. **Actualización crítica de Plugins:** una vez activado, espero a que la herramienta descargue e instale las últimas definiciones de vulnerabilidades. Considero este paso fundamental para garantizar que los resultados del escaneo sean precisos y detecten las amenazas más recientes.


## Ejemplo de uso: auditoría de red local

Como ejemplo práctico de uso, configuro un escaneo de red básico.
* **Metodología:** selecciono la plantilla básica para maximizar la compatibilidad y el descubrimiento de servicios.
* **Objetivos:** configuro mis activos locales (router y host principal), manteniéndome dentro del límite de 32 hosts de mi licencia.
* **Ejecución:** inicio el escaneo y monitorizo en tiempo real la pestaña de Vulnerabilities para observar la criticidad de los servicios detectados.

## Requisitos del Sistema (Entorno de Laboratorio)

Para asegurar un rendimiento óptimo de **Nessus Expert** durante los escaneos intensivos en mi máquina local, valido los siguientes requisitos mínimos:

* **Sistema Operativo:** Windows 11 Pro/Home (64-bit).
* **Procesador (CPU):** 4 núcleos de 2 GHz (mínimo recomendado para evitar cuellos de botella durante la compilación de plugins).
* **Memoria RAM:** 8 GB de RAM (se recomienda disponer de al menos 4 GB libres antes de iniciar el servicio `nessusd`).
* **Espacio en Disco:** 10 GB de espacio libre dedicado principalmente a la base de datos de plugins y al almacenamiento de los historiales de escaneo.
* **Navegador Web:** Google Chrome, Mozilla Firefox o Microsoft Edge actualizado para visualizar correctamente los gráficos del dashboard.
* **Navegador Web:** Google Chrome, Mozilla Firefox o Microsoft Edge actualizado.

> **Nota de rendimiento:** durante la fase de ejecución, monitorizo el Administrador de Tareas de Windows 11. Observo que el proceso de compilación de plugins es el que mayor carga de CPU genera. Por ello, cierro aplicaciones innecesarias antes de lanzar un escaneo avanzado para garantizar la integridad de los tiempos de respuesta del análisis.

## Conclusiones y Aprendizajes

Tras completar la configuración y ejecución de las auditorías con **Nessus Expert**, extraigo las siguientes conclusiones clave sobre la gestión de vulnerabilidades:

* **Visibilidad integral:** el uso de una herramienta de grado empresarial me permite pasar de una visión reactiva a una proactiva. He comprendido que identificar los activos (Discovery) es tan crítico como analizar sus fallos, ya que no se puede proteger lo que no se sabe que existe.
* **Priorización basada en riesgo:** la experiencia con la métrica VPR de Tenable me ha enseñado que no todas las vulnerabilidades críticas requieren atención inmediata; la clave de un analista eficiente es identificar cuáles tienen una probabilidad de explotación real en el contexto actual de amenazas.
* **Optimización de recursos:** la monitorización del sistema durante los escaneos me ha permitido entender el impacto técnico de las herramientas de seguridad en la infraestructura. La gestión del hardware y la correcta configuración de los plugins son determinantes para la calidad de los resultados.
* **Valor estratégico de Nessus Expert:** confirmo que las capacidades de análisis de superficie externa y IaC convierten a esta herramienta en una solución robusta para entornos modernos, yendo mucho más allá del escaneo de red tradicional.

Este proyecto consolida mi capacidad para desplegar soluciones de seguridad complejas, interpretar datos técnicos y documentar procesos de auditoría siguiendo estándares profesionales.


---

## Contacto y Portfolio

Si tienes alguna pregunta sobre este proyecto o quieres conectar para hablar sobre ciberseguridad y gestión de vulnerabilidades, no dudes en contactarme:

* **LinkedIn:** [Victor Suárez Sánchez-Pascuala](https://www.linkedin.com/in/victorssp/)
* **GitHub:** [Victor875](https://github.com/Victor875)

---
*Este proyecto fue realizado como parte de mi laboratorio de especialización en herramientas de seguridad ofensiva y defensiva.*
