# Lista de Componentes - Proyecto A.B.I.S. (Sierra 1)
**Mision de Carga Util: Advanced Biological Integrity Shield**

Este documento detalla los componentes electronicos y de hardware seleccionados para la carga util, enfocados en la adquisicion de datos para el analisis de traumatologia y neuroproteccion en entornos aeroespaciales.

---

## 1. Microcontroladores (Cerebro del Sistema)

| Opcion | Componente | Especificaciones | Justificacion |
| :--- | :--- | :--- | :--- |
| **A** | **ESP32-S3** | Dual-core 240 MHz, Wi-Fi/BT, USB Nativo. | Facilita la telemetria previa al lanzamiento y el procesamiento paralelo de sensores. |
| **B** | **Teensy 4.1** | ARM Cortex-M7 a 600 MHz, Slot SD de alta velocidad. | Necesario si se requiere muestreo superior a 1kHz para capturar microfracturas por resonancia. |

---

## 2. Sensores de Vuelo e Impacto (Variables Primarias)

* **Acelerometro High-G (ADXL375)**:
    * **Rango:** +/- 200g.
    * **Funcion:** Registrar la aceleracion maxima y el pico de impacto durante el aterrizaje sin saturacion.
* **IMU de Precision (BMI270 / ICM-20948)**:
    * **Funcion:** Monitorear el comportamiento vibratorio y la aceleracion angular durante todas las fases del vuelo.

---

## 3. Sensores Medico-Experimentales

* **Sensor de Fuerza Resistivo (FSR 402)**:
    * **Uso:** Cuantificar la transmision directa de fuerzas mecanicas hacia el huevo (analogo del craneo).
* **Sensor de Temperatura (DS18B20)**:
    * **Uso:** Monitorear la estabilidad termica del biopolimero para asegurar que sus propiedades viscoelasticas no se alteren durante la mision.

---

## 4. Almacenamiento, Vision y Energia

* **Data Logging:** Modulo MicroSD Externo (para ESP32) para el registro de parametros fisicos y tiempos de disipación.
* **Documentación Visual:** ESP32-CAM o RunCam para evaluar la integridad estructural post-vuelo.
* **Energía:** Bateria LiPo 7.4V con Regulador Buck para mantener la operacion estable bajo vibraciones prolongadas.

---

## 5. Software y Herramientas de Programacion

* **Firmware:** Arduino IDE / Visual Studio Code (PlatformIO).
* **Comunicacion Serial:** CoolTerm.
* **Analisis de Datos:** Python (Pandas/Matplotlib) o MATLAB para la interpretacion de datos fisiologicos y biomecanicos.

---

## 6. Restricciones del Sistema

* **Dimensiones:** Aproximadamente 10 x 10 x 20 cm.
* **Masa Total:** Maximo 4 kg.
* **Objetivo:** Validar el sistema de amortiguamiento pasivo comparando huevos con y sin biopolimero.

---
Ultima actualizacion: Febrero 2026.
