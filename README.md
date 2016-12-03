# Arreglo-Foto-Cris
int serie1[10]= {30, 14, 1, 36,40,5,23,55,17,2};
int serie2[10];
int dato;
int dato_ant;
int parametro = 0;//0= Mayor a Menor ---- 1=Menor a Mayor

void setup() {
Serial.begin(9600); 
pinMode(2,INPUT);
  
  for(int a = 0; a < 10 ; a++){
    Serial.print(a);
    Serial.print("serie1 desordenado:");
    Serial.println(serie1[a]);
    delay(500);
  }
  
  ordenar(parametro);
}
void loop() {
 

}
void ordenar(int valor){
    for(int i= 1; i < 11; i++){
    for( int d= 1; d < 11; d++){
      dato=dato_ant+funcion(serie1[i],serie1[d],valor); 
      dato_ant=dato;     
      
    }
    serie2[dato]=serie1[i];
    dato=0;
    dato_ant=0;
  } 
  for(int a = 1; a < 11; a++){
    Serial.print("serie1 ordenada:");
    Serial.println(serie2[a]);
    delay(500);
  }

}

int funcion(int valor1,int valor2, int valor3){
  
  if(valor3 == 1){//DE MENOR A MAYOR
    if(valor1 >= valor2){
   return 0;
  }
  else{
   return 1; 
  } 
  }
 
  else {//DE MAYOR A MENOR
    if(valor1 <= valor2){
   return 1;
  }
  else{
   return 0; 
  }
  }
}
