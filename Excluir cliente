#include <stdio.h>
#include <string.h>

#define MAX 100

// Estrutura do Cliente
struct Cliente {
    int id;
    char nome[50];
    char telefone[20];
};

int main() {

    struct Cliente clientes[MAX];

    int total = 0;
    int opcao = 0;

    while (opcao != 5) {

        printf("\n===== SISTEMA DE CLIENTES =====\n");
        printf("1 - Cadastrar cliente\n");
        printf("2 - Listar clientes\n");
        printf("3 - Buscar cliente\n");
        printf("4 - Excluir cliente\n");
        printf("5 - Sair\n");
        printf("Escolha uma opção: ");

        scanf("%d", &opcao);
        getchar(); // limpar buffer

        // Cadastro de Cliente
        if (opcao == 1) {

            if (total < MAX) {

                clientes[total].id = total + 1;

                printf("Nome: ");
                fgets(clientes[total].nome, 50, stdin);
                clientes[total].nome[strcspn(clientes[total].nome, "\n")] = '\0';

                printf("Telefone: ");
                fgets(clientes[total].telefone, 20, stdin);
                clientes[total].telefone[strcspn(clientes[total].telefone, "\n")] = '\0';

                total++;

                printf("Cliente cadastrado com sucesso!\n");

            } else {

                printf("Limite de clientes atingido!\n");
            }
        }

        // Listar Clientes
        else if (opcao == 2) {

            if (total == 0) {

                printf("Nenhum cliente cadastrado.\n");

            } else {

                printf("\n--- LISTA DE CLIENTES ---\n");

                for (int i = 0; i < total; i++) {

                    printf("ID: %d\n", clientes[i].id);
                    printf("Nome: %s\n", clientes[i].nome);
                    printf("Telefone: %s\n", clientes[i].telefone);
                    printf("-------------------------\n");
                }
            }
        }

        // Buscar Cliente
        else if (opcao == 3) {

            int idBusca;
            int encontrado = 0;

            printf("Digite o ID do cliente: ");
            scanf("%d", &idBusca);

            for (int i = 0; i < total; i++) {

                if (clientes[i].id == idBusca) {

                    printf("\nCliente encontrado!\n");
                    printf("ID: %d\n", clientes[i].id);
                    printf("Nome: %s\n", clientes[i].nome);
                    printf("Telefone: %s\n", clientes[i].telefone);

                    encontrado = 1;
                    break;
                }
            }

            if (!encontrado) {

                printf("Cliente não encontrado!\n");
            }
        }

        // Excluir Cliente
        else if (opcao == 4) {

            int idExcluir;
            int encontrado = 0;

            if (total == 0) {

                printf("Não existem clientes cadastrados.\n");

            } else {

                printf("Digite o ID do cliente que deseja excluir: ");
                scanf("%d", &idExcluir);

                for (int i = 0; i < total; i++) {

                    if (clientes[i].id == idExcluir) {

                        encontrado = 1;

                        // mover registros
                        for (int j = i; j < total - 1; j++) {

                            clientes[j] = clientes[j + 1];
                        }

                        total--;

                        // reorganizar IDs
                        for (int j = 0; j < total; j++) {

                            clientes[j].id = j + 1;
                        }

                        printf("Cliente excluído com sucesso!\n");
                        break;
                    }
                }

                if (!encontrado) {

                    printf("Cliente com ID %d não encontrado.\n", idExcluir);
                }
            }
        }

        // Opção inválida
        else if (opcao != 5) {

            printf("Opção inválida! Tente novamente.\n");
        }
    }

    printf("Encerrando o sistema...\n");

    return 0;
}
