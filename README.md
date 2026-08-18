# Statistics for Data Science

Repositorio de notebooks para la materia **Statistics for Data Science**, con ejercicios de análisis exploratorio, limpieza, transformación y visualización de datos usando Python.

## Contenido

| Archivo | Descripción |
| --- | --- |
| `Clase 1 – Airbnb.ipynb` | Análisis exploratorio de alojamientos de Airbnb en Ciudad de México. Incluye limpieza de precios, conteos por tipo de alojamiento, principales alcaldías, anfitriones y visualizaciones geográficas. |
| `Clase 2 - ECOBICI.ipynb` | Flujo ETL sobre viajes de ECOBICI. Descarga datos, los transforma, crea variables derivadas y aplica normalización/codificación para análisis posterior. |

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

## Fuentes de datos

- **Airbnb CDMX:** datos públicos de Inside Airbnb cargados directamente desde el notebook.
- **ECOBICI CDMX:** datos públicos descargados desde el portal de ECOBICI.

Los datasets locales de gran tamaño, como `2026-07.csv`, no se versionan en Git para mantener el repositorio ligero. El notebook de ECOBICI descarga el archivo necesario al ejecutarse.

## Instalación

1. Clona el repositorio:

```bash
git clone <URL_DEL_REPOSITORIO>
cd "Statistics for data science"
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

## Uso

Ejecuta los notebooks en orden:

1. `Clase 1 – Airbnb.ipynb`
2. `Clase 2 - ECOBICI.ipynb`

Algunos pasos descargan información desde internet, por lo que se requiere conexión activa. La ejecución puede tardar varios minutos cuando se descargan o procesan datasets grandes.

## Estructura recomendada

```text
.
├── Clase 1 – Airbnb.ipynb
├── Clase 2 - ECOBICI.ipynb
├── requirements.txt
├── .gitignore
└── README.md
```

## Buenas prácticas del repositorio

- No subir archivos grandes generados localmente, como `.csv`, `.parquet` o bases de datos.
- Mantener las fuentes de datos documentadas dentro del README o los notebooks.
- Usar entornos virtuales para aislar dependencias.
- Revisar que los notebooks se ejecuten de principio a fin antes de subir cambios.

## Autor

**Luis Enrique Hernández Torres**  
A01662166
