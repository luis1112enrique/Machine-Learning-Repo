# Statistics for Data Science

Repositorio de notebooks para la materia **Statistics for Data Science**. El proyecto reúne ejercicios de análisis exploratorio, procesos ETL, limpieza de datos, feature engineering, visualización, estadística descriptiva, probabilidad, regresión y evaluación de modelos de machine learning usando Python. También incluye diagnósticos de modelos, análisis de correlación e influencia y una actividad de series de tiempo en preparación.

El repositorio está organizado por clases. Cada notebook trabaja un caso distinto y busca documentar el flujo completo: desde la carga de datos hasta la preparación para análisis o modelado.

## Contenido

| Archivo | Tema principal | Descripción |
| --- | --- | --- |
| `Clase 1 – Airbnb.ipynb` | EDA | Análisis exploratorio de alojamientos de Airbnb en Ciudad de México. Incluye limpieza de precios, conteos por tipo de alojamiento, principales alcaldías, anfitriones y visualizaciones geográficas. |
| `Clase 2 - ECOBICI.ipynb` | ETL | Procesamiento de viajes de ECOBICI. Descarga datos, transforma columnas, crea variables derivadas y aplica normalización/codificación para análisis posterior. |
| `Clase 3 - Metrics classification.ipynb` | Clasificación | Evaluación de modelos de clasificación usando el dataset Breast Cancer Wisconsin de `scikit-learn`. Incluye matriz de confusión, accuracy y análisis de desbalance con datos sintéticos de fraude. |
| `Clase 4 - Mean Squared error (MSE).ipynb` | Regresión | Comparación de modelos de regresión usando el dataset Diabetes de `scikit-learn`. Calcula MSE, MAE, RMSE, R², MAPE y RMSLE para distintos modelos, incluyendo Linear Regression, Ridge, Lasso, Decision Tree y Random Forest. |
| `Clase 5 - Calidad del aire CDMX.ipynb` | ETL y estadística descriptiva | Flujo de ingesta, limpieza, control de calidad, imputación ligera, feature engineering temporal y visualización de contaminantes atmosféricos en CDMX para 2024, 2025 y 2026. |
| `Clase 6 - Meteorología.ipynb` | Probabilidad y estadística | Análisis de datos meteorológicos de CDMX para 2025. Filtra la estación `BJU` y calcula probabilidades empíricas, conjuntas y condicionales para humedad relativa y velocidad del viento. |
| `Clase 7.ipynb` | Regresión y diagnóstico de supuestos | Regresión de `O3` sobre `NO`, `NO2`, `NOX` y `CO` en la estación `MER`. Incluye R², VIF, Breusch–Pagan, Durbin–Watson y QQ-plot de los residuos. |
| `Clase 8 - Estacionariedad y patrones temporales del ozono en UIZ.ipynb` | Covarianza, correlación e influencia | Análisis de contaminantes de 2026: covarianza y correlación, eigenvalores, regresión de `PM2.5`, VIF, matriz de proyección, leverage, distancia de Cook y reajuste de modelos en `MER`. |
| `Clase 9.ipynb` | Series de tiempo, en preparación | Archivo reservado para analizar el `O3` horario de `UIZ`: tratamiento de huecos, ACF hasta 72 horas, pruebas ADF y KPSS, ajustes por hora y mes × hora y diferencia de 24 horas. Actualmente está vacío. |

Las Clases 7, 8 y 9 corresponden a los ejercicios **Notebook 1**, **Notebook 2** y **Notebook 3** de calidad del aire, respectivamente. El tercer ejercicio todavía está pendiente de incorporarse al archivo.

## Objetivos Del Repositorio

- Practicar análisis exploratorio de datos con problemas reales y sintéticos.
- Construir pipelines básicos de ETL: ingesta, limpieza, transformación y validación.
- Crear variables útiles para análisis estadístico y modelos predictivos.
- Evaluar modelos de clasificación y regresión con métricas adecuadas.
- Calcular probabilidades empíricas, conjuntas y condicionales a partir de datos observados.
- Ajustar regresiones lineales e interpretar sus coeficientes y diagnósticos de supuestos.
- Comparar covarianza y correlación, detectar multicolinealidad y estudiar observaciones influyentes.
- Explorar la autocorrelación y la estacionariedad de series horarias en la actividad de series de tiempo.
- Documentar supuestos, fuentes de datos y decisiones de limpieza.

## Tecnologías

- Python 3.10+
- Jupyter Notebook
- pandas
- polars
- numpy
- matplotlib
- seaborn
- plotly
- altair
- requests
- scikit-learn
- statsmodels

