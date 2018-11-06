# mad007
basic surface loop

![mad007](https://github.com/nicolasbaez/mad007/blob/master/mad007.gif)

```processing
float w;
float k=0;
float dSpace=0;
void setup() {
  size(512, 256);
  background(255);
  smooth();
  noStroke();
  fill(0);
  w=width/16;
}
void draw() {
  background(255);
  translate(width/2, height/2);
  pushMatrix();
  rotate(radians(dSpace));
  for (float i=-width*2; i<=width*2; i+=w) {
    for (float j=-height*2; j<=height*2; j+=w) {
      float wTemp=map(sin(radians(i+k)), -1, 1, w*0.9, w);
      rect(i-wTemp/2, j-wTemp/2, wTemp, wTemp);
    }
  }
  popMatrix();
  k++;
  dSpace+=0.5;
  if (k<=720) {
    saveFrame("gif/mad007-######.png");
  }
}
```
