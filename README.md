def exibir_menu():
    print("\n=== MINHA LISTA DE TAREFAS ===")
    print("1. Ver tarefas")
    print("2. Adicionar tarefa")
    print("3. Remover tarefa")
    print("4. Sair")

def Executar_agenda():
    tarefas = ["Estudar Python", "Configurar o GitHub"]
    
    while True:
        exibir_menu()
        opcao = input("\nEscolha uma opção (1-4): ")
        
        if opcao == "1":
            if not tarefas:
                print("\n[!] Sua lista está vazia.")
            else:
                print("\n--- Suas Tarefas ---")
                for indice, tarefa in enumerate(tarefas, start=1):
                    print(f"{indice}. {tarefa}")
                    
        elif opcao == "2":
            nova_tarefa = input("\nDigite a nova tarefa: ")
            if nova_tarefa.strip():
                tarefas.append(nova_tarefa)
                print(f"[+] '{nova_tarefa}' foi adicionada!")
            else:
                print("[!] O nome da tarefa não pode estar vazio.")
                
        elif opcao == "3":
            if not tarefas:
                print("\n[!] Não há tarefas para remover.")
            else:
                print("\n--- Escolha o número para remover ---")
                for indice, tarefa in enumerate(tarefas, start=1):
                    print(f"{indice}. {tarefa}")
                try:
                    num = int(input("\nNúmero da tarefa: "))
                    removida = tarefas.pop(num - 1)
                    print(f"[-] '{removida}' foi removida!")
                except (ValueError, IndexError):
                    print("[!] Número inválido.")
                    
        elif opcao == "4":
            print("\nAté logo! Bom trabalho com seus projetos.")
            break
        else:
            print("[!] Opção inválida. Tente novamente.")

# Executa o programa
if __name__ == "__main__":
    Executar_agenda()
