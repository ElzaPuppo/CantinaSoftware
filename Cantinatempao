#import sys
from random import randint


nomes = []
precos = []
qtds = []
cod = []
cod_ver = []

def cadastrar_produto():
    n = input("\nInforme o nome do produto (sem espaços): ")
    p = float(input("\nInforme o preço do produto: "))
    q = int(input("\nInforme a quantidade do produto: "))
    conteudo.append('\n')
    conteudo.append(n + ' ' + str(p) + ' '  + str(q))
    c = randint(0, 1000)
    while(c in cod):
        c = randint(0,1000)
    cod.append(c)
    nomes.append(n)
    precos.append(p)
    qtds.append(q)

def modificar_produto(c, par, qtd, incr, decr, nome, preco):
    if int(c) in cod_ver: # se o código corresponder a um produto cadastrado
        if(par is 0): # se o parâmetro é 0, modificar quantidade
            qtds[cod.index(int(c))] = qtd
        elif(par is 1): # se o parâmetro é 1, incrementa a quantidade
            (qtds[cod.index(int(c))]) += incr
        elif(par is 2): # se o parâmetro é 2, decrementa a quantidade
            if(int(qtds[cod.index(int(c))]) >= int(decr)):
                (qtds[cod.index(int(c))]) = str((int(qtds[cod.index(int(c))]) - int(decr)))
        elif(par is 3): # se o parâmetro for 3, muda o nome
            nomes[cod.index(int(c))] = nome
        elif(par is 4):
            precos[cod.index(int(c))] = preco
        

        conteudo[cod.index(int(c))] = (nomes[cod.index(int(c))] + ' ' + precos[cod.index(int(c))] + ' '  + str(qtd) + '\n')



def listar_produtos():
    print("\nCÓDIGO\t\t\tNOME\t\t\tQUANTIDADE\t\tVALOR\n")
    for c in cod: # isso aqui falta ajeitar a função pra identar certinho, ou fazer de forma gráfica
        print(str(c) + "\t\t\t" + str(nomes[cod.index(c)]) + "\t\t\t" + str(qtds[cod.index(c)]) + "\t\t\t" + str(precos[cod.index(c)]))
        #print(f"{20:str(c)}{20:str(nomes[cod.index(c)])}{20:str(qtds[cod.index(c)])}{str(precos[cod.index(c)])}")


# -------------- LEITURA DO ARQUIVO DE ENTRADA ------------
#arquivo = input('Digite o nome do arquivo: ') # recebe o arquivo de entrada como parâmetro no terminal


from google.colab import files
arquivo = files.upload()
#entrada = open(arquivo) # lê esse arquivo
conteudo = arquivo
conteudo



for linha in conteudo: # para cada linha no arquivo, divide em 3 vetores diferentes, um para o nome, um para preço e um para quantidade
    valores = linha.split()
    c = randint(0,1000)
    while(c in cod_ver):
        c = randint(0,1000)
    cod.append(c)
    cod_ver.append(c)
    nomes.append(valores[0])
    precos.append(valores[1])
    qtds.append(valores[2])



# ------------------ MENU --------------------------

