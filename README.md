# Análisis ConnectaTel

## Objetivo del proyecto
Analizar los usuarios de ConnectaTel, una empresa de telecomunicaciones en Latinoamérica, para limpiar los datos, entender sus patrones de uso, detectar valores atípicos y segmentar a los clientes por edad y nivel de uso. A partir de los hallazgos se proponen recomendaciones comerciales para mejorar la oferta de planes.

## Datasets utilizados
- `plans.csv`: información de los planes (Básico y Premium).
- `users_latam.csv`: datos de los usuarios (edad, ciudad, fecha de registro, plan y fecha de abandono).
- `usage.csv`: registros de uso (llamadas y mensajes, con su duración o longitud).

## Etapas del análisis
1. **Carga y exploración inicial:** lectura de los tres datasets, revisión de dimensiones y tipos de datos.
2. **Diagnóstico de calidad:** detección de nulos, valores centinela (-999 y "?") y fechas fuera de rango.
3. **Limpieza:** reemplazo de la edad -999 por la mediana, conversión de "?" y fechas inválidas a valores nulos.
4. **Construcción del perfil de usuario:** agregación del uso por usuario y unión con los datos de usuarios.
5. **Análisis de distribuciones:** histogramas de edad, mensajes, llamadas y minutos de llamada, separados por plan.
6. **Valores atípicos:** boxplots y método IQR; los outliers se conservaron por corresponder a uso intensivo real.
7. **Segmentación:** grupos por nivel de uso (Bajo, Medio y Alto) y por edad (Joven, Adulto y Adulto Mayor).
8. **Informe ejecutivo:** conclusiones y recomendaciones para el negocio.

## Cómo ejecutar el notebook
1. Abre el archivo `.ipynb` de este repositorio en Google Colab (o en Jupyter Notebook).
2. Sube los tres archivos CSV al mismo entorno. En la plataforma original se leían desde la ruta `/datasets/`; si los subes a otra ubicación, ajusta esa ruta en las celdas de `pd.read_csv`.
3. Ejecuta todas las celdas en orden, de arriba hacia abajo (en Colab: Runtime → Run all).

## Guía de reproducción
- Librerías necesarias: `pandas`, `numpy`, `matplotlib` y `seaborn`.
- Las celdas dependen del orden: si reinicias el entorno, vuelve a ejecutar desde la primera celda.
- El resultado final es el informe ejecutivo, al final del notebook.
