


https://docs.espressif.com/projects/esp-idf/en/latest/esp32/hw-reference/index.html


https://docs.espressif.com/projects/esp-idf/en/latest/esp32/get-started/index.html


Instalar drives:

https://docs.espressif.com/projects/esp-idf/en/latest/esp32/get-started/windows-setup.html


https://espressif-docs.readthedocs-hosted.com/projects/arduino-esp32/en/latest/installing.html



Siga las instrucciones de para instalar..

https://randomnerdtutorials.com/installing-the-esp32-board-in-arduino-ide-windows-instructions/




Programas

Probar primero con es scann del wifi

Error:
https://espressif-docs.readthedocs-hosted.com/projects/arduino-esp32/en/latest/troubleshooting.html


Hold down the “BOOT” button in your ESP32 board while uploading/flashing.




https://randomnerdtutorials.com/solved-failed-to-connect-to-esp32-timed-out-waiting-for-packet-header/



```ino
// the setup function runs once when you press reset or power the board
void setup() {
  // initialize digital pin LED_BUILTIN as an output.
  pinMode(LED_BUILTIN, OUTPUT);
}

// the loop function runs over and over again forever
void loop() {
  digitalWrite(LED_BUILTIN, HIGH);   // turn the LED on (HIGH is the voltage level)
  delay(1000);                       // wait for a second
  digitalWrite(LED_BUILTIN, LOW);    // turn the LED off by making the voltage LOW
  delay(1000);                       // wait for a second
}
```

https://randomnerdtutorials.com/esp32-troubleshooting-guide/

------

https://espressif-docs.readthedocs-hosted.com/projects/arduino-esp32/en/latest/index.html


Pines en:

https://espressif-docs.readthedocs-hosted.com/projects/arduino-esp32/en/latest/boards/ESP32-DevKitC-1.html

Elementos usados:
* Shock switch module (Elegoo).

```ino
const int buttonPin = 5;              // the number of the pushbutton pin (GPIO5)
const int ledPin =  LED_BUILTIN;      // the number of the LED pin

// variables will change:
int buttonState = 0;         // variable for reading the pushbutton status

void setup() {
  // initialize the LED pin as an output:
  pinMode(ledPin, OUTPUT);
  // initialize the pushbutton pin as an input:
  pinMode(buttonPin, INPUT);
}

void loop() {
  // read the state of the pushbutton value:
  buttonState = digitalRead(buttonPin);

  // check if the pushbutton is pressed. If it is, the buttonState is HIGH:
  if (buttonState == HIGH) {
    // turn LED on:
    digitalWrite(ledPin, HIGH);
  } else {
    // turn LED off:
    digitalWrite(ledPin, LOW);
  }
}
```

Actividad:
1. En vez de usar el led de la tarjeta, use el led conectado en el GPIO22 y el boton al 15. (Pista: https://microcontrollerslab.com/push-button-esp32-gpio-digital-input/) 

---------------------------

Lectura de un potenciometro


https://microcontrollerslab.com/adc-esp32-measuring-voltage-example/

https://randomnerdtutorials.com/esp32-digital-inputs-outputs-arduino/


https://esp32io.com/tutorials/esp32-button
https://esp32io.com/tutorials/esp32-potentiometer-fade-led

```ino
/*
  Ejemplo adaptado para el ESP32 de:

  https://www.arduino.cc/en/Tutorial/BuiltInExamples/AnalogInOutSerial
*/

const int analogInPin = 15;  // Analog input pin that the potentiometer is attached to GPIO15
const int analogOutPin = LED_BUILTIN; // Analog output pin that the LED is attached to ESP32 led.

int sensorValue = 0;        // value read from the pot
int outputValue = 0;        // value output to the PWM (analog out)

void setup() {
  // initialize serial communications at 9600 bps:
  Serial.begin(9600);
}

void loop() {
  // read the analog in value:
  sensorValue = analogRead(analogInPin);
  // map it to the range of the analog out:
  outputValue = map(sensorValue, 0, 4095, 0, 255); // ADC de 12 bits
  // change the analog out value:
  analogWrite(analogOutPin, outputValue);

  // print the results to the Serial Monitor:
  Serial.print("sensor = ");
  Serial.print(sensorValue);
  Serial.print("\t output = ");
  Serial.println(outputValue);

  // wait 2 milliseconds before the next loop for the analog-to-digital
  // converter to settle after the last reading:
  delay(2);
}
```


---------------------------

Fritizing parts


Vamos a agregar la de esta pagina:
https://forum.fritzing.org/t/esp32s-hiletgo-dev-boad-with-pinout-template/5357

Add: https://fritzing.org/parts/#:~:text=Fritzing%20is%20installed%20with%20a,properties%20in%20the%20info%20palette.

https://forum.fritzing.org/t/adding-a-library-on-fritzing/6950

Para saber ver:https://learn.adafruit.com/using-the-adafruit-library-with-fritzing/import-the-library-into-fritzing



http://digitalconcepts.net.au/fritzing/index.php?op=parts

