# This is my journal

Week 29

What we did:
 We added a way to check if someone is recovered.
 
What I learned:
 Nothing new
 
Questions I have:
 No

Homework for next class:

```
posx=[] #this is a list
posy=[]
h=[]    #"sick", "healthy", "recovered"
days=[] #20-40=sick, -1=healthy
critd=40
init=20
initmove=init
recmin=25
inf=0
rndm=10
iter=0
initinf=1
he=init-initinf
rec=0

for i in range(initinf):
    h.append("sick")
    days.append(int(random(recmin,recmin+20)))
    if h[i]=="sick":
        inf+=1
    
def setup():
    global posx,posy
    size(500,500)
    
    for n in range(init):
        posx.append(int(random(0,500)))
        posy.append(int(random(0,500)))
        h.append("healthy")
        days.append(-1)

def distance(x1, x2, y1, y2):
    a=x1-x2
    b=y1-y2
    d=sqrt(a**2+b**2)
    return d

def draw():
    global posx,posy,iter,he,inf,rec,initmove
    
    background(200)

    iter+=1
    

    #creating the people
    for i in range(init):
        if h[i]=="healthy": 
            fill(255)

        elif h[i]=="sick":
            fill(255,0,0)
            days[i]-=1
            if days[i]==0:
                h[i]="recovered"
                inf-=1
                rec+=1
            
        else:
            fill(0,0,255)
            
        circle(posx[i],posy[i],10)
        
        for nei in range(len(posx)):
            d= distance(posx[i], posx[nei], posy[i], posy[nei])
            if nei==i:
                continue
            
            if d<critd and (h[nei]=="sick" or h[i]=="sick"):
                if h[i]=="sick" and h[nei]=="healthy":
                    he=he-1
                    inf=inf+1 
                    days[nei]=int(random(20,40))  
                    h[nei]="sick"
                    
                if h[i]=="healthy" and h[nei]=="sick":
                    he=he-1
                    inf=inf+1 
                    days[i]=int(random(20,40))
                    h[i]="sick"
                    
                
            
                
                        
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
            
    if he<=0:
        print("Everyone was infected.")
        print("Final stats")
        print("Iterations: {}".format(iter))
        print("Healthy: {}".format(he))
        print("Infected: {}".format(inf))
        print("Recovered: {}".format(rec))
        stop
    
    if inf<=0:
        print("Not everyone was infected.")
        print("Final stats")
        print("Iterations: {}".format(iter))
        print("Infected: {}".format(inf))
        print("Healthy: {}".format(he))
        print("Recovered: {}".format(rec))
        stop
        
    #Healthy
    fill(255)
    rect(400, 450, he*2, 10)
    
    fill(0)
    text("Healthy", 335, 460)
    text(he, 460, 460)
    
    #Infected
    fill(255,0,0)
    rect(400, 470, inf*2, 10)
    
    fill(0)
    text("Infected", 335, 480)
    text(inf, 460, 480)
    
    #Recovered
    fill(0,0,255)
    rect(400, 490, rec*2, 10)
    
    fill(0)
    text("Recovered", 335, 500)
    text(rec, 460, 500)
    
    #Iteration counter
    fill(0)
    text("Iteration: {}".format(iter), 10, 480)
    
    
    delay(0)
    
```
