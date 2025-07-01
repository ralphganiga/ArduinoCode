# ArduinoCode
# One Pushbutton, One LED (Turn Off/On)

// C++ code
//

int LEDState;
int redLEDPin=4;
int buttonPin=2;
int buttonStatus;
int buttonPrevious=0;
int dt=100;


void setup()
{
  Serial.begin(9600);
  pinMode(redLEDPin, OUTPUT);
  pinMode(buttonPin, INPUT);
}

void loop()
{
  	buttonStatus = digitalRead(buttonPin);
    if (buttonPrevious == 0 && buttonStatus == 1){    // Check the status of button 
    	if (LEDState==0) {
    		LEDState=1;
          	digitalWrite(redLEDPin, HIGH);
          	Serial.println(LEDState);
    	}
    	else {
      		LEDState=0;
          	digitalWrite(redLEDPin, LOW);
          	Serial.println(LEDState);
    	}
  	} 	
    buttonPrevious=buttonStatus;
  	Serial.println(buttonPrevious);
  	delay(dt);   
  }
  
   
   
