# FUNCIONES Y DATOS PARA EL ANÁLISIS DE LA ENCUESTA NACIONAL DE SEGURIDAD PÚBLICA URBANA (ENSU) DEL INEGI EN R

## REFERENCIAS

- Los datos contenidos en la carpeta `./INEGI/` son propiedad del Instituto Nacional de Estadística y Geografía (INEGI), conforme a los [Términos de uso](https://www.inegi.org.mx/inegi/terminos.html). La consulta y descarga de los datos puede encontrarse en el siguiente link: https://www.inegi.org.mx/programas/ensu/

- Fuente: INEGI. Encuesta Nacional de Seguridad Pública Urbana (ENSU), primer trimestre de 2019 a segundo trimestre de 2025.

## AVISO

- Todos los archivos contenidos en la carpeta `./INEGI/` se presentan tal cual están en el sitio del Instituto Nacional de Estadística y Geografía (INEGI), cambiando la nomenclatura de los archivos descargables a nombres más resumidos como ensu1t25, que en breve significa ensu(número de trimestre)t(año a dos dígitos). No obstante, el archivo `./INEGI/datos/2019-2025/nm_cd.csv` se modificó al presentado en el segundo trimestre de la ENSU, dado que en lo que respecta a las Alcaldías de la Ciudad de México, estas tenían un espacio al final de sus nombres, por ejemplo: "Azcapotzalco ", además, se complementó el catálogo con todas las ciudades que han ido evaluadas en la ENSU desde el 2019, generando un solo catálogo. También se agregó una columna para abreviar el nombre de la Ciudad (conforme a los nombres empleados en los mapas de los reportes de la ENSU, especificamente en el empleado en el 4to trimestre del 2024, páginas 6 a 8). Los datos de la latitud y longitud son aproximados y no representan la realidad, se agregaron para proyectos futuros en la creación de mapas y no tienen nada que ver con lo presentado por el INEGI. Finalmente, se agregaron las columnas CVE_ENT y NOM_ENT, que buscan asignar el Estado a la ciudad de interés.
- Para una mejor replicabilidad y reproducibilidad se deben de descargar los archivos tal y como están especificados en la ruta `./INEGI/datos/2019-2025/.`
- La estructura de las carpetas y el proyecto en R, debe de ser la siguiente:
```
Carpeta del proyecto en R
 ┣ 📂datos
 ┃ ┣ 📂2019-2025
 ┃ ┃ ┣ 📄CVE_GEO.csv
 ┃ ┃ ┣ 📄ENSU_CB_0319.csv
 ┃ ┃ ┣ 📄ENSU_CB_0320.csv
 ┃ ┃ ┣ 📄ENSU_CB_0321.csv
 ┃ ┃ ┣ 📄ENSU_CB_0322.csv
 ┃ ┃ ┣ 📄ENSU_CB_0323.csv
 ┃ ┃ ┣ 📄ENSU_CB_0324.csv
 ┃ ┃ ┣ 📄ENSU_CB_0325.csv
 ┃ ┃ ┣ 📄ENSU_CB_0321.csv
 ┃ ┃ ┣ 📄ENSU_CB_0619.csv
 ┃ ┃ ┣ 📄ENSU_CB_0621.csv
 ┃ ┃ ┣ 📄ENSU_CB_0622.csv
 ┃ ┃ ┣ 📄ENSU_CB_0623.csv
 ┃ ┃ ┣ 📄ENSU_CB_0624.csv
 ┃ ┃ ┣ 📄ENSU_CB_0625.csv
 ┃ ┃ ┣ 📄ENSU_CB_0919.csv
 ┃ ┃ ┣ 📄ENSU_CB_0920a.csv
 ┃ ┃ ┣ 📄ENSU_CB_0920b.csv
 ┃ ┃ ┣ 📄ENSU_CB_0921.csv
 ┃ ┃ ┣ 📄ENSU_CB_0922.csv
 ┃ ┃ ┣ 📄ENSU_CB_0923.csv
 ┃ ┃ ┣ 📄ENSU_CB_0924.csv
 ┃ ┃ ┣ 📄ENSU_CB_1219.csv
 ┃ ┃ ┣ 📄ENSU_CB_1220.csv
 ┃ ┃ ┣ 📄ENSU_CB_1221.csv
 ┃ ┃ ┣ 📄ENSU_CB_1222.csv
 ┃ ┃ ┣ 📄ENSU_CB_1222.csv
 ┃ ┃ ┣ 📄ENSU_CB_1224.csv
 ┃ ┃ ┣ 📄ENSU_CS_0319.csv
 ┃ ┃ ┣ 📄ENSU_CS_0320.csv
 ┃ ┃ ┣ 📄ENSU_CS_0321.csv
 ┃ ┃ ┣ 📄ENSU_CS_0322.csv
 ┃ ┃ ┣ 📄ENSU_CS_0619.csv
 ┃ ┃ ┣ 📄ENSU_CS_0621.csv
 ┃ ┃ ┣ 📄ENSU_CS_0919.csv
 ┃ ┃ ┣ 📄ENSU_CS_0920.csv
 ┃ ┃ ┣ 📄ENSU_CS_0921.csv
 ┃ ┃ ┣ 📄ENSU_CS_1219.csv
 ┃ ┃ ┣ 📄ENSU_CS_1220.csv
 ┃ ┃ ┣ 📄ENSU_CS_1221.csv
 ┃ ┃ ┗ 📄nm_cd.csv
 ┣ 📄ENSU.Rproj
 ┣ 📄carga_datos.Rmd
 ┣ 📄ensu_reset.RData
 ┣ 📄setup_book.R
 ┗ 📄Los .qmd existentes de cada capítulo del reporte
```
- Al momento de la creación de los códigos y funciones empleadas, la sesión de R era:

```
> sessionInfo()
R version 4.5.1 (2025-06-13 ucrt)
Platform: x86_64-w64-mingw32/x64
Running under: Windows 11 x64 (build 26100)

Matrix products: default
  LAPACK version 3.12.1

locale:
[1] LC_COLLATE=Spanish_Mexico.utf8  LC_CTYPE=Spanish_Mexico.utf8   
[3] LC_MONETARY=Spanish_Mexico.utf8 LC_NUMERIC=C                   
[5] LC_TIME=Spanish_Mexico.utf8    

time zone: America/Mexico_City
tzcode source: internal

attached base packages:
[1] stats     graphics  grDevices utils     datasets  methods   base     

loaded via a namespace (and not attached):
 [1] compiler_4.5.1    fastmap_1.2.0     cli_3.6.5         htmltools_0.5.8.1
 [5] tools_4.5.1       rstudioapi_0.17.1 yaml_2.3.10       rmarkdown_2.29   
 [9] knitr_1.50        xfun_0.52         digest_0.6.37     rlang_1.1.6      
[13] evaluate_1.0.4   
```
