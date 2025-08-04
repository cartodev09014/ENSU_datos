# FUNCIONES Y DATOS PARA EL ANÁLISIS DE LA ENCUESTA NACIONAL DE SEGURIDAD PÚBLICA URBANA (ENSU) DEL INEGI EN R

## REFERENCIAS

- Los datos contenidos en la carpeta `./INEGI/` son propiedad del Instituto Nacional de Estadística y Geografía (INEGI), conforme a los [Términos de uso](https://www.inegi.org.mx/inegi/terminos.html). La consulta y descarga de los datos puede encontrarse en el siguiente link: https://www.inegi.org.mx/programas/ensu/

- Fuente: INEGI. Encuesta Nacional de Seguridad Pública Urbana (ENSU), primer trimestre de 2019 a segundo trimestre de 2025.

## AVISO

- Todos los archivos contenidos en la carpeta `./INEGI/` se presentan tal cual están en el sitio del Instituto Nacional de Estadística y Geografía (INEGI). No obstante, solo el archivo `./INEGI/datos/2019-2025/nm_cd.csv` tuvo una ligera modificación al presentado en el segundo trimestre de la ENSU, dado que en lo que respecta a las Alcaldías de la Ciudad de México, estas tenían un espacio al final de sus nombres, por ejemplo: "Azcapotzalco ".
- Para una mejor replicabilidad y reproducibilidad del código presentado, no se deben de modificar las funciones aquí presentadas, siendo la más importante: `cargar_ensu` como la primer función a ejecutarse una vez descargados los archivos.
- La estructura de las carpetas debe de ser la siguiente:
```
Carpeta del proyecto en R
 ┣ 📂datos
 ┃ ┣ 📂2019-2025
 ┃ ┃ ┣ 📄CVE_GEO.csv
 ┃ ┃ ┣ 📄ENSU_CB_0321.csv
 ┃ ┃ ┣ 📄ENSU_CB_0322.csv
 ┃ ┃ ┣ 📄ENSU_CB_0323.csv
 ┃ ┃ ┣ 📄ENSU_CB_0324.csv
 ┃ ┃ ┣ 📄ENSU_CB_0325.csv
 ┃ ┃ ┣ 📄ENSU_CB_0321.csv
 ┃ ┃ ┣ 📄ENSU_CB_0621.csv
 ┃ ┃ ┣ 📄ENSU_CB_0622.csv
 ┃ ┃ ┣ 📄ENSU_CB_0623.csv
 ┃ ┃ ┣ 📄ENSU_CB_0624.csv
 ┃ ┃ ┣ 📄ENSU_CB_0625.csv
 ┃ ┃ ┣ 📄ENSU_CB_0921.csv
 ┃ ┃ ┣ 📄ENSU_CB_0922.csv
 ┃ ┃ ┣ 📄ENSU_CB_0923.csv
 ┃ ┃ ┣ 📄ENSU_CB_0924.csv
 ┃ ┃ ┣ 📄ENSU_CB_1221.csv
 ┃ ┃ ┣ 📄ENSU_CB_1222.csv
 ┃ ┃ ┣ 📄ENSU_CB_1222.csv
 ┃ ┃ ┣ 📄ENSU_CB_1224.csv
 ┣ 📄ENSU.Rproj
 ┣ 📄funciones.Rmd #crea y guarda ensu_funciones.RData
 ┣ 📄ensu_funciones.RData
 ┣ 📄carga_datos.Rmd #crea y guarda ensu_tablas.RData
 ┣ 📄ensu_tablas.RData
 ┗ 📄dashboard.Rmd #carga ensu_funciones.RData y ensu_tablas.RData
```
- Al momento de la creación de los códigos y funciones empleadas, la sesión de R era:

```
> sessionInfo()
R version 4.4.2 (2024-10-31 ucrt)
Platform: x86_64-w64-mingw32/x64
Running under: Windows 11 x64 (build 26100)

Matrix products: default


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
 [1] car_3.1-3         carData_3.0-5     tibble_3.2.1      htmlwidgets_1.6.4
 [5] stringr_1.5.1     crosstalk_1.2.1   plotly_4.11.0     ggplot2_3.5.2    
 [9] tidyr_1.3.1       rlang_1.1.6       descr_1.1.8       survey_4.4-2     
[13] survival_3.7-0    Matrix_1.7-1      dplyr_1.1.4       data.table_1.17.8

loaded via a namespace (and not attached):
 [1] sass_0.4.9          generics_0.1.4      stringi_1.8.7       lattice_0.22-6     
 [5] digest_0.6.37       magrittr_2.0.3      evaluate_1.0.4      RColorBrewer_1.1-3 
 [9] fastmap_1.2.0       jsonlite_1.8.9      Formula_1.2-5       DBI_1.2.3          
[13] httr_1.4.7          purrr_1.1.0         viridisLite_0.4.2   scales_1.4.0       
[17] jquerylib_0.1.4     lazyeval_0.2.2      abind_1.4-8         cli_3.6.3          
[21] crayon_1.5.3        mitools_2.4         splines_4.4.2       cachem_1.1.0       
[25] withr_3.0.2         yaml_2.3.10         vctrs_0.6.5         R6_2.6.1           
[29] lifecycle_1.0.4     pkgconfig_2.0.3     bslib_0.9.0         pillar_1.11.0      
[33] gtable_0.3.6        glue_1.8.0          Rcpp_1.0.14         xfun_0.52          
[37] tidyselect_1.2.1    rstudioapi_0.17.1   knitr_1.50          dichromat_2.0-0.1  
[41] farver_2.1.2        xtable_1.8-4        htmltools_0.5.8.1   labeling_0.4.3     
[45] rmarkdown_2.29      compiler_4.4.2      flexdashboard_0.6.2
```
