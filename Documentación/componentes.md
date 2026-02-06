# Lista de Componentes - Proyecto A.B.I.S. (Sierra 1)
**Mision de Carga Util: Advanced Biological Integrity Shield**

Este documento detalla los componentes electronicos y de hardware seleccionados para la carga util, enfocados en la adquisicion de datos para el analisis de traumatologia y neuroproteccion en entornos aeroespaciales.

---

## 1. Microcontroladores (Cerebro del Sistema)

| Componente | Especificaciones | Justificacion |
| :--- | :--- | :--- |
| **ESP32-S3** | Dual-core 240 MHz, 512KB SRAM, Wi-Fi/Bluetooth, soporte nativo USB. | Permite el procesamiento paralelo de sensores y telemetria en tierra sin interferir con el ciclo de lectura principal. |
| **Teensy 4.1** | ARM Cortex-M7 a 600 MHz, FPU de doble precision, slot MicroSD integrado (SDIO). | Necesario para un muestreo superior a 1kHz, fundamental para capturar microfracturas por resonancia y picos de impacto. |

---

## 2. Sensores de Vuelo e Impacto (Variables Primarias)

* **Acelerometro de Alto Rango (ADXL375)**:
    * **Especificaciones:** Rango de medicion de hasta +/- 200g, resolucion de 10 bits, interfaz I2C/SPI.
    * **Justificacion:** Vital para registrar la aceleracion maxima y el impacto con el suelo, donde los sensores estandar de 16g se saturarian.
* **IMU de Precision (BMI270 / ICM-20948)**:
    * **Especificaciones:** Giroscopio de 3 ejes y acelerometro de 3 ejes con bajo ruido y alta estabilidad termica.
    * **Justificacion:** Permite analizar el comportamiento vibratorio y la aceleracion angular para modelar la lesion axonal difusa.

---

## 3. Sensores Medico-Experimentales

* **Sensor de Fuerza Resistivo (FSR 402)**:
    * **Especificaciones:** Rango de sensibilidad de 0.1N a 20N, formato ultrafino (0.45 mm de grosor).
    * **Justificacion:** Permite cuantificar la transmision directa de fuerzas mecanicas hacia el huevo, actuando como analogo del craneo humano.
* **Sensor de Temperatura Digital (DS18B20)**:
    * **Especificaciones:** Precision de +/- 0.5°C en el rango de -10°C a +85°C, interfaz One-Wire.
    * **Justificacion:** Esencial para monitorear la estabilidad termica de los biopolimeros viscoelasticos y asegurar que su capacidad de amortiguamiento no se altere.

---

## 4. Almacenamiento, Vision y Energia

* **Data Logging (Modulo MicroSD)**:
    * **Especificaciones:** Soporte para tarjetas Clase 10, interfaz SPI/SDIO de alta velocidad.
    * **Justificacion:** Garantiza el registro de parametros fisicos relevantes y tiempos de disipacion de energia durante eventos de alta aceleracion.
* **Documentacion Visual (ESP32-CAM)**:
    * **Especificaciones:** Resolucion UXGA (1600 x 1200 px), slot para tarjeta TF.
    * **Justificacion:** Provee evidencia visual para el analisis de la integridad estructural post-vuelo del sistema multicapa.
* **Sistema de Energia (Bateria LiPo + Regulador Buck)**:
    * **Especificaciones:** Bateria de 7.4V (2S), regulador de alta eficiencia con salida de 5V/3.3V y proteccion contra cortocircuitos.
    * **Justificacion:** Proporciona una fuente estable de energia capaz de soportar las vibraciones prolongadas y aceleraciones del cohete Sierra 1.

---

## 5. Software y Herramientas de Programacion

* **Entornos de Desarrollo:** Arduino IDE y Visual Studio Code (con extension PlatformIO) para gestion de librerias y control de versiones.
* **Monitoreo Serial:** CoolTerm para la visualizacion de datos en tiempo real durante pruebas estaticas.
* **Post-Procesamiento:** Python (Pandas y Matplotlib) para realizar el analisis cuantitativo de las aceleraciones y tiempos de amortiguacion.

---

## 6. Restricciones del Sistema

* **Dimensiones:** El sistema debe ajustarse a un volumen de aproximadamente 10 x 10 x 20 cm
* **Masa Total:** No debe exceder los 4 kg para mantener la compatibilidad con el cohete
* **Mision Medica:** Validar un sistema pasivo que minimice la transmision de fuerzas hacia sistemas fragiles multicapa.

---
Ultima actualizacion: Febrero 2026.
