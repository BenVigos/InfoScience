# This is my journal

3d class

What did we do?
We made a fair dice, then an unfair one where one of the numbers shows up more. We changed the dice's and circle's thickness and colour

What I learned:
How to use the rectangle command and how to change the thickness and the colour of the lines

Questions I have:
No


Homework for next class:
make a program that counts how many times each number has been rolled

(I made the ratio 1/10, so for each roll the size of the appropriate bar increases by 1/10)

```
r1=0
r2=0
r3=0
r4=0
r5=0
r6=0
total=0
def setup():
    size(600,600)
    background(255)

    


def tr():
    circle(200,200,50)
    
def mr():
    circle(200,300,50)
    
def br():
    circle(200,400,50)
    
def mm():
    circle(300,300,50)
    
def tl():
    circle(400,200,50)
    
def ml():
    circle(400,300,50)
    
def bl():
    circle(400,400,50)
    
def one():
    mm()
    
def two():
    tl()
    br()
    
def three():
    tl()
    mm()
    br()
    
def four():
    tl()
    bl()
    tr()
    br()
    
def five():
    tl()
    bl()
    mm()
    tr()
    br()
    
def six():
    tl()
    ml()
    bl()
    tr()
    mr()
    br()

def draw():
    global r1,r2,r3,r4,r5,r6,total
    
    background(255)
    
    fill(255,255,255)
    n=random(0,6)
    
    strokeWeight(5)
    stroke(0,0,0)
    rect(100,100,400,400,20)
    strokeWeight(10)
    stroke(255,0,0)
    
    if 0<=n<1:
        one()
        r1=r1+1
        
    if 1<=n<2:
        two()
        r2=r2+1
    if 2<=n<3:
        three()
        r3=r3+1
    if 3<=n<4:
        four()
        r4=r4+1
    if 4<=n<5:
        five()
        r5=r5+1
    if 5<=n<6:
        six()
        r6=r6+1
        
    fill(0,0,0)
    textSize(20)   
     
    text("1",30,590)
    rect(30,565,10,-r1/10)
    
    text("2",100,590)
    rect(100,565,10,-r2/10)
    
    text("3",170,590)
    rect(170,565,10,-r3/10)
    
    text("4",240,590)
    rect(240,565,10,-r4/10)
    
    text("5",310,590)
    rect(310,565,10,-r5/10)
    
    text("6",380,590)
    rect(380,565,10,-r6/10)
    
    text("total",450,590)
    text(total,500,590)
    
    total=total+1  
    ```
