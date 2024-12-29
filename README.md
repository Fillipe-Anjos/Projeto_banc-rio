# Projeto_bancário

menu = """"

[1] Depositar
[2] Sacar
[3] Extrato
[0] Sair

=> """

saldo = 3000

limite = 500

extrato = ""

numero_saques = 0

LIMITE_SAQUE = 3

while True:
    
    opcao = input(menu)
    
    if opcao == "1":
        valor = float(input("Informe o valor que deseja depositar:"))
        print(f"Você acabou de depositar R${valor}.")
        
        if valor > 0:
            saldo += valor
            extrato += f"Depósito: R$ {valor:.2f}\n"
            
        else:
            print("Operação negada! O valor informado é inválido.")
            
    elif opcao == "2":
        valor = float(input("Informe o valor que desja sacar"))
        print(f"Você acabou de sacar R${valor}.")
        
        excedeu_saldo = valor > saldo
        
        excedeu_limite = valor > limite
        
        excedeu_saques = numero_saques >= LIMITE_SAQUE
        
        if excedeu_saldo:
            print("Operação negada! Você não tem saldo suficiente.")
            
        elif excedeu_limite:
            print("Operação negada! O valor do saque excede o limite que você tem na conta.")
            
        elif excedeu_saques:
            print("Operação negada! Número máximo de saques excedido.")
            
        elif valor > 0:
            saldo -= valor
            extrato += f"Saque: R$ {valor:.2f}\n"
            numero_saques += 1
            
        else:
            print("Operação negada! O valor informado é inválido.")
            
    elif opcao =="3":
        print("\n================ EXTRATO ================")
        print("Não houve movimentação na conta." if not extrato else extrato)
        print(f"\nSaldo: {saldo:.2f}")
        print("==========================================")
        
    elif opcao == "0":
        print("Volte sempre. Saindo...")
        break
    
    else:
        print("Operação inválida, por favor selecione novamente a opção desejada.")
        
        
