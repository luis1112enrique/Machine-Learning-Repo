# Statistics for Data Science

Repositorio de notebooks para la materia **Statistics for Data Science**. El proyecto reúne ejercicios de análisis exploratorio, procesos ETL, limpieza de datos, feature engineering, visualización, estadística descriptiva, probabilidad, regresión, evaluación de modelos y análisis de series de tiempo con Python.

El repositorio está organizado por clases. Actualmente contiene ocho notebooks desarrollados y dos actividades en preparación. Cada ejercicio documenta el flujo de trabajo desde la carga y validación de los datos hasta el análisis estadístico o el modelado.

## Contenido

| Clase | Notebook | Tema principal | Estado |
| --- | --- | --- | --- |
| 1 | [Airbnb](<./Clase 1 – Airbnb.ipynb>) | Análisis exploratorio de alojamientos de Airbnb en Ciudad de México con Polars: precios, tipos de alojamiento, alcaldías, anfitriones y visualizaciones geográficas. | Disponible |
| 2 | [ECOBICI](<./Clase 2 - ECOBICI.ipynb>) | Proceso ETL de viajes de ECOBICI de julio de 2026: limpieza, variables derivadas, normalización y codificación. | Disponible |
| 3 | [Métricas de clasificación](<./Clase 3 - Metrics classification.ipynb>) | Evaluación de clasificadores con Breast Cancer Wisconsin y análisis del efecto del desbalance mediante datos sintéticos de fraude. | Disponible |
| 4 | [Mean Squared Error (MSE)](<./Clase 4 - Mean Squared error (MSE).ipynb>) | Comparación de modelos de regresión con el dataset Diabetes mediante MSE, MAE, RMSE, R², MAPE y RMSLE. | Disponible |
| 5 | [Calidad del aire CDMX](<./Clase 5 - Calidad del aire CDMX.ipynb>) | ETL, control de calidad, feature engineering temporal y visualización de contaminantes de 2024 a 2026. | Disponible |
| 6 | [Meteorología](<./Clase 6 - Meteorología.ipynb>) | Probabilidades empíricas, conjuntas y condicionales para humedad relativa y velocidad del viento en la estación `BJU`. | Disponible |
| 7 | [Diagnóstico de una regresión lineal para ozono](<./Clase 7 - Diagnóstico de una regresión lineal para ozono.ipynb>) | Regresión de `O3` en la estación `MER`, con diagnósticos de multicolinealidad, heterocedasticidad, dependencia temporal y normalidad. | Disponible |
| 8 | [Covarianza, correlación, multicolinealidad e influencia](<./Clase 8 - Covarianza, correlación, multicolinealidad e influencia.ipynb>) | Covarianza, correlación, eigenvalores, modelos de `PM2.5`, VIF, leverage, distancia de Cook y análisis de sensibilidad. | Disponible |
| 9 | [Estacionariedad y patrones temporales del ozono en UIZ](<./Clase 9 - Estacionariedad y patrones temporales del ozono en UIZ.ipynb>) | Actividad prevista sobre el `O3` horario de `UIZ`, su autocorrelación y estacionariedad. | En preparación |
| 10 | [Análisis de la serie temporal de CO₂](<./Clase 10 - Análisis de la serie temporal de CO₂ .ipynb>) | Archivo reservado para un análisis de serie temporal de CO₂. | En preparación |

> **Nota:** los archivos de las Clases 9 y 10 están vacíos por el momento. Todavía no contienen la estructura JSON de un notebook y no se pueden ejecutar hasta que se guarde su contenido.

Las Clases 7, 8 y 9 corresponden, respectivamente, a los ejercicios **Notebook 1**, **Notebook 2** y **Notebook 3** de la secuencia de calidad del aire. La Clase 10 inicia una actividad distinta sobre una serie temporal de CO₂; su fuente de datos y metodología aún no están documentadas.

## Objetivos del repositorio

- Practicar análisis exploratorio con datos reales y sintéticos.
- Construir pipelines básicos de ETL: ingesta, limpieza, transformación y validación.
- Crear variables útiles para análisis estadístico y modelos predictivos.
- Evaluar modelos de clasificación y regresión con métricas adecuadas.
- Calcular probabilidades empíricas, conjuntas y condicionales a partir de observaciones.
- Ajustar regresiones lineales e interpretar sus coeficientes y diagnósticos.
- Comparar covarianza y correlación, detectar multicolinealidad y estudiar observaciones influyentes.
- Explorar autocorrelación, patrones temporales y estacionariedad en series horarias.
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

