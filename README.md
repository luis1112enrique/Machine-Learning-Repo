# Statistics for Data Science

Repositorio de notebooks para la materia **Statistics for Data Science**. El proyecto reúne ejercicios de análisis exploratorio, procesos ETL, limpieza de datos, feature engineering, visualización, estadística descriptiva y evaluación de modelos de machine learning usando Python.

El repositorio está organizado por clases. Cada notebook trabaja un caso distinto y busca documentar el flujo completo: desde la carga de datos hasta la preparación para análisis o modelado.

## Contenido

| Archivo | Tema principal | Descripción |
| --- | --- | --- |
| `Clase 1 – Airbnb.ipynb` | EDA | Análisis exploratorio de alojamientos de Airbnb en Ciudad de México. Incluye limpieza de precios, conteos por tipo de alojamiento, principales alcaldías, anfitriones y visualizaciones geográficas. |
| `Clase 2 - ECOBICI.ipynb` | ETL | Procesamiento de viajes de ECOBICI. Descarga datos, transforma columnas, crea variables derivadas y aplica normalización/codificación para análisis posterior. |
| `Clase 3 - Metrics classification.ipynb` | Clasificación | Evaluación de modelos de clasificación usando el dataset Breast Cancer Wisconsin de `scikit-learn`. Incluye matriz de confusión, accuracy y análisis de desbalance con datos sintéticos de fraude. |
| `Clase 4 - Mean Squared error (MSE).ipynb` | Regresión | Comparación de modelos de regresión usando el dataset Diabetes de `scikit-learn`. Calcula MSE, MAE, RMSE y R² para Linear Regression, Ridge, Lasso, Decision Tree y Random Forest. |
| `Clase 5 - Calidad del aire CDMX.ipynb` | ETL y estadística descriptiva | Flujo de ingesta, limpieza, control de calidad, imputación ligera, feature engineering temporal y visualización de contaminantes atmosféricos en CDMX para 2024, 2025 y 2026. |

## Objetivos Del Repositorio

- Practicar análisis exploratorio de datos con problemas reales y sintéticos.
- Construir pipelines básicos de ETL: ingesta, limpieza, transformación y validación.
- Crear variables útiles para análisis estadístico y modelos predictivos.
- Evaluar modelos de clasificación y regresión con métricas adecuadas.
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

Las dependencias principales están listadas en `requirements.txt`.

## Fuentes De Datos

- **Airbnb CDMX:** datos públicos de Inside Airbnb cargados desde el notebook.
- **ECOBICI CDMX:** datos públicos de viajes de ECOBICI.
- **Calidad del aire CDMX:** archivos locales de contaminantes atmosféricos del sistema de monitoreo de la Ciudad de México.
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
| `contaminantes_2026.csv` | Clase 5 | Datos crudos de calidad del aire 2026. |
| `calidad_aire_long_limpio.csv` | Clase 5 | Dataset limpio en formato largo, generado por el ETL. |
| `calidad_aire_wide_features.csv` | Clase 5 | Dataset transformado a formato ancho con variables temporales. |
| `calidad_aire_model_ready.csv` | Clase 5 | Dataset preparado para modelado predictivo. |

Nota para la Clase 5: los archivos `contaminantes_2024.csv`, `contaminantes_2025.csv` y `contaminantes_2026.csv` contienen 9 filas de metadatos antes del encabezado real. Por eso se cargan con `skiprows=9`.

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
pip install -r requirements.txt
```

4. Abre Jupyter Notebook:

```bash
jupyter notebook
```

También puedes usar JupyterLab:

```bash
jupyter lab
```

## Uso

Ejecuta los notebooks en orden sugerido:

1. `Clase 1 – Airbnb.ipynb`
2. `Clase 2 - ECOBICI.ipynb`
3. `Clase 3 - Metrics classification.ipynb`
4. `Clase 4 - Mean Squared error (MSE).ipynb`
5. `Clase 5 - Calidad del aire CDMX.ipynb`

Algunos notebooks descargan información desde internet o procesan archivos grandes. La ejecución puede tardar varios minutos dependiendo del tamaño de los datos y del equipo.

Para la Clase 5, verifica que los archivos crudos estén en la raíz del repositorio antes de ejecutar:

```text
contaminantes_2024.csv
contaminantes_2025.csv
contaminantes_2026.csv
```

## Estructura Del Proyecto

```text
.
├── Clase 1 – Airbnb.ipynb
├── Clase 2 - ECOBICI.ipynb
├── Clase 3 - Metrics classification.ipynb
├── Clase 4 - Mean Squared error (MSE).ipynb
├── Clase 5 - Calidad del aire CDMX.ipynb
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

## Estado Actual

- Clases 1 a 4: notebooks de análisis, ETL y evaluación de modelos.
- Clase 5: notebook activo de calidad del aire con ETL, estadística descriptiva y gráficas de distribución.
- Datasets grandes: disponibles localmente, pero excluidos del repositorio mediante `.gitignore`.

## Autor

**Luis Enrique Hernández Torres**  
A01662166
