# Análisis de Datos para Zuber - Empresa de Viajes Compartidos

## 📋 Descripción del Proyecto

Este proyecto fue desarrollado como parte del análisis de datos para **Zuber**, una nueva empresa de viajes compartidos que se está lanzando en Chicago. El objetivo principal es identificar patrones en los datos de viajes en taxi, comprender las preferencias de los pasajeros y evaluar el impacto de factores externos (como el clima) en la frecuencia y duración de los viajes.

## 🎯 Objetivos

- Analizar patrones de uso de taxis en Chicago
- Comprender las preferencias de los pasajeros
- Evaluar el impacto del clima en los viajes
- Probar hipótesis sobre la duración de viajes en condiciones climáticas específicas

## 🔧 Metodología

### Paso 1: Análisis de Datos Climáticos
- Extracción y análisis de datos meteorológicos de Chicago (noviembre 2017)
- Fuente: [Chicago Weather Data](https://practicum-content.s3.us-west-1.amazonaws.com/data-analyst-eng/moved_chicago_weather_2017.html)

### Paso 2: Análisis Exploratorio de Datos (SQL)
- **Análisis por empresa**: Número de viajes por empresa de taxis (15-16 noviembre 2017)
- **Filtrado por nombre**: Viajes de empresas con "Yellow" o "Blue" (1-7 noviembre 2017)
- **Análisis de popularidad**: Comparación entre Flash Cab, Taxi Affiliation Services y otras empresas

### Paso 3: Prueba de Hipótesis (SQL)
- Identificación de barrios Loop y O'Hare
- Clasificación de condiciones climáticas ("Bad" vs "Good")
- Análisis de viajes Loop → O'Hare en sábados

### Paso 4: Análisis Exploratorio (Python)
- Procesamiento de archivos CSV generados
- Visualización de datos de empresas de taxis
- Análisis de los top 10 barrios por finalizaciones
- Generación de gráficos y conclusiones

### Paso 5: Prueba de Hipótesis (Python)
**Hipótesis**: "La duración promedio de los viajes desde el Loop hasta el Aeropuerto Internacional O'Hare cambia los sábados lluviosos"

## 🛠️ Tecnologías Utilizadas

- **SQL**: Para consultas y análisis de base de datos
- **Python**: Para análisis estadístico y visualización
- **Pandas**: Manipulación de datos
- **Matplotlib/Seaborn**: Visualización de datos
- **SciPy/Stats**: Pruebas estadísticas

## 📈 Resultados Principales

### Análisis de Empresas
- Identificación de las empresas de taxis más activas
- Comparación de volumen de viajes entre diferentes operadores
- Agrupación de empresas menores en categoría "Other"

### Análisis de Barrios
- Top 10 barrios por número de finalizaciones de viajes
- Patrones geográficos de demanda de transporte

### Impacto Climático
- Clasificación de condiciones climáticas en "Good" y "Bad"
- Análisis de duración de viajes bajo diferentes condiciones meteorológicas
- Prueba estadística de la hipótesis planteada

## 🔍 Conclusiones

El objetivo es evaluar si el clima lluvioso tiene un impacto significativo en la duración promedio de los viajes en taxi desde el barrio Loop hasta el Aeropuerto Internacional O’Hare, exclusivamente los sábados.

Se trabajó con dos grupos de datos:
Viajes realizados en sábados con condiciones climáticas etiquetadas como "Bad" (lluvia o tormenta).
Viajes realizados en sábados con condiciones "Good" (sin lluvia ni tormenta).

Para comparar las medias de dos grupos independientes (viajes en clima lluvioso vs. buen clima), se utilizó una prueba t de Student para muestras independientes, específicamente la versión de Welch (ttest_ind con equal_var=False), porque:

Los tamaños de muestra pueden ser distintos.
Las varianzas entre los grupos podrían no ser iguales.
Ambas muestras son independientes y cuantitativas (duración en segundos).

Según el resultado del análisis (que depende del valor p calculado), se puede concluir si el clima lluvioso afecta o no significativamente la duración de los viajes en sábado desde el Loop hasta O'Hare.

## 🚀 Cómo Ejecutar el Proyecto

1. **Requisitos previos**:
   ```bash
   pip install pandas matplotlib seaborn scipy numpy
   ```

2. **Ejecución**:
   - Ejecutar las consultas SQL para generar los archivos CSV
   - Ejecutar los notebooks de Python para análisis y visualización
