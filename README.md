# Vision por Computador - Clasificacion y deteccion en xView

Repositorio de la practica de Vision por Computador, centrada en el uso de modelos de Deep Learning sobre imagenes aereas del dataset xView.

El trabajo se divide en dos partes:

- **Clasificacion de imagenes**: cada imagen contiene un unico objeto y el objetivo es asignarle una de las clases disponibles.
- **Deteccion de objetos**: cada imagen puede contener varios objetos y el objetivo es localizar cada instancia mediante cajas delimitadoras.

La explicacion completa de los experimentos, resultados y conclusiones se encuentra en la memoria del trabajo. Este README solo resume la organizacion del repositorio.

## Estructura del repositorio

```text
.
+-- notebooks_clasificacion/
|   +-- Zips_Codabench/
|   +-- 00_estudio_datos.ipynb
|   +-- 00_1_crear_arrayspreprocesados.ipynb
|   +-- 01_... / 05_...  modelos FFNN
|   +-- 06_... / 08_...  modelos CNN propios
|   +-- 09_... / 10_...  arquitecturas entrenadas desde cero
|   +-- 11_... / 18_...  transfer learning y modelos finales
|
+-- notebooks_detection/
    +-- YOLO/
    |   +-- notebooks con pruebas de YOLOv8, YOLO11 y variantes
    +-- FasterRCNN/
        +-- notebooks con pruebas de Faster R-CNN y mejoras
```

## Parte de clasificacion

En la carpeta `notebooks_clasificacion` se recogen los experimentos de reconocimiento de imagenes. El desarrollo sigue una evolucion progresiva:

1. Analisis inicial del dataset y distribucion de clases.
2. Modelos `FFNN` sencillos como linea base.
3. Redes `CNN` propias con normalizacion, regularizacion y aumento de datos.
4. Arquitecturas mas profundas entrenadas desde cero.
5. Modelos con `transfer learning`, incluyendo ResNet, EfficientNet y DenseNet.

El mejor resultado externo de esta parte se obtuvo con una ResNet101 con transfer learning y TTA, desarrollada en el notebook `17_resnet101_transfer_learning_tta.ipynb`.

## Parte de deteccion

En la carpeta `notebooks_detection` se guardan los notebooks de deteccion de objetos. Se probaron principalmente dos familias de modelos:

- **YOLO**: pruebas con YOLOv8 y YOLO11.
- **Faster R-CNN**: modelos de dos etapas con ajustes sobre anchors, umbrales, aumentos y configuracion de inferencia.

El mejor resultado numerico de deteccion se obtuvo con YOLO11, mientras que Faster R-CNN se uso tambien para realizar un analisis mas detallado de errores y comportamiento por clase.

## Dataset y evaluacion

Los experimentos se realizan sobre los benchmarks `xview_recognition` y `xview_detection`. La evaluacion final se contrasta mediante Codabench, generando los ficheros de prediccion correspondientes desde los notebooks.

## Nota

Los notebooks estan pensados como registro del proceso experimental: no todos son modelos finales, sino pasos intermedios que permiten justificar las decisiones tomadas en la memoria.