Las dependencias principales están listadas en `requirements.txt`. Los notebooks de las Clases 7 y 8 también requieren `statsmodels`, que todavía no aparece en ese archivo; su instalación se incluye más adelante. La actividad de la Clase 9 utiliza la misma librería para ADF, KPSS y ACF.

## Fuentes De Datos

- **Airbnb CDMX:** datos públicos de Inside Airbnb cargados desde el notebook.
- **ECOBICI CDMX:** datos públicos de viajes de ECOBICI.
- **Calidad del aire CDMX:** archivos locales de contaminantes atmosféricos del Sistema de Monitoreo Atmosférico (SIMAT) de la Ciudad de México, utilizados en las Clases 5, 7 y 8 y previstos para la Clase 9.
- **Meteorología CDMX:** archivo local de variables meteorológicas del sistema de monitoreo de la Ciudad de México.
- **Breast Cancer Wisconsin:** dataset incluido en `scikit-learn`, usado para métricas de clasificación.
- **Diabetes:** dataset incluido en `scikit-learn`, usado para métricas de regresión.
- **Fraude sintético:** dataset generado con `make_classification` de `scikit-learn` para ilustrar problemas de desbalance de clases.

## Datos Locales

Los archivos `.csv` están ignorados por Git para mantener el repositorio ligero. Para reproducir todos los notebooks, algunos datasets deben estar disponibles localmente o descargarse desde sus fuentes originales.

Archivos usados localmente:

| Archivo | Uso | Notas |
| --- | --- | --- |
| `2026-07.csv` | Clase 2 | Dataset de viajes de ECOBICI. |
| `contaminantes_2024.csv` | Clase 5 | Datos crudos de calidad del aire 2024. |
| `contaminantes_2025.csv` | Clase 5 | Datos crudos de calidad del aire 2025. |
| `contaminantes_2026.csv` | Clases 5, 7 y 8; previsto para Clase 9 | Datos crudos de calidad del aire. La copia local contiene enero y febrero de 2026, no el año completo. |
| `calidad_aire_long_limpio.csv` | Clase 5 | Dataset limpio en formato largo, generado por el ETL. |
| `calidad_aire_wide_features.csv` | Clase 5 | Dataset transformado a formato ancho con variables temporales. |
| `calidad_aire_model_ready.csv` | Clase 5 | Dataset preparado para modelado predictivo. |
| `meteorología_2025.csv` | Clase 6 | Datos meteorológicos de CDMX 2025 en formato largo. |

Nota para las Clases 5 y 6: los archivos crudos contienen 9 filas de metadatos antes del encabezado real. Por eso se cargan con `skiprows=9`.

Las Clases 7 y 8 localizan automáticamente el encabezado después de los metadatos. Los datos de contaminantes están en formato largo: cada fila representa una medición de un contaminante en una estación y una fecha-hora. La columna `unit` contiene códigos de unidad, no factores de conversión.

Los tres archivos `calidad_aire_*.csv` se generan al ejecutar la Clase 5. Las Clases 7 y 8 leen directamente `contaminantes_2026.csv`, por lo que no necesitan esos archivos procesados.

## Clase 5: Calidad Del Aire CDMX

El notebook de calidad del aire trabaja un flujo ETL completo:

1. Ingesta de los archivos de contaminantes 2024, 2025 y 2026.
2. Estandarización de columnas, incluyendo el cambio de `value` a `valor` en 2024.
3. Conversión de fechas, variables numéricas y códigos de estación/contaminante.
4. Tratamiento de valores negativos y datos faltantes.
5. Consolidación de duplicados por fecha, estación y contaminante.
6. Imputación ligera con interpolación por estación y contaminante.
7. Feature engineering temporal: año, mes, día, hora, fin de semana, ciclos horarios y temporadas.
8. Transformación de formato largo a formato ancho.
9. Creación de variable objetivo para predicción, por ejemplo `PM2.5` una hora adelante.
10. Split temporal entre entrenamiento y prueba.
11. Cálculo de medidas de tendencia central: media, mediana y moda.
12. Visualización de distribuciones por año y por contaminante.

## Clase 6: Meteorología

El notebook de meteorología trabaja con datos horarios de la Ciudad de México durante 2025. El análisis se enfoca en la estación `BJU` y en dos parámetros:

- `RH`: humedad relativa.
- `WSP`: velocidad del viento.

Los eventos definidos para el análisis son:

- Humedad alta: `RH >= 70`.
- Viento tranquilo: `WSP <= 1`.

El análisis estadístico calcula:

1. Probabilidad empírica de humedad alta: `P(RH >= 70)`.
2. Probabilidad empírica de viento tranquilo: `P(WSP <= 1)`.
3. Probabilidad conjunta: `P(RH >= 70 y WSP <= 1)`.
4. Probabilidad condicional de humedad alta dado viento tranquilo: `P(RH >= 70 | WSP <= 1)`.
5. Probabilidad condicional de viento tranquilo dado humedad alta: `P(WSP <= 1 | RH >= 70)`.

