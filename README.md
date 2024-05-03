# Guido-obstacle-detecting-device-for-blind-people

const int echopin1=8;
const int trigpin1=7;
const int echopin2=10;
const int trigpin2=9;
const int echopin3=12;
const int trigpin3=11;
const int buzz=6;

long duration1;
long dist1;
long duration2;
long dist2;
long duration3;
long dist3;


void setup() {
  // put your setup code here, to run once:
  pinMode(trigpin1, OUTPUT);
  pinMode(echopin1, INPUT);
  pinMode(trigpin2, OUTPUT);
  pinMode(echopin2, INPUT);
  pinMode(trigpin3, OUTPUT);
  pinMode(echopin3, INPUT);
  pinMode(buzz,OUTPUT); 
  Serial.begin(9600);

}

void loop() {
  // put your main code here, to run repeatedly:
 

  digitalWrite(trigpin1, LOW);
  delayMicroseconds(2);
  digitalWrite(trigpin1, HIGH);
  delayMicroseconds(10);
  digitalWrite(trigpin1, LOW);
  duration1= pulseIn(echopin1, HIGH) ;
  dist1=duration1*0.034/2;
  
   
  digitalWrite(trigpin2, LOW);
  delayMicroseconds(2);
  digitalWrite(trigpin2, HIGH);
  delayMicroseconds(10);
  digitalWrite(trigpin2, LOW);
  duration2= pulseIn(echopin2, HIGH) ;
  dist2=duration2*0.034/2;
 
   
  digitalWrite(trigpin3, LOW);
  delayMicroseconds(2);
  digitalWrite(trigpin3, HIGH);
  delayMicroseconds(10);
  digitalWrite(trigpin3, LOW);
  duration3= pulseIn(echopin3, HIGH) ;
  dist3=duration3*0.034/2;
   
if(dist1<30){
    Serial.println("1:"); // Sensor 1
    Serial.println(dist1);  
    tone(buzz,150);
    delay(500);
    noTone(buzz);

    
}
 
 if(dist2<30){
    Serial.println("2:"); // Sensor 1
    Serial.println(dist2); 
    tone(buzz,450);
    delay(500);
    noTone(buzz);

 
 }
 if(dist3<30){
   Serial.println("3:"); // Sensor 1
   Serial.println(dist3  );
   tone(buzz,150);
   delay(500);
   noTone(buzz);
 
   }
   
 }   
