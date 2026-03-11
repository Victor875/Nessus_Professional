# Nessus Expert
1. Introducción

En este proyecto, realizo una auditoría de seguridad utilizando Nessus Expert sobre un entorno controlado en Windows 11. Mi objetivo es demostrar la capacidad de identificar, clasificar y priorizar vulnerabilidades tanto en activos internos como en la superficie de ataque externa. Esta práctica simula un flujo de trabajo real de un analista de ciberseguridad, desde la fase de reconocimiento hasta la propuesta de remediación.

2. ¿Por qué utilizar Nessus Expert?

He seleccionado la versión Expert frente a la Professional o Essentials por su capacidad de ir más allá de la red tradicional. Como estoy documentando una auditoría integral, necesito las funciones exclusivas que esta versión ofrece:

Ventajas:
- External Attack Surface Management (EASM): me permite descubrir activos expuestos en internet que la organización podría desconocer (shadow IT).
- Escaneo de infraestructura como código (IaC): permite auditar archivos de configuración de nube antes del despliegue.
- Priorización VPR: a diferencia del CVSS estático, el VPR de Tenable me indica qué vulnerabilidades están siendo explotadas activamente en el mundo real.

Desventajas:

- Curva de aprendizaje: la configuración de módulos de superficie de ataque requiere conocimientos más profundos de DNS y activos externos.
- Requerimientos de hardware: al ser una herramienta tan completa, el consumo de recursos en mi máquina local durante escaneos intensivos es notable.

3. Guía de instalación y configuración
Para replicar este entorno en Windows 11, sigo estos pasos:
    1. Descarga: obtengo el instalador oficial de Nessus Expert desde el portal de Tenable.
    2. Instalación: ejecuto el archivo .msi y sigo el asistente, asegurándome de que el servicio nessusd se inicie correctamente.
    3. Activación: utilizo mi licencia Trial (limitada a 32 hosts) para activar el producto a través de la interfaz web en https://localhost:8834.
    4. Actualización de Plugins: espero a que la herramienta descargue las últimas definiciones de vulnerabilidades (paso crítico para obtener resultados precisos).


4. Ejemplo de uso: Auditoría de Red Local

Como ejemplo práctico de uso, configuro un Basic Network Scan.
- Metodología: selecciono la plantilla básica para maximizar la compatibilidad y el descubrimiento de servicios.
- Objetivos: configuro mis activos locales (router y host principal), manteniéndome dentro del límite de 32 hosts de mi licencia.
- Ejecución: inicio el escaneo y monitorizo en tiempo real la pestaña de Vulnerabilities para observar la criticidad de los servicios detectados.
