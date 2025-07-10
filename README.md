# 📱 MyAccelerometer

**MyAccelerometer** is a simple Android application that reads data from the device's built-in accelerometer sensor and displays the x, y, and z acceleration values in real time. This app can be used as a foundation for motion tracking, step counting, or detecting device orientation.

---

## 📦 Features

- 📈 Real-time accelerometer data (X, Y, Z axes)
- 📲 Lightweight and responsive UI
- 🧪 Sensor lifecycle management
- ✅ Permissions handled gracefully
- 📤 Extendable for logging or data export

---

## 🧰 Tech Stack

- **Language**: Java / Kotlin
- **Platform**: Android SDK
- **Minimum SDK**: 21 (Android 5.0)
- **IDE**: Android Studio

---

## 📁 Project Structure

```

MyAccelerometer/
├── app/
│   ├── java/
│   │   └── com/example/myaccelerometer/
│   │       ├── MainActivity.java
│   │       └── SensorHelper.java
│   ├── res/
│   │   ├── layout/
│   │   │   └── activity\_main.xml
│   │   └── values/
│   │       └── strings.xml
│   └── AndroidManifest.xml
├── build.gradle
└── README.md

````

---

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/yourusername/MyAccelerometer.git
cd MyAccelerometer
````

### 2. Open in Android Studio

* Open Android Studio
* Select "Open an Existing Project"
* Navigate to the cloned `MyAccelerometer` folder

### 3. Build & Run

* Connect your Android device or start an emulator
* Click **Run ▶️** in Android Studio

---

## 📄 How It Works

* Registers a `SensorEventListener` for the **Accelerometer Sensor**
* Updates the UI with `onSensorChanged()` values from X, Y, and Z axes
* Automatically handles sensor registration/unregistration during lifecycle events (`onResume`, `onPause`)

---

## 📸 Screenshots

![screenshot](screenshots/realtime_data.png)

---

## 🛡️ Permissions

No runtime permissions are required unless extended to log data to storage or access location.

---

## 🔧 Sample Code

### Kotlin

```kotlin
val sensorManager = getSystemService(Context.SENSOR_SERVICE) as SensorManager
val accelerometer = sensorManager.getDefaultSensor(Sensor.TYPE_ACCELEROMETER)

val listener = object : SensorEventListener {
    override fun onSensorChanged(event: SensorEvent) {
        val x = event.values[0]
        val y = event.values[1]
        val z = event.values[2]
        // Update UI
    }
    override fun onAccuracyChanged(sensor: Sensor?, accuracy: Int) {}
}

sensorManager.registerListener(listener, accelerometer, SensorManager.SENSOR_DELAY_UI)
```

---

## 📦 Extend This Project

You can extend **MyAccelerometer** to:

* Record motion data to a file or database
* Visualize motion using charts (e.g., MPAndroidChart)
* Trigger alerts when sudden movement is detected (fall detection, shake detection)
* Combine with gyroscope or magnetometer for full orientation tracking

---

## 🤝 Contribution

Contributions are welcome!

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/my-feature`)
3. Commit your changes (`git commit -am 'Add new feature'`)
4. Push to the branch (`git push origin feature/my-feature`)
5. Open a Pull Request

---

## 📬 Contact

Created by [Your Name](mailto:your.email@example.com)
GitHub: [https://github.com/yourusername](https://github.com/yourusername)

---

## 📜 License

This project is licensed under the MIT License. See `LICENSE` for details.

---

Made with ❤️ for Android Sensors.
