# calculos_imobiliarios
#Program made from Brazilian, very VERY simple!!!
from time import sleep
print('---'*20)
print('Bem vindo ao programa de calculos imobiliarios.')
nome = str(input('Digite seu nome completo: ')).strip()
print('Prazer em te conhecer, {}!'.format(nome.split()[0]))
print('---'*20)
imovel = float(input('Para começar, digite o valor do imovel que você deseja adquirir: R$'))
if imovel < 180.000:
    imovel = imovel - (imovel * 10 / 100)
    print('Parabens você ganhou um desconto do Governo de 10%... Valor do imovel R${:.3f}!'.format(imovel))
elif imovel < 250.000:
    imovel = imovel - (imovel * 5 / 100)
    print('Parabens você ganhou um desconto do Governo de 5%... Valor do imovel R${:.3f}!'.format(imovel))
else:
    print('Esse valor não se enquadra no desconto que o governo dá, infelizmente o valor se mantem.')
entrada = str(input('Você gostaria de dar entrada?')).strip().lower()
if entrada in 'quero sim gostaria':
    print('Ok, se você tiver um carro, moto ou terreno e quiser dar de entrada, aceitamos.')
    entrada = float(input('Digite o valor: R$'))
    imovel = imovel - entrada
    print('O valor do imovel com sua entrada fica, R${:.3f}'.format(imovel))
else:
    print('Tudo bem, sem uma entrada fica mais apertado nas parcelas mensais do imovel.')
salario = str(input('Atualmente você é casado(a) ou é solteiro(a)?')).strip().lower()
salario1 = 0
if salario in 'casado casada':
    salario = float(input('Digite o salario do marido: R$'))
    salario1 = float(input('Digite o salario da esposa: R$'))
elif salario in 'solteiro solteira':
    salario = float(input('Digite seu salario atualmente: R$'))
anos = int(input('Em quantos anos você quer pagar seu imovel? '))
anos = anos * 12
print('Calculando...')
sleep(1)
print('---'*20)
parcelas = imovel / anos
salario2 = ((salario + salario1) * 30 / 100)
if parcelas <= salario2:
    print('30% do seu salario fica R${:.3f}, e o valor da parcela fica R${:.3f}'.format(salario2,parcelas))
    print('Parabens, você consegue comprar seu imovel.')
else:
    print('A parcela mensal não pode passar dos 30% do seu salario que é R${:.3f}, e o valor da parcela é R${:.3f}'.format(salario2, parcelas))
    print('infelzimente você não consegue comprar seu apartamento, aumente a entrada ou faça em mais parcelas, desculpe!')
print('Obrigado pela paciência!')
print('---'*20)
