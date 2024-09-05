## LED Pins

```Cpp
int redLed = 11; //The number the pin is connected to on the board

void setup() {
  // put your setup code here, to run once:
  pinMode(redLed, OUTPUT); //Setting up the led pin to have the function of an OUTPUT.
}

void loop() {
  //put your main code here, to run repeatedly:
  digitalWrite(redLed, HIGH); //Lights up the red LED to maximum brightness
  delay(5000); //Waits 5 seconds
  digitalWrite(redLed, LOW); //Turns off red LED
}
```
