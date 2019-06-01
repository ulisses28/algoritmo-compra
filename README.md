Slide Type
Algoritimo Compras
fazendo uma analise no ramo de tecnologia,e analizando o mercado de compras,nos deparamos com avanço das tecnologias web que vem facilitando a vida dos clientes,atravéz de sites que permitem fazer compras de um certo ponto a varios lugares do mundo,em comparação com a mercantilização das capitanias do seculo XXV até aqui,vemos que o mercado de comercialização evoluiu gradativamente,aprimorando cada vez mais os meios de comunicação e transportes. A logistica faz parte dessa evolução,o que podemos chamar de Cadeia de suprimentos,que envolve desde a materia prima do produto,até ao cliente final,pois dentro dessa cadeia envolve uma serie de processos e procedimentos,que sem uma gestão eficaz de processos jamais atingiria os objetivos de entrega no tempo certo aos clientes. Com o surgimento da internet,e os advanços das tecnologias,permite uma gestão eficaz,melhora nos processos produtivos,comodidade para clientes,controle e monitoramento de transportes de produtos,relatorios de vendas e produção,podendo assim fazer melhorias continuas em seus processos.Então,hoje dia,o mercado tornou-se dependente das tecnogias,pelo seu grande potencial de interligar meios e pessoas,e sua ferramentas poderosas que são fundamentais nos processos de gestão de processos e por processos.

Objetivos
pensando nisso,resolvi em criar uma forma para facilitar a vida de muitas pessoas que tem problemas com tempo,sabemos que hoje em dia,são muitas tarefas,compromissos do dia a dia que consomem o tempo das pessoas,é trabalho,estudo,reunioes de trabalho e escolares,entre outros compromisso. De fato, queremos facilitar a vida das pessoas que utilizam as redes de supermecado trazendo comodidade para fazerem suas compras,pois hoje em dia compramos tudo pela internet,moveis,eletrodomestico,eletronicos,comesticos,roupas, e entres outros produtos,mas não ouvi falar de um sistema que permitem pessoas fazer suas compras alimentares nas redes de supermercado pelo site,e terem suas compras entregues na sua casa,com qualidade,mas dizem que alguns supermecados ja adotam esse método,mas pergunto: é viavel? as pessoas utilizariam? então resolvi criar a solução para esse problema usando a linguagem python,para através de um algoritmo solucionar esse problema.

caso de uso 1
Cadastrar cliente NAO UTILIZAREMOS NO ALGORITMO
Referencia. RF-F1 Descrição

os clientes para acessar o site primeiramente precisaram se cadastrar no site,criando um login e senha. Pré-condições
é preciso de internet,e entrar no site para se cadastrar,ter documentamenta em dia,e ser maior do que 18 anos. Fluxo Básico
entrar no menu,opção, cadastrar-se.
prencher todos os campos pedidos do cadastro.
digitar finalizar.
o sistema salvara o login e senha criado pelo usuario no banco de dados.
apos finalizar,o cliente tera que fazer o login para entrar no sistema
caso de uso 2
menu interno - cliente
Referência RF-F2 Descrição
para acessar o abiente interno dos menus do site, o cliente deve ter feito o cadastro,e o login de acesso ao sistema. Pré-Condições
Ter cadastro no sistema,e ser ativo em compras. fluxo basico








from openpyxl import load_workbook
from openpyxl import workbook
from datetime import datetime
from openpyxl import cell
import xlrd

diretorio ='C:/Users/GUARITA.CIVIT/Downloads/LISTA COMPRA TRABALHO.xlsx'

wb = xlrd.open_workbook(diretorio)
sh = wb.sheet_by_index(0)

#l_dia = []
#l_cod = []
#l_nome = []
#l_hora = []
#l_cargo = []

x = "S"

while x != "N":

    id_item = input("\nCódigo: ")

    for row_num in range(sh.nrows):
        row_value = sh.row_values(row_num)
        if row_value[0] == id_item:
            id_produto = row_value[1]
            id_preco = row_value[2]
            id_quant = row_value[3]
            id_vencimento = row_value[4]

            print("\n#################################################################")
            print("Código              :", id_item)
            print("Produto             :", id_produto)
            print("Preço               :", id_preco)
            print("Quantidade          :", id_quant)
            print("Vencimento          :", id_vencimento)
            print("#################################################################")
            print("\nValores")

            break

    salvar = input("Colocar item na carrinho de compras? (S/N)")

    if salvar == "S" or salvar == "s":

        wb1 = load_workbook(diretorio)
        ws = wb1.worksheets.pop(1)

        i = 0

        for i in range(2, 100000):
            valor = ws.cell(row=i, column=2).value
            if valor == None:
                break

        ws.cell(row=i, column=2).value = id_item
        ws.cell(row=i, column=3).value = id_produto
        ws.cell(row=i, column=4).value = id_preco
        ws.cell(row=i, column=5).value = id_quant
        ws.cell(row=i, column=6).value = id_vencimento
        ws.cell(row=i, column=7).value = "Item no Carrinho de Compra."

        wb1.save(diretorio)

        print("\n Dados salvos com sucesso!")

    continuar = input("Continuar Comprando? (S/N)")

    if continuar == "N" or continuar == "n":
        x = "N"

menus
meu perfil
histórico de compras
comprar
caso de uso 3
menu-comprar
Referencia RF-F3 Descrição
Para comprar o cliente deve selecionar todos os itens desejados
fluxo basico

O sistema tera um carrinho virtual onde sera jogado todos os itens.
Apos selecionados os produtos o sistema mostrar na tela uma lista com todos os produtos,e o valor total da comprar.
o sistema deve perguntar ao cliente se realmente deseja realizar compra,se 'sim',o sistema deve perguntar os dados do cartão do cliente,se aprovado retorne uma mensagem 'Deseja finalizar compra?'.
o sistema deve salvar a comprar no banco de dados e gerar um pedido de compra ao cliente na tela.
caso de uso 4
relatorio-diariodecompras
Referencia RF-F4
Descrição algoritma.
usando as estrutura principais das linguagens de programação,'if/else','while/for',listas/dicionarios'bibliotecas,iremos envolver uma quantidade de aplicações para desenvolver a solução problema,e importante frizar que o banco de dados será fundamental em nosso codigo,pois iremos trabalhar com uma serie de variáveis que ser,ao armazenados,dados e graficos dashboard,é fundamental a qualidade de nosso algoritmo,pois envolve uma serie de questões e aprendizados,dando uma visão mais ampla sobre o funcionamento de um programa e suas respectivas funcionalidades,agregando para nós alunos aprendizados que servirão para nosso carreira profissional,desenvolver esse algoritmo e um grande desafio,pode nao sair perfeitamente como planejamos,nmas só desafio de desenvolver e tentar encontrar uma solução atraves da linguagem python ja nos agregará valor intelectual e profissional.

passos
ambiente com o menu em que o cliente devera fazer um previo cadastro com as informações do tipo:nome sobrenome endereço,data de nascimento,cpf,cep,senha( a senha devera ter caracter minusculos e maiusculo,numero),já o login sera dado pelo numero do cpf.
os cadastros devem estar atualizados.
esse sistema na vida real funcionaria: o cliente fazia o cadastro,entrava no sistema,realizava a compra,e a logistica do supermecado selecionava os itens e enviava para a casa do cliente através dos seus dados.
apos cada dia de expediente,o sistema emitia o numero de vendas realizadas naquele dia no progrma e o total em dinheiro das vendas.















