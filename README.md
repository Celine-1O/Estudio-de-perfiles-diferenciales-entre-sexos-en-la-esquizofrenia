# Estudio-de-perfiles-diferenciales-entre-sexos-en-la-esquizofrenia

El uso de single-cell RNA sequencing (scRNA-seq) se ha extendido ampliamente en los últimos años gracias a su capacidad para analizar la heterogeneidad celular con gran precisión, lo que lo convierte en una herramienta clave para el estudio de enfermedades complejas como la esquizofrenia.

Seurat es uno de los paquetes más utilizados en R para el análisis de datos de scRNA-seq. En este repositorio se presenta una guía introductoria para el uso de Seurat (Seurat-guide.qmd), basada en la documentación oficial, junto con ejemplos prácticos de su aplicación.

Para los análisis introductorios se emplean datos públicos que pueden descargarse desde 10x Genomics:
https://cf.10xgenomics.com/samples/cell/pbmc3k/pbmc3k_filtered_gene_bc_matrices.tar.gz

Además, el repositorio incluye un informe de análisis que aplica Seurat a un database de humanos con y sin esquizofrenia (Diferencias-de-sexo-en-la-esquizofrenia.pdf) y aborda la reproducibilidad del estudio:

Single-Cell Transcriptional Profiling Reveals Cell Type-Specific Sex-Dependent Molecular Patterns of Schizophrenia

Zhou, R., Zhang, T., & Sun, B. (2025). International Journal of Molecular Sciences, 26(5), 2227. https://doi.org/10.3390/ijms26052227. 

- Dichos archivos pueden obtenerse desde:
https://brainscope.gersteinlab.org/data/snrna_expr_matrices_zip/SZBDMulti-Seq.zip

- PEC2_sample_metadata.txt contiene los datos relativos a las matrices descargadas.


## Paquetes R

El análisis se ha realizado utilizando **R** y las siguientes librerías:

| Categoría | Librería | Descripción | Fuente |
| :--- | :--- | :--- | :---: |
| **Single-Cell Core** | `Seurat` | Flujo de trabajo principal para análisis, filtrado y clustering de scRNA-seq. | CRAN |
| | `harmony` | Integración de datos y corrección de efecto de lote (Batch effect). | CRAN |
| **Visualización** | `ggplot2` | Motor base para la generación de gráficos. | CRAN |
| | `patchwork` | Combinación y composición de múltiples gráficos. | CRAN |
| | `EnhancedVolcano`| Visualización de expresión diferencial (Volcano plots). | Bioc |
| | `ComplexHeatmap` | Mapas de calor complejos y anotados. | Bioc |
| | `ComplexUpset` | Visualización de intersecciones de conjuntos (alternativa a Venn). | CRAN |
| | `circlize` | Gráficos circulares (dependencia visual). | CRAN |
| **Análisis Funcional** | `clusterProfiler` | Análisis de enriquecimiento (GSEA, ORA) y visualización. | Bioc |
| | `org.Hs.eg.db` | Anotación del genoma humano (Entrez IDs, Símbolos). | Bioc |
| | `GSEAmining` | Agrupación e interpretación de términos de GSEA. | Bioc |
| **Manipulación de Datos**| `dplyr` / `tidyr` | Manipulación, filtrado y limpieza de datos (Tidyverse). | CRAN |
| | `purrr` | Programación funcional y manejo de listas. | CRAN |
| | `tidytext` | Minería de texto (procesamiento de términos biológicos). | CRAN |
| **Utilidades** | `qs2` | Lectura y escritura ultrarrápida de objetos R (serialización). | CRAN |
| | `R.utils` | Utilidades varias para manejo de archivos. | CRAN |

