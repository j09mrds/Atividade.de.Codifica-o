# Atividade.de.Codifica-o
#Controle de Produtos de Higiene de bebês (python)
#Sistema de uma empresa de revenda de produtos higiênicos de bebês(baseado em uma empresa real)
# Fraldas, Pomadas, Sabonete liquido, lenço umidecido, entre outros


class Produto:
    def __init__(self, nome, marca, quantidade, validade, fornecimento, lote_demanda):
        self.nome = nome
        self.marca = marca
        self.quantidade = quantidade
        self.validade = validade
        self.fornecimento = fornecimento
        self.lote_demanda = lote_demanda

class ControleHigiênico:
    def __init__(self):
        self.produtos = []

    def CadastrarProduto(self, nome, marca, quantidade, validade, fornecimento, lote_demanda):
        produto = Produto(nome, marca, quantidade, validade, fornecimento, lote_demanda)
        self.produtos.append(produto)
        print("Produto Higiênico foi cadastrado!")

    def BuscarProduto(self, nome):
        for produto in self.produtos:
            if produto.nome == nome:
                print("Produto encontrado:")
                print("Nome:", produto.nome)
                print("Marca:" produto.marca)
                print("Quantidade:" produto.quantidade)
                print("Validade:" produto.validade)
                print("Fornecimento:" produto.fornecimento)
                print("Lote da demanda:" produto.lote_demanda)
                return
        print("Produto não encontrado no sistema, se necessário reinicie o processo.")

    def ExibirEstoque(self):
        print("Estoque:")
        for produto in self.produtos:
            print("Nome:", produto.nome)
            print("Quantidade:", produto.quantidade)
            print("Marca:", produto.marca)
        
    def RegistrarVenda(self, nome, marca, quantidade):
        for produto in self.produtos:
            if produto.nome == nome:
                if produto.quantidade >= quantidade:
                    prduto.marca = marca
                    produto.quantidade -= quantidade
                    print("Venda de produtos higiênicos realizado com sucesso!")
                    return
                else:
                    print("Insuficiência no estoque para essa revenda.")
                    return
        print("O produto não encontrado no estoque.")

    def EncontrarRelatorio(self):
        print("Relatório de Estoque:")
        for produto in self.produtos:
             print("Nome:", produto.nome)
             print("Marca:" produto.marca)
             print("Quantidade:" produto.quantidade)
             print("Validade:" produto.validade)
             print("Fornecimento:" produto.fornecimento)
             print("Lote da demanda:" produto.lote_demanda)

    def ExibirMenu():
        print("Opções de ações no sistema (O Menu)")
        print("1. Cadastrar Produto Higiênico de bebê")
        print("2. Buscar Produto Higiênico de bebê")
        print("3. Exibir Estoque de abastacimento")
        print("4. Registrar Venda e Revendas")
        print("5. Encontrar Relatório de Funcionamento")
        print("6. Sair do Sistema ")

controle = ControleHigiênico()

while True:
    ExibirEstoque()
    opcao = input("Selecione a opção que deseja: ")

    if opcao == "1":
        nome = input("Digite o nome do produto que deseja cadastrar: ")
        marca = input("Digite o nome da marca do produto:")
        quantidade = int(input("Digite a quantidade do produto:"))
        validade = input("Digite qual é a validade do produto a registrar:")
        fornecimento = input("Digite o nome da empresa de fornecimento")
        lote_demanda= input("Digite o lote desse produto: ")
       
        controle.CadastrarProduto( nome, marca, quantidade, validade, fornecimento, lote_demanda)
        print()

    elif opcao == "2":
        nome = input("Digite o nome do produto que deseja procurar no sistema: ")
        controle.BuscarProduto(nome)
        print()

    elif opcao == "3":
        controle.ExibirEstoque()
        print()

    elif opcao == "4":
        nome = input("Digite o nome do produto: ")
        quantidade = int(input("Digite a quantidade vendida: "))
        controle.RegistrarVenda(nome, marca, quantidade)
        print()

    elif opcao == "5":
        controle.EncontrarRelatorio()
        print()

    elif opcao == "6":
        print("Finalização do sistema.")
        break

    else:
        print("Opção foi considerada inválida. Tente novamente e reinice o sistema.")
        print()
