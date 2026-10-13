int leds[] = {2,3,4,5};
const int btn1 = A4;
const int btn2 = A5;
void setup() {
  for (int i = 0; i < 4; i++) pinMode(leds[i], OUTPUT);
  pinMode(btn1, INPUT_PULLUP);
  pinMode(btn2, INPUT_PULLUP);
}
void loop() {
  if (digitalRead(btn1) == LOW) patternOne();
  else if (digitalRead(btn2) == LOW) patternTwo();
  else for (int i = 0; i < 4; i++) digitalWrite(leds[i], LOW);
}
void patternOne() {
  for (int i = 0; i < 4; i++) {
    digitalWrite(leds[i], HIGH); delay(150);
    digitalWrite(leds[i], LOW);
  }
}
void patternTwo() {
  for (int i = 0; i < 3; i++) {
    for (int j = 0; j < 4; j++) digitalWrite(leds[j], HIGH);
    delay(200);
    for (int j = 0; j < 4; j++) digitalWrite(leds[j], LOW);
    delay(200);
  }
}# ex1-iot
