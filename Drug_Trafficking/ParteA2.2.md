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

### **Almacen Mataró 2**
- **Archivo:** `Almacen mataro 2.jpg`  
- **Vista previa:** ![mataro2](/pruebas/archivos_eliminados/almacen_mataro2.png)  
- **Fechas importantes:**  
  - Modificación: 27/03/2013 06:39:14 CET  
  - Creación/Acceso: 19/06/2013 04:11:24 CEST  
- **Tamaño:** 9.935 bytes  
- **Ubicación original:** `/img_AFI_W.E01/$OrphanFiles/Almacen mataro 2.jpg`  
- **Hashes:** MD5 `ba0268ffe1d3a340a595cfd9a8cd6b87` / SHA-256 `9dd2e70416e70e5099303f04e5d48ad72d27155cf3e8dd5bc50dcfb93ebc056d`  

---

### **Almacen Mataró 3**
- **Archivo:** `Almacen mataro 3.jpg`  
- **Vista previa:** ![mataro3](/pruebas/archivos_eliminados/almacen_mataro3.png)  
- **Fechas:** Modificación 27/03/2013 06:39:26 CET / Creación/Acceso 19/06/2013 04:11:24 CEST  
- **Tamaño:** 14.399 bytes  
- **Ubicación:** `/img_AFI_W.E01/$OrphanFiles/Almacen mataro 3.jpg`  
- **Hashes:** MD5 `07e03d5971f5b5a6433a13565cac407d` / SHA-256 `9e75a74404967693442b99278fcce969ddc4f7046903e3fc449b537960e93394`  

---

### **Almacen Mataró**
- **Archivo:** `Almacen mataro.jpg`  
- **Vista previa:** ![mataro](/pruebas/archivos_eliminados/almacen_mataro.png)  
- **Fechas:** Modificación 27/03/2013 06:39:04 CET / Creación/Acceso 19/06/2013 04:11:24 CEST  
- **Tamaño:** 6.998 bytes  
- **Ubicación:** `/img_AFI_W.E01/$OrphanFiles/Almacen mataro.jpg`  
- **Hashes:** MD5 `c7c5a5521ed005ddad94cb9a9b254d6b` / SHA-256 `5cec8378687c3255665e4123cb30b6e05b2117a8ee9e65fe9a4b986e0cc0fe84`  

---

### **Almacen Terrassa 3**
- **Archivo:** `Almacen terrassa 3.jpg`  
- **Vista previa:** ![terrasa3](/pruebas/archivos_eliminados/almacen_terrassa3.png)  
- **Fechas:** Modificación 27/03/2013 06:39:42 CET / Creación/Acceso 19/06/2013 04:11:24 CEST  
- **Tamaño:** 6.943 bytes  
- **Ubicación:** `/img_AFI_W.E01/$OrphanFiles/Almacen terrassa 3.jpg`  
- **Hashes:** MD5 `1e6f15394d075ba43308da22ba92059c` / SHA-256 `805967a139624368bb0c0dd494a0b4c751a649e022b7a32f957d6f592784a29a`  

---

### **Almacen Terrassa 4**
- **Archivo:** `Almacen terrassa 4.jpg`  
- **Vista previa:** ![terrasa4](/pruebas/archivos_eliminados/almacen_terrassa4.png)  
- **Fechas:** Modificación 27/03/2013 06:40:28 CET / Creación/Acceso 19/06/2013 04:11:24 CEST  
- **Tamaño:** 7.349 bytes  
- **Ubicación:** `/img_AFI_W.E01/$OrphanFiles/Almacen terrassa 4.jpg`  
- **Hashes:** MD5 `c641391cfe11009563aaf6d5ff7caf1b` / SHA-256 `c8ab21e06cdcf9524c68f6ab6e2df645a19ebe86fc253a85c052c0d5696910cb`  

---

