## Análisis de Texto y Modelado de Tópicos

Este repositorio está dedicado a la **Tarea 2 de NLP**, en la que se compara:

1. Un modelo **LDA** mejorado con **bigramas** para la extracción de tópicos.  
2. Un método de **clustering** clásico (**KMeans**) aplicado a la misma representación DTM (unigramas + bigramas).

Se incluyen siguientes pasos:
- Carga y pre-procesamiento del subset de “El Chile que Queremos”  
- Generación de bigramas con Gensim  
- Diagnóstico y selección del número óptimo de temas (`Coherence C_V`)  
- Entrenamiento y etiquetado de tópicos LDA  
- Construcción de la matriz DTM con `CountVectorizer`  
- Diagnóstico del número óptimo de clusters (`Silhouette score`) y entrenamiento de KMeans  
- Comparación de particiones (tablas de contingencia, heatmap)  
- Conclusiones y recomendaciones finales

---

### 📁 Estructura del Repositorio

```
tarea2-NLP/
│
├── data/
│ ├── raw/ # Datos originales (CSV)
│ │ └── ecqq.csv
│ └── processed/ # Datos intermedios y limpios
│   └── ecqq_limpio.csv
│
├── output/
│ ├── figures/ # Gráficos generados
│
└── README.md # Documentación principal
```


###  Instalación y Entorno

Se reomienda utilizar **Anaconda** para evitar conflictos de dependencias:

1. **Clonar el Repositorio**
   ```bash
    git clone https://github.com/Vikktor93/tarea2-NLP
    cd tarea2-NLP
2. **Crear entorno**  
   ```bash
   conda create -n nlp python=3.11.13 -c conda-forge -y
   conda activate nlp
3. **Instalar Dependencias**  
   ```bash
    conda install -c conda-forge pandas numpy matplotlib seaborn scikit-learn gensim nltk spacy -y
4. **Descargar Recursos**  
   ```bash
    import nltk; nltk.download('stopwords')