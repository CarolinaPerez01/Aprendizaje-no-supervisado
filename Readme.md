# 🧠 Aprendizaje No Supervisado: Análisis de Clientes Mayoristas

**Realizado por:** Carolina Pérez Molina

## 📌 1. ¿Qué es el Aprendizaje No Supervisado?

El **aprendizaje no supervisado** es una rama del *machine learning* en la que los algoritmos exploran datos sin etiquetas, es decir, sin una variable objetivo conocida. El propósito principal es **descubrir patrones, estructuras o relaciones ocultas** dentro de los datos.  
A diferencia del aprendizaje supervisado, no se entrena al modelo con ejemplos con respuestas correctas, sino que se deja que el algoritmo encuentre similitudes, agrupamientos o representaciones compactas de los datos por sí mismo.

Entre las técnicas más comunes de aprendizaje no supervisado están:

- **Clustering (agrupamiento)**: agrupación de observaciones similares (ej. K-means).
- **Reducción de dimensionalidad**: representar datos complejos en espacios más simples (ej. PCA).
- **Análisis de asociaciones**: descubrir reglas y relaciones frecuentes (ej. en cestas de mercado).


## 📌 2. Descripción del Dataset

Se utilizó el dataset **Wholesale Customers Data**, que contiene información sobre los gastos anuales de diferentes clientes mayoristas en varios productos. Las variables incluidas son:

- **Fresh**: productos frescos  
- **Milk**: productos lácteos  
- **Grocery**: comestibles  
- **Frozen**: productos congelados  
- **Detergents_Paper**: detergentes y papel  
- **Delicassen**: productos delicatessen  
- **Channel**: canal de venta (1 = Horeca, 2 = Retail)  
- **Region**: región geográfica (1 = Lisboa, 2 = Oporto, 3 = Otra)

El objetivo del análisis no supervisado es **descubrir patrones de consumo** y segmentar a los clientes en grupos con características similares.


## 📌 3. Paso a Paso del Análisis

### 🔍 a. Carga y Exploración Inicial

- Se cargó el dataset y se revisaron estadísticas descriptivas.
- Se detectaron algunas correlaciones fuertes entre variables (ej. Grocery y Detergents_Paper).

### ⚖️ b. Preprocesamiento

- Se estandarizaron los datos con `StandardScaler` para igualar la escala de todas las variables.
- Se realizó un análisis de correlación para evaluar redundancias.

### 🧭 c. Reducción de Dimensionalidad con PCA

- Se aplicó **Análisis de Componentes Principales (PCA)** para reducir las dimensiones del conjunto de datos a solo dos componentes principales.
- Esto permitió visualizar mejor la distribución de los datos y su posible agrupamiento.

### 📊 d. Agrupamiento con K-Means

- Se aplicó el algoritmo **K-Means** con distintos valores de k (número de clusters).
- Se usó el **método del codo** y el **coeficiente de silueta** para determinar el número óptimo de clusters.
- Se repitió el análisis en tres versiones del dataset:
  1. Conjunto completo
  2. Conjunto reducido con PCA
  3. Conjunto tras eliminar variables redundantes por alta correlación

### 🔎 e. Interpretación de Resultados

- Se analizaron las características medias de cada cluster.
- Se compararon los clusters con las variables originales para entender sus perfiles de consumo.


## 📌 4. Conclusiones

- El análisis permitió **segmentar a los clientes** en grupos claramente diferenciados por sus patrones de consumo.
- La reducción de dimensionalidad con PCA fue útil para visualizar la estructura interna de los datos sin perder demasiada información.
- La eliminación de variables redundantes mejoró la simplicidad del modelo sin afectar significativamente la calidad del agrupamiento.
- Se observó que algunas variables (como *Grocery* y *Detergents_Paper*) aportaban información muy similar, lo cual puede ser útil en futuros análisis para reducir complejidad.
- El modelo puede servir como base para estrategias de marketing más personalizadas, asignación de recursos, o diseño de promociones específicas para cada tipo de cliente.