### **Almacen Terrassa**
- **Archivo:** `Almacen terrassa.jpg`  
- **Vista previa:** ![terrasa](/pruebas/archivos_eliminados/almacen_terrassa.png)  
- **Fechas:** Modificación 27/03/2013 06:20:50 CET / Creación/Acceso 19/06/2013 04:11:24 CEST  
- **Tamaño:** 9.637 bytes  
- **Ubicación:** `/img_AFI_W.E01/$OrphanFiles/Almacen terrassa.jpg`  
- **Hashes:** MD5 `e9bc32019fe6c4bffb1ec9bef18b85aa` / SHA-256 `bd9a18a33b5cec923b6a19d7ddcfb27c580377211761eb602c209d5fb8dfa9bd`  

---

### **Coca**
- **Archivo:** `coca.jpg`  
- **Vista previa:** ![coca](/pruebas/archivos_eliminados/coca.png)  
- **Fechas:** Modificación 27/03/2013 06:19:58 CET / Creación/Acceso 19/06/2013 04:11:24 CEST  
- **Tamaño:** 5.777 bytes  
- **Ubicación:** `/img_AFI_W.E01/$OrphanFiles/coca.jpg`  
- **Hashes:** MD5 `1ffb5afbe2990760fd1b504386593f95` / SHA-256 `061c9e9cef4e2f62ddf8ab1e25e7f665037890119f958d385868d752832148c0`  

---

### **Fabricando Coca 2**
- **Archivo:** `fabricando coca 2.jpg`  
- **Vista previa:** ![fabricando-coca2](/pruebas/archivos_eliminados/fabricando_coca2.png)  
- **Fechas:** Modificación 27/03/2013 06:42:34 CET / Creación/Acceso 19/06/2013 04:11:24 CEST  
- **Tamaño:** 14.373 bytes  
- **Ubicación:** `/img_AFI_W.E01/$OrphanFiles/fabricando coca 2.jpg`  
- **Hashes:** MD5 `5131b40b7b745677b6a6b06e3580508c` / SHA-256 `12ac6ae66c460ba004e1389991f429495246d743080c2c00c05c326b4da8368c`  

---

### **Fabricando Coca 3**
- **Archivo:** `fabricando coca 3.jpg`  
- **Vista previa:** ![fabricando-coca3](/pruebas/archivos_eliminados/fabricando_coca3.png)  
- **Fechas:** Modificación 27/03/2013 06:43:20 CET / Creación/Acceso 19/06/2013 04:11:24 CEST  
- **Tamaño:** 9.994 bytes  
- **Ubicación:** `/img_AFI_W.E01/$OrphanFiles/fabricando coca 3.jpg`  
- **Hashes:** MD5 `99631163aabedd753f9a5d00b6fe74ac` / SHA-256 `800242322a228a4db8567b0de03f33f259ebd46e6601b51a2b8e4907f7c87853`  

---

### **Fabricando Coca 4**
- **Archivo:** `fabricando coca 4.jpg`  
- **Vista previa:** ![fabricando-coca4](/pruebas/archivos_eliminados/fabricando_coca4.png)  
- **Fechas:** Modificación 27/03/2013 06:43:30 CET / Creación/Acceso 19/06/2013 04:11:24 CEST  
- **Tamaño:** 12.608 bytes  
- **Ubicación:** `/img_AFI_W.E01/$OrphanFiles/fabricando coca 4.jpg`  
- **Hashes:** MD5 `ffbedbaa75fff0a2f405489082667c65` / SHA-256 `7c6dffced23041315aa7fb9e3ac90e2f3934e1430d819eebb135ee9d634c3b63`  

---

### **Fabricando Coca**
- **Archivo:** `fabricando coca.jpg`  
- **Vista previa:** ![fabricando-coca](/pruebas/archivos_eliminados/fabricando_coca.png)  
- **Fechas:** Modificación 27/03/2013 06:42:28 CET / Creación/Acceso 19/06/2013 04:11:24 CEST  
- **Tamaño:** 6.413 bytes  
- **Ubicación:** `/img_AFI_W.E01/$OrphanFiles/fabricando coca.jpg`  
- **Hashes:** MD5 `66a8a952396995a7800ac63e8e2234bd` / SHA-256 `7352059b3e7a29143d0c38dcb8610cbc79251049d41cc8a58662a8101dd2cdf3`  

---

