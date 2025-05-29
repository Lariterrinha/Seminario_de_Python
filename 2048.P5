import random
import os

def main():
    global tabuleiro,movs,lets,posis
    tabuleiro = ["#","#","#","#",
                 "#","#","#","#",
                 "#","#","#","#",
                 "#","#","#","#"]
    
    movs = ["W","A","S","D"]
    lets = ["A","B","C","D","E","F","G","H","I","J","K"]

    posis = [0,1,2,3,4,5,6,7,8,9,10,11,12,13,14,15]

    aleatoria()
    aleatoria() 
    jogo()



def imprimir():
    cont = 0
    for i in tabuleiro:
        print(i,end=" "*4)
        cont+=1
        if cont==4:
            print("\n")
            cont=0


def movimentos(m):
    def mov(t,ordem,move,parede):
        if t==1:
            soma=0        
            for i in ordem:
                if tabuleiro[i] in lets:
                    a = i
                    
                    while True:
                        if not(0<=(a+move)<=15):
                            break
                        
                        if (tabuleiro[a+move]!="#" and tabuleiro[a+move]!= tabuleiro[a]) or (a in parede):
                            break
                        
                        if tabuleiro[a+move]== tabuleiro[a]:
                            aux = tabuleiro[a]
                            tabuleiro[a] = "#"
                            tabuleiro[a+move] = lets[lets.index(aux)+1]
                            soma += 1
                            break
                            
                        if tabuleiro[a+move]=="#":
                            aux = tabuleiro[a]
                            tabuleiro[a] = "#"
                            tabuleiro[a+move] = aux
                            a += move
                            soma =+ 1
                            
                
        if not(soma==0): aleatoria()
        jogo()
                      
    ordemw = [4,5,6,7,8,9,10,11,12,13,14,15]
    ordema = [1,2,3,5,6,7,9,10,11,13,14,15]
    ordems = [11,10,9,8,7,6,5,4,3,2,1,0]
    ordemd = [2,1,0,6,5,4,10,9,8,14,13,12]
    paredew = [0,1,2,3]
    paredea = [0,4,8,12]
    paredes = [12,13,14,15]
    pareded = [3,7,11,15]
    if m=="W": mov(1,ordemw,-4,paredew)
    if m=="A": mov(1,ordema,-1,paredea)
    if m=="S": mov(1,ordems,4,paredes)
    if m=="D": mov(1,ordemd,1,pareded)
    

def aleatoria():       
    a1 = random.choice(posis)
    
    while tabuleiro[a1] != "#":
        a1 = random.choice(posis)
        
    tabuleiro[a1] = lets[0]



def jogo():
    os.system('cls')
    imprimir()
    mov = input("\nMovimento: ").upper()
    while mov not in movs:
            os.system('cls')
            imprimir()
            mov = input("\nMovimento vaalido: ").upper()

    movimentos(mov)
    
main()
