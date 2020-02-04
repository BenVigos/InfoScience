# This is my journal

2nd class
What did we do?
Made the canvas bigger, coloured it, made circles, coloured them, made them print when we click the mouse, make them have text in them, make them have a delay

What I learned:
I learned the processing specific commands like delay(),mouseX and others, learned how to print text and colour the canvas

Questions I have:
For the 2nd homework assignment how can we make it so the first circle doesn't have a line? In other words how can I make only for the first circle x=px and y=py so then the line created has a length of 0?

Homework for next class:
1. Add lines from center of screen to center of circle
```.py
  def setup():
      size(500,500)
      background(255)
      textAlign(CENTER,CENTER)

  def draw():
      print("")


  def mouseClicked():
      x=mouseX
      y=mouseY
      r=random(0,100)
      myr=random(0,255)
      myg=random(0,255)
      myb=random(0,255)

      fill(myr,myg,myb)
      circle(x,y,r)

      fill(0)
      textSize(r/5)
      text("K.B.V.",x,y)

      line(x,y,250,250)
      
```
2. Add lines from circle to circle 

```.py
px=250
py=250
x=0
y=0
def setup():
    size(500,500)
    background(255)
    textAlign(CENTER,CENTER)

def draw():
    circle(0,0,0)
    

def mouseClicked(): 
    global px,py,x,y
    
    x=mouseX
    y=mouseY
    line(x,y,px,py)
    r=random(0,100)
    myr=random(0,255)
    myg=random(0,255)
    myb=random(0,255)
    fill(myr,myg,myb)
    circle(x,y,r)
   
    fill(0)
    textSize(r/5)
    text("K.B.V.",x,y)

    print (x,y)
    print(px,py)
    
    px=x
    py=y
    ```
    
