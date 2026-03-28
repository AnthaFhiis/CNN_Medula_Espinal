# RSNA 2022 Cervical Spine Fracture Detection 🦴

![Banner del Proyecto](https://github.com/anm2367l/Proyecto-IA2/blob/main/baner-ia2-2.png)

Este proyecto implementa un modelo de Inteligencia Artificial para la identificación de fracturas en la columna cervical a partir de escaneos de tomografía computarizada (CT).

## 👤 Realizado Por:
* **Lewing Andrés Mendez Ortiz** - Código 2162120

## 🎯 Objetivos del Proyecto

### Objetivo Principal
Realizar una clasificación de las vértebras cervicales para determinar la probabilidad de fractura en cada una de ellas, utilizando un dataset masivo de tomografías de pacientes globales.

### Objetivos Secundarios
* Generar un dataset basado en los datos originales.
* Diseñar un modelo de redes neuronas convolucionales (CNN) que se adapte al problema.
* Clasificar las tomografías en 14 carpetas categorizadas (7 vértebras × 2 estados).
* Entrenar la red neuronal con los datos categorizados.
* Probar el desempeño de la red con datos completamente desconocidos para el modelo.

## 📊 Datos y Entrenamiento
Los datos fueron obtenidos de un concurso de la Radiological Society of North America (RSNA) en Kaggle.
* **Dataset Original:** 343.51 GB de información médica.
* **Uso de Datos:** Se utilizaron **8 GB** para entrenamiento y **2 GB** para testeo y evaluación constante. Además, se emplearon las tomografías de 10 pacientes para generar diagnósticos de prueba.
* **Selección de Pacientes:** De los 2019 pacientes disponibles, se seleccionaron **655** para el desarrollo del proyecto.

## 🛠️ Tratamiento de Datos
* **División por vértebras:** Las tomografías se dividieron en 7 secciones (C1 a C7) basándose en que se posee la tomografía completa de la espina cervical.
* **Conversión de formato:** Los archivos DICOM (`.dcm`) se transformaron en imágenes `.jpg` escaladas a 255.0 (blanco y negro).
* **Normalización:** Para evitar sesgos, se equilibraron las clases resultando en aproximadamente **38,730 imágenes con fractura** y **38,724 sin fractura**.

## 🏗️ Arquitectura del Modelo: CNN
Se diseñó una **Red Neuronal Convolucional (CNN)** secuencial con la siguiente configuración:
* **Entrada:** Imágenes reescaladas a 384 x 384 en escala de grises.
* **Capas:** Cuatro bloques de `Conv2D` con filtros crecientes (16, 32, 48, 64), acompañados de `BatchNormalization`, `MaxPooling2D` y capas de `Dropout` (0.3 a 0.5) para mitigar el sobreajuste.
* **Optimización:** El mejor optimizador identificado de manera empírica fue **Adadelta** (learning rate = 0.01).

## 📈 Resultados y Conclusiones
* **Entrenamiento:** El proceso total tomó aproximadamente **24 horas** de ejecución.
* **Desempeño:** Se alcanzó un accuracy de validación final de **0.7341**.
* **Conclusiones:** * Se detectó **overfitting** en el proceso.
    * El modelo aprendió con gran éxito a identificar **vértebras sin fractura**.
    * El procesamiento consumió casi la totalidad de la memoria RAM (93%), evidenciando la importancia de recursos físicos robustos.

## 🔗 Enlaces del Proyecto
* **Video de Presentación:** [Ver en YouTube](https://youtu.be/VsstbbjJ-n0)
* **Repositorio GitHub:** [Proyecto-IA2](https://github.com/anm2367l/Proyecto-IA2.git)
* **Dataset de Referencia:** [Kaggle RSNA 2022](https://www.kaggle.com/datasets/jirkaborovec/cervical-spine-fracture-detection-npz-3d-volumes)
