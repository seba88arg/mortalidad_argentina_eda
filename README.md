# mortalidad_argentina_eda
Análisis de las causas de muerte en Argentina. 2024.
Análisis exploratorio de datos oficiales de defunciones — DEIS / Ministerio de Salud de la Nación

Descripción
Análisis exploratorio completo de las defunciones registradas en Argentina, utilizando datos oficiales de la Dirección de Estadísticas e Información en Salud (DEIS). El proyecto responde preguntas concretas sobre causas de muerte, distribución geográfica, perfil demográfico y diferencias por sexo, trabajando con más de 376.000 defunciones registradas.

Preguntas que responde este análisis

¿Cuáles son las principales causas de muerte en Argentina?
¿Qué grupos de enfermedades concentran la mayor mortalidad?
¿Existen diferencias en las causas de muerte según sexo?
¿De qué muere cada franja etaria — desde recién nacidos hasta adultos mayores?
¿Qué provincias presentan mayor cantidad de defunciones?


Hallazgos principales 

376.141 defunciones analizadas, distribuidas en 1.053 causas distintas (códigos CIE-10).
Las enfermedades del sistema circulatorio son la principal causa de muerte (27,9% del total), seguidas por las respiratorias (20,6%).
La neumonía es la causa individual más frecuente con 39.185 defunciones (10,4%), seguida por la insuficiencia cardíaca (7,0%) y las causas mal definidas (5,5%).
En jóvenes de 15 a 34 años, el suicidio es la primera causa de muerte, representando el 12,4% de las defunciones en ese grupo etario.
Las causas externas (accidentes, violencia) afectan 2,5 veces más a hombres que a mujeres.
En la franja neonatal, las principales causas son el distrés respiratorio y la prematurez — reflejando problemáticas perinatales prevenibles.
Buenos Aires concentra la mayor cantidad de defunciones absolutas (151.602), mientras que Tierra del Fuego registra el menor volumen (733).


Fuente de datos
FuenteDescripciónAccesoDEIS — Ministerio de Salud de la NaciónDefunciones por provincia, sexo, causa y edaddatos.salud.gob.ar
Nota técnica: El dataset incluye una columna MAT que solo contiene valores para el subconjunto de mortalidad materna (M = materna, T = tardía). Las defunciones generales tienen ese campo nulo. El filtro correcto para el análisis general es df[df['MAT'].isnull()].

Estructura del proyecto
mortalidad-argentina-eda/
│
├── README.md
├── requirements.txt
│
├── data/
│   └── raw/
│       └── defunciones_deis.csv        ← Dataset original DEIS
│
├── notebooks/
│   ├── 01_carga_y_limpieza.ipynb       ← Carga, encoding, mapeos, limpieza
│   ├── 02_analisis_exploratorio.ipynb  ← EDA: causas, provincias, pirámide edad/sexo
│   └── 03_visualizaciones.ipynb        ← Visualizaciones avanzadas por franja etaria y sexo
│
└── outputs/
    └── figures/                        ← Gráficos exportados en PNG

Visualizaciones
#GráficoNotebook1Top 15 causas de defunción022Defunciones por provincia023Pirámide de defunciones por edad y sexo024Top 10 causas por sexo025Defunciones por grupos CIE-10036Heatmap: distribución de causas por provincia037Top 5 causas por franja etaria (8 franjas)038Proporción masculino/femenino por grupo de causas03

Tecnologías
![Python](https://img.shields.io/badge/Python-3.11-blue)
![Pandas](https://img.shields.io/badge/Pandas-2.0-lightblue)
![Matplotlib](https://img.shields.io/badge/Matplotlib-3.7-orange)
![Seaborn](https://img.shields.io/badge/Seaborn-0.12-teal)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange)

Cómo reproducir
bash# 1. Clonar el repositorio
git clone https://github.com/tu-usuario/mortalidad-argentina-eda.git
cd mortalidad-argentina-eda

# 2. Instalar dependencias
pip install -r requirements.txt

# 3. Abrir Jupyter
jupyter notebook
Ejecutar los notebooks en orden: 01 → 02 → 03.
El dataset original puede descargarse desde datos.salud.gob.ar y debe colocarse en data/raw/defunciones_deis.csv.

Autor
Sebastián — Data Analyst
Experiencia en el sector salud en Argentina · Excel · Power BI ·
