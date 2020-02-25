# This is my journal

4th class

What did we do?
Made a checker board and made it move therefore creating an optical illusion

What I learned:
Got a better understanding of how to use the for command

Questions I have:
No


Homework for next class:
Make an optical Illusion

```
offset=295
def setup():
    size(1000,500)
    background(255)
    textAlign(CENTER,CENTER)
    
def purple():
    stroke(136, 136, 165)
    fill(136, 136, 165)

def orange():
    stroke(224, 130, 0)
    fill(224, 130, 0)
    
def mouseClicked():
    global offset 
    offset=offset+15
    
    if offset>900:
        offset=295
    
    
def draw():
    global offset
    
    background(255)
    
    fill(0)
    stroke(0)
    circle(900,250,70)
    
    textSize(30)
    text("Click mouse to move",500,50)
    
    fill(255)
    textSize(10)
    text("Here to reset",900,250)
    
    purple()
    circle(250,170,80)
    circle(210,250,80)
    circle(250,330,80)
    
    circle(340,170,80)
    circle(380,250,80)
    circle(340,330,80)

    orange()
    circle(offset,250,50)
    
    purple()
    circle(670,285,30)
    circle(655,250,30)
    circle(670,215,30)
    
    circle(705,300,30)
    circle(705,200,30)
    
    circle(740,285,30)
    circle(755,250,30)
    circle(740,215,30)

    orange()
    circle(705,250,50)```