Para comparar humedad y viento en la misma hora, el dataset se transforma de formato largo a formato ancho usando `pivot_table`, con `date` como índice y `id_parameter` como columnas.

## Clase 7: Regresión Y Diagnóstico De Supuestos

El notebook trabaja con los contaminantes horarios de la estación `MER` (Merced) y ajusta una regresión lineal múltiple de `O3` sobre `NO`, `NO2`, `NOX` y `CO`.

El análisis incluye:

1. Lectura del CSV y localización automática del encabezado.
2. Selección de la estación y transformación a formato ancho.
3. Selección de las horas con las cinco mediciones disponibles, sin imputar faltantes.
4. Ajuste OLS con intercepto, R², R² ajustado, coeficientes e intervalos de confianza.
5. Diagnóstico de multicolinealidad mediante VIF y revisión de la relación `NOX = NO + NO2`.
6. Gráfica de residuos frente a predichos y prueba de Breusch–Pagan para evaluar heterocedasticidad.
7. Análisis temporal de residuos, promedio por hora del día y estadístico de Durbin–Watson.
8. QQ-plot para examinar la normalidad de los residuos.

Las asociaciones estimadas son descriptivas. La multicolinealidad, la heterocedasticidad y la dependencia temporal deben considerarse antes de interpretar coeficientes y valores p convencionales.

## Clase 8: Covarianza, Correlación E Influencia

El notebook utiliza nueve contaminantes de 2026: `CO`, `NO`, `NO2`, `NOX`, `O3`, `PM10`, `PM2.5`, `PMCO` y `SO2`. La organización de datos y el análisis de correlación abarcan las estaciones del archivo; los modelos de regresión se enfocan en `MER`.

El análisis incluye:

1. Preparación de una tabla con una fila por estación-hora y una columna por contaminante.
2. Cálculo de covarianza y correlación entre `CO` y `NOX`, globalmente y en `MER`, usando pares completos.
3. Comparación de los eigenvalores de matrices de correlación calculadas por pares y con casos completos.
4. Regresión de `PM2.5` sobre los demás contaminantes y comparación con un modelo que utiliza solo gases, sobre las mismas horas completas.
5. Cálculo de R² y VIF, con revisión de las relaciones `NOX = NO + NO2` y `PM10 = PM2.5 + PMCO`.
6. Construcción de la matriz de proyección `H` para una semana y comprobación de simetría, idempotencia y traza.
7. Cálculo del leverage para todo el periodo de regresión sin construir una matriz `H` de tamaño completo.
8. Comparación de las diez observaciones con mayor distancia de Cook y las diez con mayor leverage.
9. Reajuste de cada modelo después de retirar sus diez observaciones más influyentes y análisis del cambio en coeficientes y métricas.

El notebook conserva los faltantes y utiliza muestras completas según cada cálculo. El reajuste constituye un análisis de sensibilidad; retirar observaciones no demuestra que sean incorrectas ni que mejore el pronóstico fuera de muestra.

Aunque el nombre actual del archivo de la Clase 8 menciona estacionariedad y ozono en `UIZ`, su contenido corresponde al Notebook 2 de covarianza, correlación e influencia en `MER`. La actividad de estacionariedad se describe en la Clase 9 como trabajo pendiente.

## Clase 9: Estacionariedad Del Ozono En UIZ

**Estado:** actividad en preparación. `Clase 9.ipynb` todavía es un archivo vacío y no se puede ejecutar como notebook hasta guardar su contenido desde Jupyter o un editor compatible.

La actividad prevista utiliza el `O3` horario de `UIZ` y contempla:

1. Contar las horas faltantes y los huecos consecutivos, y justificar su tratamiento.
2. Graficar la serie y su función de autocorrelación (ACF) hasta 72 horas.
3. Ejecutar las pruebas ADF y KPSS para evaluar estacionariedad.
4. Restar la media de cada hora del día y repetir las pruebas.
5. Restar la media de cada combinación mes × hora y repetir las pruebas.
6. Aplicar la diferencia de 24 horas y repetir las pruebas.
7. Comparar la ACF y la varianza de la diferencia diaria con las del ajuste mes × hora, utilizando las mismas fechas.

El análisis debe conservar una cuadrícula horaria regular para que los rezagos representen horas reales. También debe documentar cualquier interpolación y limitar sus conclusiones al periodo disponible en el CSV.

## Instalación

1. Clona el repositorio:

```bash
git clone <URL_DEL_REPOSITORIO>
cd Machine-Learning-Repo
```

