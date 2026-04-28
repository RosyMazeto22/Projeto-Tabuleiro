chamados = []

def abrir_chamado():
    titulo = input("Título do chamado: ")
    descricao = input("Descrição: ")
    
    chamado = {
        "titulo": titulo,
        "descricao": descricao,
        "status": "Aberto"
    }
    
    chamados.append(chamado)
    print("Chamado aberto com sucesso!\n")

def listar_chamados():
    if not chamados:
        print("Nenhum chamado registrado.\n")
        return
    
    for i, chamado in enumerate(chamados):
        print(f"{i} - {chamado['titulo']} | {chamado['status']}")
    print()

def atualizar_status():
    listar_chamados()
    indice = int(input("Escolha o número do chamado: "))
    
    if 0 <= indice < len(chamados):
        chamados[indice]["status"] = "Resolvido"
        print("Chamado atualizado!\n")
    else:
        print("Índice inválido!\n")

def menu():
    while True:
        print("1 - Abrir chamado")
        print("2 - Listar chamados")
        print("3 - Atualizar status")
        print("0 - Sair")
        
        opcao = input("Escolha: ")
        
        if opcao == "1":
            abrir_chamado()
        elif opcao == "2":
            listar_chamados()
        elif opcao == "3":
            atualizar_status()
        elif opcao == "0":
            break
        else:
            print("Opção inválida!\n")

menu()
