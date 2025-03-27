<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ultrasonic Distance Meter</title>
</head>
<body>

<h1 align="center">📏 Ultrasonic Distance Meter</h1>
<h2 align="center">🔍 Measuring Distances with Precision</h2>

<hr>

<h2>📌 The Problem</h2>

<p>Measuring distances manually can be time-consuming, inaccurate, and inefficient. Traditional measuring tools often require physical contact, making it challenging to measure hard-to-reach areas.</p>

<p>Whether for robotics, automation, or industrial applications, a reliable and contactless distance measurement system is essential.</p>

<hr>

<h2>💡 The Smart Solution</h2>

<p>This project introduces an <b>Ultrasonic Distance Meter</b> using an <b>HC-SR04 ultrasonic sensor</b> and an <b>Arduino board</b>. It provides real-time, accurate distance measurements displayed on a <b>16x2 LCD</b>.</p>

<hr>

<h2>🚀 Features</h2>

<ul>
    <li>✅ <b>Real-time Distance Measurement</b> – Instant feedback on distances.</li>
    <li>✅ <b>Contactless Operation</b> – No need for physical touch.</li>
    <li>✅ <b>LCD Display</b> – Clear visualization of measured values.</li>
    <li>✅ <b>Energy Efficient</b> – Uses minimal power.</li>
    <li>✅ <b>DIY Friendly</b> – Simple and easy to build.</li>
</ul>

<hr>

<h2>🛠️ How It Works</h2>

<ul>
    <li>🔹 The <b>ultrasonic sensor</b> sends an ultrasonic pulse.</li>
    <li>🔹 The pulse bounces off an object and returns to the sensor.</li>
    <li>🔹 The <b>Arduino</b> calculates the time taken and determines the distance.</li>
    <li>🔹 The distance is displayed on a <b>16x2 LCD</b>.</li>
</ul>

<hr>

<h2>✨ Key Process Flow</h2>
<ol>
    <li>The <b>trigger pin</b> sends an ultrasonic pulse.</li>
    <li>The <b>echo pin</b> receives the reflected signal.</li>
    <li>The <b>Arduino</b> calculates the time taken for the pulse to return.</li>
    <li>Using the speed of sound, the distance is calculated and displayed.</li>
</ol>

<hr>

<h2>🌍 Why This Project Matters for the Future?</h2>

<ul>
    <li>✅ <b>Automation & Robotics</b> – Used in obstacle detection and smart robots.</li>
    <li>✅ <b>Industrial Applications</b> – Helps in distance monitoring in manufacturing.</li>
    <li>✅ <b>Smart Home Integration</b> – Can be used in security and IoT systems.</li>
</ul>

<hr>

<h2>🔮 Future Enhancements</h2>

<ul>
    <li>🚀 <b>Wireless Data Transmission</b> – Send measurements to a mobile app.</li>
    <li>📶 <b>Bluetooth & Wi-Fi Integration</b> – Remote distance monitoring.</li>
    <li>🌐 <b>IoT Connectivity</b> – Cloud-based distance tracking.</li>
</ul>

<hr>

<h2>📜 Project Components</h2>

<ul>
    <li><b>Arduino Uno</b></li>
    <li><b>HC-SR04 Ultrasonic Sensor</b></li>
    <li><b>16x2 LCD Display</b></li>
    <li><b>Resistors & Connecting Wires</b></li>
</ul>

<hr>

<h2>🖥️ Arduino Code</h2>

<pre>
#include &lt;LiquidCrystal.h&gt;

#define TRIGGER_PIN 18
#define ECHO_PIN 19
#define SPEED_OF_SOUND 0.034

LiquidCrystal lcd(2, 3, 4, 5, 6, 7);

void setup() {
    lcd.begin(16, 2);
    pinMode(TRIGGER_PIN, OUTPUT);
    pinMode(ECHO_PIN, INPUT);
    lcd.print("Ultrasonic Meter");
    delay(2000);
    lcd.clear();
}

void loop() {
    digitalWrite(TRIGGER_PIN, LOW);
    delayMicroseconds(2);
    digitalWrite(TRIGGER_PIN, HIGH);
    delayMicroseconds(10);
    digitalWrite(TRIGGER_PIN, LOW);

    float duration = pulseIn(ECHO_PIN, HIGH);
    float distanceCm = duration * SPEED_OF_SOUND / 2.0;

    if (duration == 0 || distanceCm > 400) {
        lcd.clear();
        lcd.print("Out of Range");
    } else {
        lcd.clear();
        lcd.print("Distance: ");
        lcd.print(distanceCm, 2);
        lcd.print(" cm");
        lcd.setCursor(0, 1);
        lcd.print("Distance: ");
        lcd.print(distanceCm / 100, 2);
        lcd.print(" m");
    }
    delay(1000);
}
</pre>

<hr>

<hr>

<h2>📽️ Project Demos</h2>

<p>Here are some project snapshots:</p>

<table align="center" border="0" cellpadding="10">
    <tr>
        <td align="center">
            <img src="https://github.com/Rakibul10x/Ultrasonic-Distance-Meter/blob/main/Project%20Component%20List.png" alt="Project Component List" width="300">
            <p>📸 Project Component List</p>
        </td>
        <td align="center">
            <img src="https://github.com/Rakibul10x/Ultrasonic-Distance-Meter/blob/main/Wiring%20and%20Schematic%20Diagram.png" alt="Wiring and Schematic Diagram" width="300">
            <p>📸 Wiring and Schematic Diagram</p>
        </td>
        <td align="center">
            <img src="[images/performance_analysis.jpg](https://github.com/Rakibul10x/Ultrasonic-Distance-Meter/blob/main/Ultrasonic%20Distance%20Sensor%20Test%20and%20Performance%20Analysis.png)" alt="Ultrasonic Distance Sensor Test and Performance Analysis" width="300">
            <p>📸 Ultrasonic Distance Sensor Test and Performance Analysis</p>
        </td>
    </tr>
</table>

<hr>



<h2>📌 Contribution & Support</h2>

<p>If you love this project, consider giving it a ⭐ and contributing to its future enhancements!</p>

<p>📩 Feel free to <b>fork</b>, <b>improve</b>, and <b>submit a pull request</b> to add new features.</p>

<p>For any queries or suggestions, reach out to <b><a href="mailto:YourEmail@example.com">YourEmail@example.com</a></b>.</p>

<hr>

<h2>🔗 Let's Build the Future Together! 🌍✨</h2>

<p>🚀 <b>Clone the Repository & Start Building:</b></p>

<pre>
git clone https://github.com/YourUsername/Ultrasonic-Distance-Meter.git
</pre>

</body>
</html>