Las dependencias base están listadas en `requirements.txt`. Las Clases 7 y 8 también utilizan `statsmodels`, que todavía no forma parte de ese archivo; la instalación adicional se incluye en la sección de instalación. La actividad prevista para la Clase 9 también contempla esta librería para ADF, KPSS y ACF.

## Fuentes de datos

- **Airbnb CDMX:** datos públicos de Inside Airbnb descargados desde el notebook.
- **ECOBICI CDMX:** datos públicos de viajes de ECOBICI.
- **Calidad del aire CDMX:** mediciones del Sistema de Monitoreo Atmosférico (SIMAT) de la Ciudad de México, utilizadas en las Clases 5, 7 y 8 y previstas para la Clase 9.
- **Meteorología CDMX:** variables meteorológicas del sistema de monitoreo de la Ciudad de México.
- **Breast Cancer Wisconsin:** dataset incluido en `scikit-learn`, usado para métricas de clasificación.
- **Diabetes:** dataset incluido en `scikit-learn`, usado para métricas de regresión.
- **Fraude sintético:** dataset generado con `make_classification` de `scikit-learn` para ilustrar el desbalance de clases.
- **Serie de CO₂:** fuente pendiente de documentar cuando se incorpore el contenido de la Clase 10.

## Datos locales

Los archivos `.csv` están ignorados por Git para mantener el repositorio ligero. Para reproducir todos los notebooks, algunos datasets deben estar disponibles localmente o descargarse desde sus fuentes originales.

### Archivos de entrada

| Archivo | Uso | Notas |
| --- | --- | --- |
| `2026-07.csv` | Clase 2 | Viajes de ECOBICI de julio de 2026. |
| `contaminantes_2024.csv` | Clase 5 | Datos crudos de calidad del aire de 2024. |
| `contaminantes_2025.csv` | Clase 5 | Datos crudos de calidad del aire de 2025. |
| `contaminantes_2026.csv` | Clases 5, 7 y 8; previsto para la Clase 9 | Datos crudos de calidad del aire. El análisis queda limitado al periodo incluido en la copia local. |
| `meteorología_2025.csv` | Clase 6 | Datos meteorológicos de 2025 en formato largo. |

### Archivos generados

La Clase 5 produce los siguientes archivos al ejecutar su pipeline:

| Archivo | Contenido |
| --- | --- |
| `calidad_aire_long_limpio.csv` | Dataset limpio en formato largo. |
| `calidad_aire_wide_features.csv` | Dataset en formato ancho con variables temporales. |
| `calidad_aire_model_ready.csv` | Dataset preparado para modelado predictivo. |

Los archivos crudos de las Clases 5 y 6 contienen nueve filas de metadatos antes del encabezado real, por lo que se cargan con `skiprows=9`. Las Clases 7 y 8 localizan el encabezado automáticamente.

Los datos de contaminantes están en formato largo: cada fila representa una medición para una estación, un contaminante y una fecha-hora. La columna `unit` contiene códigos de unidad, no factores de conversión. Las Clases 7 y 8 leen directamente `contaminantes_2026.csv`, por lo que no dependen de los archivos procesados de la Clase 5.

## Clase 5: calidad del aire CDMX

El notebook implementa un flujo ETL completo:

1. Ingesta de los archivos de contaminantes de 2024, 2025 y 2026.
2. Estandarización de columnas, incluido el cambio de `value` a `valor` en 2024.
3. Conversión de fechas, variables numéricas y códigos de estación y contaminante.
4. Tratamiento de valores negativos y datos faltantes.
5. Consolidación de duplicados por fecha, estación y contaminante.
6. Imputación ligera mediante interpolación por estación y contaminante.
7. Feature engineering temporal: año, mes, día, hora, fin de semana, ciclos horarios y temporadas.
8. Transformación de formato largo a formato ancho.
9. Creación de una variable objetivo, por ejemplo `PM2.5` una hora adelante.
10. División temporal entre entrenamiento y prueba.
11. Cálculo de media, mediana y moda.
12. Visualización de distribuciones por año y contaminante.

## Clase 6: meteorología

El notebook trabaja con datos horarios de la Ciudad de México durante 2025. El análisis se enfoca en la estación `BJU` y en dos parámetros:

- `RH`: humedad relativa.
- `WSP`: velocidad del viento.

Los eventos definidos son:

- Humedad alta: `RH >= 70`.
- Viento tranquilo: `WSP <= 1`.

El análisis calcula:

1. Probabilidad empírica de humedad alta: `P(RH >= 70)`.
2. Probabilidad empírica de viento tranquilo: `P(WSP <= 1)`.
3. Probabilidad conjunta: `P(RH >= 70 y WSP <= 1)`.
4. Probabilidad condicional de humedad alta dado viento tranquilo: `P(RH >= 70 | WSP <= 1)`.
5. Probabilidad condicional de viento tranquilo dado humedad alta: `P(WSP <= 1 | RH >= 70)`.

