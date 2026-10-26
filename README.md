# arrays-vetores-estruturas-de-repeti-o.
calcula a soma dos múltiplos de 3, a média dos pares.

#include <stdio.h>

#define TAM 20

int main() {
    int numeros[TAM];
    int i;

    int somaMultiplos3 = 0;
    int somaPares = 0;
    int quantidadePares = 0;

    int positivos = 0;
    int negativos = 0;

    int maior, menor;
    float mediaPares;

    // Leitura dos 20 numeros inteiros
    printf("=== ANALISE DE VETORES ===\n\n");

    for (i = 0; i < TAM; i++) {
        printf("Digite o %d numero inteiro: ", i + 1);
        scanf("%d", &numeros[i]);
    }

    // Inicializa o maior e o menor com o primeiro elemento
    maior = numeros[0];
    menor = numeros[0];

    // Percorre o vetor para realizar os calculos
    for (i = 0; i < TAM; i++) {

        // Soma dos multiplos de 3
        if (numeros[i] % 3 == 0) {
            somaMultiplos3 += numeros[i];
        }

        // Soma e contagem dos numeros pares
        if (numeros[i] % 2 == 0) {
            somaPares += numeros[i];
            quantidadePares++;
        }

        // Contagem de positivos e negativos
        if (numeros[i] > 0) {
            positivos++;
        } else if (numeros[i] < 0) {
            negativos++;
        }

        // Identificacao do maior valor
        if (numeros[i] > maior) {
            maior = numeros[i];
        }

        // Identificacao do menor valor
        if (numeros[i] < menor) {
            menor = numeros[i];
        }
    }

    // Exibe os resultados
    printf("\n=== RESULTADOS ===\n");

    printf("Soma dos multiplos de 3: %d\n", somaMultiplos3);

    if (quantidadePares > 0) {
        mediaPares = (float) somaPares / quantidadePares;
        printf("Media dos numeros pares: %.2f\n", mediaPares);
    } else {
        printf("Nao existem numeros pares no vetor.\n");
    }

    printf("Quantidade de positivos: %d\n", positivos);
    printf("Quantidade de negativos: %d\n", negativos);

    printf("Maior valor: %d\n", maior);
    printf("Menor valor: %d\n", menor);

    // Exibe todos os elementos armazenados
    printf("\n=== ELEMENTOS DO VETOR ===\n");

    for (i = 0; i < TAM; i++) {
        printf("%d ", numeros[i]);
    }

    printf("\n");

    return 0;
}
