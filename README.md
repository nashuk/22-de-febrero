# 22-de-febrero
Combinación de colores en LED RGB por medio de entradas digitales

int pull1= 5;
int pull2= 6;
int pull3= 7;
int red= 4;
int blue= 2;
int green= 3;
int s1;
int s2;
int s3;

void setup() {
  Serial.begin(9600);
  pinMode(pull1, INPUT_PULLUP);
  pinMode(pull2, INPUT_PULLUP);
  pinMode(pull3, INPUT_PULLUP);
  pinMode(red, OUTPUT);
  pinMode(blue, OUTPUT);
  pinMode(green, OUTPUT);
}

void loop() {
  s1= digitalRead(pull1);
  s2= digitalRead(pull2);
  s3= digitalRead(pull3);
  
if(s1 & s2 & !s3 ){
  digitalWrite(green,LOW);
  }
if(s1 & !s2 & s3){
  digitalWrite(blue, LOW);
  }
if(!s1 & s2 & s3){
  digitalWrite(red,LOW);
  }
if(!s1 & !s2 & s3){
  digitalWrite(red, LOW);
  digitalWrite(blue,LOW);
  }
if(!s1 & s2 & !s3){
  digitalWrite(red,LOW);
  digitalWrite(green,LOW);
  }
if(s1 & !s2 & !s3){
  digitalWrite(blue,LOW);
  digitalWrite(green,LOW);
  }
if(!s1 & !s2 & !s3){
  digitalWrite(red,LOW);
  digitalWrite(blue,LOW);
  digitalWrite(green,LOW);
  }
}
