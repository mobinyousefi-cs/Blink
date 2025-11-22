# Blink - Arduino LED Blink Project

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
![Arduino](https://img.shields.io/badge/Arduino-Compatible-blue.svg)
![Difficulty](https://img.shields.io/badge/Difficulty-Beginner-green.svg)

## 📖 Description

This project demonstrates the most fundamental example of physical computing with Arduino: controlling an LED. It's the first step in learning how to make the Arduino interact with the physical world by providing visual output. The sketch blinks the built-in LED on your Arduino board, or you can wire up an external LED to see the results more clearly.

This is the Arduino equivalent of "Hello World" and serves as the foundation for all physical computing projects.

## ✨ Features

- **Beginner Friendly**: No prior experience required
- **Built-in LED Support**: Uses onboard LED with no additional components
- **External LED Option**: Expandable to external circuits
- **Fully Customizable**: Adjustable timing and patterns
- **Cross-Platform**: Works with all major Arduino boards
- **Educational**: Teaches fundamental electronics and programming concepts

## 🔧 Circuit Setup

### Option 1: Built-in LED (No Components Needed)
Most Arduino boards include a built-in LED connected to a digital pin. The `LED_BUILTIN` constant automatically maps to the correct pin for your specific board.

### Option 2: External LED Circuit

#### 📋 Components Required
| Component | Quantity | Notes |
|-----------|----------|-------|
| Arduino Board | 1 | Uno, Nano, Mega, etc. |
| LED | 1 | Any color |
| 220Ω Resistor | 1 | Red-Red-Brown |
| Breadboard | 1 | Optional but recommended |
| Jumper Wires | 2-3 | Male-to-Male |

#### ⚡ Step-by-Step Wiring Instructions
1. **Identify LED polarity**: Long leg = Anode (+), Short leg = Cathode (-)
2. **Connect resistor**: One end to Arduino digital pin 13 (LED_BUILTIN)
3. **Connect LED anode**: Other end of resistor to LED's long leg
4. **Connect LED cathode**: LED's short leg to Arduino GND pin
5. **Verify connections**: Double-check all connections before powering

## 📐 Resistor Calculation

### Understanding the Need for Resistors
LEDs require current limiting to prevent damage. Without a resistor, excessive current can destroy both the LED and Arduino pin.

### Ohm's Law Application
Formula: R = (V_source - V_LED) / I_LED

Where:

- V_source = Arduino output voltage (5V or 3.3V)
- V_LED = LED forward voltage (typically 1.8V-3.3V)
- I_LED = Desired LED current (typically 10-20mA)
- Example Calculation for Red LED:
- V_source = 5V (Arduino UNO)
- V_LED = 2.0V (typical red LED)
- I_LED = 15mA (0.015A)
- R = (5V - 2.0V) / 0.015A = 200Ω

Nearest standard value: 220Ω

### Resistor Value Guide
| LED Color | Forward Voltage | Recommended Resistor (5V) | Current |
|-----------|-----------------|---------------------------|---------|
| Red | 1.8-2.2V | 220Ω | ~13.6mA |
| Green | 2.0-2.4V | 220Ω | ~12.7mA |
| Blue | 2.8-3.3V | 150Ω | ~14.7mA |
| White | 3.0-3.4V | 150Ω | ~13.3mA |

## 🚀 Installation & Usage

### Step 1: Hardware Setup
Choose one of the following options:
- **Quick Start**: Use built-in LED (no additional wiring)
- **Learning Path**: Build external LED circuit for hands-on experience

### Step 2: Software Setup

#### Method A: Load from Examples (Recommended for Beginners)
1. Open Arduino IDE
2. Navigate to: **File → Examples → 01.Basics → Blink**
3. The code will open in a new window

#### Method B: Copy-Paste Code
```cpp
/*
 * Blink - Arduino LED Blink Example
 * Turns an LED on for one second, then off for one second, repeatedly.
 * 
 * This example code is in the public domain.
 */

// The setup function runs once when you press reset or power the board
void setup() {
  // Initialize digital pin LED_BUILTIN as an output
  pinMode(LED_BUILTIN, OUTPUT);
}

// The loop function runs over and over again forever
void loop() {
  digitalWrite(LED_BUILTIN, HIGH);   // Turn the LED on (HIGH voltage level)
  delay(1000);                       // Wait for 1000 milliseconds (1 second)
  digitalWrite(LED_BUILTIN, LOW);    // Turn the LED off (LOW voltage level)
  delay(1000);                       // Wait for 1 second
}
```

