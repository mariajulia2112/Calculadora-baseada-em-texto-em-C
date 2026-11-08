#include <stdio.h>
#include <stdlib.h>

int main() {
    float X, Y, resultado;
    int opcao;
    char continuar;

    do{
        printf("\n===============================\n");
        printf("   Calculadora Simples");
        printf("\n===============================\n");
        printf("Selecione uma operação: \n");
        printf("1. Adição\n");
        printf("2. Subtração\n");
        printf("3. Multiplicação\n");
        printf("4. Divisão\n");
        printf("5. Sair\n");
        printf("Opção: ");
        scanf("%d", &opcao);

        if (opcao == 5) {
            printf("\nObrigado por usar a calculadora! Até a próxima.\n");
            break;
        }

        if (opcao > 5 || opcao < 1) {
            printf("Opção inválida. Por favor, tente novamente.\n");
            continue;
        }

        printf("\nDigite o primeiro número: ");
        scanf("%f", &X);

        printf("\nDigite o segundo número: ");
        scanf("%f", &Y);

        switch(opcao) {
            case 1:
                resultado = X + Y;
                printf("Resultado: %.2f + %.2f = %.2f\n", X, Y, resultado);
                break;
            case 2:
                resultado = X - Y;
                 printf("Resultado: %.2f - %.2f = %.2f\n", X, Y, resultado);
                break;
            case 3:
                resultado = X * Y;
                 printf("Resultado: %.2f * %.2f = %.2f\n", X, Y, resultado);
                break;
            case 4:
                if (Y == 0) {
                    printf("Erro: Divisão por zero não é permitida.\n");
                } else {
                    resultado = X / Y;
                    printf("Resultado: %.2f / %.2f = %.2f\n", X, Y, resultado);
                }
                break;
        }
        do {
            printf("\nDeseja realizar outra operação? (s/n): ");
            scanf(" %c", &continuar);

            if (continuar == 'S') {
                continuar = 's';
            } else if (continuar == 'N') {
                continuar = 'n';
            }

            if (continuar != 's' && continuar != 'n') {
                printf("Resposta inválida! Digite s ou n.\n");
            }
        } while (continuar != 's' && continuar !='n');

    } while (continuar == 's');

    if (continuar == 'n') {
        printf("\nObrigado por usar a calculadora! Até a próxima.\n");
    }
    
    return 0;
}
