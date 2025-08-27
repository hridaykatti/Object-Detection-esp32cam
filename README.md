# Object Detection on ESP32-CAM using Edge Impulse (FOMO Model)

## 📌 Project Description
This project implements real-time **object detection** on the **ESP32-CAM** using a **FOMO (Faster Objects, More Objects)** model trained with **Edge Impulse Studio**.  
The ESP32-CAM captures images and performs **on-device inference** to detect and classify objects into **three categories** from the custom dataset.  
The inference runs entirely on the ESP32-CAM (TinyML), without requiring cloud services.

---

## 🛠️ Hardware & Software Requirements
### Hardware
- ESP32-CAM module (with OV2640 camera)
- USB cable
- Jumper wires
- Power supply (5V)

### Software
- [Arduino IDE](https://www.arduino.cc/en/software) (1.8.x or 2.x)
- ESP32 board package installed in Arduino IDE
- Edge Impulse Studio (for dataset collection & model training)
- Exported **Arduino Library** from Edge Impulse (FOMO model)

---

## 📊 Model Details
- **Model type:** FOMO (lightweight object detection for TinyML)
- **Dataset:** Custom dataset with **3 object classes**
- **Training platform:** Edge Impulse Studio
- **Deployment:** Exported as Arduino library → integrated into ESP32-CAM code

---

## ⚙️ Setup Instructions
1. **Model Training in Edge Impulse**
   - Collected images for 3 object categories.
   - Trained FOMO model for real-time object detection.
   - Evaluated performance with test dataset.
   - Exported as **Arduino library**.

2. **Arduino IDE Setup**
   - Install ESP32 boards in Arduino IDE:  
     ```
     File → Preferences → Additional Board Manager URLs
     ```
     Add:  
     ```
     https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package_esp32_index.json
     ```
   - Install ESP32 board package from **Boards Manager**.
   - Install the exported Edge Impulse library (`.zip`).

3. **Flashing the ESP32-CAM**
   - Connect ESP32-CAM to your USB breakout board.  
   - Select **ESP32 Wrover Module** in Arduino IDE.  
   - Choose the correct COM port.  
   - Upload the sketch from `src/object_detection.ino`.

4. **Running Inference**
   - Open the **Serial Monitor** (115200 baud).  
   - Reset the ESP32-CAM.  
   - The ESP32 will start running inference and display detected objects + probabilities.  
   - If code is set for streaming, you can also view results via web server (ESP32-CAM IP).

---

## 📂 Project Structure
```
object-detection-esp32cam/
│── src/ # ESP32 source code (Arduino .ino file)
│── models/ # Edge Impulse exported FOMO model files
│── images/ # Example results/screenshots
│── README.md # Project description (this file)
│── LICENSE # License file
```
---

## 🚀 Applications
- Smart surveillance cameras  
- Edge AI IoT devices  
- Real-time monitoring systems  
- Low-cost embedded vision projects  

---

## 📜 License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
