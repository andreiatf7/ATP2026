 # TPC3: Jogo "Corrida para o 100"

  ## Autor

  - **Nome:** Andreia Teixeira Freitas
  - **ID:** A114696
  - **Foto:**
<img width="300" alt="foto yme" src="https://github.com/user-attachments/assets/903c123e-ad62-4d23-b9f4-e107634bc36c" />

  ## Resumo do TPC
  
  Neste trabalho, desenvolvi um programa em Python para o jogo “Corrida para o 100”. Neste jogo, o total começa em 0 e o jogador e o computador jogam alternadamente, adicionando um número entre 1 e 10 ao total. O objetivo é atingir exatamente o número 100, sendo vencedor quem conseguir chegar primeiro a esse valor. O programa apresenta duas possibilidades: na primeira, o computador joga primeiro e utiliza uma estratégia que lhe permite garantir a vitória; na segunda, o computador joga em segundo lugar, podendo ganhar ou perder dependendo das jogadas realizadas pelo jogador.
  
-----------------------------
  ## Resultado


```python
import random

def jogada_computador(total):
    if total % 11 != 1:
        return (1 - total) % 11
    return random.randint(1, min(10, 100 - total))

print("O total começa em 0. O jogador e o computador alternam somando um número de 1 a 10 ao total. Quem atingir exatamente o número 100 vence. Estás pronto para jogar?")

menu = -1

while menu != 0:

    if menu == 1:
        total = 0
        while total < 100:
            n = int(input("Escolhe um número inteiro de 1 a 10: "))
            total += n
            #print("Total", total)
            if total == 100:
                print("Venceste!")
                menu = -1
                break

            n = jogada_computador(total)
            total += n
            print("O computador soma", n)
            print("Total", total)
            if total == 100:
                print("O computador venceu!")
                menu = -1

    elif menu == 2:
        total = 0
        while total < 100:
            n = jogada_computador(total)
            print("O computador soma", n)
            total += n
            print("Total", total)
            #print("Total", total)
            if total == 100:
                print("O computador venceu!")
                menu = -1
                break

            n = int(input("Escolhe um número inteiro de 1 a 10: "))
            total += n
            print("Total", total)
            if total == 100:
                print("Venceste!")
                menu = -1

    elif menu == 0:
        exit
    else:
        print("Escolhe uma das seguintes opções:")
        print("1 - Quero jogar primeiro.")
        print("2 - O computador joga primeiro.")
        print("0 - Sair do jogo")
        texto = input("Resposta: ")
        if texto.isdigit():
            menu = int(texto)
            texto = -1
        else:
            menu = -1
print("Terminou o jogo!")
        
