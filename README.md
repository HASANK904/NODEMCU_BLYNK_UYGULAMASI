# NODEMCU_BLYNK_UYGULAMASI


#define BLYNK_TEMPLATE_ID "TMPL6wrmkY8nM"
#define BLYNK_TEMPLATE_NAME "LED1"
#define BLYNK_AUTH_TOKEN "sRLpaeXnlpmDWbK2O3sOYbGqzfEdCt0L"
#include <ESP8266WiFi.h>
#include <BlynkSimpleEsp8266.h>

char auth[] = "sRLpaeXnlpmDWbK2O3sOYbGqzfEdCt0L";
char ssid[] = "Kobastar_ARGE";
char pass[] = "47805224";

#define LED_PIN D0

void setup()
{
  Serial.begin(115200);
  Blynk.begin(auth, ssid, pass);
  pinMode(LED_PIN, OUTPUT);
}

void loop()
{
  Blynk.run();
}

BLYNK_WRITE(V1) // Butonun “Virtual Pin”i V1 ise
{
  int ledState = param.asInt();
  Serial.print("BLYNK_WRITE(V1) çağrıldı, ledState: ");
  Serial.println(ledState);
  digitalWrite(LED_PIN, ledState);
}
