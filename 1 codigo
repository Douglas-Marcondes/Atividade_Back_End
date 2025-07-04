# # Sistema simples de denúncias urbanas
denuncias = []
usuarios = []
problemas = ["Buraco na rua", "Lâmpada queimada", "Lixo acumulado", "Vazamento de água"]

def menu_principal():
    print("\nSistema de Denúncias Urbanas")
    print("1. Fazer nova denúncia")
    print("2. Listar denúncias")
    print("3. Sair")
    return input("Escolha uma opção: ")

def cadastrar_usuario():
    print("\nCadastro de Usuário")
    nome = input("Nome: ")
    email = input("Email: ")
    usuarios.append({"nome": nome, "email": email})
    print("Usuário cadastrado com sucesso!")
    return len(usuarios) - 1  # Retorna o ID do usuário

def fazer_denuncia(usuario_id):
    print("\nNova Denúncia")
    print("Problemas disponíveis:")
    for i, problema in enumerate(problemas, 1):
        print(f"{i}. {problema}")
    
    try:
        problema_id = int(input("Escolha o número do problema: ")) - 1
        if problema_id < 0 or problema_id >= len(problemas):
            print("Número inválido!")
            return
    except:
        print("Digite um número válido!")
        return
    
    descricao = input("Descreva o problema: ")
    endereco = input("Endereço do problema: ")
    
    denuncias.append({
        "usuario_id": usuario_id,
        "problema": problemas[problema_id],
        "descricao": descricao,
        "endereco": endereco,
        "status": "Aberta"
    })
    print("Denúncia registrada com sucesso!")

def listar_denuncias():
    print("\nLista de Denúncias")
    if not denuncias:
        print("Nenhuma denúncia registrada.")
        return
    
    for i, denuncia in enumerate(denuncias, 1):
        usuario = usuarios[denuncia["usuario_id"]]
        print(f"\nDenúncia #{i}")
        print(f"Problema: {denuncia['problema']}")
        print(f"Descrição: {denuncia['descricao']}")
        print(f"Endereço: {denuncia['endereco']}")
        print(f"Status: {denuncia['status']}")
        print(f"Registrado por: {usuario['nome']} ({usuario['email']})")

def main():
    print("Bem-vindo ao Sistema de Denúncias Urbanas!")
    
    # Cadastra um usuário automaticamente para simplificar
    usuario_id = cadastrar_usuario()
    
    while True:
        opcao = menu_principal()
        
        if opcao == "1":
            fazer_denuncia(usuario_id)
        elif opcao == "2":
            listar_denuncias()
        elif opcao == "3":
            print("Obrigado por usar nosso sistema!")
            break
        else:
            print("Opção inválida. Tente novamente.")

if __name__ == "__main__":
    main()