Para comparar ambas variables en una misma hora, el dataset se transforma de formato largo a formato ancho mediante `pivot_table`, con `date` como índice e `id_parameter` como columnas.

## Clase 7: regresión y diagnóstico de supuestos

El notebook trabaja con datos horarios de la estación `MER` (Merced) y ajusta una regresión lineal múltiple de `O3` sobre `NO`, `NO2`, `NOX` y `CO`.

El análisis incluye:

1. Lectura del CSV y localización automática del encabezado.
2. Selección de la estación y transformación a formato ancho.
3. Selección de las horas con las cinco mediciones disponibles, sin imputar faltantes.
4. Ajuste OLS con intercepto, R², R² ajustado, coeficientes e intervalos de confianza.
5. Diagnóstico de multicolinealidad mediante VIF y revisión de la relación `NOX = NO + NO2`.
6. Gráfica de residuos frente a valores predichos y prueba de Breusch–Pagan.
7. Análisis temporal de residuos, promedio por hora del día y estadístico de Durbin–Watson.
8. QQ-plot para examinar la normalidad de los residuos.

Las asociaciones estimadas son descriptivas. La multicolinealidad, la heterocedasticidad y la dependencia temporal deben considerarse antes de interpretar los coeficientes y valores p convencionales.

## Clase 8: covarianza, correlación e influencia

El notebook utiliza nueve contaminantes de 2026: `CO`, `NO`, `NO2`, `NOX`, `O3`, `PM10`, `PM2.5`, `PMCO` y `SO2`. La organización de datos y el análisis de correlación abarcan las estaciones presentes en el archivo; los modelos de regresión se enfocan en `MER`.

El análisis incluye:

1. Preparación de una tabla con una fila por estación-hora y una columna por contaminante.
2. Cálculo de covarianza y correlación entre `CO` y `NOX`, globalmente y en `MER`, mediante pares completos.
3. Comparación de eigenvalores de matrices de correlación calculadas por pares y con casos completos.
4. Regresión de `PM2.5` sobre los demás contaminantes y comparación con un modelo que utiliza solo gases sobre las mismas horas completas.
5. Cálculo de R² y VIF, con revisión de las relaciones `NOX = NO + NO2` y `PM10 = PM2.5 + PMCO`.
6. Construcción de la matriz de proyección `H` para una semana y comprobación de simetría, idempotencia y traza.
7. Cálculo del leverage para todo el periodo de regresión sin construir una matriz `H` de tamaño completo.
8. Comparación de las diez observaciones con mayor distancia de Cook y las diez con mayor leverage.
9. Reajuste de cada modelo después de retirar sus diez observaciones más influyentes y análisis de los cambios en coeficientes y métricas.

El notebook conserva los faltantes y utiliza muestras completas según cada cálculo. El reajuste constituye un análisis de sensibilidad; retirar observaciones no demuestra que sean incorrectas ni que mejore el pronóstico fuera de muestra.

## Clase 9: estacionariedad del ozono en UIZ

**Estado:** actividad en preparación. El archivo existe, pero está vacío y todavía no se puede ejecutar como notebook.

La actividad prevista utiliza el `O3` horario de `UIZ` y contempla:

1. Contar las horas faltantes y los huecos consecutivos, y justificar su tratamiento.
2. Graficar la serie y su función de autocorrelación (ACF) hasta 72 horas.
3. Ejecutar las pruebas ADF y KPSS para evaluar estacionariedad.
4. Restar la media de cada hora del día y repetir las pruebas.
5. Restar la media de cada combinación mes × hora y repetir las pruebas.
6. Aplicar la diferencia de 24 horas y repetir las pruebas.
7. Comparar la ACF y la varianza de la diferencia diaria con las del ajuste mes × hora, utilizando las mismas fechas.

El análisis deberá conservar una cuadrícula horaria regular para que los rezagos representen horas reales, documentar cualquier interpolación y limitar sus conclusiones al periodo disponible en el CSV.

## Clase 10: serie temporal de CO₂

**Estado:** actividad en preparación. El archivo existe, pero está vacío y todavía no se puede ejecutar como notebook.

Por ahora, el nombre del archivo solo permite identificar el tema general. La fuente, la frecuencia, la cobertura temporal, el tratamiento de faltantes, la metodología y los resultados deberán documentarse cuando se guarde el contenido del notebook.

## Instalación

1. Clona el repositorio y entra en su directorio:

