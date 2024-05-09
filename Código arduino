#include <LiquidCrystal.h>

// Definição dos pinos
const int pinLDR = A0;
const int pinLEDVermelho = 8;
const int pinLEDAmarelo = 9;
const int pinLEDVerde = 10;
const int buzzerPin = 7;
const int SensorTempPino = 0;

// Inicialização do LCD
LiquidCrystal lcd(4, 3, A2, A3, A4, A5);

void setup() {
  pinMode(pinLEDVermelho, OUTPUT);
  pinMode(pinLEDAmarelo, OUTPUT);
  pinMode(pinLEDVerde, OUTPUT);
  pinMode(buzzerPin, OUTPUT);

  lcd.begin(16, 2);
}

void loop() {
  int valorLDR = analogRead(pinLDR);
  int valorUmidade = analogRead(A1);
  float valorTemperatura = readTemperature(SensorTempPino);

  // Atualiza o display com a temperatura e umidade
  lcd.clear();
  lcd.setCursor(0, 0);
  if (valorTemperatura < 20) {
    lcd.print("Temp: Baixa");
  } else if (valorTemperatura >= 20 && valorTemperatura <= 30) {
    lcd.print("Temp: Ok");
  } else {
    lcd.print("Temp: Alta");
  }
  lcd.setCursor(0, 1);
  lcd.print(valorTemperatura);
  lcd.print(" C");

  // Aguarda um tempo para visualização
  delay(2000);

  // Limpa o display
  lcd.clear();

  // Condições para umidade
  lcd.setCursor(0, 0);
  if (valorUmidade < 30) {
    lcd.print("Umidade: Baixa");
  } else if (valorUmidade >= 30 && valorUmidade <= 70) {
    lcd.print("Umidade: Ok");
  } else {
    lcd.print("Umidade: Alta");
  }
  lcd.setCursor(0, 1);
  lcd.print(valorUmidade);
  lcd.print("%");

  // Aguarda um tempo para visualização
  delay(3000);

  // Atualiza os LEDs e o buzzer com base na luminosidade
  if (valorLDR < 300) { // Ambiente escuro
    digitalWrite(pinLEDVerde, LOW);
    digitalWrite(pinLEDAmarelo, LOW);
    digitalWrite(pinLEDVermelho, HIGH);
    tone(buzzerPin, 1000);
  } else if (valorLDR >= 300 && valorLDR < 800) { // Meia luz
    digitalWrite(pinLEDVerde, LOW);
    digitalWrite(pinLEDAmarelo, HIGH);
    digitalWrite(pinLEDVermelho, LOW);
    noTone(buzzerPin);
  } else { // Ambiente claro
    digitalWrite(pinLEDVerde, HIGH);
    digitalWrite(pinLEDAmarelo, LOW);
    digitalWrite(pinLEDVermelho, LOW);
    noTone(buzzerPin);
  }

  delay(1000);
}

float readTemperature(int pin) {
  float sum = 0;
  for (int i = 0; i < 5; i++) {
    sum += analogRead(pin);
    delay(10);
  }
  return (sum / 5.0) * 0.48828125;
}
