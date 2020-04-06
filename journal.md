# This is my journal

Week 29

What we did:
 Dove deeper into for loops. Did some exercises, for example printing x "bears" where x was the number of the for loop iteration.

 We continued our simulation by adding infected individuals and counters for the healthy, the infected and the number of iterations.

What I learned:
 Nothing new yet
 
Questions I have:
 Yes:
How can we check the distance between a circle and every other circle?
I suppose that we would need to create two lists? One for the healthy and one for the infected?

 
Homework for next class:
 The for loop tasks 1. 2. and 3. will be submited as photographs
 
 1. 2.
 ```
 posx=[] #this is a list
posy=[]
rndm=10
iter=0

def setup():
    global posx,posy
    size(500,500)
    
    for i in range(10):
        posx.append(int(random(0,500)))
        posy.append(int(random(0,500)))


def draw():
    global posx, posy, iter
    
    background(200)
  
    fill(255)
    
    iter=iter+1
        
    #creating the people
    for i in range(10):
        circle(posx[i],posy[i],10)
        
        posx[i]= posx[i]+random(-rndm,rndm)
        posy[i]= posy[i]+random(-rndm,rndm)
        
        #setting a boundary
        if posx[i]>500:
            posx[i]=500
                
        if posx[i]<0:
            posx[i]=0
            
        if posy[i]>500:
            posy[i]=500
            
        if posy[i]<0:
            posy[i]=0
    
    #Healthy
    fill(0)
    text("Healthy", 350, 460)
    text("10", 460, 460)
    
    
    fill(255)
    rect(400, 450, 50, 10)
    
    #Infected
    fill(0)
    text("Infected", 350, 480)
    text("0", 460, 480)
    
    fill(255,0,0)
    rect(400, 470, 5, 10)
    
    #Iteration counter
    fill(0)
    text("Iteration: "+str(iter), 10, 480)
    
    
    delay(100)
```
