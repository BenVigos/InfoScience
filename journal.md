# This is my journal

Week 28

What we did:
1. Read the article "How your personal computer can help science battle the coronavirus while you sleep"

2. Watched introductory video.

3. Represented an individual with random movement within processing 

4. Represented many people with random movement within processing

What I learned:
1. I learned about protein simulations and how they can help find a cure to covid-19. I also learned about how protein simulations helped find a therapeutic utility for Ebola.

3. and 4. I learned how to set boundary conditions, how to create a list, how to add more items to that list and make those items random and how to itterate that procedure as many times as I want.
 
Questions I have:
 No

Questions set by teacher:
1. Computer science can help the fight against coronavirus by running simulations, specifically protein simulations that help us understand the virus and how to defeat it. But one computer alone doesn't have enough computational power to run these simulations. 
 That's where we come in. Everyone in the world could download specific software on their computer and allow it to use the computers hardware to make the simulation run faster. Of course there are risks, your computer and your personal information could be compromised, but the risk is smaller than entering a random website or downloading pirated content while the outtake could be much greater. That's why I believe that people should enable access to the resources of their personal computers as tools for research.
 
Homework for next class:
3. Set boundaries for all directions
4. Make a set of 10 individuals with random starting positions

```
posx=[] #this is a list
posy=[]
rndm=10

def setup():
    global posx,posy
    size(500,500)
    
    for i in range(10):
        posx.append(int(random(0,500)))
        posy.append(int(random(0,500)))
        
        
def draw():
    global posx, posy
    
    background(255)
  
    fill(0)
      
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
    
    delay(100)
    ```
