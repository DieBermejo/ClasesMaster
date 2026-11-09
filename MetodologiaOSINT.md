[Metodología OSINT	1

[1. Fase 1 · Planificación	2

[2. Fase 2 · Recolección	2

[2.1 Pasos a seguir	2

[Distintos tipos de casos.	2

[2.2 Caso 1 · Partimos de una imagen o fotografía	2

[2.3 Caso 2 · Partimos de un nombre y apellidos	2

[2.4 Caso 3 · Partimos de un nombre de usuario	3

[2.5 Caso 4 · Partimos de un correo electrónico	3

[2.6 Caso 5 · Partimos de un número de teléfono	3

[2.7 Caso 6 · Partimos de una organización o un dominio	4

[2.8 Herramientas de automatización y correlación	4

[3. Fase 3 · Procesamiento y análisis	4

[3.1 Procesamiento de los datos	5

[3.2 Correlación y eliminación de falsos positivos	5

[4. Fase 4 · Difusión: estructura del informe	5

# 
# Metodología OSINT
## 1. Fase 1 · Planificación
1. **Definición de objetivos**: qué queremos saber y qué preguntas necesitamos responder.

2. **Alcance**: límites de la investigación y preguntas quién, qué, dónde, cuándo.

3. **Requerimientos de información**: qué tipo de dato responde a cada pregunta.

4. **Punto** **de partida**: Que se tiene desde el inicio (foto, nombre, alias, email, teléfono, dominio) para saber desde qué caso empezar.

5. **Selección de fuentes**: qué casos y herramientas se van a aplicar.
## 2. Fase 2 · Recolección
### 2.1 Pasos a seguir
1. **Ejecución**: recopilar la información de las fuentes seleccionadas en la planificación.

2. **Métodos**: primero técnicas pasivas y después activas.

3. **Herramientas**: aplicar la herramienta adecuada a cada fuente.

4. **Organización**: almacenar la información encontrada de forma estructurada.

5. **Verificación**: contrastar la información en la medida de lo posible.
### Distintos tipos de casos.
### 2.2 Caso 1 · Partimos de una imagen o fotografía
1. **Preservar el original**: descargar el archivo orginal para no perder metadatos. 

2. **Extraer metadatos** EXIF/XMP/IPTC: fecha de captura, cámara o móvil, número de serie, software, autor y coordenadas GPS. Herramientas: ExifTool, FotoForensics.

3. **Análisis forense**: comprobar si la imagen ha sido editada o generada. Herramientas: FotoForensics, Forensically.

4. **Búsqueda inversa** en varios motores. Herramientas: Google Lens, Yandex Images, Bing Visual Search, TinEye.

5. **Reconocimiento facial** si aparece una cara, para encontrar otras fotos de la misma persona. Herramientas: PimEyes, FaceCheck.ID.

6. **Análisis conceptual**: listar los indicios visibles: arquitectura, geografía, vegetación, idioma de los carteles, matrículas, señales, logotipos, clima, información adicional. Herramientas: observación con zoom, Yandex Images.

7. **Geolocalización**: acotar la zona. Herramientas: GeoEstimation, Google Maps/Earth, Street View, Mapillary, Overpass Turbo.

8. **Cámaras públicas**: si la foto procede de una, localizar la cámara para obtener su nombre y la fecha y hora exactas. Herramientas: EarthCam, SkylineWebcams, Shodan.
### 2.3 Caso 2 · Partimos de un nombre y apellidos
1. **Generar variantes del nombre**: con y sin tildes, segundo apellido, iniciales, apodos, orden invertido.

2. **Búsqueda con Google Dorks**: "Nombre Apellido", filetype:pdf, site:linkedin.com/in, "@gmail.com". Herramientas: Google, Bing, DuckDuckGo, Yandex.

3. **Redes sociales**: perfil, fotos, contactos, empleo y ubicación, filtrando por ciudad o empresa. Herramientas: Facebook, LinkedIn, X, Instagram.

4. **Fuentes oficiales y registros públicos**: nombramientos, cargos en sociedades, contratos y subvenciones. Herramientas: BOE, BORME, LibreBOR, Infoempresa, Portal de Transparencia, ABCTelefonos.

5. **Directorios profesionales**, colegios, universidades y páginas de empresas. Herramientas: Google Dorks.

6. **Imágenes del nombre**: confirmar que las fotos encontradas son de la misma persona. Herramientas: Google Imágenes.

7. **Generar** **usernames** **y emails candidatos** nombre.apellido, napellido...
### 2.4 Caso 3 · Partimos de un nombre de usuario
1. **Enumeración automática del alias**. Herramientas: WhatsMyName, Sherlock.

2. **Búsqueda en motores** del alias exacto ("usuario", inurl:usuario) en foros, Reddit, Pastebin y GitHub. Herramientas: Google, Bing, DuckDuckGo.

3. **Eliminar falsos positivos**: comparar foto de perfil, biografía, ubicación, fechas, estilo de escritura y enlaces entre perfiles. Herramientas: navegador, búsqueda inversa.

4. **Histórico de perfiles**: versiones antiguas y perfiles borrados. Herramientas: Wayback Machine, archive.ph.

5. **Extraer pivotes**: correos en biografías, webs personales, nombre real y el correo de los commits de GitHub. Herramientas: GitHub, Gravatar, Keybase.
### 2.5 Caso 4 · Partimos de un correo electrónico
1. **Validar el correo y su dominio** ya sea personal o corporativo y obtener el patrón de correo de la empresa. Herramientas: Hunter.io, dig MX.

2. **Cuentas asociadas**: usar “recuperar contraseña” en sitios populares para ver si el correo tiene cuenta; obtener nombre y foto de la cuenta Google. Herramientas: Holehe, Epieos, GHunt.

3. **Filtraciones de datos**: brechas donde aparece el correo y datos asociados como usernames o teléfonos. Herramientas: HaveIBeenPwned, DeHashed.
### 2.6 Caso 5 · Partimos de un número de teléfono
1. **Normalizar** a formato internacional +34612345678.

2. **Información técnica**: país, operador y tipo de línea. Herramientas: PhoneInfoga.

3. **Dorks con todas las variantes** y búsqueda en portales de anuncios y webs de empresas. Herramientas: Google, Bing.

4. **Aplicaciones de mensajería**: foto de perfil, nombre y estado. Herramientas: WhatsApp, Telegram, Signal.

5. **Identificadores de llamada**: nombre con el que otros usuarios guardan el número. Herramientas: Truecaller, Sync.me.

6. **Cuentas y filtraciones** asociadas al número. Herramientas: Ignorant, DeHashed.

7. **Identificación de titular del número**. Herramienta: Bizum
### 2.7 Caso 6 · Partimos de una organización o un dominio
**Enumeración pasiva**

1. **WHOIS del dominio**: registros, fechas y servidores DNS. Herramientas: who.is, whois.

2. **Certificados SSL/TLS** para descubrir subdominios. Herramientas: crt.sh, Censys.

3. **DNS público**: ver la infraestructura DNS del dominio. Herramientas: DNSDumpster.

4. **Información histórica de la web** a lo largo del tiempo. Herramientas: Wayback Machine, archive.ph.

5. **Motores de búsqueda de dispositivos**: puertos, servicios y versiones expuestos. Herramientas: Shodan, ZoomEye, Censys, FOFA.

6. **Google** **Dorking** sobre el dominio: documentos, paneles y ficheros indexados. Herramientas: Google, DuckDuck.

7. **Búsqueda en GitHub y Pastebin**: código, configuraciones y API keys. Herramientas: GitHub Search, Pastebin.

8. **Fingerprinting de tecnologías**: CMS, frameworks y servidor web. Herramientas: Wappalyzer, BuiltWith.

9. **Personas de la organización**: empleados, cargos y correos corporativos. Herramientas: LinkedIn (dorks), theHarvester, Hunter.io.

10. **Fuentes gubernamentales e industriales.** Herramientas: BORME, BOE, LibreBor.

**Enumeración activa**

11. **Consultas DNS directas**: registros MX, A, TXT y NS e IP de los hosts. Herramientas: host, dig, nslookup.

12. **Enumeración de subdominios**. Herramientas: Sublist3r, dnsrecon, dnsenum, Amass.

13. **Fuzzing** de directorios y ficheros. Herramientas: Gobuster, Wfuzz, Dirb.

14. **Fingerprinting activo** de servicios y tecnologías. Herramientas: Nmap, WhatWeb.

15. **URLs públicas conocidas**: robots.txt, sitemap.xml, comentarios HTML. Herramientas: navegador, curl.

16. **Cabeceras HTTP de seguridad**. Herramientas: curl -I.
### 2.8 Herramientas de automatización y correlación
- **Maltego**: conecta personas, emails, dominios, IP, teléfonos y saca relaciones entre ellas.

- **theHarvester**: recolecta emails, subdominios, hosts y nombres desde fuentes públicas.
## 3. Fase 3 · Procesamiento y análisis
### 3.1 Procesamiento de los datos
1. **Limpiar y** **borrar duplicados** de los resultados de las herramientas automáticas.

2. **Organizar** **formatos**

3. **Tabla de** **valores**: una fila por dato con tipo, valor, fuente, fecha y evidencia.

4. **Cronología** de los eventos encontrados.

5. **Grafo de relaciones** entre entidades.
### 3.2 Correlación y eliminación de falsos positivos
- **Interpretación**: entender el significado de cada dato en su contexto.

- **Correlación**: relacionar piezas de información para encontrar patrones y conexiones.

- **Contraste**: cada hecho clave debe confirmarse con al menos dos fuentes independientes.
## 4. Fase 4 · Difusión: estructura del informe
1. **Resumen ejecutivo**: que contenga las conclusiones.

2. **Objetivos y alcance**: preguntas planteadas, límites y datos de partida.

3. **Metodología**: casos aplicados, herramientas, técnicas...

4. **Hallazgos**: organizados por pregunta o por entidad, cada hallazgo con captura y fecha.

5. **Grafo de relaciones y cronología**: visualización de información y de la línea temporal.

6. **Conclusiones**: respuesta a cada pregunta con su confianza e hipótesis descartadas.


