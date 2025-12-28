author: Nerea Candón Ramos
summary: Actividad Drug Trafficking parte 1
id: docs
categories: codelab,markdown
environments: Web
status: Published

# A2.2-DrugTrafficking

## Entorno de trabajo

Para la realización de esta actividad se van a utilizar las siguientes herramientas:

- **Máquina propia:**

    En este caso usaré mi propia máquina, un portátil MSi con un sistema operativo Windows 10, dónde se usarán las siguientes herramientas para poder completar la actividad.

<br>

- **Autopsy:**

   Es una herramienta de análisis forense digital orientada al estudio de dispositivos de almacenamiento, como discos duros, memorias USB o imágenes de disco. Su objetivo es facilitar la recuperación de archivos eliminados, el análisis de la información almacenada y la identificación de rastros de actividad del usuario que puedan utilizarse como evidencia en una investigación. Dispone de funcionalidades avanzadas como el análisis de sistemas de archivos, la revisión del historial de navegación, el examen de correos electrónicos y la recuperación de imágenes y vídeos. Mediante esta herramienta podremos extraer los distintos archivos que posteriormente serán analizados con Windows Registry Recovery.

<br>


## Información del sistema
| Información del sistema |  |
| :---- | :---- |
| **Tamaño de la partición (Byte)** | 2623832064 |
| **Prueba** | ![Sistema](/pruebas/sistema/sistema1.png) |
| **Sistema y versión del SO** | Microsoft Windows XP |
| **Nombres de usuarios registrados** | John |
| **Organización registrada** | home |
| **“Product ID” asociado al sistema** | 76487-341-1072684-22504 |
| **“Service Pack” instalado** | Service Pack 3 |
| **Fecha y hora de instalación del sistema operativo** | 18 de abril de 2013 a las 15:17:02 (UTC) |
| **Fecha y hora del último “shutdown”** | 19/06/2013 2:11:46 |
| **Pruebas** | ![Foto2](/pruebas/sistema/sistema2.png)  |

## Análisis de cuentas de usuario

Se han identificado las cuentas configuradas en el sistema. Excluyendo las predeterminadas, los usuarios personalizados son los siguientes:

### John
- **Último inicio de sesión:** 28/03/2013 – 03:10:49  
- **Último cambio de contraseña:** 18/04/2013 – 15:18:44  
- ![John](/pruebas/usuarios/usuario1.png)

### Ian
- **Último inicio de sesión:** 25/04/2013 – 02:06:52  
- **Último cambio de contraseña:** 18/04/2013 – 15:18:44  
- ![Ian](/pruebas/usuarios/usuario3.png)

### Jessy
- **Último inicio de sesión:** 23/04/2013 – 02:18:56  
- **Último cambio de contraseña:** 18/04/2013 – 15:18:44  
- ![Jessy](/pruebas/usuarios/usuario2.png)

---

## Inconsistencias temporales detectadas

Se ha detectado una discrepancia entre las fechas de inicio de sesión y la fecha de instalación del sistema:

- **John:** último inicio de sesión 28/03/2013 – 03:10:49  
- **Fecha de instalación del sistema:** 18/04/2013 – 15:17:02 (UTC)  

Esto indica que hubo actividad registrada en un sistema que, según los registros, aún no estaba instalado. Posibles explicaciones:

- **Restauración desde copia de seguridad:** El sistema pudo haber sido reinstalado o restaurado desde una imagen anterior, conservando los registros antiguos.  
- **Manipulación intencionada:** Alguien podría haber alterado las fechas para ocultar actividades o generar confusión.  

Este tipo de inconsistencias es relevante en investigaciones forenses, ya que puede evidenciar modificaciones del sistema o reutilización de configuraciones previas.

## Extracción de Archivos Eliminados

Se han recuperado múltiples archivos del sistema, con sus metadatos completos y hashes de integridad. A continuación se presenta un registro organizado por archivo, incluyendo vista previa, fechas relevantes, tamaño, ubicación y hashes MD5 y SHA-256.

![Ruta](/pruebas/archivos_eliminados/ruta1.png)  

---