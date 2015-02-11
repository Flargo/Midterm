# Midterm
//Nick Adams
include <Servo.h> 
 
Servo arm; 

int armangle = 0;// the position of the "arm"
 
float difficulty;    // float which controls the speed and difficulty
int maxi = 90;
int mini = 5;

int pin = 0; 
 
void setup() 
{ 
  arm.attach(9);   
} 
 
void loop() 
{ 
  difficulty = analogRead(pin);           
  difficulty = map(difficulty, 0, 1023, 1, 3);     // scales the difficulty to 3 options 

 
   for(armangle = mini; armangle <= maxi; armangle +=difficulty) // tells the arm to go forwards 
  {                                                          // The potentiometer controls the speed/difficulty
    arm.write(armangle);           
    delay(10);                       
  } 
  for(armangle = maxi; armangle>=mini; armangle-=difficulty)  // and go back   
  {                                
    arm.write(armangle);              
    delay(10);                       
    } 
  }
  
