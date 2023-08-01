# Banco-Python
# Sistema básico de banco deposito, saque e ver extrato
saque = 0
dinheiro = 0
ope = 0
deposito= 0
valor = []
while ope != 4:
    print('Bom dia! qual operação deseja realizar?')
    print('Depositar: Digite (1)')
    print('Sacar: digite (2)')
    print('Ver extrato: digite (3)')
    print('Sair: digite 4')
    ope = int(input(':'))
    if ope == 1:
        ValorDeposito = int(input('Digite o valor que deseja depositar:'))
        if ValorDeposito > 0:
            dinheiro = dinheiro + ValorDeposito
            deposito += 1
            valor.append(ValorDeposito)
            print(f'Deposito no valor de {valor} realizado com sucesso!')
        else:
            print('ERRO: Valor invalido')
    elif ope == 2:
        if dinheiro > 0:
            if saque < 3:
                print('São permitidos 3 saques por dia no valor de R$500:')
                valsa = int(input('Digite o valor que deseja sacar!!!!'))
                if valsa <= dinheiro and valsa <= 500:
                    dinheiro = dinheiro - valsa
                    saque += 1
                else:
                    print('Valor invalido!!!!!')
            else:
                print('LIMITE DE SAQUES EXCEDIDO')
        else:
            print('Sem valor para sacar')
    elif ope == 3:
        print(f'Sua conta tem R${dinheiro}')
        print(f'Voce fez {deposito} depositos de {valor}')
        print(f'Voce realizou {saque} saques hoje')