### **Fiesta Jorge**
- **Archivo:** `fiesta Jorge.jpg`  
- **Vista previa:** ![fiesta-jorge](/pruebas/archivos_eliminados/fiesta_jorge.png)  
- **Fechas:** Modificación 27/03/2013 06:20:20 CET / Creación/Acceso 19/06/2013 04:11:24 CEST  
- **Tamaño:** 8.905 bytes  
- **Ubicación:** `/img_AFI_W.E01/$OrphanFiles/fiesta Jorge.jpg`  
- **Hashes:** MD5 `c6661d1558b767f31c1f65242af95118` / SHA-256 `bd87c563633f99998dc3956239afcf2b3ea8d19dd8f65e6f483c1bc8ca27166e`  

---

### **Kasius 2**
- **Archivo:** `kasius 2.jpg`  
- **Vista previa:** ![kasius-2](/pruebas/archivos_eliminados/kasius2.png)  
- **Fechas:** Modificación 27/03/2013 06:42:04 CET / Creación/Acceso 19/06/2013 04:11:24 CEST  
- **Tamaño:** 5.716 bytes  
- **Ubicación:** `/img_AFI_W.E01/$OrphanFiles/kasius 2.jpg`  
- **Hashes:** MD5 `28f5966b1a4a72cb3b434f688bf8dd0b` / SHA-256 `1ed78fad0270ba13b15f1222d973cab3f2de072f5d72902af7bc48bd1ac35db1`  

---

### **Kasius**
- **Archivo:** `kasius.jpg`  
- **Vista previa:** ![kasius](/pruebas/archivos_eliminados/kasius.png)  
- **Fechas:** Modificación 27/03/2013 06:41:58 CET / Creación/Acceso 19/06/2013 04:11:24 CEST  
- **Tamaño:** 9.175 bytes  
- **Ubicación:** `/img_AFI_W.E01/$OrphanFiles/kasius.jpg`  
- **Hashes:** MD5 `d56befec0c93acbad7fe9d48f5415a2b` / SHA-256 `28bb98cf7e09a6d96f8bcb4ee5d683740a4a334790f946354df061f175ba20c0`  

---

### **Maria en negocio Jorge**
- **Archivo:** `Maria en negocio Jorge.jpg`  
- **Vista previa:** ![maria](/pruebas/archivos_eliminados/maria.png)  
- **Fechas:** Modificación 27/03/2013 06:38:30 CET / Creación/Acceso 19/06/2013 04:11:24 CEST  
- **Tamaño:** 5.083 bytes  
- **Ubicación:** `/img_AFI_W.E01/$OrphanFiles/Maria en negocio Jorge.jpg`  
- **Hashes:** MD5 `18f5a99105c58f8a71a3405562d2eafa` / SHA-256 `b2412594f86335be25a83db0ee9ecaf576f9182a322fe69581ece2ccd4d6911f`  

---

### **Mercancia 2**
- **Archivo:** `mercancia 2.jpg`  
- **Vista previa:** ![mercancia-2](/pruebas/archivos_eliminados/mercancia2.png)  
- **Fechas:** Modificación 27/03/2013 06:21:06 CET / Creación/Acceso 19/06/2013 04:11:24 CEST  
- **Tamaño:** 8.620 bytes  
- **Ubicación:** `/img_AFI_W.E01/$OrphanFiles/mercancia 2.jpg`  
- **Hashes:** MD5 `5b5a015f4041bbed1bca11fc7be74fcc` / SHA-256 `25543a3af9f7a0e72fed485116c24a4a45f9705aba49470b1cd891bf8ec8ea0`  

---

### **Mercancia Terrassa**
- **Archivo:** `Mercancia terrassa.jpg`  
- **Vista previa:** ![mercancia-terrassa](/pruebas/archivos_eliminados/mercancia_terrassa.png)  
- **Fechas:** Modificación 27/03/2013 06:38:52 CET / Creación/Acceso 19/06/2013 04:11:24 CEST  
- **Tamaño:** 8.968 bytes  
- **Ubicación:** `/img_AFI_W.E01/$OrphanFiles/Mercancia terrassa.jpg`  
- **Hashes:** MD5 `957894f16f61655cec7110625c7e344b` / SHA-256 `bbc8f083cb8bd891463aa62d477620fe884f653e6725ad833f13b312b9f43490`  

