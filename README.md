const int motionSensorPin = 2;  // Pin connected to the motion sensor
const int ledPin = 7;           // Pin connected to the LED

void setup() {
  pinMode(motionSensorPin, INPUT);  // Set motion sensor pin as input
  pinMode(ledPin, OUTPUT);           // Set LED pin as output
  Serial.begin(9600);               // Initialize serial communication
}

void loop() {
  if (digitalRead(motionSensorPin) == HIGH) {
    digitalWrite(ledPin, HIGH);    // Turn on the LED
    Serial.println("Motion detected!");
  } else {
    digitalWrite(ledPin, LOW);     // Turn off the LED
    Serial.println("No motion detected.");
  }

  delay(1000);  // Delay between readings
}
