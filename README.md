# Pleito de tinta: retórica, poder y alteridad en las crónicas rioplatenses ante el ojo computacional

[![Licence](https://img.shields.io/badge/License-CC--BY--NC--SA%204.0-lightgrey.svg)](LICENSE)
[![Python 3.10+](https://img.shields.io/badge/python-3.10+-blue.svg)](https://www.python.org/)
[![Minimal Computing](https://img.shields.io/badge/design-minimal%20computing-orange.svg)](https://go-dh.github.io/mincomp/)
[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/)

**Autora:** Romina De León  
**Programa:** Especialización en Ciencias Sociales Computacionales — Universidad Nacional Guillermo Brown (UNAB)  

---

## Descripción del proyecto

Este proyecto de Trabajo Final Integrador se inscribe en la intersección de la Historia colonial temprana y las Ciencias Sociales Computacionales buscando examinar un corpus censal de cuatro crónicas y un poema histórico del Río de la Plata y Paraguay en los siglos XVI y principios del XVII. La propuesta busca desandar el predominio de estudios filológicos e históricos individuales, por una lectura mixta que adopta un diseño secuencial explicativo sustentado con macroanálisis, georreferenciación y estadística textual. Con una matriz rectangular de datos no estructurados conformada con párrafos y estrofas, el plan cuantitativo operacionaliza las dimensiones de legitimación imperial, faccionalismo y alteridad indígena. A través de un análisis estadístico multietápico y bajo los principios de minimal computing, aseguraré un flujo de trabajo que habilitará la portabilidad y reproducibilidad analítica en entornos abiertos de Python, que además me proveerán de una base empírica para evaluar la hipótesis sobre la singularidad retórico-defensiva de los Comentarios de Cabeza de Vaca, estadísticamente diferenciable frente a las obras contemporáneas que conforman el corpus, así como contrastar las espacialidades textuales históricas (asentamientos fundacionales, fuertes, aldeas indígenas y rutas terrestres/fluviales) con las capas geográficas contemporáneas e históricas de la Cuenca del Plata y los ríos Paraná y Paraguay.

* *Comentarios* — Álvar Núñez Cabeza de Vaca (1555)
* *Relación de las cosas sucedidas en el Río de la Plata* — Pero Hernández (c. 1556)
* *Viaje al Río de la Plata* — Ulrich Schmídel (1567)
* *Argentina y Conquista del Río de la Plata* — Martín del Barco Centenera (1602)
* *La Argentina Manuscrita* — Ruy Díaz de Guzmán (c. 1612)

Frente a la tradición filológica de lectura cercana individual, se implementa un **diseño mixto secuencial explicativo** que traduce el corpus a una matriz rectangular estructurada por párrafos y estrofas ($N = 8.057$). A partir de allí, se operacionalizan cuantitativamente los discursos de legitimación imperial, faccionalismo y alteridad indígena mediante estadística univariada, tablas de contingencia bivariadas (*Odds Ratio*), pruebas de hipótesis ($\chi^2$, Kruskal-Wallis/ANOVA), modelado probabilístico de tópicos (LDA) y modelado geoespacial (SIG) sobre la hidrografía de la Cuenca del Plata.

---

## Estructura del repositorio

```text
tif-unab/
│
├── README.md
├── LICENSE
├── CITATION.cff
├── requirements.txt
├── environment.yml
├── .gitignore
│
├── data/
│   ├── txt/
│   │       ├── comentarios_cabezadevaca/
│   │       ├── relacion_hernandez/
│   │       ├── viaje_schmidel/
│   │       ├── poema_centenera/
│   │       └── historia_diazdeguzman/
│   │
│   └── geodata/
│       ├── raw/
│       │   ├── ign_hidrografia/ <- Cursos de agua superficiales (WFS / SHP)
│       │   └── osm_asentamientos/ <- Localidades y toponimia actual (OSM)
│       └── processed/
│           ├── red_hidrografica_plata.gpkg
│           └── itinerarios_combinados.gpkg
│
├── notebooks/
│   ├── ...
│   └── 01_analisis_corpus.ipynb
│
├── maps/
|   ├── propios
|   |   ├── ulrico.csv
|   |   ├── centeneraPlaces.js
|   |   ├── comentarios.csv
|   |   ├── perohernandezPlaces.js
|   |   └── ruydiazPlaces.js     
├── outputs/
│   ├── tables/ <- Tablas univariadas, contingencia y keyness (CSV/LaTeX)
│   ├── figures/ <- Dendrogramas, nubes léxicas, boxplots y gráficos de sentimiento
│   └── itinerarios/ <- Mapas interactivos (HTML)
│
├── docs/
│   ├── metodologia.md
│   ├── diccionario_datos.md
│   └── decisiones_analiticas.md
│
└── references/
    └── bibliografia.bib
```

---

## Requisitos e instalación

Este entorno de trabajo sigue los principios de la **minimal computing**, garantizando dependencias ligeras, portabilidad multiplataforma y software de código abierto.

```bash
# Clonar el repositorio
git clone ...

# Instalar dependencias
pip install -r requirements.txt
```

### Principales librerías empleadas (no definidas)

* **Procesamiento de texto y NLP:** `spaCy`, `Gensim`, `NLTK`.
* **Análisis cuantitativo y estadística:** `pandas`, `numpy`, `scipy`, `statsmodels`.
* **Análisis geoespacial (SIG):** `geopandas`, `shapely`, `contextily`, `folium`.
* **Visualización:** `matplotlib`, `seaborn`, `networkx`.

---

## Licencia

Este proyecto se distribuye bajo licencia **Creative Commons Atribución-NoComercial-CompartirIgual 4.0 Internacional (CC BY-NC-SA 4.0)**. El código fuente asociado está bajo licencia MIT.