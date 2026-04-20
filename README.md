# telecom-analysis
Este repositorio contiene el análisis de comportamiento de clientes de ConnectaTel, una empresa de telecomunicaciones en Latinoamérica, desarrollado durante el Sprint 7.

El objetivo es evaluar el uso de los servicios (llamadas, mensajes, consumo de datos), limpiar y explorar los datos, segmentar clientes y generar recomendaciones estratégicas basadas en patrones de consumo y calidad de datos.

📂 Contenido del repositorio
notebooks/S7_Version-Estudiante-Project-ConnectaTel.ipynb
→ Notebook principal con carga de datos, limpieza, análisis exploratorio, visualizaciones, detección de outliers, segmentación y conclusiones ejecutivas.

▶ Cómo abrir el notebook en Google Colab
Haz clic en el siguiente botón:

[https://colab.research.google.com/assets/colab-badge.svg
](https://colab.research.google.com/drive/1utXs5ttb9PMrebnf6RpM2edO-lVLbJAH?usp=sharing)

O:

Abre el archivo .ipynb en GitHub

Haz clic en Open in Colab

📘 Cómo reproducir el análisis
Abre notebooks/S7_Version-Estudiante-Project-ConnectaTel.ipynb en Colab o Jupyter

Ejecuta las celdas en orden

El notebook carga automáticamente los datasets desde la ruta /datasets/ (asume que los archivos están disponibles en el entorno de ejecución)

🧠 Objetivo del análisis
Identificar y corregir problemas de calidad de datos (valores nulos, sentinels, fechas inválidas)

Construir un perfil estadístico de los clientes (edad, plan, uso de mensajes, llamadas, minutos)

Detectar outliers y comportamientos extremos

Segmentar clientes por nivel de uso y por edad

Generar insights accionables para mejorar planes y estrategias de retención

📊 Datasets utilizados
plans.csv → Información de los planes (precio, minutos incluidos, GB incluidos, costo por extra)

users_latam.csv → Datos demográficos y de contratación de clientes (edad, ciudad, fecha de registro, plan, churn)

usage.csv → Registro detallado de uso real (llamadas y mensajes)

🔍 Resumen de pasos del análisis
Carga y exploración – shape, tipos de datos, primeras filas.

Identificación de problemas – valores nulos, sentinels (edad = -999, city = "?"), fechas futuras.

Limpieza – imputación de edad con mediana, reemplazo de "?" por NA, corrección de fechas fuera de rango.

Agregación de uso – total de mensajes, llamadas y minutos por usuario.

Estadísticas y visualizaciones – histogramas por plan, boxplots, detección de outliers mediante IQR.

Segmentación – grupos por uso (bajo, medio, alto) y por edad (joven, adulto, adulto mayor).

Insights ejecutivos – recomendaciones de negocio basadas en los hallazgos.

💡 Principales hallazgos y recomendaciones
Los datos presentaban valores inválidos en ciudad (≈11.7% nulos) y fechas futuras (año 2026). Se corrigieron adecuadamente.

Las columnas duration y length tenían muchos nulos pero por diseño (dependen del tipo de registro: llamada o mensaje), por lo que se mantuvieron como nulos.

Los clientes de mayor edad (60+) tienden a contratar más el plan Básico.

Los segmentos de alto uso (tanto en mensajes como en minutos) representan una oportunidad para migrar a planes Premium o crear nuevos planes escalonados.

Se detectaron outliers en cant_minutos_llamada (2.7% de los registros), que podrían corresponder a clientes de alto valor o uso inusual.

Recomendaciones:

Diseñar planes personalizados por rango de edad y nivel de uso.

Ofrecer incentivos para migrar de Básico a Premium a usuarios con alto consumo de minutos.

Monitorear a los clientes con consumo extremo para evitar abandono y mejorar la experiencia.

🔗 Enlace al repositorio público
https://github.com/tuusuario/connectatel-analysis
