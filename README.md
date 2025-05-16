# Análisis y Procesamiento de Datos Bancarios

Este proyecto contiene una serie de notebooks para el procesamiento, análisis y modelado de datos bancarios. El flujo de trabajo incluye la traducción de datos, la generación de variables objetivo (aprobación de créditos) y el análisis utilizando técnicas de machine learning.

## Contenido

El proyecto está compuesto por tres notebooks principales:

1. **taller4-traducir.ipynb**: Traduce los datos de portugués a inglés utilizando la API de DeepL.
2. **taller4-hallarY.ipynb**: Genera la variable objetivo (Approved) usando un sistema de puntuación basado en múltiples características.
3. **taller4-analisis.ipynb**: Analiza los datos y entrena modelos de machine learning (Random Forest) para predecir aprobaciones.

## Requisitos

- Python 3.13 o superior
- Dependencias detalladas en `requirements.txt`
- Clave de API para DeepL (para el notebook de traducción)

## Configuración del Entorno

### Configuración del entorno virtual

```bash
# Crear entorno virtual
python -m venv venv

# Activar entorno virtual
# En Windows:
venv\Scripts\activate
# En macOS/Linux:
source venv/bin/activate

# Instalar dependencias
pip install -r requirements.txt
```

### Configuración de la API de DeepL (para taller4-traducir.ipynb)

1. Obtén una clave de API desde [DeepL API](https://www.deepl.com/pro-api)
2. Crea un archivo `.env` en el directorio raíz con el siguiente contenido:
   ```
   DEEPL_AUTH_KEY=tu_clave_de_api_aquí
   ```
3. Instala python-dotenv y carga las variables de entorno al principio del notebook:
   ```python
   import os
   from dotenv import load_dotenv
   load_dotenv()
   ```

## Flujo de Ejecución

1. Ejecuta primero `taller4-traducir.ipynb` para traducir los datos originales
2. Luego ejecuta `taller4-hallarY.ipynb` para generar la variable objetivo
3. Finalmente, ejecuta `taller4-analisis.ipynb` para analizar y modelar los datos

## Resultados

El modelo Random Forest entrenado alcanza una alta precisión en la predicción de aprobaciones de crédito. Los modelos entrenados se guardan como archivos `.pkl` para su posterior uso en producción.

## Notas

- El notebook de análisis incluye visualizaciones de árboles de decisión y matrices de correlación para entender los factores que influyen en las aprobaciones.
- Los datos procesados se guardan como archivos CSV intermedios entre cada etapa del flujo de trabajo.
