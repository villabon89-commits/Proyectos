# Análisis de Comportamiento de Clientes - ConnectaTel

## 📄 Descripción del Proyecto

Este proyecto tiene como objetivo principal evaluar el **comportamiento de los clientes** de ConnectaTel, una empresa de telecomunicaciones en Latinoamérica. Como analista de datos, se trabajó con información registrada hasta el año 2024 para identificar patrones de consumo, detectar comportamientos atípicos y crear segmentos de clientes. El análisis busca proporcionar insights que permitan diseñar estrategias de retención y sugerir mejoras en los planes de servicio ofrecidos por la empresa.

## 📊 Datasets Utilizados

Se utilizaron tres datasets principales, alojados en `/datasets/`:

1.  **`plans.csv`**: Contiene información sobre los planes actuales de ConnectaTel, incluyendo precio, minutos incluidos, GB incluidos y costo por extras.
2.  **`users_latam.csv`**: Almacena datos de los clientes, como edad, ciudad, fecha de registro, plan contratado y estado de churn.
3.  **`usage.csv`**: Detalla el uso real de los servicios, como la duración de las llamadas y la cantidad de mensajes.

## 📈 Etapas del Análisis

El análisis se estructuró en las siguientes etapas:

1.  **Carga y Exploración de Datos**: Familiarización con la estructura de los datasets, carga en memoria y revisión preliminar con `.head()` y `.info()`.
2.  **Identificación de Problemas de Calidad de Datos**: Revisión de valores nulos, detección de valores inválidos (sentinels) y estandarización de formatos de fecha.
3.  **Limpieza Básica de Datos**: Corrección de sentinels en `age` y `city`, así como manejo de fechas imposibles en `reg_date`. Se verificó el tipo de valores nulos (MAR) en `duration` y `length` para decidir su tratamiento.
4.  **Summary Statistics de Uso por Usuario**: Creación de una tabla agregada (`user_profile`) que resume el número total de mensajes, llamadas y minutos de llamadas por cada `user_id`. Esta tabla se combinó con el dataset de usuarios.
5.  **Visualización de Distribuciones y Outliers**: Uso de histogramas para visualizar la distribución de `age`, `cant_mensajes`, `cant_llamadas` y `cant_minutos_llamada` según el tipo de plan. Se emplearon boxplots para identificar outliers y se calculó el rango intercuartílico (IQR) para evaluar su magnitud.
6.  **Segmentación de Clientes**: Creación de nuevas columnas (`grupo_uso` y `grupo_edad`) para segmentar a los clientes basándose en su comportamiento de uso y rangos de edad. Se visualizó la distribución de estos segmentos.
7.  **Insight Ejecutivo para Stakeholders**: Resumen de los hallazgos clave, incluyendo problemas de datos, identificación de segmentos valiosos, implicaciones de los outliers y recomendaciones estratégicas para mejorar la oferta de planes y la gestión de clientes.

## 🚀 Cómo Ejecutar el Notebook

Este notebook fue desarrollado en Google Colab, lo que facilita su ejecución y reproducción.

1.  **Abrir en Google Colab**: Haz clic en el siguiente badge para abrir el notebook directamente en Google Colab:
    [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/TU_REPO_DE_GITHUB/ConnectaTel_Analysis/blob/main/ConnectaTel_Analysis.ipynb) <!-- Reemplaza TU_REPO_DE_GITHUB/ConnectaTel_Analysis/blob/main/ConnectaTel_Analysis.ipynb con la ruta real a tu notebook en GitHub -->
2.  **Montar Google Drive**: Al inicio del notebook, se te pedirá montar tu Google Drive. Esto es necesario para acceder a los archivos CSV que se asumen estar en la ruta `/content/drive/MyDrive/Colab Notebooks/Proyecto S7/`.
3.  **Ejecutar Celdas**: Simplemente puedes ejecutar todas las celdas en orden (`Runtime > Run all`) o ir ejecutándolas una por una para seguir el flujo del análisis.

## ♻️ Guía de Reproducción

Para reproducir este análisis, sigue estos pasos:

1.  **Clonar el Repositorio**:
    ```bash
    git clone https://github.com/TU_USUARIO/TU_REPOSITORIO.git
    cd TU_REPOSITORIO
    ```
    (Asegúrate de reemplazar `TU_USUARIO` y `TU_REPOSITORIO` con tu información de GitHub).
2.  **Preparar los Datos**: Asegúrate de que los archivos `plans.csv`, `users_latam.csv` y `usage.csv` estén ubicados en la ruta esperada dentro de tu Google Drive, específicamente en `MyDrive/Colab Notebooks/Proyecto S7/`. Si los archivos están en una ubicación diferente, deberás actualizar las rutas en las celdas de carga de datos.
3.  **Abrir en Colab y Ejecutar**: Sigue las instrucciones de "Cómo Ejecutar el Notebook" para abrir y ejecutar el análisis en Google Colab.