```bash
git clone https://github.com/luis1112enrique/Machine-Learning-Repo.git
cd Machine-Learning-Repo
```

2. Crea y activa un entorno virtual:

```bash
python3 -m venv .venv
source .venv/bin/activate
```

En Windows:

```powershell
python -m venv .venv
.venv\Scripts\activate
```

3. Instala las dependencias:

```bash
python -m pip install --upgrade pip
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

Los notebooks desarrollados pueden ejecutarse en el siguiente orden sugerido:

1. `Clase 1 – Airbnb.ipynb`
2. `Clase 2 - ECOBICI.ipynb`
3. `Clase 3 - Metrics classification.ipynb`
4. `Clase 4 - Mean Squared error (MSE).ipynb`
5. `Clase 5 - Calidad del aire CDMX.ipynb`
6. `Clase 6 - Meteorología.ipynb`
7. `Clase 7 - Diagnóstico de una regresión lineal para ozono.ipynb`
8. `Clase 8 - Covarianza, correlación, multicolinealidad e influencia.ipynb`

Ejecuta las celdas de cada notebook de arriba hacia abajo. Las Clases 9 y 10 se incorporarán a la secuencia cuando tengan contenido guardado.

### Datos necesarios por clase

| Clase | Requisito |
| --- | --- |
| 1 | Conexión a internet para descargar datos de Inside Airbnb. |
| 2 | `2026-07.csv`. |
| 3 y 4 | Datasets incluidos en `scikit-learn`; no requieren CSV local. |
| 5 | `contaminantes_2024.csv`, `contaminantes_2025.csv` y `contaminantes_2026.csv`. |
| 6 | `meteorología_2025.csv`. |
| 7 y 8 | `contaminantes_2026.csv`. |
| 9 | Se prevé utilizar `contaminantes_2026.csv`; la implementación sigue pendiente. |
| 10 | Fuente de datos pendiente de documentar. |

Algunos notebooks descargan información o procesan archivos grandes, por lo que la ejecución puede tardar varios minutos. Coloca los CSV en la raíz del repositorio, junto a los notebooks correspondientes.

Si usas Google Colab, carga los archivos en la sesión y ajusta las rutas, por ejemplo a `/content/contaminantes_2026.csv`. Los datos locales del equipo no se transfieren automáticamente a Colab.

## Estructura principal del proyecto

```text
.
├── Clase 1 – Airbnb.ipynb
├── Clase 2 - ECOBICI.ipynb
├── Clase 3 - Metrics classification.ipynb
├── Clase 4 - Mean Squared error (MSE).ipynb
├── Clase 5 - Calidad del aire CDMX.ipynb
├── Clase 6 - Meteorología.ipynb
├── Clase 7 - Diagnóstico de una regresión lineal para ozono.ipynb
├── Clase 8 - Covarianza, correlación, multicolinealidad e influencia.ipynb
├── Clase 9 - Estacionariedad y patrones temporales del ozono en UIZ.ipynb
├── Clase 10 - Análisis de la serie temporal de CO₂ .ipynb
├── requirements.txt
├── .gitignore
└── README.md
```

Los archivos `.csv` no aparecen en la estructura porque se mantienen fuera del control de versiones. El espacio antes de `.ipynb` en el nombre actual de la Clase 10 forma parte del nombre real del archivo.

## Buenas prácticas del repositorio

- No subir archivos grandes generados localmente, como `.csv`, `.parquet`, `.sqlite` o bases de datos.
- Mantener documentadas las fuentes de datos y las decisiones de limpieza.
- Usar entornos virtuales para aislar dependencias.
- Ejecutar los notebooks de principio a fin antes de subir cambios.
- Guardar datasets procesados solo cuando sean necesarios para reproducibilidad o modelado.
- Separar datos crudos, datos limpios y datos listos para modelo cuando el proyecto crezca.
- Conservar la frecuencia horaria y usar periodos comunes al comparar transformaciones de series de tiempo.
- Distinguir ajuste dentro de muestra, análisis de sensibilidad y desempeño predictivo fuera de muestra.

## Estado actual

- **Clases 1 a 4:** análisis exploratorio, ETL y evaluación de modelos de clasificación y regresión.
- **Clases 5 y 6:** calidad del aire, meteorología, estadística descriptiva y probabilidad.
- **Clases 7 y 8:** regresión, diagnósticos, covarianza, correlación y análisis de influencia con datos de SIMAT.
- **Clases 9 y 10:** archivos reservados y todavía vacíos; sus actividades no están implementadas.
- **Datos locales:** disponibles en el entorno de trabajo, pero excluidos del repositorio mediante `.gitignore`.

## Autor

**Luis Enrique Hernández Torres**  
A01662166
