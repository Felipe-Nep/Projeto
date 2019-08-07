/* Projeto monitoriamento de umidade no solo 
Escrito por Gedeane Kenshima
Data: 07/08/2017

Adaptação: Felipe Nepomuceno da Silva
*/
   
int buzzer = 11;
  
void setup() {
  
Serial.begin(9600);
}
  
void loop() {
   
int sensorValue = analogRead(A0);
 
    if (sensorValue > 600){
 
    int thisPitch = map(sensorValue, 200, 1023, 1500, 120);
 
    tone(buzzer, thisPitch, 50);
 
    Serial.print("Valor lido por sensor: ");
    
    Serial.println(sensorValue);
    
    Serial.println("Solo está seco: necessário regar!");
    
    delay(100);
 
}
 
else{
 
  Serial.print("Valor lido por sensor: ");
 
  Serial.println(sensorValue);
  delay(100);
  }
  
}
