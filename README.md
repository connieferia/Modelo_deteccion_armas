# Sistema de Detección de Armas con TinyML en ESP32-S3

Este proyecto implementa un sistema de detección de armas en tiempo real utilizando técnicas de Deep Learning y TinyML,
ejecutado en un dispositivo embebido ESP32-S3. El modelo fue entrenado para detectar objetos
de tipo "Pistol" y "Knife", permitiendo identificar la presencia de armas en escenarios reales.

## Tecnologías utilizadas

- Edge Impulse
- Arduino IDE
- ESP32-S3
- FOMO (Faster Objects, More Objects)
- MobileNetV2

## Dataset

El modelo fue entrenado con un conjunto de datos de 2808 imágenes anotadas, distribuidas en:

- 70% entrenamiento
- 20% validación
- 10% prueba

Clases:
- Knife
- Pistol
- Background (generada automáticamente)

## Resultados

Modelo Edge Impulse:

- Precisión: 0.62
- Recall: 0.51
- F1-Score: 55.8%

El modelo fue optimizado en formato INT8 para su ejecución en sistemas embebidos.

## Funcionamiento

El sistema captura imágenes en tiempo real desde la cámara de la ESP32-S3 y ejecuta inferencias para detectar armas.

- Si detecta: muestra bounding box + confianza
- Si no detecta: imprime "Sin arma"

Además:
- Se puede analizar movimiento mediante coordenadas (x, y)
- Se puede estimar distancia mediante el tamaño del bounding box

## Requisitos

- ESP32-S3
- Arduino IDE
- Librerías de Edge Impulse
- Cámara compatible (OV2640 / OV5640)

## Uso

- Encender el dispositivo
- Apuntar la cámara hacia el objeto
- Observar resultados en el monitor serial

## Limitaciones

- Sensible a baja iluminación
- Puede generar falsos positivos con objetos oscuros
- Requiere estabilidad de la cámara
- Distancia efectiva: ~1 metro

## 🎥 Demostración del sistema

El siguiente video muestra el funcionamiento del sistema de detección de armas en tiempo real en la ESP32-S3:


