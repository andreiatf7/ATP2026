
 # TPC4: Aplicação
  ## Autor

  - **Nome:** Andreia Teixeira Freitas
  - **ID:** A114696
  - **Foto:**
<img width="300" alt="foto yme" src="https://github.com/user-attachments/assets/903c123e-ad62-4d23-b9f4-e107634bc36c" />

  ## Resumo do TPC
  
  Desenvolvi uma aplicação em Python com um menu interativo que permite criar uma lista de números (aleatória ou introduzida pelo utilizador) e realizar operações sobre ela: soma, média, maior, menor, verificação de ordenação crescente ou decrescente e procura de um elemento. O programa está organizado em funções, usa ciclos while para percorrer a lista e termina quando o utilizador escolhe a opção 0, mostrando a lista guardada.

-----------------------------
  ## Resultado


```python

import random

def menu():
    lista = []
    opcao = -1
    while opcao != 0:
        
        print("(1) Criar Lista")
        print("(2) Ler Lista")
        print("(3) Soma")
        print("(4) Média")
        print("(5) Maior")
        print("(6) Menor")
        print("(7) estaOrdenada por ordem crescente")
        print("(8) estaOrdenada por ordem decrescente")
        print("(9) Procura um elemento")
        print("(0) Sair")
    
        opcao = int(input("Seleciona uma das opções de 0-9:"))

        if opcao == 1:
            lista = criarlista()
            print(f"Lista criada com sucesso : {lista}")

        elif opcao == 2:
            lista = Lerlista()
            print(f"Lista lida com sucesso : {lista}")

        elif opcao >= 3 <=9 and len(lista) == 0:
            print("A lista está vazia! Use primeiro a opção 1 ou 2.")

        elif opcao == 3:
            print(f"Soma dos elementos: {soma(lista)}")

        elif opcao == 4:
            print(f"Média dos elementos : { média(lista)}")

        elif opcao == 5:
            print(f"Maior elemento : {maior(lista)}")

        elif opcao == 6:
            print(f"Menor elemento : {menor(lista)}")

        elif opcao == 7:
            print(f"Ordenada por ordem crescente? {estaOrdenadaCrescente(lista)}")

        elif opcao == 8:
            print(f"Ordenada por ordem decrescente? {estaOrdenadaDecrescente(lista)} ")

        elif opcao == 9:
            elem = int(input("Qual o elemento que procuras?"))
            print(f"Posição do elemento (-1 se não existir): {procuraelem(lista, elem)}")

        elif opcao == 0 :
            print("Fim do programa!")
            print(lista)


def criarlista ():
    N = int(input("Introduza a quantidade de números que quer na sua lista: "))
    i=0
    lista = []
    comprimento = random.randint(1,10)
    while i < N:
        n = random.randint(1,100)
        lista.append(n)
        i = i + 1
    return lista

def Lerlista() :
    lista = []
    N = int(input("Introduza o total de algarismos que quer por na lista"))
    i = 0
    while i < N:
        n = int(input("Introduza um número inteiro"))
        lista.append(n)
        i = i + 1
    
    return lista

def soma (lista):
    i=0
    soma=0
    while i<len(lista):
        soma = soma + lista[i]
        i=i+1

def média (lista):
    i = 0
    soma=0
    while i<len(lista):
        soma = soma + lista[i]
        i=i+1
    média = soma/len(lista)
    return média
    
def maior(lista):
    i=0
    maior=lista[0]
    while i<len(lista):
        if lista[i]>maior:
            maior=lista[i]
        i=i+1
    return maior

def menor(lista):
    i=0
    menor=lista[i]
    while i<len(lista):
        if lista[i]<menor:
            menor=lista[i]
        i=i+1
    return menor

def estaOrdenadaCrescente(lista):
    res = True
    i = 0
    while i < len(lista)-1 and res == True:
        if lista[i]>lista[i+1]:
            res = False
    return res

def estaOrdenadaDecrescente(lista):
    res = True
    i = 0
    while i < len(lista)-1 and res == True:
        if lista[i]<lista[i+1]:
            res = False
    return res

def procuraelem(lista, elem):
    i=0
    res=-1
    while i<len(lista) and elem != lista[i]:
        i=i+1
    if i<len(lista):
        res=i
    return res

menu ()
