# Lista-de-compras
é uma lista de compras simples, que pode: adicionar, remover ou listar os itens de dentro da lista
#lista de compras
print('Lista de compras')
print('-' * 10)

import os

lista_compras = []
letras_permitidas = 'ail'

while True:
    
    lista = input('Selecione uma opção:\n'
                  '[i]inserir [a]apagar [l]listar: ')

    if len(lista) > 1:
        print('Digite apenas uma letra.')
        continue

    elif lista == '':
        print('Digite pelo menos uma letra.')
        continue

    elif lista not in letras_permitidas:
        print('Digite uma das letras indicadas.')
        continue

    if lista.lower() == 'i':
        produto = input('Digite qual produto deseja adicionar na lista: ')
        if len(produto) < 1:
            print('Você precisa digitar algum produto para adicionar na lista.')
            continue
        lista_compras.append(produto)
        os.system('cls')

    
    elif lista_compras == []:
        print('A lista está vazia.')
        continue

    elif lista.lower() == 'l':
        for item in enumerate(lista_compras):
            numero, produto = item
            print(f'Número: {numero}\n', f'Produto: {produto}')
    
    try:

        if lista.lower() == 'a':
            apagar_produto = int(input('Digite o número do produto que deseja remover da lista: '))
            lista_compras.pop(apagar_produto)
            os.system('cls')
    except:
        print('Não foi possível deletar o item, pois ele não existe. Favor, digitar um item válido.')
    
