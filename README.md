# FUNCIONES Y DATOS PARA EL ANÁLISIS DE LA ENCUESTA NACIONAL DE SEGURIDAD PÚBLICA URBANA (ENSU) DEL INEGI

## REFERENCIAS

- Los datos contenidos en la carpeta `./INEGI/` son propiedad del Instituto Nacional de Estadística y Geografía (INEGI), conforme a los [Términos de uso](https://www.inegi.org.mx/inegi/terminos.html). La consulta y descarga de los datos puede encontrarse en el siguiente link: https://www.inegi.org.mx/programas/ensu/

- Fuente: INEGI. Encuesta Nacional de Seguridad Pública Urbana (ENSU), primer trimestre de 2019 a segundo trimestre de 2025.

## AVISO

- Todos los archivos contenidos en la carpeta `./INEGI/` se presentan tal cual están en el sitio del Instituto Nacional de Estadística y Geografía (INEGI). No obstante, solo el archivo `./INEGI/datos/2019-2025/nm_cd.csv` tuvo una ligera modificación al presentado en el segundo trimestre de la ENSU, dado que en lo que respecta a las Alcaldías de la Ciudad de México, estas tenían un espacio al final de sus nombres, por ejemplo: "Azcapotzalco ".
- Para una mejor replicabilidad y reproducibilidad del código presentado, no se deben de modificar las funciones aquí presentadas, siendo la más importante: `cargar_ensu` como la primer función a ejecutarse una vez descargados los archivos.
- La estructura de las carpetas 
