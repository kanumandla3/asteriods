float shipX;//initial location
float shipY;//initial location
float shipAngle;
float direction;//ships's direction
PVector location;//ships's location
PVector velocity;//ship's speeds
PVector accel;//ship acceleration
 
 
 
void setup() {
  size(500, 500);
 
 
  location = new PVector(width/2, height/2, 0);
  velocity = new PVector();
  accel = new PVector();
 
  shipX = width/2;
  shipY = height/2;
 
  shipAngle = 0.0;
 
}
 
 
 
void draw() {
 
  checkKeys();
 
  background(0);
  stroke(0);
 
  velocity.add(accel);
  location.add(velocity);
  drawShip();
 
  accel.set(0, 0, 0);
  if (velocity.mag() != 0) velocity.mult(0.99);
 
  //wrap function
  if (location.x<0) {
    location.x = location.x+width;
  }
   if (location.x>width) {
      location.x = 0;
    }
    if (location.y<0) {
      location.y = location.y+height;
    }
    if (location.y>height) {
      location.y = 0;
    }
}
 
  void drawShip() {
 
 
  pushMatrix();
    // Translate ship origin
    translate(location.x, location.y);
 
    // Rotate ship
    rotate(direction);
 
    // Display the ship
    fill(105,95,95);
    stroke(255,0,0);
    triangle(-10, 20, 10, 20, 0, -20);
 
    // if the ship is accelerating draw a thruster
    if (accel.mag() != 0) {
 
    float thrusterCol = random(0,255);//thuster feature that appears behind the ship when accelerating
    fill(thrusterCol, thrusterCol/2, 0);
    triangle(-5, 22, 5, 22, 0, 40);
  }
  popMatrix();
 
  }
 
//moving the ship
void checkKeys() {
   if (keyPressed && key == CODED) {
    if (keyCode == LEFT) {
      direction-=0.1;
    }
    else if (keyCode == RIGHT) {
      direction+=0.1;
    }
    else if (keyCode == UP) {
      float totalAccel = 0.2;                 // how much ship accelerates
      accel.x = totalAccel * sin(direction);  // total accel
      accel.y = -totalAccel * cos(direction); // total accel
    }
   }
}
