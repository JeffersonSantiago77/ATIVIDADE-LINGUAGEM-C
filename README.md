1. Escrever um algoritmo que lê 5 valores para a, um de cada vez, e conta quantos destes valores são negativos, escrevendo esta informação.
#include <stdio.h>

int main() {
    float a;
    int contador = 0;

    for (int i = 1; i <= 5; i++) {
        printf("Digite o valor %d: ", i);
        scanf("%f", &a);

        if (a < 0) {
            contador++;
        }
    }

    printf("Quantidade de valores negativos: %d\n", contador);

    return 0;
}
