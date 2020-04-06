# This is my journal

Week 29

What we did:
 Dove deeper into for loops. Did some exercises, for example printing x "bears" where x was the number of the for loop iteration.

 We continued our simulation by adding infected individuals and counters for the healthy, the infected and the number of iterations.

What I learned:
 Nothing new yet
 
Questions I have:
 Yes:
Could I maybe have some extra resources to advance faster?

 
Homework for next class:
 The for loop tasks 1. 2. and 3. will be submited as photographs
 
 1., 2., 3.
```
posx=[] #this is a list
posy=[]
h=[False, True] #False=infected
init=25
initmove=init
he=init-1
inf=1
rndm=10
iter=0

def setup():
    global posx,posy
    size(500,500)
    
    for n in range(init):
        posx.append(int(random(0,500)))
        posy.append(int(random(0,500)))
        h.append(True)
        
def distance(x1, x2, y1, y2):
    a=x1-x2
    b=y1-y2
    d=sqrt(a**2+b**2)
    return d

def draw():
    global posx,posy,iter,he,inf,initmove
    
    background(200)
  
    fill(255)
    
    iter=iter+1
        
    #creating the people
    for i in range(init):
        if h[i]==True: 
            fill(255)
            hs=True
        else:
            fill(255,0,0)
            hs=False
            
        circle(posx[i],posy[i],10)
        
        for nei in range(len(posx)):
            d= distance(posx[i], posx[nei], posy[i], posy[nei])
            if nei==i:
                continue
            
            if d<40 and (h[nei]==False or h[i]==False):
                if h[i]==False and h[nei]==True:
                    he=he-1
                    inf=inf+1    
                h[i]=False
                h[nei]=False
                
                
        if hs==True and h[i]==False:
            he=he-1
            inf=inf+1
        
        for m in range(initmove):        
            posx[m]+= random(-rndm,rndm)
            posy[m]+= random(-rndm,rndm)
            
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
    fill(255)
    rect(400, 450, he*2, 10)
    
    fill(0)
    text("Healthy", 350, 460)
    text(he, 460, 460)
    
    #Infected
    fill(255,0,0)
    rect(400, 470, inf*2, 10)
    
    fill(0)
    text("Infected", 350, 480)
    text(inf, 460, 480)
    
    #Iteration counter
    fill(0)
    text("Iteration: "+str(iter), 10, 480)
    
    
    delay(100)
```
