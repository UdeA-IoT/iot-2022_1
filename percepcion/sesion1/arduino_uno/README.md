# Arduino UNO

## Pinout

![arduino_uno](arduino_uno.png)


## Ejemplos basicos

### Ejemplo 1 

ARDUINO

```ino
void setup()
{
  pinMode(LED_BUILTIN, OUTPUT);
}

void loop()
{
  digitalWrite(LED_BUILTIN, HIGH);
  delay(1000); // Wait for 1000 millisecond(s)
  digitalWrite(LED_BUILTIN, LOW);
  delay(1000); // Wait for 1000 millisecond(s)
}
```


ESP8266

```ino
#define LED_BUILTIN 2

void setup() {
  // El LED integrado está conectado al pin 2.
  pinMode(LED_BUILTIN, OUTPUT);
}

void loop() {
    digitalWrite(LED_BUILTIN, LOW); // LED ON en bajo
    delay(1000); 
    digitalWrite(LED_BUILTIN, HIGH); // LED OFF
    delay(1000); 
}
```
ESP32

```ino
// the setup function runs once when you press reset or power the board
void setup() {
  // initialize digital pin LED_BUILTIN as an output.
  pinMode(LED_BUILTIN, OUTPUT);
}

// the loop function runs over and over again forever
void loop() {
  digitalWrite(LED_BUILTIN, HIGH);   
  delay(1000);                       
  digitalWrite(LED_BUILTIN, LOW);    
  delay(1000);                       
}
```


### Ejemplo 2