2. Crea y activa un entorno virtual:

```bash
python3 -m venv .venv
source .venv/bin/activate
```

En Windows:

```bash
python -m venv .venv
.venv\Scripts\activate
```

3. Instala las dependencias:

```bash
python -m pip install -r requirements.txt
python -m pip install statsmodels
```

4. Abre Jupyter Notebook:

```bash
jupyter notebook
```

También puedes instalar y usar JupyterLab de forma opcional:

```bash
python -m pip install jupyterlab
jupyter lab
```

## Uso

Ejecuta los notebooks en orden sugerido:

1. `Clase 1 – Airbnb.ipynb`
2. `Clase 2 - ECOBICI.ipynb`
3. `Clase 3 - Metrics classification.ipynb`
4. `Clase 4 - Mean Squared error (MSE).ipynb`
5. `Clase 5 - Calidad del aire CDMX.ipynb`
6. `Clase 6 - Meteorología.ipynb`
7. `Clase 7.ipynb`
8. `Clase 8 - Estacionariedad y patrones temporales del ozono en UIZ.ipynb`

La Clase 9 continuará la secuencia cuando se incorpore su contenido. Ejecuta las celdas de cada notebook de arriba hacia abajo; las variables y tablas se crean dentro de cada archivo.

Algunos notebooks descargan información desde internet o procesan archivos grandes. La ejecución puede tardar varios minutos dependiendo del tamaño de los datos y del equipo.

Para la Clase 5, verifica que los archivos crudos estén en la raíz del repositorio antes de ejecutar:

```text
contaminantes_2024.csv
contaminantes_2025.csv
contaminantes_2026.csv
```

Para la Clase 6, verifica que el archivo meteorológico esté en la raíz del repositorio:

```text
meteorología_2025.csv
```

Para las Clases 7 y 8, coloca `contaminantes_2026.csv` junto a los notebooks. En la Clase 8 puedes modificar `RUTA` y `ESTACION` para cambiar la ubicación del archivo o la estación de regresión. La Clase 9 utilizará ese mismo CSV para la estación `UIZ`.

Si usas Google Colab, carga los CSV en la sesión y ajusta las rutas a su ubicación, por ejemplo `/content/contaminantes_2026.csv`. Los archivos locales del equipo no se transfieren automáticamente a Colab.

## Estructura Del Proyecto

```text
.
├── Clase 1 – Airbnb.ipynb
├── Clase 2 - ECOBICI.ipynb
├── Clase 3 - Metrics classification.ipynb
├── Clase 4 - Mean Squared error (MSE).ipynb
├── Clase 5 - Calidad del aire CDMX.ipynb
├── Clase 6 - Meteorología.ipynb
├── Clase 7.ipynb
├── Clase 8 - Estacionariedad y patrones temporales del ozono en UIZ.ipynb
├── Clase 9.ipynb
├── requirements.txt
├── .gitignore
└── README.md
```

Los archivos `.csv` no aparecen en la estructura porque se mantienen fuera del control de versiones.

## Buenas Prácticas Del Repositorio

- No subir archivos grandes generados localmente, como `.csv`, `.parquet`, `.sqlite` o bases de datos.
- Mantener documentadas las fuentes de datos y las decisiones de limpieza.
- Usar entornos virtuales para aislar dependencias.
- Ejecutar los notebooks de principio a fin antes de subir cambios.
- Guardar datasets procesados solo cuando sean necesarios para reproducibilidad o modelado.
- Separar datos crudos, datos limpios y datos listos para modelo cuando el proyecto crezca.
- Conservar la frecuencia horaria y usar periodos comunes al comparar transformaciones de series de tiempo.
- Distinguir ajuste dentro de muestra, análisis de sensibilidad y desempeño predictivo fuera de muestra.

## Estado Actual

- Clases 1 a 4: notebooks de análisis, ETL y evaluación de modelos.
- Clase 5: notebook activo de calidad del aire con ETL, estadística descriptiva y gráficas de distribución.
- Clase 6: notebook de meteorología enfocado en probabilidades empíricas, conjuntas y condicionales para la estación `BJU`.
- Clase 7: notebook de regresión de ozono en `MER` con diagnóstico de multicolinealidad, heterocedasticidad, dependencia temporal y normalidad de residuos.
- Clase 8: notebook de covarianza, correlación, matrices de proyección y análisis de influencia en modelos de `PM2.5` de `MER`.
- Clase 9: archivo vacío reservado para el análisis de estacionariedad del ozono horario de `UIZ`.
- Datasets grandes: disponibles localmente, pero excluidos del repositorio mediante `.gitignore`.

## Autor

**Luis Enrique Hernández Torres**  
A01662166
