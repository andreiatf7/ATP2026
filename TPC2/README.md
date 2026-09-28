
  # TPC2: Jogo de Adivinhar o número

  ## Autor

  - **Nome:** Andreia Teixeira Freitas
  - **ID:** A114696
  - **Foto:**
<img width="300" alt="foto yme" src="https://github.com/user-attachments/assets/903c123e-ad62-4d23-b9f4-e107634bc36c" />

  ## Resumo do TPC
  Desenvolvi um barco no Blockly Games, utilizei diferentes blocos para programar os movimentos necessários para fazer o desenho. Foi também realizada a resolução do exercício 10 do Maze.

  ## Resultado


cont_jogo1 = 0
cont_jogo2 = 0
menu = 9

while menu != 0:
    if menu == 1:
        print ("Advinha o número!")
        jogo1 = int(input("Escolhe um número inteiro de 0 a 100:"))

        import random

        pc1 = random.randint(0, 100)

        while jogo1 != pc1:
            if jogo1 > pc1:
                print("Escolhe um número menor")
            else:
                print("Escolhe um número maior")
            cont_jogo1 = cont_jogo1 + 1
            jogo1 = int(input("Escolhe um número inteiro de 0 a 100:"))
        print ("Boa! Adivinhaste o número.")
        print ("O número de tentativas foi =",cont_jogo1 )

        break

    elif menu == 2:
        print("Programa2:")

        print ("Pensa num número!")

        minimo = 0
        maximo = 100

        correto = 0

        while correto == 0:


            import random

            pc2 = random.randint(minimo, maximo)
            print("O número é:", pc2)
            feedback = int(input("1- Acertou \n2-O número que pensei é menor\n3- O número que pensei é maior\n Resposta: "))
            cont_jogo2 = cont_jogo2 + 1

            if feedback == 1:
                print("Jogo concluído!")
                correto = 1
                print ("O número de tentativas foi =",cont_jogo2 )
                break
            elif feedback == 2:
                maximo = pc2 - 1
            else:
                minimo = pc2 + 1   
        break

    else:
        print("Escolhe uma das seguintes opções:")
        print("1 - Adivinha o número pensado pelo jogo")
        print("2- Escolhe o número e deixa o jogo adivinhar")
        print("0- Sair do jogo")

        menu = int(input("Resposta:"))

print("Terminou o jogo")
  
