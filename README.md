# Hi there! I'm Jorge Hurtado Soriano 👋

🧬 **Bioinformatician & Life Sciences Data Scientist**  
B.Sc. in Genomic Sciences (UACM) | M.Sc. in Bioinformatics (UNIR) & M.Sc. in Big Data (TECH)

📍 **Location:** Mexico City, Mexico  
✉️ **Contact:** jorgehurt.sor@gmail.com  
🔗 **Links:** [LinkedIn](https://linkedin.com/in/your-profile) | [ResearchGate](https://researchgate.net/profile/your-profile) | [B.Sc. Thesis (UACM)](http://repositorioinstitucionaluacm.mx/jspui/handle/123456789/2984)

---

### 🔬 About Me
- 📊 Specialized in **Exploratory Data Analysis (EDA)**, **Metabolomics (UPLC-MS/MS)**, **Computational Genomics**, and **Pipeline Development**.
- 🛠️ Experienced in developing reproducible analytical workflows using **R**, **Python**, and **Linux/Bash** environments.
- 📝 Co-author of peer-reviewed scientific publications on epigenetics, epigenetic clocks, and aging epidemiology.

---

### 🛠️ Tech Stack & Tools

- **Languages & Shell:** `R`, `Python`, `Bash/Shell Scripting`
- **Data Analysis & Bioinformatics:** `Tidyverse`, `Bioconductor`, `UPLC-MS/MS Data Processing`, `KEGG/GO Functional Enrichment`
- **Environments & Version Control:** `Linux (Ubuntu/Debian)`, `RStudio`, `Jupyter Notebooks`, `Git/GitHub`, `Google Colab`

---

### 📚 Featured Scientific Publications
1. **Martínez-Magaña, J. J., Hurtado-Soriano, J., et al. (2024).** *Towards a Novel Frontier in the Use of Epigenetic Clocks in Epidemiology.* Archives of Medical Research, 55(5), 103033.
2. **Martínez-Magaña, J. J., Hurtado-Soriano, J., et al. (2024).** *Potential use of epigenetic clocks to understand factors associated with aging at the population level and in public health.* Gaceta Médica de México, 160(3), 341-343.
3. **Hurtado-Soriano, J. (2024).** *Exploratory Metabolomic Analysis of Individuals with Cognitive Impairment from the Obesity, Sarcopenia, and Frailty Cohort.* B.Sc. Thesis, UACM.

-------------------------------------------------------------------------------------------------------------------------
# Semi-Untargeted UPLC-TQ/MS Serum Metabolomics Pipeline

This repository details the bioinformatics protocol and analytical pipeline for semi-untargeted metabolomic processing of human serum samples acquired via UPLC-TQ-MS/MS (Waters Xevo TQ-S).

The analytical workflow addresses low-resolution MS1 centroid data processing, peak detection, retention time alignment, adduct selection, batch correction, and covariate-adjusted statistical analysis (limma/ANOVA) for cognitive impairment research.


## 📌 Contents
- `data/`: `batch_data.csv` (metabolite intensity data) and `metaData.csv` (sample metadata for group-level processing).
- `docs/`: Bioinformatics protocol used for MS-DIAL data processing and undergraduate thesis documentation.

## 🛠️ Requirements

- **MS-DIAL** Processing Parameters (v4.92)
- **Data Type:** Soft ionization (LC-MS) | Centroid data (MS1) | ESI Positive.
- **Peak Detection:** Minimum peak height: 3000 amplitude; Mass slice width: 0.1 Da.
- **Smoothing:** Linear-weighted moving average (level 1, min peak width: 5 scans).
- **Identification:** Matched against **MoNA (MassBank of North America)** spectral library (`.msp`) with ID score cutoff > 80%.
- **Adducts Included:** `[M+H]+`, `[M+Na]+`, `[M+NH4]+`, `[M+K]+`, `[2M+H]+`, among others.
- **Alignment:** QC-based alignment with RT tolerance of 0.05 min and MS1 tolerance of 0.015 Da. Blank subtraction enabled.

--------------------------------------------------------------------------------------------------------------------------

# Statistical Analysis of Gene Expression Data in R

This repository contains a reproducible computational pipeline for the statistical analysis of transcriptomic and clinical datasets, developed as a technical biostatistics project for the Master's in Bioinformatics at UNIR.

The workflow focuses on a first-principles approach, rigorously evaluating empirical statistical distribution assumptions prior to test selection, and applying predictive modeling and dimensionality reduction to extract significant biological features from high-dimensional genomic data.

## 📌 Contents
- **`AnalisisgenR.html`**: The primary reference file. This is a self-contained, interactive HTML report rendered from RMarkdown (using Pandoc and jQuery). It compiles all source code, statistical outputs, and graphical visualizations of the entire pipeline.
- **`AnalisisgenR.Rmd`**: The source code containing the raw R scripts and markdown narrative.
- **`data/`**: Directory containing raw expression counts and clinical metadata.

## 🛠️ Requirements
 - Scripting and narrative via **RMarkdown** in an **RStudio** environment.
 - Dependency management via `renv` utilizing **Posit Package Manager** for stable binary packages.
 - System-level isolation using **Docker** running an **Ubuntu Linux** base image to handle system libraries and command-line toolchains.

Docker Container 

```bash
git clone https://github.com/JorgeGenn/Anlisis-estadisticos-R-en-genes.git

cd Analisis-estadisticos-R-en-genes

1. Build the Docker image:

  sudo docker build -t biostats-unir .

2. Run the container and access RStudio Server at http://localhost:8787:

   sudo docker run -d -p 8787:8787 --name analisis_genes -e PASSWORD=docker biostats-unir

   Password: docker
   name: rstudio
```
---------------------------------------------------------------------------------------------------------------------------
# 🧬 Applied Biostatistical Analysis of Gene Expression in *The Simpsons* Population


An end-to-end bioinformatics and biostatistical pipeline implemented in **R Markdown**. This study evaluates non-parametric gene expression profiles, dimensionality reduction via Principal Component Analysis (PCA), spatial clustering, Spearman correlation heatmaps, and multivariate logistic regression modeling to predict overweight/obesity risk ($N = 59$, 37 target genes).

## 📌 Contents

- **`Simulation_Simpsons.html`**: The primary reference file. This is a self-contained, interactive HTML report rendered from RMarkdown (using Pandoc and jQuery). It compiles all source code, statistical outputs, and graphical visualizations of the entire pipeline.
- **`Simulation_Simpsons.Rmd`**: The source code containing the raw R scripts and markdown narrative.
- **`data/`**: Directory containing raw expression counts and clinical metadata.

## 🛠️ Required R Packages

Ensure you have R (>= 4.0.0) installed. The script automatically verifies and installs missing dependencies upon execution:

```r
mis_paquetes <- c(
  "tidyverse", "gtsummary", "gt", "rmarkdown", "knitr", 
  "stats", "readr", "dplyr", "tidyr", "factoextra", 
  "reshape", "ggplot2", "car", "pROC", "broom", "kableExtra"
)
```
Docker Container 

   ```bash
git clone https://github.com/JorgeGenn/Simulation_Simpsons.git

cd Simulation_Simpsons

1. Build the Docker image:

 sudo docker build -t simpsons-biostats .

2. Run the container and access RStudio Server at http://localhost:8787:

sudo docker run -d -p 8787:8787 -e PASSWORD=Simulation --name simpsons simpsons-biostats

   Password: Simulation
   name: rstudio
   ```
---
###########################################################################################################################
# ¡Hola! Soy Jorge Hurtado Soriano 👋

🧬 **Bioinformático y Científico de Datos en Ciencias de la Vida**  
Licenciado en Ciencias Genómicas (UACM) | Máster en Bioinformática (UNIR) y Máster en Big Data (TECH)

📍 **Ubicación:** Ciudad de México, México  
✉️ **Contacto:** jorgehurt.sor@gmail.com  
🔗 **Enlaces:** [LinkedIn](https://linkedin.com/in/your-profile) | [ResearchGate](https://researchgate.net/profile/your-profile) | [Tesis de Licenciatura (UACM)](http://repositorioinstitucionaluacm.mx/jspui/handle/123456789/2984)

---

### 🔬 Sobre mí

- 📊 Especializado en **Análisis Exploratorio de Datos (EDA)**, **Metabolómica (UPLC-MS/MS)**, **Genómica Computacional** y **Desarrollo de Pipelines**.
- 🛠️ Experiencia en el desarrollo de flujos de trabajo analíticos reproducibles utilizando entornos **R**, **Python** y **Linux/Bash**.
- 📝 Coautor de publicaciones científicas arbitradas sobre epigenética, relojes epigenéticos y epidemiología del envejecimiento.

---

### 🛠️ Stack Tecnológico y Herramientas

- **Lenguajes y Shell:** `R`, `Python`, `Bash/Shell Scripting`
- **Análisis de Datos y Bioinformática:** `Tidyverse`, `Bioconductor`, `Procesamiento de Datos UPLC-MS/MS`, `Enriquecimiento Funcional KEGG/GO`
- **Entornos y Control de Versiones:** `Linux (Ubuntu/Debian)`, `RStudio`, `Jupyter Notebooks`, `Git/GitHub`, `Google Colab`

---

### 📚 Publicaciones Científicas Destacadas

1. **Martínez-Magaña, J. J., Hurtado-Soriano, J., et al. (2024).** *Towards a Novel Frontier in the Use of Epigenetic Clocks in Epidemiology.* Archives of Medical Research, 55(5), 103033.
2. **Martínez-Magaña, J. J., Hurtado-Soriano, J., et al. (2024).** *Potential use of epigenetic clocks to understand factors associated with aging at the population level and in public health.* Gaceta Médica de México, 160(3), 341-343.
3. **Hurtado-Soriano, J. (2024).** *Análisis metabolómico exploratorio de individuos con deterioro cognitivo de la cohorte de obesidad, sarcopenia y fragilidad.* Tesis de Licenciatura, UACM.

---

# Pipeline de Metabolómica Sérica Semi-No Dirigida mediante UPLC-TQ/MS

Este repositorio detalla el protocolo bioinformático y el pipeline analítico para el procesamiento metabolómico semi-no dirigido de muestras de suero humano adquiridas mediante UPLC-TQ-MS/MS (Waters Xevo TQ-S).

El flujo de trabajo analítico aborda el procesamiento de datos centroides MS1 de baja resolución, detección de picos, alineación de tiempos de retención, selección de aductos, corrección de efecto lote (*batch correction*) y análisis estadístico ajustado por covariables (`limma`/ANOVA) para la investigación del deterioro cognitivo.

## 📌 Contenido

- `data/`: `batch_data.csv` (datos de intensidad de metabolitos) y `metaData.csv` (metadatos de las muestras para el procesamiento por grupos).
- `docs/`: Protocolo bioinformático utilizado para el procesamiento de datos en MS-DIAL y documentación de tesis de licenciatura.

## 🛠️ Requisitos

- Parámetros de procesamiento de **MS-DIAL** (v4.92)
- **Tipo de datos:** Ionización suave (LC-MS) | Datos centroides (MS1) | ESI Positivo.
- **Detección de picos:** Altura mínima de pico: amplitud de 3000; ancho de corte de masa (*mass slice width*): 0.1 Da.
- **Suavizado (*Smoothing*):** Media móvil ponderada linealmente (nivel 1, ancho mínimo de pico: 5 escaneos).
- **Identificación:** Comparación contra la biblioteca espectral **MoNA (MassBank of North America)** (`.msp`) con puntaje de identificación (*ID score*) > 80%.
- **Aductos incluidos:** `[M+H]+`, `[M+Na]+`, `[M+NH4]+`, `[M+K]+`, `[2M+H]+`, entre otros.
- **Alineación:** Alineación basada en muestras de control de calidad (QC) con tolerancia de tiempo de retención (RT) de 0.05 min y tolerancia MS1 de 0.015 Da. Sustracción de blanco (*blank subtraction*) habilitada.

---

# Análisis Estadístico de Datos de Expresión Génica en R

Este repositorio contiene un pipeline computacional reproducible para el análisis estadístico de conjuntos de datos transcriptómicos y clínicos, desarrollado como proyecto técnico de bioestadística para el Máster en Bioinformática en la UNIR.

El flujo de trabajo se centra en un enfoque desde primeros principios, evaluando rigurosamente los supuestos de distribución estadística empírica antes de seleccionar las pruebas, y aplicando modelado predictivo y reducción de dimensionalidad para extraer características biológicas significativas a partir de datos genómicos de alta dimensionalidad.

## 📌 Contenido

- **`AnalisisgenR.html`**: El archivo de referencia principal. Es un reporte HTML autocontenido e interactivo renderizado desde RMarkdown (utilizando Pandoc y jQuery). Compila todo el código fuente, los resultados estadísticos y las visualizaciones gráficas de todo el pipeline.
- **`AnalisisgenR.Rmd`**: El código fuente que contiene los scripts puros de R y la narrativa en Markdown.
- **`data/`**: Directorio que contiene los conteos crudos de expresión y los metadatos clínicos.

## 🛠️ Requisitos

- Programación y narrativa mediante **RMarkdown** en un entorno **RStudio**.
- Gestión de dependencias mediante `renv` utilizando **Posit Package Manager** para paquetes binarios estables.
- Aislamiento a nivel de sistema utilizando **Docker** sobre una imagen base de **Ubuntu Linux** para gestionar librerías del sistema y herramientas de línea de comandos.


Docker Container

```bash
git clone https://github.com/JorgeGenn/Anlisis-estadisticos-R-en-genes.git

cd Analisis-estadisticos-R-en-genes

1. Build the Docker image:

  sudo docker build -t biostats-unir .

2. Run the container and access RStudio Server at http://localhost:8787:

   sudo docker run -d -p 8787:8787 --name analisis_genes -e PASSWORD=docker biostats-unir

   Password: docker
   name: rstudio

```
---

# 🧬 Análisis Bioestadístico Aplicado de la Expresión Génica en la Población de *Los Simpson*

Un pipeline integral de bioinformática y bioestadística implementado en **R Markdown**. Este estudio evalúa perfiles no paramétricos de expresión génica, reducción de dimensionalidad mediante Análisis de Componentes Principales (PCA), agrupamiento espacial (*clustering*), mapas de calor (*heatmaps*) de correlación de Spearman y modelado de regresión logística multivariada para predecir el riesgo de sobrepeso/obesidad ($N = 59$, 37 genes diana).

## 📌 Contenido

- **`Simulation_Simpsons.html`**: El archivo de referencia principal. Es un reporte HTML autocontenido e interactivo renderizado desde RMarkdown (utilizando Pandoc y jQuery). Compila todo el código fuente, los resultados estadísticos y las visualizaciones gráficas de todo el pipeline.
- **`Simulation_Simpsons.Rmd`**: El código fuente que contiene los scripts puros de R y la narrativa en Markdown.
- **`data/`**: Directorio que contiene los conteos crudos de expresión y los metadatos clínicos.

## 🛠️ Paquetes de R Requeridos

Asegúrate de tener R (>= 4.0.0) instalado. El script verifica e instala automáticamente las dependencias faltantes al ejecutarse:

```{r, eval=FALSE}
mis_paquetes <- c(
  "tidyverse", "gtsummary", "gt", "rmarkdown", "knitr", 
  "stats", "readr", "dplyr", "tidyr", "factoextra", 
  "reshape", "ggplot2", "car", "pROC", "broom", "kableExtra"
)
```
Docker Container 

   ```bash
git clone https://github.com/JorgeGenn/Simulation_Simpsons.git

cd Simulation_Simpsons

1. Build the Docker image:

 sudo docker build -t simpsons-biostats .

2. Run the container and access RStudio Server at http://localhost:8787:

sudo docker run -d -p 8787:8787 -e PASSWORD=Simulation --name simpsons simpsons-biostats

   Password: Simulation
   name: rstudio
   ```
