# Push-button-counter.
#include <DHT.h>

#define DHTPIN 4
#define DHTTYPE DHT22

DHT dht(DHTPIN, DHTTYPE);

void setup() {
  Serial.begin(9600);
  dht.begin();
}

void loop() {
  float temp = dht.readTemperature();
  float hum = dht.readHumidity();

  Serial.print("Temp: ");
  Serial.print(temp);
  Serial.print(" °C | ");

  Serial.print("Humidity: ");
  Serial.print(hum);
  Serial.println(" %");

  delay(2000);
}

#OUTPUT
<img width="1915" height="919" alt="Image" src="https://github.com/user-attachments/assets/818e4d14-1aa8-44f9-9a76-af0022ebcc10" />
