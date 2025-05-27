# projeto-da-biblioteca
livros = []
emprestados = []
matriz = []

while True:
    print('='*30)
    print("bem vindo a biblioteca")
    print("você é aluno ou funcionario ? ")
    print('='*30)
    resp1 = input("resposta: ")

    if resp1 == "funcionario":
        while True:
            print('=' * 30)
            print("==========BEM VINDO===========")
            print("O QUE DESEJA FAZER")
            print("1.ADICIONAR LIVRO")
            print("2.MOSTRAR LIVROS DISPONIVEIS")
            print("3.REMOVER LIVRO")
            print("4.MOSTRAR LIVROS EMPRRESTADO")
            print("5.TROCAR DE USUARIO")
            print("0.SAIR")
            print('=' * 30)
            respf = int(input("selecione a opção desejada: "))

            if respf == 0:
                print("encerrando programa")
                exit()

            elif respf == 1:
                d = int(input("digite a quantidade de livros que você deseja adicionar: "))
                for c in range(0, d):
                    livro = (input("digite o nome do livro: "))
                    livros.append(livro)

            elif respf == 2:
                print("aqui esta a lista de todos os livros disponiveis")
                print(f"{livros}")

            elif respf == 3:
                print(f"aqui esta a lista de livros: {livros}")
                remove = (input("digite o nome do livro que você deseja remover: "))
                if remove in livros:
                    print("o livro foi removido com sucesso")
                    livros.remove(remove)
                else:
                    print("!!!!!!!!!!!!!!!! ERRO !!!!!!!!!!!!!!!!!!")
                    print("por favor selecione um livro disponivel")

            elif respf == 4:
                print(f"aqui estão todos os livros emprestados no momento \n {emprestados}")

            elif respf == 5:
                break 

    elif resp1 == "aluno":
        while True:
            print('=' * 30)
            print("==========BEM VINDO===========")
            print("OQUE DESEJA FAZER")
            print("1.PEGAR LIVRO")
            print("2.DEVOLVER LIVRO")
            print("5.TROCAR DE USUARIO")
            print("0.SAIR")
            print('=' * 30)
            respa = int(input("selecione a opção desejada: "))

            if respa == 0:
                print("encerrando programa")
                exit()

            elif respa == 1:
                print(f"aqui esta a lista dos livros disponiveis no momento {livros}")
                data = input("digite a data que o livro esta sendo emprestado (DD/MM/AA): ")
                matricula = input("por favor digite sua matricula")
                emprestimo = input("digite o  nome do livro que deseja pegar: ")

                if emprestimo in livros:
                    livros.remove(emprestimo)
                    emprestados.append(emprestimo)
                    matriz.append((matricula, data, emprestimo))
                else:
                    print("o livro selecinado nao esta cadastrado em nosso sistema")

            elif respa == 2:
                devm = input("digite sua matricula:")
                devd = input("digite a data do emprestimo:")
                devl = input("digite o livro que voce ira devolver:")

                if (devm, devd, devl) in matriz:
                    matriz.remove((devm, devd, devl))
                    livros.append(devl)
                    emprestados.remove(devl)
                    print(f"o livro {devl} foi devolvido com sucesso")
                else:
                    print("o livro que voce esta tentando devolver não está registrado como emprestado")

            elif respa == 5:
                break 
