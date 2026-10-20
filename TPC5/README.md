 # TPC4: Aplicação
  ## Autor

  - **Nome:** Andreia Teixeira Freitas
  - **ID:** A114696
  - **Foto:**
<img width="300" alt="foto yme" src="https://github.com/user-attachments/assets/903c123e-ad62-4d23-b9f4-e107634bc36c" />

  ## Resumo do TPC
  


def criarTurma():     
    lista = []
    return lista 

def lerNota (texto):
    nota = -1 #valor inválido de propósito, assim o while é verdadeiro à primeira vez e o ciclo corre
    while not (0 <= nota <= 20):
        try:
            nota=float(input(texto))
            if not 0 <= nota <= 20:
                print("A nota tem de ser entre 0 a 20.")
        except ValueError:
            print("o valor está inválido, escreve outra nota.")
    return nota

def inserirAluno(turma):
    nome = input("Nome: ")
    idAluno = input( "ID: ")
    notaTPC = lerNota("Nota do TPC: ")
    notaProj = lerNota("Nota do Projeto: ")
    notaTeste = lerNota("Nota do Teste: ")
    turma.append((nome, idAluno, [notaTPC, notaProj, notaTeste]))
    print("Aluno inserido na turma com sucesso.")
    return turma

def lerLista(turma):
    if len(turma) == 0:
        print("A turma não tem ninguém.")
        return
    for nome, idAluno, notas in turma:
        print(f"{nome} - {idAluno}: TPC={notas[0]}, Projetos={notas[1]}, Teste={notas[2]}")

def consultarAluno (turma, idAluno) :
    res = None
    for aluno in turma:
        if aluno[1] == idAluno:
            res = aluno
    return res 

def guardarTurma (turma):
    fnome = input("Nome do ficheiro: ")
    file = open(fnome,"w") # "r", "w"
    for nome, idAluno, notas in turma:
        file.write(f"{nome};{idAluno};{notas[0]};{notas[1]};{notas[2]}\n")
    file.close()
    print(f"{len(turma)} alunos guardados em {fnome}")

def carregarTurma (fnome):
    file = open(fnome, "r")
    turma = file.read()
    file.close()
    return turma
    
def menu ():
    turma = []
    comando = -1
    while comando != 0:
        print("1: Cria uma turma; ")
        print("2: Inserir um aluno na turma;")
        print("3: Lista a turma;")
        print("4: Consulta um aluno por id;")
        print("8: Guardar a turma em ficheiro;")
        print("9: Carregar uma turma dum ficheiro;")
        print("0: Sair da aplicação" )

        comando = int(input("Seleciona uma das opções anteriores:"))

        if comando == 1:
            turma = criarTurma ()
            print(f"Turma criada com sucesso: (vazio)")

        elif comando == 2:
            turma = inserirAluno (turma)
            print(f"Turma com novo aluno inserido: {turma}")

        elif comando == 3:
            turma = lerLista (turma)
            print(f"Turma listada: {turma}")

        elif comando == 4:
            idAluno = input("ID a consultar: ")
            aluno = consultarAluno (turma, idAluno)
            if aluno != None:
                print(f"Esse id corresponde ao aluno: {aluno[0]} ")
            else: 
                print("Aluno não encontrado.")

        elif comando == 8:
            guardarTurma (turma)

        elif comando == 9:
            fnome = input("Nome do ficheiro: ")
            turma = carregarTurma(fnome)
            print (f"A turma foi carregada com sucesso, {turma}")

        elif comando == 0 :
            print("A sua pesquisa vai ser encerrada. Obrigada!")

        else:
            print("Opção inválida.")
    

menu()
