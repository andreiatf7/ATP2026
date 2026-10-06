 # TPC3: Jogo de 

  ## Autor

  - **Nome:** Andreia Teixeira Freitas
  - **ID:** A114696
  - **Foto:**
<img width="300" alt="foto yme" src="https://github.com/user-attachments/assets/903c123e-ad62-4d23-b9f4-e107634bc36c" />

  ## Resumo do TPC
  Neste trabalho, desenvolvi um programa em Python para o jogo “Adivinha o Número”. O programa permite jogar em duas modalidades: o computador escolhe um número entre 0 e 100 e o utilizador tenta adivinhar, ou o utilizador escolhe um número e o computador tenta descobri-lo.
  Durante o jogo, são dadas indicações sobre se o número escolhido é maior ou menor que a tentativa realizada. O programa repete as tentativas até o número ser descoberto e, no final, apresenta o número de tentativas necessárias para chegar à resposta.
  
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
        
