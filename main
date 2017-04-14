/*
 * Ardrumo sketch
 *
 * Use with the Ardrumo software here:
 * <a href="http://code.google.com/p/ardrumo/" rel="nofollow"> <a href="http://code.google.com/p/ardrumo/"> <a href="http://code.google.com/p/ardrumo/"> <a href="http://code.google.com/p/ardrumo/" rel="nofollow"> <a href="http://code.google.com/p/ardrumo/" rel="nofollow"> http://code.google.com/p/ardrumo/
</a>
</a>
</a>
</a>
</a>
 * This is designed to let an Arduino act as a drum machine
 * in GarageBand (sorry, Mac OS X only).
 */


#define PIEZOTHRESHOLD 5  // analog threshold for piezo sensing
#define PADNUM 4          // number of pads

int LEDPIN[4] = {13,12,11,10}; // define the LEDs Array

int val;

void setup() {
  pinMode(LEDPIN[0], OUTPUT); // Set the led 1 as an output
  pinMode(LEDPIN[1], OUTPUT); // Set the led 2 as an output
  pinMode(LEDPIN[2], OUTPUT); // Set the led 3 as an output
  pinMode(LEDPIN[3], OUTPUT); // Set the led 4 as an output
  Serial.begin(57600);   // set serial output rate
}

void loop() {

  // Loop through each piezo and send data
  // on the serial output if the force exceeds
  // the piezo threshold
  for(int i = 0; i < PADNUM; i++) {
    val = analogRead(i);
    if( val >= PIEZOTHRESHOLD ) {
      digitalWrite(LEDPIN[i],HIGH);  // light up the drum that has been hit
      Serial.print(i);
      Serial.print(",");
      Serial.print(val);
      Serial.println();
      digitalWrite(LEDPIN[i],LOW);
    }
  }
}
