# RSNA 2022 Cervical Spine Fracture Detection 🦴

![Banner del Proyecto](https://github.com/anm2367l/Proyecto-IA2/blob/main/baner-ia2-2.png)

[cite_start]Este proyecto implementa un modelo de Inteligencia Artificial para la identificación de fracturas en la columna cervical a partir de escaneos de tomografía computarizada (CT)[cite: 554].

## 👤 Realizado Por:
* [cite_start]**Lewing Andrés Mendez Ortiz** - Código 2162120 [cite: 540]
* [cite_start]**Diego Andrés Lozada Niño** - Código 2170078 [cite: 540]

## 🎯 Objetivos del Proyecto

### Objetivo Principal
[cite_start]Realizar una clasificación de las vértebras cervicales para determinar la probabilidad de fractura en cada una de ellas, utilizando un dataset masivo de tomografías de pacientes globales[cite: 554].

### Objetivos Secundarios
* [cite_start]Generar un dataset basado en los datos originales[cite: 571, 744].
* [cite_start]Diseñar un modelo de redes neuronales convolucionales (CNN) que se adapte al problema[cite: 932].
* [cite_start]Clasificar las tomografías en 14 carpetas categorizadas (7 vértebras × 2 estados)[cite: 744].
* [cite_start]Entrenar la red neuronal con los datos categorizados[cite: 934].
* [cite_start]Probar el desempeño de la red con datos completamente desconocidos para el modelo[cite: 1391].

## 📊 Datos y Entrenamiento
[cite_start]Los datos fueron obtenidos de un concurso de la Radiological Society of North America (RSNA) en Kaggle[cite: 555].
* [cite_start]**Dataset Original:** 343.51 GB de información médica[cite: 557].
* **Uso de Datos:** Se utilizaron **8 GB** para entrenamiento y **2 GB** para testeo y evaluación constante. Además, se emplearon las tomografías de 10 pacientes para generar diagnósticos de prueba.
* [cite_start]**Selección de Pacientes:** De los 2019 pacientes disponibles, se seleccionaron **655** para el desarrollo del proyecto[cite: 569].

## 🛠️ Tratamiento de Datos
* [cite_start]**División por vértebras:** Las tomografías se dividieron en 7 secciones (C1 a C7) basándose en que se posee la tomografía completa de la espina cervical[cite: 571, 572].
* [cite_start]**Conversión de formato:** Los archivos DICOM (`.dcm`) se transformaron en imágenes `.jpg` escaladas a 255.0 (blanco y negro)[cite: 691, 724].
* [cite_start]**Normalización:** Para evitar sesgos, se equilibraron las clases resultando en aproximadamente **38,730 imágenes con fractura** y **38,724 sin fractura**[cite: 783, 844].

## 🏗️ Arquitectura del Modelo: CNN
[cite_start]Se diseñó una **Red Neuronal Convolucional (CNN)** secuencial con la siguiente configuración[cite: 932]:
* [cite_start]**Entrada:** Imágenes reescaladas a $384 \times 384$ en escala de grises[cite: 849, 865].
* [cite_start]**Capas:** Cuatro bloques de `Conv2D` con filtros crecientes (16, 32, 48, 64), acompañados de `BatchNormalization`, `MaxPooling2D` y capas de `Dropout` (0.3 a 0.5) para mitigar el sobreajuste[cite: 932, 933].
* [cite_start]**Optimización:** El mejor optimizador identificado de manera empírica fue **Adadelta** (learning rate = 0.01)[cite: 935, 938].

## 📈 Resultados y Conclusiones
* [cite_start]**Entrenamiento:** El proceso total tomó aproximadamente **24 horas** de ejecución[cite: 1446].
* [cite_start]**Desempeño:** Se alcanzó un accuracy de validación final de **0.7341**[cite: 1395, 1396].
* [cite_start]**Conclusiones:** * Se detectó **overfitting** en el proceso[cite: 1455].
    * [cite_start]El modelo aprendió con gran éxito a identificar **vértebras sin fractura**[cite: 1457].
    * [cite_start]El procesamiento consumió casi la totalidad de la memoria RAM (93%), evidenciando la importancia de recursos físicos robustos[cite: 1408, 1458].

## 🔗 Enlaces del Proyecto
* **Video de Presentación:** [Ver en YouTube](https://youtu.be/VsstbbjJ-n0)
* **Repositorio GitHub:** [Proyecto-IA2](https://github.com/anm2367l/Proyecto-IA2.git)
* [cite_start]**Dataset de Referencia:** [Kaggle RSNA 2022](https://www.kaggle.com/datasets/jirkaborovec/cervical-spine-fracture-detection-npz-3d-volumes) [cite: 566]
