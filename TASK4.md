const int button1 = 2;   // Push Button 1 connected to D2
const int button2 = 3;   // Push Button 2 connected to D3
const int ledLight = 12; // LED for Light connected to D12
const int ledFan = 13;   // LED for Fan connected to D13

void setup() {
  pinMode(button1, INPUT_PULLUP);  // Configure Button 1 with internal pull-up resistor
  pinMode(button2, INPUT_PULLUP);  // Configure Button 2 with internal pull-up resistor
  pinMode(ledLight, OUTPUT);       // Set LED pins as outputs
  pinMode(ledFan, OUTPUT);

  // Initialize LEDs as OFF
  digitalWrite(ledLight, LOW);
  digitalWrite(ledFan, LOW);
}

void loop() {
  // Check Button 1 (Light Control)
  if (digitalRead(button1) == LOW) {  // Button 1 pressed (LOW)
    digitalWrite(ledLight, HIGH);     // Turn on Light LED
  } else {
    digitalWrite(ledLight, LOW);      // Turn off Light LED when Button 1 is released
  }

  // Check Button 2 (Fan Control)
  if (digitalRead(button2) == LOW) {  // Button 2 pressed (LOW)
    digitalWrite(ledFan, HIGH);       // Turn on Fan LED
  } else {
    digitalWrite(ledFan, LOW);        // Turn off Fan LED when Button 2 is released
  }
}