---

### **Mercancia**
- **Archivo:** `mercancia.jpg`  
- **Vista previa:** ![mercancia](/pruebas/archivos_eliminados/mercancia.png)  
- **Fechas:** Modificación 27/03/2013 06:20:08 CET / Creación/Acceso 19/06/2013 04:11:24 CEST  
- **Tamaño:** 6.917 bytes  
- **Ubicación:** `/img_AFI_W.E01/$OrphanFiles/mercancia.jpg`  
- **Hashes:** MD5 `c1481b245fe4f3b5362cd5e19ffaffba` / SHA-256 `32700fcb07ed7a1c760911c5aa43a24a06afbb42c119fa54197330dc57978546`  

---

### **Pastillas**
- **Archivo:** `pastillas.jpg`  
- **Vista previa:** ![pastillas](/pruebas/archivos_eliminados/pastilla.png)  
- **Fechas:** Modificación 27/03/2013 06:19:22 CET / Creación/Acceso 19/06/2013 04:11:24 CEST  
- **Tamaño:** 12.942 bytes  
- **Ubicación:** `/img_AFI_W.E01/$OrphanFiles/pastillas.jpg`  
- **Hashes:** MD5 `6fe69a3ad25893e824b7c40e252f96a8` / SHA-256 `9d51fd7fabfa93a72fcc7b947cc88d12536834756597b7dcf8b155eaf6f5d7c0`  

---
## Archivos cifrados y comprimidos

Durante el análisis del sistema, se identificaron varios archivos que se encontraban en formatos comprimidos y protegidos mediante cifrado, lo que sugiere que podrían contener información sensible. Entre los archivos recuperados destacan:

- `pedofilia.zip`  
- `Contactes.xls`  

![archivos-cifrados](/pruebas/ficheros_encriptados/fichero1.png)  

Tras la investigación, fue posible determinar la titularidad de cada uno de estos ficheros:  

- El archivo **`pedofilia.zip`** estaba vinculado al usuario **Ian**.  
  ![pedofilia](/pruebas/ficheros_encriptados/pedofilia.png)  

- El archivo **`Contactes.xls`** pertenecía al usuario **John**.  
  ![contactos](/pruebas/ficheros_encriptados/contactos.png)  

### Hallazgos y acciones forenses

No se localizaron, hasta el momento, otros archivos directamente relacionados con conductas delictivas distintas de las mencionadas. Sin embargo, como perito informático, se recomienda llevar a cabo las siguientes acciones para garantizar la integridad de la evidencia y ampliar la investigación:

1. **Verificación de integridad:**  
   - Generar y registrar hashes (MD5 y SHA-256) de cada archivo para asegurar que no se alteren durante el análisis.

2. **Análisis de contenido cifrado:**  
   - Intentar descifrar o acceder a los contenidos de los archivos mediante métodos legales y autorizados, respetando la cadena de custodia.

3. **Identificación de metadatos:**  
   - Extraer metadatos de los archivos comprimidos y de los documentos para determinar fecha de creación, modificación, autoría y posibles rastros de actividad ilícita.

4. **Registro de evidencia:**  
   - Documentar cuidadosamente cada paso realizado, con capturas, rutas de archivo y logs de análisis para incluirlos en el informe final.

5. **Correlación de usuarios y ficheros:**  
   - Relacionar cada archivo con su respectivo propietario dentro del sistema y establecer un seguimiento de posibles vínculos con otras actividades delictivas.

Este procedimiento garantiza que se mantenga la cadena de custodia y que los hallazgos puedan presentarse de manera sólida en el contexto de una investigación judicial.

- Prueba search
  ![search](/pruebas/ficheros_encriptados/search.png)  

- Prueba webhistory 
  ![Web History](/pruebas/ficheros_encriptados/webhistory.png)  

- Prueba webookmarks 
  ![Web Bookmark ](/pruebas/ficheros_encriptados/webbookmark.png)  