# project-arduino-mengukur-jarak-menggunakan-ultrasonik
# Deskripsi
mengukur jarak antara Arduino dengan objek atau kendaraan di sekitarnya. 
Sensor ultrasonik bekerja dengan cara mengirimkan gelombang suara pada frekuensi ultrasonik dan mendeteksi gelombang yang dipantulkan kembali oleh objek. Informasi yang diterima sensor ultrasonik kemudian diproses oleh mikrokontroler Arduino.
# Komponen (alat & bahan) :
• Arduino (Uno, Nano, atau jenis lainnya)
• Sensor Ultrasonik HC-SR04
• Breadboard dan kabel jumper
• Resistor (jika diperlukan untuk level shifting, tergantung pada sistem yang digunakan
  Komputer dengan Arduino IDE terinstal)
# Skema Sirkuit
![SKEMA SIRKUT ARDUINO](https://github.com/user-attachments/assets/757b36a2-1725-4202-b0ff-5dc5c467bb24)
# Code Program
``` const int trigpin = 10;
const int echopin = 9;
long timer;
int jarak;

void setup() {
  // put your setup code here, to run once:
Serial.begin(9600);
pinMode(trigpin, OUTPUT);
pinMode(echopin, INPUT);

}

void loop() {
  // put your main code here, to run repeatedly:
digitalWrite(trigpin, LOW);
delayMicroseconds(2);
digitalWrite(trigpin, HIGH);
delayMicroseconds(10);
digitalWrite(trigpin, LOW);

timer = pulseIn(echopin, HIGH);
jarak = timer/58;
Serial.println(jarak);
delay(200);
}
