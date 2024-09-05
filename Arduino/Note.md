## LED Pins

Need:

1. M-M Jumper Wire to connect the led from breadboard to arduino pin.
2. 200Ω resistor connected to the negative side of led (be sure to ground the resistor)

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

## Buttons

Need:

1. M-M Jumper Wire to connect the led from breadboard to arduino pin.
2. 200Ω resistor connected to the negative side of led (be sure to ground the resistor)

```Cpp
int ledPin = 7;
int buttonPin = 2;

void setup() {
  // put your setup code here, to run once:
  //Initializing the modules to their appropriate pins.
  pinMode(ledPin, OUTPUT);
  pinMode(buttonPin, INPUT);
}

void loop() {
  //put your main code here, to run repeatedly:
  if(digitalRead(buttonPin) == HIGH){ //Checks the button state
    digitalWrite(ledPin, HIGH); //Turn on light
  } else {
    digitalWrite(ledPin, LOW); //Turn off light
  }
}
```
