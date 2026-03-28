# RSNA 2022 Cervical Spine Fracture Detection 🦴

![Banner del Proyecto](https://github.com/anm2367l/Proyecto-IA2/blob/main/baner-ia2-2.png)

[cite_start]Este proyecto implementa un modelo de Inteligencia Artificial para la identificación de fracturas en la columna cervical a partir de escaneos de tomografía computarizada (CT)[cite: 554].

## 👤 Realizado Por:
* [cite_start]**Lewing Andrés Mendez Ortiz** - Código 2162120 [cite: 540]

## 🎯 Objetivos del Proyecto

### Objetivo Principal
[cite_start]Realizar una clasificación de las vértebras cervicales para determinar la probabilidad de fractura en cada una de ellas, utilizando un dataset masivo de tomografías de pacientes globales[cite: 555].

### Objetivos Secundarios
* [cite_start]Generar un dataset propio basado en los datos brutos[cite: 571].
* [cite_start]Diseñar un modelo de redes neuronales adaptado al problema médico[cite: 932].
* [cite_start]Clasificar las tomografías en 14 categorías (7 vértebras × 2 estados)[cite: 744].
* [cite_start]Entrenar y probar el desempeño de la red con datos desconocidos (validación externa)[cite: 1391].

## 📊 Datos y Entrenamiento
[cite_start]Los datos provienen del concurso RSNA 2022 en Kaggle[cite: 551].
* [cite_start]**Dataset Original:** 343.51 GB de información médica[cite: 557].
* **Uso de Datos:** Se utilizaron **8 GB** para entrenamiento y **2 GB** para testeo y evaluación constante.
* **Diagnóstico Final:** Se emplearon las tomografías completas de 10 pacientes distintos para generar pruebas de diagnóstico final.

## 🛠️ Tratamiento de Datos
* [cite_start]**Submuestreo:** De 2019 pacientes, se seleccionaron **655** para el desarrollo[cite: 569].
* [cite_start]**Preprocesamiento:** Conversión de archivos DICOM (`.dcm`) a imágenes `.jpg` en escala de grises[cite: 691, 724].
* [cite_start]**Normalización:** Se equilibraron las clases para tener aproximadamente **38,730 imágenes con fractura** y **38,724 sin fractura** para evitar sesgos[cite: 919, 921].

## 🏗️ Arquitectura del Modelo: CNN
[cite_start]Se utilizó una **Red Neuronal Convolucional (CNN)** secuencial con TensorFlow/Keras[cite: 932]:
* [cite_start]**Entrada:** Imágenes de $384 \times 384$ en escala de grises[cite: 849].
* [cite_start]**Capas:** Bloques de `Conv2D` (16, 32, 48, 64 filtros), `BatchNormalization`, `MaxPooling2D` y `Dropout` (0.3 - 0.5) para control de sobreajuste[cite: 932, 933].
* [cite_start]**Optimización:** Adadelta con una tasa de aprendizaje de 0.01[cite: 935].

## 📈 Resultados y Conclusiones
* [cite_start]**Entrenamiento:** El proceso total tomó alrededor de **24 horas**[cite: 1446].
* [cite_start]**Accuracy:** Se logró un accuracy de validación final de **0.7341** tras múltiples etapas de entrenamiento[cite: 1395].
* [cite_start]**Hallazgos:** El modelo es altamente eficiente identificando vértebras **sin fractura**[cite: 1457]. [cite_start]Se identificó la necesidad de mayores recursos de hardware, ya que el proceso consumió el **93% de la RAM** disponible[cite: 1408, 1458].

## 🔗 Enlaces del Proyecto
* **Video de Presentación:** [Ver en YouTube](https://youtu.be/VsstbbjJ-n0)
* **Repositorio GitHub:** [Proyecto-IA2](https://github.com/anm2367l/Proyecto-IA2.git)
* [cite_start]**Dataset Original:** [Kaggle RSNA 2022](https://www.kaggle.com/datasets/jirkaborovec/cervical-spine-fracture-detection-npz-3d-volumes) [cite: 566]


