# FUNCIONES Y DATOS PARA EL ANÁLISIS DE LA ENCUESTA NACIONAL DE SEGURIDAD PÚBLICA URBANA (ENSU) DEL INEGI EN R

## REFERENCIAS

- Los datos contenidos en la carpeta `./INEGI/` son propiedad del Instituto Nacional de Estadística y Geografía (INEGI), conforme a los [Términos de uso](https://www.inegi.org.mx/inegi/terminos.html). La consulta y descarga de los datos puede encontrarse en el siguiente link: https://www.inegi.org.mx/programas/ensu/

- Fuente: INEGI. Encuesta Nacional de Seguridad Pública Urbana (ENSU), primer trimestre de 2019 a cuarto trimestre de 2025.

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
 ┃ ┃ ┣ 📄ENSU_CB_0925.csv
 ┃ ┃ ┣ 📄ENSU_CB_1219.csv
 ┃ ┃ ┣ 📄ENSU_CB_1220.csv
 ┃ ┃ ┣ 📄ENSU_CB_1221.csv
 ┃ ┃ ┣ 📄ENSU_CB_1222.csv
 ┃ ┃ ┣ 📄ENSU_CB_1222.csv
 ┃ ┃ ┣ 📄ENSU_CB_1224.csv
 ┃ ┃ ┣ 📄ENSU_CB_1225.csv
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
[1] tools     grid      stats     graphics  grDevices utils     datasets  methods  
[9] base     

other attached packages:
 [1] quarto_1.5.1       RColorBrewer_1.1-3 rstatix_0.7.2      car_3.1-3         
 [5] carData_3.0-5      purrr_1.1.0        DT_0.33            kableExtra_1.4.0  
 [9] rmarkdown_2.29     tibble_3.3.0       htmlwidgets_1.6.4  stringr_1.5.1     
[13] crosstalk_1.2.1    plotly_4.11.0      ggplot2_3.5.2      tidyr_1.3.1       
[17] rlang_1.1.6        descr_1.1.8        srvyr_1.3.0        survey_4.4-2      
[21] survival_3.8-3     Matrix_1.7-3       dplyr_1.1.4        data.table_1.17.8 
[25] lessR_4.4.5        colorspace_2.1-1  

loaded via a namespace (and not attached):
 [1] gtable_0.3.6        ellipse_0.5.0       xfun_0.52           processx_3.8.6     
 [5] latticeExtra_0.6-30 lattice_0.22-7      ps_1.9.1            vctrs_0.6.5        
 [9] generics_0.1.4      DEoptimR_1.1-4      pkgconfig_2.0.3     lifecycle_1.0.4    
[13] compiler_4.5.1      farver_2.1.2        deldir_2.0-4        textshaping_1.0.1  
[17] leaps_3.2           mitools_2.4         htmltools_0.5.8.1   yaml_2.3.10        
[21] lazyeval_0.2.2      Formula_1.2-5       crayon_1.5.3        later_1.4.2        
[25] pillar_1.11.0       MASS_7.3-65         abind_1.4-8         robustbase_0.99-6  
[29] tidyselect_1.2.1    zip_2.3.3           digest_0.6.37       stringi_1.8.7      
[33] splines_4.5.1       fastmap_1.2.0       cli_3.6.5           magrittr_2.0.3     
[37] utf8_1.2.6          broom_1.0.9         withr_3.0.2         backports_1.5.0    
[41] scales_1.4.0        httr_1.4.7          jpeg_0.1-11         interp_1.1-6       
[45] png_0.1-8           openxlsx_4.2.8      evaluate_1.0.5      knitr_1.50         
[49] viridisLite_0.4.2   Rcpp_1.1.0          xtable_1.8-4        glue_1.8.0         
[53] DBI_1.2.3           xml2_1.3.8          svglite_2.2.1       rstudioapi_0.17.1  
[57] jsonlite_2.0.0      R6_2.6.1            systemfonts_1.2.3  
```