print(" _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ __ ")
print("|                                                                                  |")
print("|                             NA CANTINA TEM PÃO?                                  |")
print("|_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _  _ _ _ _ _|\n")
print('----------NA CANTINA TEM PÃO?----------')
print('1 - Cadastrar produto')
print('2 - Visualizar produtos')
print('3 - Remover produto')
print('4 - Modificar quantidade')
print('5 - Aumentar quantidade')
print('6 - Diminuir quantidade')
print('7 - Mudar nome do produto')  
print('8 - Mudar o preço do produto')
print('9 - Realizar venda')
print('10 - Fechar')
opcao = input()
while(opcao != '10'):
    if(opcao == '1'):
        cadastrar_produto()
    elif(opcao == '2'):
        listar_produtos()
        print('\n')
    elif(opcao == '3'):
        remove = input('Informe o nome do produto que deseja remover: ')
        indice = nomes.index(remove)
        del(nomes[indice])
        del(cod[indice])
        del(precos[indice])
        del(qtds[indice])
    elif(opcao == '4'):
        listar_produtos()
        print("Informe o código do produto: ")
        cod_mod = input()
        print('Informe a quantidade que há disponível do produto: ')
        #print('Informe a quantidade que há disponível do produto: ' + nomes[cod.index(cod_mod)])
        qtd_mod = input()
        modificar_produto(cod_mod, 0, qtd_mod, 0, 0, '', precos[cod.index(int(cod_mod))])
        listar_produtos()
    elif(opcao == '5'):
        listar_produtos()
        print("Informe o código do produto: ")
        cod_mod = input()
        if(int(cod_mod) in cod):
            print('Informe em quanto deseja aumentar a quantidade: ')
            incr = input()
            modificar_produto(cod_mod, 1, 0, incr, 0, '', precos[cod.index(int(cod_mod))])
            listar_produtos()
        else:
            print('Código inválido')
    elif(opcao == '6'):
        listar_produtos()
        print("Informe o código do produto: ")
        cod_mod = input()
        if(int(cod_mod) in cod):
            print(cod_mod)
            print('Informe em quanto deseja diminuir a quantidade: ')
            decr = input()
            print(cod.index(int(cod_mod)))
            if(int(decr) <= int(qtds[cod_ver.index(int(cod_mod))])):
                modificar_produto(cod_mod, 2, 0, 0, decr, '', precos[cod.index(int(cod_mod))])
            else:
                print('A quantidade não pode ficar negativa')
            listar_produtos()
        else:
            print('Código inválido')
    elif(opcao == '7'):
        listar_produtos()
        print("Informe o código do produto: ")
        cod_mod = input()
        if(int(cod_mod) in cod):
            print('Informe o novo nome do produto: ')
            n = input()
            modificar_produto(cod_mod, 3, qtds[cod.index(int(cod_mod))], 0, 0, n, precos[cod.index(int(cod_mod))])
            listar_produtos()
    elif(opcao == '8'):
        listar_produtos()
        print("Informe o código do produto: ")
        cod_mod = input()
        if(int(cod_mod) in cod):
            print('Informe o novo preço do produto: ')
            p = input()
            modificar_produto(cod_mod, 4, qtds[cod.index(int(cod_mod))], 0, 0, nomes[cod.index(int(cod_mod))], p)
            listar_produtos()
    elif(opcao == '9'):
        listar_produtos()
        print("Informe o código do produto: ")
        cod_mod = input()
        if(int(cod_mod) in cod):
            print(cod_mod)
            print('Informe a quantidade que deseja vender: ')
            decr = input()
            print(cod.index(int(cod_mod)))
            if(int(decr) <= int(qtds[cod_ver.index(int(cod_mod))])):
                modificar_produto(cod_mod, 2, 0, 0, decr, '', precos[cod.index(int(cod_mod))])
            else:
                print('Venda bloqueada! Quantidade insuficiente.')
            listar_produtos()
        
    
    if(opcao != '1' and opcao != '2' and opcao != '3' and opcao != '4' and opcao != '5' and opcao != '6' and opcao != '7' and opcao != '8' and opcao != '9' and opcao != '10'):
        print('Opção inválida, por favor, digite novamente: ')
    else:
        print('----------NA CANTINA TEM PÃO?----------')
    print('1 - Cadastrar produto')
    print('2 - Visualizar produtos')
    print('3 - Remover produto')
    print('4 - Modificar quantidade')
    print('5 - Aumentar quantidade')
    print('6 - Diminuir quantidade')
    print('7 - Mudar nome do produto')
    print('8 - Mudar preço do produto')
    print('9 - Realizar venda')
    print('10 - Fechar')
    opcao = input()


    
entrada = open(arquivo, 'w')
entrada.writelines(conteudo)
entrada.close()