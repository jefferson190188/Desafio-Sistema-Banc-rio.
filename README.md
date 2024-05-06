    menu = '''

    [1] depositar
    [2] sacar
    [3] extrato
    [4] sair

    => '''

    saldo = 0
    limite = 500
    extrato = ''
    numero_saque = 0
    LIMITE_SAQUE = 3

    while True:
    
    opcao = input(menu)



    if opcao == '1':
        valor = float(input('informe o valor do deposito:'))
        if valor > 0:
            saldo += valor
            extrato += f'deposito: R$ {valor:.2f}\n'
        else:
            print('Operação não realizada! O valor informado é inválido')
            
           

    elif opcao == '2':
        valor = float(input('informe o valor do saque:'))
        
        execedeu_saldo = valor > saldo

        excedeu_limite = valor > limite

        excedeu_saques = numero_saque >= LIMITE_SAQUE

        if execedeu_saldo:
            print('Operação falhou! Você não tem saldo suficiente')

        elif excedeu_limite:
            print('Operação falhou! Limite insuficiente.')

        elif excedeu_saques:
            print('Operação falhou! Limite de saques excedido')

        elif valor > 0:
            saldo += valor
            extrato += f'Saque: R$ {valor:.2f}\n'
            numero_saque += 1

        else:
            print('Operação falhou! O valor informado é inválido.')

           

    elif opcao == '3':
        print('\n#################### EXTRATO ####################')
        print('não foram realizadas movimentações.' if not extrato else extrato)
        print(f'\nSaldo: R$ {saldo:.2f}')
        print('#################################################')

    elif opcao == '4':

        break
    else:
        print('opção invalida, por favor selecione novamente a operação desejada.')
