# Push-button-counter.
const int button = 2;
const int led = 13;
int count = 0;

bool lastState = HIGH;

void setup() {
  pinMode(button, INPUT_PULLUP);
  pinMode(led, OUTPUT);
  Serial.begin(9600);
}

void loop() {
  bool currentState = digitalRead(button);

  if (lastState == HIGH && currentState == LOW) {
    count++;

    Serial.print("Count: ");
    Serial.println(count);

    digitalWrite(led, HIGH);
    delay(200);
    digitalWrite(led, LOW);
  }

  lastState = currentState;
}
#OUTPUT
<img width="1915" height="919" alt="Image" src="https://github.com/user-attachments/assets/818e4d14-1aa8-44f9-9a76-af0022ebcc10" />
