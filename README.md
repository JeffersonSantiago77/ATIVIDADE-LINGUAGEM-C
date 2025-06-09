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
2. Escrever um algoritmo que lê um valor N inteiro e positivo e que calcula e escreve o valor de E.
E = 1 + 1 / 1! + 1 / 2! + 1 / 3! + 1 / N!
#include <stdio.h>

// Função para calcular fatorial de um número inteiro não negativo
unsigned long long fatorial(int num) {
    unsigned long long fat = 1;
    for (int i = 2; i <= num; i++) {
        fat *= i;
    }
    return fat;
}

int main() {
    int N;
    double E = 1.0; // Começa com o primeiro termo 1

    printf("Digite um valor inteiro e positivo para N: ");
    scanf("%d", &N);

    if (N < 0) {
        printf("Valor invalido! N deve ser positivo.\n");
        return 1;
    }

    for (int i = 1; i <= N; i++) {
        E += 1.0 / fatorial(i);
    }

    printf("Valor de E para N = %d: %.6lf\n", N, E);

    return 0;
}
3. A prefeitura de uma cidade fez uma pesquisa entre seus habitantes, coletando dados sobre o salário e número de filhos. A prefeitura deseja saber:
a) média do salário da população;
b) média do número de filhos;
c) maior salário;
d) percentual de pessoas com salário até R$100,00
#include <stdio.h>

int main() {
    int n, i;
    float salario, soma_salario = 0, maior_salario = 0;
    int filhos, soma_filhos = 0, count_salario_ate_100 = 0;

    printf("Digite o número de habitantes pesquisados: ");
    scanf("%d", &n);

    for (i = 0; i < n; i++) {
        printf("Habitante %d\n", i + 1);

        printf("Digite o salário: ");
        scanf("%f", &salario);

        printf("Digite o número de filhos: ");
        scanf("%d", &filhos);

        soma_salario += salario;
        soma_filhos += filhos;

        if (salario > maior_salario) {
            maior_salario = salario;
        }

        if (salario <= 100.0) {
            count_salario_ate_100++;
        }
        printf("\n");
    }

    if (n > 0) {
        float media_salario = soma_salario / n;
        float media_filhos = (float)soma_filhos / n;
        float percentual_ate_100 = ((float)count_salario_ate_100 / n) * 100;

        printf("Média do salário da população: R$ %.2f\n", media_salario);
        printf("Média do número de filhos: %.2f\n", media_filhos);
        printf("Maior salário: R$ %.2f\n", maior_salario);
        printf("Percentual de pessoas com salário até R$100,00: %.2f%%\n", percentual_ate_100);
    } else {
        printf("Nenhum dado foi inserido.\n");
    }

    return 0;
}
4. Chico tem 1,50 metro e cresce 2 centímetros por ano, enquanto Zé tem 1,10 metro e cresce 3 centímetros por ano. Construa um algoritmo que calcule e imprima quantos
anos serão necessários para que Zé seja maior que Chico.
#include <stdio.h>

int main() {
    float alturaChico = 1.50;
    float alturaZe = 1.10;
    int anos = 0;

    while (alturaZe <= alturaChico) {
        alturaChico += 0.02;  // 2 cm = 0,02 m
        alturaZe += 0.03;     // 3 cm = 0,03 m
        anos++;
    }

    printf("Serao necessarios %d anos para que Ze seja maior que Chico.\n", anos);

    return 0;
}
5. Construir um algoritmo que calcule a média aritmética de vários valores inteiros positivos, lidos externamente. O final da leitura acontecerá quando for lido um valor
negativo.
#include <stdio.h>

int main() {
    int n, i;
    float salario, soma_salario = 0, maior_salario = 0;
    int filhos, soma_filhos = 0, count_salario_ate_100 = 0;

    printf("Digite o número de habitantes pesquisados: ");
    scanf("%d", &n);

    for (i = 0; i < n; i++) {
        printf("Habitante %d\n", i + 1);

        printf("Digite o salário: ");
        scanf("%f", &salario);

        printf("Digite o número de filhos: ");
        scanf("%d", &filhos);

        soma_salario += salario;
        soma_filhos += filhos;

        if (salario > maior_salario) {
            maior_salario = salario;
        }

        if (salario <= 100.0) {
            count_salario_ate_100++;
        }
        printf("\n");
    }

    if (n > 0) {
        float media_salario = soma_salario / n;
        float media_filhos = (float)soma_filhos / n;
        float percentual_ate_100 = ((float)count_salario_ate_100 / n) * 100;

        printf("Média do salário da população: R$ %.2f\n", media_salario);
        printf("Média do número de filhos: %.2f\n", media_filhos);
        printf("Maior salário: R$ %.2f\n", maior_salario);
        printf("Percentual de pessoas com salário até R$100,00: %.2f%%\n", percentual_ate_100);
    } else {
        printf("Nenhum dado foi inserido.\n");
    }

    return 0;
}
6. Em uma eleição presidencial existem quatro candidatos. Os votos são informados através de códigos. Os dados utilizados para a contagem dos votos obedecem à seguinte
codificação:
- 1,2,3,4 = voto para os respectivos candidatos;
- 5 = voto nulo;
- 6 = voto em branco;
Elabore um algoritmo que leia o código do candidado em um voto. Calcule e escreva:
- total de votos para cada candidato;
- total de votos nulos;
- total de votos em branco;
Como finalizador do conjunto de votos, tem-se o valor 0.
#include <stdio.h>

int main() {
    int voto;
    int votos_cand1 = 0, votos_cand2 = 0, votos_cand3 = 0, votos_cand4 = 0;
    int votos_nulos = 0, votos_brancos = 0;

    printf("Digite os votos (0 para encerrar):\n");

    while (1) {
        printf("Voto: ");
        scanf("%d", &voto);

        if (voto == 0) {
            break; // encerra a leitura
        }

        switch (voto) {
            case 1:
                votos_cand1++;
                break;
            case 2:
                votos_cand2++;
                break;
            case 3:
                votos_cand3++;
                break;
            case 4:
                votos_cand4++;
                break;
            case 5:
                votos_nulos++;
                break;
            case 6:
                votos_brancos++;
                break;
            default:
                printf("Codigo de voto invalido!\n");
                break;
        }
    }

    printf("\nResultado da Eleicao:\n");
    printf("Candidato 1: %d votos\n", votos_cand1);
    printf("Candidato 2: %d votos\n", votos_cand2);
    printf("Candidato 3: %d votos\n", votos_cand3);
    printf("Candidato 4: %d votos\n", votos_cand4);
    printf("Votos Nulos: %d\n", votos_nulos);
    printf("Votos em Branco: %d\n", votos_brancos);

    return 0;
}
7. Escreva um algoritmo que calcule a média aritmética das 3 notas dos alunos de uma classe. O algoritmo deverá ler, além das notas, o código do aluno e deverá ser
encerrado quando o código for igual a zero.
#include <stdio.h>

int main() {
    int codigo;
    float nota1, nota2, nota3, media;

    while (1) {
        printf("Digite o codigo do aluno (0 para sair): ");
        scanf("%d", &codigo);

        if (codigo == 0) {
            break; // encerra o programa
        }

        printf("Digite as 3 notas do aluno %d:\n", codigo);
        scanf("%f %f %f", &nota1, &nota2, &nota3);

        media = (nota1 + nota2 + nota3) / 3.0;

        printf("Codigo: %d, Media: %.2f\n\n", codigo, media);
    }

    printf("Programa encerrado.\n");
    return 0;
}
8. Escreva um algoritmo que calcule a média dos números digitados pelo usuário, se eles forem pares. Termine a leitura se o usuário digitar zero (0).
#include <stdio.h>

int main() {
    int num;
    int soma = 0, contador = 0;
    float media;

    printf("Digite numeros (0 para sair):\n");

    while (1) {
        printf("Numero: ");
        scanf("%d", &num);

        if (num == 0) {
            break;
        }

        if (num % 2 == 0) {
            soma += num;
            contador++;
        }
    }

    if (contador > 0) {
        media = (float)soma / contador;
        printf("Media dos numeros pares digitados: %.2f\n", media);
    } else {
        printf("Nenhum numero par foi digitado.\n");
    }

    return 0;
}
9. Escreva um algoritmo que leia 50 valores e encontre o maior e o menor deles. Mostre o resultado.
#include <stdio.h>

int main() {
    int valor, maior, menor;

    printf("Digite 50 valores:\n");

    for (int i = 0; i < 50; i++) {
        printf("Valor %d: ", i + 1);
        scanf("%d", &valor);

        if (i == 0) {  // Inicializa maior e menor com o primeiro valor lido
            maior = valor;
            menor = valor;
        } else {
            if (valor > maior) {
                maior = valor;
            }
            if (valor < menor) {
                menor = valor;
            }
        }
    }

    printf("Maior valor: %d\n", maior);
    printf("Menor valor: %d\n", menor);

    return 0;
}
10. Escreva um algoritmo que leia o código de um aluno e suas três notas. Calcule a média ponderada do aluno, considerando que o peso para a maior nota seja 4 e para as
duas restantes, 3. Mostre o código do aluno, suas três notas, a média calculada e uma mensagem "APROVADO" se a média for maior ou igual a 5 e "REPROVADO" se a
média for menor que 5. Repita a operação até que o código lido seja negativo.
#include <stdio.h>

int main() {
    int codigo;
    float n1, n2, n3, maior, media;
    float peso_maior = 4.0;
    float peso_outros = 3.0;
    float soma_pesos = peso_maior + 2 * peso_outros;

    while (1) {
        printf("Digite o codigo do aluno (negativo para sair): ");
        scanf("%d", &codigo);

        if (codigo < 0) {
            break;
        }

        printf("Digite as tres notas do aluno: ");
        scanf("%f %f %f", &n1, &n2, &n3);

        // Encontrar a maior nota
        maior = n1;
        if (n2 > maior) maior = n2;
        if (n3 > maior) maior = n3;

        // Calcular média ponderada
        if (maior == n1) {
            media = (n1 * peso_maior + n2 * peso_outros + n3 * peso_outros) / soma_pesos;
        } else if (maior == n2) {
            media = (n1 * peso_outros + n2 * peso_maior + n3 * peso_outros) / soma_pesos;
        } else {
            media = (n1 * peso_outros + n2 * peso_outros + n3 * peso_maior) / soma_pesos;
        }

        printf("\nCodigo: %d\n", codigo);
        printf("Notas: %.2f, %.2f, %.2f\n", n1, n2, n3);
        printf("Media ponderada: %.2f\n", media);
        if (media >= 5.0) {
            printf("APROVADO\n\n");
        } else {
            printf("REPROVADO\n\n");
        }
    }

    printf("Programa encerrado.\n");
    return 0;
}
11. Escreva um algoritmo que leia um número n (número de termos de uma progressão aritmética), a1 ( o primeiro termo da progressão) e r (a razão da progressão) e
escreva os n termos desta progressão, bem como a soma dos elementos.
#include <stdio.h>

int main() {
    int n;
    float a1, r, termo, soma = 0;

    printf("Digite o numero de termos (n): ");
    scanf("%d", &n);

    printf("Digite o primeiro termo (a1): ");
    scanf("%f", &a1);

    printf("Digite a razao (r): ");
    scanf("%f", &r);

    termo = a1;

    printf("Termos da PA:\n");
    for (int i = 1; i <= n; i++) {
        printf("%.2f ", termo);
        soma += termo;
        termo += r;
    }

    printf("\nSoma dos termos: %.2f\n", soma);

    return 0;
}
12. Escrever um algoritmo que leia 20 valores para uma variável n e, para cada um deles, calcule a tabuada de 1 até n. Mostre a tabuada na forma:
1 x n = n
2 x n = 2n
3 x n = 3n
.......
n x n = n2
#include <stdio.h>

int main() {
    int n, i, j;

    for (i = 1; i <= 20; i++) {
        printf("Digite o valor %d: ", i);
        scanf("%d", &n);

        printf("Tabuada de %d:\n", n);
        for (j = 1; j <= n; j++) {
            printf("%d x %d = %d\n", j, n, j * n);
        }
        printf("\n");
    }

    return 0;
}
13. Escrever um algoritmo que leia um número n que indica quantos valores devem ser lidos a seguir. Para cada número lido, mostre uma tabela contendo o valor lido e o
fatorial deste valor.
#include <stdio.h>

// Função para calcular o fatorial de um número
unsigned long long fatorial(int num) {
    unsigned long long fat = 1;
    for (int i = 2; i <= num; i++) {
        fat *= i;
    }
    return fat;
}

int main() {
    int n, valor;

    printf("Quantos valores deseja digitar? ");
    scanf("%d", &n);

    printf("\nValor\tFatorial\n");
    printf("---------------------\n");

    for (int i = 0; i < n; i++) {
        printf("Digite o valor %d: ", i + 1);
        scanf("%d", &valor);

        if (valor < 0) {
            printf("%d\tFatorial nao definido para negativos.\n", valor);
        } else {
            printf("%d\t%llu\n", valor, fatorial(valor));
        }
    }

    return 0;
}
14. Escrever um algoritmo que leia um número não determinado de valores e calcule a média aritmética dos valores lidos, a quantidade de valores positivos, a quantidade de
valores negativos e o percentual de valores negativos e positivos. Mostre os resultados.
#include <stdio.h>

int main() {
    int valor, positivos = 0, negativos = 0, total = 0;
    float soma = 0;

    printf("Digite valores inteiros (0 para encerrar):\n");

    while (1) {
        printf("Valor: ");
        scanf("%d", &valor);

        if (valor == 0) {
            break;
        }

        soma += valor;
        total++;

        if (valor > 0)
            positivos++;
        else if (valor < 0)
            negativos++;
    }

    if (total == 0) {
        printf("Nenhum valor foi digitado.\n");
    } else {
        float media = soma / total;
        float perc_positivos = (float)positivos / total * 100;
        float perc_negativos = (float)negativos / total * 100;

        printf("\nResultados:\n");
        printf("Media aritmetica: %.2f\n", media);
        printf("Quantidade de positivos: %d\n", positivos);
        printf("Quantidade de negativos: %d\n", negativos);
        printf("Percentual de positivos: %.2f%%\n", perc_positivos);
        printf("Percentual de negativos: %.2f%%\n", perc_negativos);
    }

    return 0;
}
15. Escrever um algoritmo que leia uma quantidade desconhecida de números e conte quantos deles estão nos seguintes intervalos: [0.25], [26,50], [51,75] e [76,100]. A
entrada de dados deve terminar quando for lido um número negativo.
#include <stdio.h>

int main() {
    int numero;
    int intervalo_0_25 = 0;
    int intervalo_26_50 = 0;
    int intervalo_51_75 = 0;
    int intervalo_76_100 = 0;

    printf("Digite numeros inteiros (negativo para encerrar):\n");

    while (1) {
        printf("Numero: ");
        scanf("%d", &numero);

        if (numero < 0) {
            break;
        }

        if (numero >= 0 && numero <= 25) {
            intervalo_0_25++;
        } else if (numero >= 26 && numero <= 50) {
            intervalo_26_50++;
        } else if (numero >= 51 && numero <= 75) {
            intervalo_51_75++;
        } else if (numero >= 76 && numero <= 100) {
            intervalo_76_100++;
        }
        // Se estiver fora dos intervalos, apenas ignora.
    }

    printf("\nQuantidade de numeros em cada intervalo:\n");
    printf("[0 - 25]     : %d\n", intervalo_0_25);
    printf("[26 - 50]    : %d\n", intervalo_26_50);
    printf("[51 - 75]    : %d\n", intervalo_51_75);
    printf("[76 - 100]   : %d\n", intervalo_76_100);

    return 0;
}
16. Escrever um algoritmo que lê um conjunto não determinado de valores, um de cada vez, e escreve uma tabela com cabeçalho, que deve ser repetido a cada 20 linhas. A
tabela conterá o valor lido, seu quadrado, seu cubo e sua raiz quadrada.
#include <stdio.h>
#include <math.h>

// Função para imprimir o cabeçalho da tabela
void imprimirCabecalho() {
    printf("\n%-10s %-10s %-10s %-15s\n", "Valor", "Quadrado", "Cubo", "Raiz Quadrada");
    printf("-------------------------------------------------------------\n");
}

int main() {
    double valor;
    int contador = 0;

    printf("Digite valores (negativo para encerrar):\n");

    imprimirCabecalho();

    while (1) {
        printf("Valor: ");
        scanf("%lf", &valor);

        if (valor < 0) {
            break;
        }

        double quadrado = valor * valor;
        double cubo = valor * valor * valor;
        double raiz = sqrt(valor);

        printf("%-10.2lf %-10.2lf %-10.2lf %-15.4lf\n", valor, quadrado, cubo, raiz);

        contador++;

        if (contador % 20 == 0) {
            imprimirCabecalho();
        }
    }

    printf("\nPrograma encerrado.\n");

    return 0;
}
17. Escrever um algoritmo que lê um número não determinado de pares de valores m,n, todos inteiros e positivos, um par de cada vez, e calcula e escreve a soma dos n
inteiros consecutivos a partir de m inclusive.
#include <stdio.h>

int main() {
    int m, n;

    while (1) {
        printf("Digite os valores de m e n (ambos positivos, zero ou negativo para encerrar): ");
        scanf("%d %d", &m, &n);

        if (m <= 0 || n <= 0) {
            break;  // encerra o programa
        }

        int soma = 0;
        printf("Numeros somados: ");
        for (int i = 0; i < n; i++) {
            printf("%d ", m + i);
            soma += (m + i);
        }

        printf("\nSoma = %d\n\n", soma);
    }

    printf("Programa encerrado.\n");
    return 0;
}
18. Escrever um algoritmo que lê um número não determinado de valores para m, todos inteiros e positivos, um de cada vez. Se m for par, verificar quantos divisores possui e
escrever esta informação. Se m for ímpar e menor do que 10 calcular e escrever o fatorial de m. Se m for ímpar e maior ou igual a 10 calcular e escrever a soma dos inteiros
de 1 até m.
#include <stdio.h>

// Função para calcular o fatorial
unsigned long long fatorial(int num) {
    unsigned long long fat = 1;
    for (int i = 2; i <= num; i++) {
        fat *= i;
    }
    return fat;
}

int main() {
    int m;

    while (1) {
        printf("Digite um valor inteiro positivo (<= 0 para sair): ");
        scanf("%d", &m);

        if (m <= 0) {
            break;  // Encerra o programa
        }

        if (m % 2 == 0) {  // Número par
            int divisores = 0;
            for (int i = 1; i <= m; i++) {
                if (m % i == 0) {
                    divisores++;
                }
            }
            printf("O numero %d e par e possui %d divisores.\n\n", m, divisores);

        } else {  // Número ímpar
            if (m < 10) {
                printf("O numero %d e impar e seu fatorial e %llu.\n\n", m, fatorial(m));
            } else {
                int soma = 0;
                for (int i = 1; i <= m; i++) {
                    soma += i;
                }
                printf("O numero %d e impar >= 10 e a soma de 1 ate %d e %d.\n\n", m, m, soma);
            }
        }
    }

    printf("Programa encerrado.\n");
    return 0;
}
19. Faça um algoritmo que leia uma quantidade não determinada de números positivos. Calcule a quantidade de números pares e ímpares, a média de valores pares e a
média geral dos números lidos. O número que encerrará a leitura será zero.
#include <stdio.h>

int main() {
    int numero;
    int qtd_pares = 0, qtd_impares = 0, qtd_total = 0;
    int soma_pares = 0, soma_total = 0;

    printf("Digite numeros positivos (0 para encerrar):\n");

    while (1) {
        printf("Numero: ");
        scanf("%d", &numero);

        if (numero == 0) {
            break;
        }

        if (numero < 0) {
            printf("Numero invalido. Digite apenas positivos.\n");
            continue;
        }

        soma_total += numero;
        qtd_total++;

        if (numero % 2 == 0) {
            qtd_pares++;
            soma_pares += numero;
        } else {
            qtd_impares++;
        }
    }

    if (qtd_total == 0) {
        printf("Nenhum numero valido foi digitado.\n");
    } else {
        float media_pares = (qtd_pares > 0) ? (float)soma_pares / qtd_pares : 0;
        float media_geral = (float)soma_total / qtd_total;

        printf("\nResultados:\n");
        printf("Quantidade de pares: %d\n", qtd_pares);
        printf("Quantidade de impares: %d\n", qtd_impares);
        printf("Media dos pares: %.2f\n", media_pares);
        printf("Media geral: %.2f\n", media_geral);
    }

    return 0;
}
20. Faça um algoritmo que leia vários números inteiros e calcule o somatório dos números negativos. O fim da leitura será indicado pelo número 0.
#include <stdio.h>

int main() {
    int numero, soma_negativos = 0;

    printf("Digite numeros inteiros (0 para encerrar):\n");

    while (1) {
        printf("Numero: ");
        scanf("%d", &numero);

        if (numero == 0) {
            break;
        }

        if (numero < 0) {
            soma_negativos += numero;
        }
    }

    printf("\nSomatorio dos numeros negativos: %d\n", soma_negativos);

    return 0;
}
21. Faça um algoritmo que leia vários números inteiros e positivos e calcule o produtório dos números pares. O fim da leitura será indicado pelo número 0.
#include <stdio.h>

int main() {
    int numero;
    unsigned long long produto_pares = 1;
    int encontrou_par = 0;

    printf("Digite numeros inteiros positivos (0 para encerrar):\n");

    while (1) {
        printf("Numero: ");
        scanf("%d", &numero);

        if (numero == 0) {
            break;
        }

        if (numero < 0) {
            printf("Numero invalido. Digite apenas positivos.\n");
            continue;
        }

        if (numero % 2 == 0) {
            produto_pares *= numero;
            encontrou_par = 1;
        }
    }

    if (encontrou_par) {
        printf("\nProdutorio dos numeros pares: %llu\n", produto_pares);
    } else {
        printf("\nNenhum numero par foi digitado.\n");
    }

    return 0;
}
22. Foi feita uma pesquisa entre os habitantes de uma região. Foram coletados os dados de idade, sexo (M/F) e salário. Faça um algoritmo que informe:
a) a média de salário do grupo;
b) maior e menor idade do grupo;
c) quantidade de mulheres com salário até R$100,00.
Encerre a entrada de dados quando for digitada uma idade negativa. (Use o comando enquanto-faça e não use vetores ou matrizes)
#include <stdio.h>

int main() {
    int idade, total_pessoas = 0;
    char sexo;
    float salario;
    float soma_salario = 0;
    int menor_idade = 0, maior_idade = 0;
    int mulheres_salario_baixo = 0;
    int primeira_entrada = 1;

    while (1) {
        printf("\nDigite a idade (negativa para encerrar): ");
        scanf("%d", &idade);

        if (idade < 0) {
            break;
        }

        printf("Digite o sexo (M/F): ");
        scanf(" %c", &sexo);  // espaço antes de %c para consumir o \n anterior

        printf("Digite o salario: ");
        scanf("%f", &salario);

        // Contagem e soma
        total_pessoas++;
        soma_salario += salario;

        // Atualização de menor e maior idade
        if (primeira_entrada) {
            menor_idade = idade;
            maior_idade = idade;
            primeira_entrada = 0;
        } else {
            if (idade < menor_idade) menor_idade = idade;
            if (idade > maior_idade) maior_idade = idade;
        }

        // Contar mulheres com salário até 100
        if ((sexo == 'F' || sexo == 'f') && salario <= 100.0) {
            mulheres_salario_baixo++;
        }
    }

    if (total_pessoas == 0) {
        printf("\nNenhum dado foi inserido.\n");
    } else {
        float media_salario = soma_salario / total_pessoas;

        printf("\n--- Resultados da Pesquisa ---\n");
        printf("Media de salario do grupo: R$%.2f\n", media_salario);
        printf("Maior idade do grupo: %d\n", maior_idade);
        printf("Menor idade do grupo: %d\n", menor_idade);
        printf("Quantidade de mulheres com salario ate R$100,00: %d\n", mulheres_salario_baixo);
    }

    return 0;
}
23. Foi realizada uma pesquisa de algumas características físicas da população de uma certa região, a qual coletou os seguintes dados referentes a cada habitante para
serem analisados:
- sexo (masculino e feminino)
- cor dos olhos (azuis, verdes ou castanhos)
- cor dos cabelos ( louros, castanhos, pretos)
- idade 
#include <stdio.h>
#include <string.h>

int main() {
    char sexo;
    char cor_olhos[10];
    char cor_cabelos[10];
    int idade;

    int total_pessoas = 0;
    int qtd_homens = 0, qtd_mulheres = 0;
    int olhos_azuis = 0, olhos_verdes = 0, olhos_castanhos = 0;
    int cabelos_louros = 0, cabelos_castanhos = 0, cabelos_pretos = 0;
    int soma_idade = 0;

    printf("Digite os dados dos habitantes (idade negativa para sair):\n");

    while (1) {
        printf("\nIdade: ");
        scanf("%d", &idade);
        if (idade < 0) break;

        printf("Sexo (M/F): ");
        scanf(" %c", &sexo);

        printf("Cor dos olhos (azuis, verdes, castanhos): ");
        scanf("%s", cor_olhos);

        printf("Cor dos cabelos (louros, castanhos, pretos): ");
        scanf("%s", cor_cabelos);

        total_pessoas++;
        soma_idade += idade;

        // Sexo
        if (sexo == 'M' || sexo == 'm') {
            qtd_homens++;
        } else if (sexo == 'F' || sexo == 'f') {
            qtd_mulheres++;
        }

        // Cor dos olhos
        if (strcmp(cor_olhos, "azuis") == 0) {
            olhos_azuis++;
        } else if (strcmp(cor_olhos, "verdes") == 0) {
            olhos_verdes++;
        } else if (strcmp(cor_olhos, "castanhos") == 0) {
            olhos_castanhos++;
        }

        // Cor dos cabelos
        if (strcmp(cor_cabelos, "louros") == 0) {
            cabelos_louros++;
        } else if (strcmp(cor_cabelos, "castanhos") == 0) {
            cabelos_castanhos++;
        } else if (strcmp(cor_cabelos, "pretos") == 0) {
            cabelos_pretos++;
        }
    }

    if (total_pessoas == 0) {
        printf("\nNenhum dado foi inserido.\n");
    } else {
        float media_idade = (float)soma_idade / total_pessoas;

        printf("\n--- Estatísticas da pesquisa ---\n");
        printf("Total de pessoas: %d\n", total_pessoas);
        printf("Homens: %d\n", qtd_homens);
        printf("Mulheres: %d\n", qtd_mulheres);
        printf("Olhos azuis: %d\n", olhos_azuis);
        printf("Olhos verdes: %d\n", olhos_verdes);
        printf("Olhos castanhos: %d\n", olhos_castanhos);
        printf("Cabelos louros: %d\n", cabelos_louros);
        printf("Cabelos castanhos: %d\n", cabelos_castanhos);
        printf("Cabelos pretos: %d\n", cabelos_pretos);
        printf("Media de idade: %.2f\n", media_idade);
    }

    return 0;
}
24. Faça um algoritmo que determine e escreva:
- a maior idade dos habitantes
- a quantidade de indivíduos do sexo feminino cuja idade está entre 18 e 35 anos inclusive e que tenham olhos verdes e cabelos louros.
O final do conjunto de habitantes é reconhecido pelo valor -1 entrada como idade.
#include <stdio.h>
#include <string.h>

int main() {
    int idade;
    char sexo;
    char cor_olhos[10];
    char cor_cabelos[10];

    int maior_idade = 0;
    int qtd_mulheres_verdes_louros = 0;

    printf("Digite os dados dos habitantes (idade -1 para sair):\n");

    while (1) {
        printf("\nIdade: ");
        scanf("%d", &idade);
        if (idade == -1) break;

        printf("Sexo (M/F): ");
        scanf(" %c", &sexo);

        printf("Cor dos olhos (azuis, verdes, castanhos): ");
        scanf("%s", cor_olhos);

        printf("Cor dos cabelos (louros, castanhos, pretos): ");
        scanf("%s", cor_cabelos);

        // Atualiza maior idade
        if (idade > maior_idade) {
            maior_idade = idade;
        }

        // Verifica condições para mulheres com olhos verdes e cabelos louros, idade entre 18 e 35
        if ((sexo == 'F' || sexo == 'f') &&
            idade >= 18 && idade <= 35 &&
            strcmp(cor_olhos, "verdes") == 0 &&
            strcmp(cor_cabelos, "louros") == 0) {
            qtd_mulheres_verdes_louros++;
        }
    }

    printf("\nMaior idade dos habitantes: %d\n", maior_idade);
    printf("Quantidade de mulheres com idade entre 18 e 35, olhos verdes e cabelos louros: %d\n", qtd_mulheres_verdes_louros);

    return 0;
}
25. Uma empresa deseja aumentar seus preços em 20%. Faça um algoritmo que leia o código e o preço de custo de cada produto e calcule o preço novo. Calcule também, a
média dos preços com e sem aumento. Mostre o código e o preço novo de cada produto e, no final, as médias. A entrada de dados deve terminar quando for lido um código
de produto negativo. (Use o comando enquanto-faça)
#include <stdio.h>

int main() {
    int codigo;
    float preco_custo, preco_novo;
    float soma_preco_custo = 0, soma_preco_novo = 0;
    int contador = 0;

    printf("Digite o codigo e o preco de custo dos produtos (codigo negativo para terminar):\n");

    while (1) {
        printf("\nCodigo do produto: ");
        scanf("%d", &codigo);

        if (codigo < 0) {
            break;
        }

        printf("Preco de custo: ");
        scanf("%f", &preco_custo);

        preco_novo = preco_custo * 1.20;  // aumento de 20%
        printf("Codigo: %d, Preco novo: %.2f\n", codigo, preco_novo);

        soma_preco_custo += preco_custo;
        soma_preco_novo += preco_novo;
        contador++;
    }

    if (contador > 0) {
        printf("\nMedia dos precos sem aumento: %.2f\n", soma_preco_custo / contador);
        printf("Media dos precos com aumento: %.2f\n", soma_preco_novo / contador);
    } else {
        printf("\nNenhum produto foi cadastrado.\n");
    }

    return 0;
}
26. Escreva um algoritmo que gere o números de 1000 a 1999 e escreva aqueles que dividido por 11 dão resto igual a 5.
#include <stdio.h>

int main() {
    int i;

    printf("Numeros entre 1000 e 1999 que ao dividir por 11 deixam resto 5:\n");

    for (i = 1000; i <= 1999; i++) {
        if (i % 11 == 5) {
            printf("%d\n", i);
        }
    }

    return 0;
}
27. Escreva um algoritmo que leia 500 valores inteiros e positivos e:
a) encontre o maior valor;
b) encontre o menor valor;
c) calcule a média dos números lidos.
#include <stdio.h>

int main() {
    int i, valor;
    int maior, menor;
    long long soma = 0;  // para evitar overflow
    int quantidade = 500;

    printf("Digite 500 valores inteiros positivos:\n");

    for (i = 0; i < quantidade; i++) {
        scanf("%d", &valor);

        // validar entrada (valor positivo)
        while (valor <= 0) {
            printf("Valor invalido! Digite um valor inteiro positivo:\n");
            scanf("%d", &valor);
        }

        if (i == 0) {
            maior = valor;
            menor = valor;
        } else {
            if (valor > maior) {
                maior = valor;
            }
            if (valor < menor) {
                menor = valor;
            }
        }

        soma += valor;
    }

    printf("\nMaior valor: %d\n", maior);
    printf("Menor valor: %d\n", menor);
    printf("Media dos valores: %.2f\n", (float)soma / quantidade);

    return 0;
}
28. Escreva um algoritmo que lê um valor n inteiro e positivo e que calcula a seguinte soma:
S := 1 + 1/2 + 1/3 + 1/4 + ... + 1/n
O algoritmo deve escrever cada termo gerado e o valor final de S
#include <stdio.h>

int main() {
    int n, i;
    float S = 0.0;

    printf("Digite um numero inteiro positivo: ");
    scanf("%d", &n);

    while (n <= 0) {
        printf("Numero invalido! Digite um inteiro positivo: ");
        scanf("%d", &n);
    }

    printf("Termos da soma:\n");
    for (i = 1; i <= n; i++) {
        float termo = 1.0 / i;
        S += termo;
        printf("1/%d = %.5f\n", i, termo);
    }

    printf("Valor final de S: %.5f\n", S);

    return 0;
}
29. Escrever um algoritmo que calcule e mostre a média aritmética dos números lidos entre 13 e 73.
#include <stdio.h>

int main() {
    int valor;
    int soma = 0;
    int count = 0;

    printf("Digite numeros (digite negativo para terminar):\n");

    while (1) {
        scanf("%d", &valor);
        if (valor < 0) {
            break;
        }
        if (valor >= 13 && valor <= 73) {
            soma += valor;
            count++;
        }
    }

    if (count > 0) {
        printf("Media dos numeros entre 13 e 73: %.2f\n", (float)soma / count);
    } else {
        printf("Nenhum numero valido foi digitado.\n");
    }

    return 0;
}
30. Escrever um algoritmo que gera e escreve os números ímpares entre 100 e 200.
#include <stdio.h>

int main() {
    int i;

    printf("Numeros impares entre 100 e 200:\n");

    for (i = 101; i < 200; i += 2) {
        printf("%d\n", i);
    }

    return 0;
}
31. Escrever um algoritmo que lê 10 valores, um de cada vez, e conta quantos deles estão no intervalo [10,20] e quantos deles estão fora do intervalo, escrevendo estas
informações.
#include <stdio.h>

int main() {
    int i, valor;
    int dentro = 0, fora = 0;

    printf("Digite 10 valores:\n");

    for (i = 0; i < 10; i++) {
        scanf("%d", &valor);
        if (valor >= 10 && valor <= 20) {
            dentro++;
        } else {
            fora++;
        }
    }

    printf("Quantidade dentro do intervalo [10,20]: %d\n", dentro);
    printf("Quantidade fora do intervalo: %d\n", fora);

    return 0;
}
32. Escrever um algoritmo que lê 5 pares de valores a, b, todos inteiros e positivos, um par de cada vez, e com a < b, escreve os inteiros pares de a até b, incluindo o a e o b
se forem pares.
#include <stdio.h>

int main() {
    int a, b;
    int i;

    for (int k = 0; k < 5; k++) {
        printf("Digite o par %d (a b) com a < b: ", k + 1);
        scanf("%d %d", &a, &b);

        // validação simples
        while (a >= b || a <= 0 || b <= 0) {
            printf("Valores invalidos! Digite novamente o par %d (a b) com a < b e ambos positivos: ", k + 1);
            scanf("%d %d", &a, &b);
        }

        printf("Numeros pares entre %d e %d:\n", a, b);

        for (i = a; i <= b; i++) {
            if (i % 2 == 0) {
                printf("%d ", i);
            }
        }
        printf("\n\n");
    }

    return 0;
}
33. Escrever um algoritmo que leia 20 valores para uma variável N e, para cada um deles, calcule a tabuada de 1 até N. Mostre a tabuada na forma: 1 x N = N 2 x N = 2N 3 x
N = 3N ...... N x N = N2 34. Escrever um algoritmo que leia 5 conjuntos de 2 valores, o primeiro representando o número de um aluno, e o segundo representando a sua altura
em centímetros. Encontre o aluno mais alto e o mais baixo. Mostre o número do aluno mais alto e do mais baixo, junto com suas alturas
#include <stdio.h>

void tabuada(int n) {
    for (int i = 1; i <= n; i++) {
        printf("%d x %d = %d\n", i, n, i * n);
    }
}

int main() {
    int N;

    printf("Digite 20 valores para calcular a tabuada:\n");

    for (int i = 0; i < 20; i++) {
        printf("Valor %d: ", i + 1);
        scanf("%d", &N);

        printf("Tabuada de %d:\n", N);
        tabuada(N);
        printf("\n");
    }

    return 0;
}
35. Escrever um algoritmo que leia um conjunto de 50 informações contendo, cada uma delas, a altura e o sexo de uma pessoa (código=1, masculino código=2, feminino),
calcule e mostre o seguinte:
a) a maior e a menor altura da turma
b) a média da altura das mulheres
c) a média da altura da turma.
#include <stdio.h>

int main() {
    float altura, soma_mulheres = 0.0, soma_turma = 0.0;
    int sexo;
    int count_mulheres = 0, count_turma = 0;
    float maior_altura = 0.0, menor_altura = 1000.0; // iniciando menor com valor alto

    for (int i = 0; i < 50; i++) {
        printf("Pessoa %d - Digite a altura (em metros): ", i + 1);
        scanf("%f", &altura);

        printf("Pessoa %d - Digite o sexo (1 - Masculino, 2 - Feminino): ", i + 1);
        scanf("%d", &sexo);

        // Validação simples
        while (sexo != 1 && sexo != 2) {
            printf("Sexo inválido! Digite 1 para Masculino ou 2 para Feminino: ");
            scanf("%d", &sexo);
        }

        // Atualiza maior e menor altura
        if (altura > maior_altura) {
            maior_altura = altura;
        }
        if (altura < menor_altura) {
            menor_altura = altura;
        }

        // Soma para média geral
        soma_turma += altura;
        count_turma++;

        // Soma para média das mulheres
        if (sexo == 2) {
            soma_mulheres += altura;
            count_mulheres++;
        }
    }

    printf("\nMaior altura da turma: %.2f metros\n", maior_altura);
    printf("Menor altura da turma: %.2f metros\n", menor_altura);

    if (count_mulheres > 0) {
        printf("Media da altura das mulheres: %.2f metros\n", soma_mulheres / count_mulheres);
    } else {
        printf("Nao ha mulheres na turma.\n");
    }

    printf("Media da altura da turma: %.2f metros\n", soma_turma / count_turma);

    return 0;
}
36. Escrever um algoritmo que leia um número N que indica quantos valores devem ser lidos a seguir. Para cada número lido, mostre uma tabela contendo o valor lido e o
fatorial deste valor.
#include <stdio.h>

// Função para calcular fatorial
unsigned long long fatorial(int num) {
    unsigned long long fat = 1;
    for (int i = 2; i <= num; i++) {
        fat *= i;
    }
    return fat;
}

int main() {
    int N, valor;

    printf("Digite quantos valores deseja ler: ");
    scanf("%d", &N);

    printf("Digite os %d valores:\n", N);

    printf("Valor\tFatorial\n");
    printf("----------------\n");

    for (int i = 0; i < N; i++) {
        scanf("%d", &valor);
        if (valor < 0) {
            printf("Fatorial nao definido para numeros negativos.\n");
            continue;
        }
        printf("%d\t%llu\n", valor, fatorial(valor));
    }

    return 0;
}
37. Escrever um algoritmo que leia um valor X e calcule e mostre os 20 primeiros termos da série:
1 1 1 1 .....
X X2 X3 X4
#include <stdio.h>
#include <math.h>

int main() {
    int i;
    double X;

    printf("Digite o valor de X: ");
    scanf("%lf", &X);

    printf("Serie:\n");

    // primeiros 4 termos = 1
    for (i = 1; i <= 4; i++) {
        printf("1 ");
    }

    // termos de 5 a 20 = X^1, X^2, ..., X^16
    for (i = 1; i <= 16; i++) {
        printf("%.2lf ", pow(X, i));
    }

    printf("\n");

    return 0;
}
38. Escrever um algoritmo que calcula e escreve o produto dos números primos entre 92 e 1478.
#include <stdio.h>
#include <math.h>

// Função para verificar se um número é primo
int ehPrimo(int num) {
    if (num < 2) return 0;
    int limite = (int)sqrt(num);
    for (int i = 2; i <= limite; i++) {
        if (num % i == 0) return 0;
    }
    return 1;
}

int main() {
    unsigned long long produto = 1;
    int encontrouPrimo = 0;  // para controlar overflow e saída

    for (int n = 92; n <= 1478; n++) {
        if (ehPrimo(n)) {
            // Aviso: o produto pode crescer muito rápido e ultrapassar o limite de unsigned long long
            // Para evitar overflow, pode-se limitar ou apenas contar os primos, mas aqui vai o produto simples.
            produto *= n;
            encontrouPrimo = 1;
        }
    }

    if (encontrouPrimo) {
        printf("Produto dos numeros primos entre 92 e 1478: %llu\n", produto);
    } else {
        printf("Nao foram encontrados numeros primos nesse intervalo.\n");
    }

    return 0;
}
39. Escrever um algoritmo que gera e escreve os 5 primeiros números perfeitos. Um número perfeito é aquele que é igual a soma dos seus divisores. (Ex.: 6 = 1+2+3; 28=
1+2+4+7+14 etc).
#include <stdio.h>

// Função que verifica se um número é perfeito
int ehPerfeito(int num) {
    int soma = 0;
    for (int i = 1; i <= num / 2; i++) {
        if (num % i == 0) {
            soma += i;
        }
    }
    return (soma == num);
}

int main() {
    int contador = 0;
    int num = 2;  // começamos a checar a partir do 2

    printf("Os 5 primeiros numeros perfeitos sao:\n");

    while (contador < 5) {
        if (ehPerfeito(num)) {
            printf("%d\n", num);
            contador++;
        }
        num++;
    }

    return 0;
}
40. Escrever um algoritmo que lê um valor n que indica quantos valores devem ser lidos para m, valores inteiros e positivos, com leitura de um valor de cada vez. Escreva
uma tabela contendo o valor lido, o somatório dos inteiros de 1 até m e o fatorial de m.
#include <stdio.h>

// Função para calcular o fatorial de m
unsigned long long fatorial(int m) {
    unsigned long long fat = 1;
    for (int i = 2; i <= m; i++) {
        fat *= i;
    }
    return fat;
}

// Função para calcular o somatório de 1 até m
int somatorio(int m) {
    return (m * (m + 1)) / 2;  // fórmula da soma dos primeiros m inteiros
}

int main() {
    int n, m;

    printf("Digite quantos valores deseja ler: ");
    scanf("%d", &n);

    printf("Digite os %d valores inteiros e positivos:\n", n);

    printf("Valor\tSomatorio\tFatorial\n");
    printf("----------------------------------\n");

    for (int i = 0; i < n; i++) {
        scanf("%d", &m);
        if (m < 0) {
            printf("Valor invalido (negativo). Ignorado.\n");
            i--;  // para não contar o valor inválido
            continue;
        }
        printf("%d\t%d\t\t%llu\n", m, somatorio(m), fatorial(m));
    }

    return 0;
}
41. Faça um algoritmo que leia as três notas de 50 alunos de uma turma. Para cada aluno, calcule a média ponderada, como segue: MP = ( n1*2 + n2*4 + n3*3 ) / 10
#include <stdio.h>

int main() {
    float n1, n2, n3, media;
    int aluno;

    for (aluno = 1; aluno <= 50; aluno++) {
        printf("Aluno %d - Digite as tres notas: ", aluno);
        scanf("%f %f %f", &n1, &n2, &n3);

        media = (n1 * 2 + n2 * 4 + n3 * 3) / 10.0;

        printf("Media ponderada do aluno %d: %.2f\n\n", aluno, media);
    }

    return 0;
}
42. Faça um algoritmo que calcule a seguinte soma: H = 10 + 10 + 10 + ... + 10
O algoritmo deve ler um número n (inteiro e positivo) e mostrar o resultado final de H. A soma deve ser calculada apenas uma vez.
#include <stdio.h>

int main() {
    int n;
    int H;

    printf("Digite um numero inteiro e positivo: ");
    scanf("%d", &n);

    if (n > 0) {
        H = 10 * n;
        printf("O resultado da soma H = 10 + 10 + ... + 10 (n vezes) e: %d\n", H);
    } else {
        printf("Numero invalido! Digite um valor inteiro e positivo.\n");
    }

    return 0;
}
43. Fazer um algoritmo que leia 5 grupos de 4 valores (A,B,C,D) e mostre-os na ordem lida. Em seguida, ordene-os em ordem decrescente e mostre-os novamente, já
ordenados.
#include <stdio.h>

// Função para ordenar 4 valores em ordem decrescente (bubble sort simples)
void ordenarDecrescente(int v[], int tamanho) {
    int temp;
    for (int i = 0; i < tamanho - 1; i++) {
        for (int j = 0; j < tamanho - 1 - i; j++) {
            if (v[j] < v[j + 1]) {
                temp = v[j];
                v[j] = v[j + 1];
                v[j + 1] = temp;
            }
        }
    }
}

int main() {
    int grupos[5][4];

    // Leitura dos grupos
    printf("Digite 5 grupos de 4 valores (A, B, C, D):\n");
    for (int i = 0; i < 5; i++) {
        printf("Grupo %d:\n", i + 1);
        for (int j = 0; j < 4; j++) {
            scanf("%d", &grupos[i][j]);
        }
    }

    // Mostrar na ordem lida
    printf("\nValores na ordem lida:\n");
    for (int i = 0; i < 5; i++) {
        printf("Grupo %d: ", i + 1);
        for (int j = 0; j < 4; j++) {
            printf("%d ", grupos[i][j]);
        }
        printf("\n");
    }

    // Ordenar cada grupo em ordem decrescente
    for (int i = 0; i < 5; i++) {
        ordenarDecrescente(grupos[i], 4);
    }

    // Mostrar valores ordenados
    printf("\nValores ordenados em ordem decrescente:\n");
    for (int i = 0; i < 5; i++) {
        printf("Grupo %d: ", i + 1);
        for (int j = 0; j < 4; j++) {
            printf("%d ", grupos[i][j]);
        }
        printf("\n");
    }

    return 0;
}
44. Foi feita uma estatística nas 200 principais cidades brasileiras para coletar dados sobre acidentes de trânsito. Foram obtidos os seguintes dados:
- código da cidade
- estado (RS, SC, PR, SP, RJ, ...)
- número de veículos de passeio (em 1992)
- número de acidentes de trânsito com vítimas (em 1992)
Deseja-se saber:
a) qual o maior e o menor índice de acidentes de trânsito e a que cidades pertencem
b) qual a média de veículos nas cidades brasileiras
c) qual a média de acidentes com vítimas entre as cidades do Rio Grande do Sul
#include <stdio.h>
#include <string.h>

#define TOTAL_CIDADES 200

int main() {
    int codigoCidade;
    char estado[3];
    int numVeiculos, numAcidentes;

    int maiorAcidente = -1;
    int menorAcidente = 1000000000;
    int codigoMaiorAcidente = 0, codigoMenorAcidente = 0;

    long long somaVeiculos = 0;
    long long somaAcidentesRS = 0;
    int contRS = 0;

    printf("Digite os dados das %d cidades:\n", TOTAL_CIDADES);

    for (int i = 0; i < TOTAL_CIDADES; i++) {
        printf("\nCidade %d\n", i + 1);
        printf("Codigo da cidade: ");
        scanf("%d", &codigoCidade);

        printf("Estado (RS, SC, PR, SP, RJ, ...): ");
        scanf("%s", estado);

        printf("Numero de veiculos de passeio (1992): ");
        scanf("%d", &numVeiculos);

        printf("Numero de acidentes com vitimas (1992): ");
        scanf("%d", &numAcidentes);

        // a) maior e menor indice de acidentes
        if (numAcidentes > maiorAcidente) {
            maiorAcidente = numAcidentes;
            codigoMaiorAcidente = codigoCidade;
        }
        if (numAcidentes < menorAcidente) {
            menorAcidente = numAcidentes;
            codigoMenorAcidente = codigoCidade;
        }

        // b) soma veículos para media geral
        somaVeiculos += numVeiculos;

        // c) media acidentes RS
        if (strcmp(estado, "RS") == 0) {
            somaAcidentesRS += numAcidentes;
            contRS++;
        }
    }

    printf("\nResultados:\n");
    printf("a) Maior indice de acidentes: %d (Cidade codigo %d)\n", maiorAcidente, codigoMaiorAcidente);
    printf("   Menor indice de acidentes: %d (Cidade codigo %d)\n", menorAcidente, codigoMenorAcidente);

    printf("b) Media de veiculos nas cidades brasileiras: %.2f\n", (float)somaVeiculos / TOTAL_CIDADES);

    if (contRS > 0) {
        printf("c) Media de acidentes com vitimas nas cidades do RS: %.2f\n", (float)somaAcidentesRS / contRS);
    } else {
        printf("c) Nenhuma cidade do RS foi informada.\n");
    }

    return 0;
}
45. Foi feita uma pesquisa entre os 1000 habitantes de uma região para coletar os seguintes dados: sexo (0-feminino, 1-masculino), idade e altura. Faça um algoritmo que leia
as informações coletadas e mostre as seguintes informações: (use o comando repita-até)
a) média da idade do grupo;
b) média da altura das mulheres;
c) média da idade dos homens;
d) percentual de pessoas com idade entre 18 e 35 anos (inclusive).
#include <stdio.h>

int main() {
    int sexo, idade, contador = 0;
    float altura;

    int somaIdadeTotal = 0;
    int somaIdadeHomens = 0;
    int contHomens = 0;
    float somaAlturaMulheres = 0;
    int contMulheres = 0;
    int contIdade18a35 = 0;

    do {
        printf("Habitante %d\n", contador + 1);
        printf("Sexo (0-feminino, 1-masculino): ");
        scanf("%d", &sexo);
        printf("Idade: ");
        scanf("%d", &idade);
        printf("Altura (em metros): ");
        scanf("%f", &altura);

        somaIdadeTotal += idade;

        if (sexo == 0) {  // mulher
            somaAlturaMulheres += altura;
            contMulheres++;
        } else if (sexo == 1) {  // homem
            somaIdadeHomens += idade;
            contHomens++;
        }

        if (idade >= 18 && idade <= 35) {
            contIdade18a35++;
        }

        contador++;
    } while (contador < 1000);

    printf("\nResultados:\n");
    printf("a) Media da idade do grupo: %.2f\n", (float)somaIdadeTotal / contador);

    if (contMulheres > 0) {
        printf("b) Media da altura das mulheres: %.2f metros\n", somaAlturaMulheres / contMulheres);
    } else {
        printf("b) Nenhuma mulher informada.\n");
    }

    if (contHomens > 0) {
        printf("c) Media da idade dos homens: %.2f\n", (float)somaIdadeHomens / contHomens);
    } else {
        printf("c) Nenhum homem informado.\n");
    }

    printf("d) Percentual de pessoas com idade entre 18 e 35 anos: %.2f%%\n", ((float)contIdade18a35 / contador) * 100);

    return 0;
}
46. Foi realizada uma pesquisa de algumas características físicas da população de um certa região. Foram entrevistadas 500 pessoas e coletados os seguintes dados:
a- sexo: M (masculino) e F (feminino)
b- cor dos olhos: A (azuis), V (verdes) e C (castanhos)
c- cor dos cabelos: L (louros), C (castanhos) e P (pretos)
d- idade
Deseja-se saber:
a maior idade do grupo
a quantidade de indivíduos do sexo feminino, cuja idade está entre 18 e 35 anos e que tenham olhos verdes e cabelos louros.
#include <stdio.h>

int main() {
    char sexo, corOlhos, corCabelos;
    int idade;
    int maiorIdade = 0;
    int contMulheresEspeciais = 0;

    for (int i = 0; i < 500; i++) {
        printf("Pessoa %d\n", i+1);

        // Ler sexo
        do {
            printf("Sexo (M/F): ");
            scanf(" %c", &sexo);
            sexo = toupper(sexo);
        } while (sexo != 'M' && sexo != 'F');

        // Ler cor dos olhos
        do {
            printf("Cor dos olhos (A - azuis, V - verdes, C - castanhos): ");
            scanf(" %c", &corOlhos);
            corOlhos = toupper(corOlhos);
        } while (corOlhos != 'A' && corOlhos != 'V' && corOlhos != 'C');

        // Ler cor dos cabelos
        do {
            printf("Cor dos cabelos (L - louros, C - castanhos, P - pretos): ");
            scanf(" %c", &corCabelos);
            corCabelos = toupper(corCabelos);
        } while (corCabelos != 'L' && corCabelos != 'C' && corCabelos != 'P');

        // Ler idade
        do {
            printf("Idade: ");
            scanf("%d", &idade);
        } while (idade < 0);

        if (idade > maiorIdade) {
            maiorIdade = idade;
        }

        // Verificar condição para mulheres específicas
        if (sexo == 'F' && idade >= 18 && idade <= 35 && corOlhos == 'V' && corCabelos == 'L') {
            contMulheresEspeciais++;
        }

        printf("\n");
    }

    printf("Maior idade do grupo: %d\n", maiorIdade);
    printf("Quantidade de mulheres com idade entre 18 e 35 anos, olhos verdes e cabelos louros: %d\n", contMulheresEspeciais);

    return 0;
}
47. Uma loja tem 150 clientes cadastrados e deseja mandar uma correspondência a cada um deles anunciando um bônus especial. Escreva um algoritmo que leia o nome do
cliente e o valor das suas compras no ano passado e calcule um bônus de 10% se o valor das compras for menor que 500.000 e de15 %, caso contrário.
#include <stdio.h>

int main() {
    char nome[100];
    double valorCompras, bonus;

    for (int i = 1; i <= 150; i++) {
        printf("Cliente %d\n", i);

        printf("Nome do cliente: ");
        // Lê o nome (incluindo espaços)
        getchar(); // limpar buffer
        fgets(nome, sizeof(nome), stdin);

        printf("Valor das compras no ano passado: R$ ");
        scanf("%lf", &valorCompras);

        // Calcula bônus
        if (valorCompras < 500000) {
            bonus = valorCompras * 0.10;
        } else {
            bonus = valorCompras * 0.15;
        }

        printf("Cliente: %s", nome);
        printf("Bônus: R$ %.2lf\n\n", bonus);
    }

    return 0;
}
48. Faça um algoritmo que mostre os conceitos finais dos alunos de uma classe de 75 alunos, considerando (use o comando CASO):
a) os dados de cada aluno (número de matrícula e nota numérica final) serão fornecidos pelo usuário
b) a tabela de conceitos segue abaixo:
Nota Conceito
de 0,0 a 4,9 D
de 5,0 a 6,9 C
de 7,0 a 8,9 B
de 9,0 a 10,0 A
#include <stdio.h>

int main() {
    int matricula;
    float nota;
    char conceito;

    for (int i = 1; i <= 75; i++) {
        printf("Aluno %d\n", i);
        printf("Número de matrícula: ");
        scanf("%d", &matricula);
        printf("Nota final: ");
        scanf("%f", &nota);

        // Definir conceito usando switch baseado na faixa de nota
        // Como switch não aceita intervalos, vamos usar truques:
        // Multiplicamos nota por 10 e convertemos para int para usar no switch

        int notaInt = (int)(nota * 10);

        switch (notaInt) {
            case 0: case 1: case 2: case 3: case 4: case 5: case 6: case 7: case 8: case 9:
            case 10: case 11: case 12: case 13: case 14: case 15: case 16: case 17: case 18: case 19:
            case 20: case 21: case 22: case 23: case 24: case 25: case 26: case 27: case 28: case 29:
            case 30: case 31: case 32: case 33: case 34: case 35: case 36: case 37: case 38: case 39:
            case 40: case 41: case 42: case 43: case 44: case 45: case 46: case 47: case 48: case 49:
                conceito = 'D';
                break;

            case 50: case 51: case 52: case 53: case 54: case 55: case 56: case 57: case 58: case 59:
            case 60: case 61: case 62: case 63: case 64: case 65: case 66: case 67: case 68: case 69:
                conceito = 'C';
                break;

            case 70: case 71: case 72: case 73: case 74: case 75: case 76: case 77: case 78: case 79:
            case 80: case 81: case 82: case 83: case 84: case 85: case 86: case 87: case 88: case 89:
                conceito = 'B';
                break;

            case 90: case 91: case 92: case 93: case 94: case 95: case 96: case 97: case 98: case 99:
            case 100:
                conceito = 'A';
                break;

            default:
                conceito = 'I'; // inválido
                break;
        }

        printf("Matrícula: %d | Nota: %.1f | Conceito: %c\n\n", matricula, nota, conceito);
    }

    return 0;
}
49.Faça um algoritmo que lê um valor N inteiro e positivo e que calcula e escreve o fatorial de N (N!).
#include <stdio.h>

int main() {
    int N, i;
    unsigned long long fatorial = 1; // usar unsigned long long para valores maiores

    printf("Digite um valor inteiro e positivo N: ");
    scanf("%d", &N);

    if (N < 0) {
        printf("Valor inválido! N deve ser positivo.\n");
        return 1;
    }

    for (i = 1; i <= N; i++) {
        fatorial *= i;
    }

    printf("%d! = %llu\n", N, fatorial);

    return 0;
}
50. Faça um algoritmo que leia 2 valores inteiros e positivos: X e Y. O algoritmo deve calcular e escrever a função potência X Y
#include <stdio.h>

int main() {
    int X, Y, i;
    unsigned long long resultado = 1;

    // Leitura dos valores
    printf("Digite o valor de X (inteiro e positivo): ");
    scanf("%d", &X);
    printf("Digite o valor de Y (inteiro e positivo): ");
    scanf("%d", &Y);

    if (X < 0 || Y < 0) {
        printf("Valores inválidos! X e Y devem ser inteiros e positivos.\n");
        return 1;
    }

    // Cálculo da potência X^Y
    for (i = 1; i <= Y; i++) {
        resultado *= X;
    }

    printf("%d elevado a %d = %llu\n", X, Y, resultado);

    return 0;
}
51. Faça um algoritmo que calcule o fatorial de um número.
#include <stdio.h>

int main() {
    int n, i;
    unsigned long long fatorial = 1;

    printf("Digite um número inteiro não negativo: ");
    scanf("%d", &n);

    if (n < 0) {
        printf("Número inválido! O fatorial não é definido para negativos.\n");
        return 1;
    }

    for (i = 1; i <= n; i++) {
        fatorial *= i;
    }

    printf("Fatorial de %d = %llu\n", n, fatorial);

    return 0;
}
52. Faça um algoritmo que calcule a combinação e arranjo de um conjunto de tamanho N em subconjuntos de p elementos
#include <stdio.h>

// Função para calcular fatorial
unsigned long long fatorial(int num) {
    unsigned long long fat = 1;
    for (int i = 2; i <= num; i++) {
        fat *= i;
    }
    return fat;
}

int main() {
    int N, p;
    unsigned long long combinacao, arranjo;

    printf("Digite o valor de N (tamanho do conjunto): ");
    scanf("%d", &N);

    printf("Digite o valor de p (tamanho do subconjunto): ");
    scanf("%d", &p);

    if (N < 0 || p < 0 || p > N) {
        printf("Valores inválidos! Certifique-se que 0 <= p <= N.\n");
        return 1;
    }

    combinacao = fatorial(N) / (fatorial(p) * fatorial(N - p));
    arranjo = fatorial(N) / fatorial(N - p);

    printf("Combinação C(%d, %d) = %llu\n", N, p, combinacao);
    printf("Arranjo A(%d, %d) = %llu\n", N, p, arranjo);

    return 0;
}
53. Faça um algoritmo que calcule os 20 primeiros números primos, dados os tres primeiros 1,2 e 3.
#include <stdio.h>
#include <stdbool.h>

// Função que verifica se um número é primo
bool ehPrimo(int num) {
    if (num < 2) return false;
    for (int i = 2; i * i <= num; i++) {
        if (num % i == 0) return false;
    }
    return true;
}

int main() {
    int count = 3; // Já temos 3 números primos (1,2,3) dados no problema
    int num = 4;
    
    printf("Números primos:\n");
    printf("1\n2\n3\n"); // Dados os três primeiros
    
    while (count < 20) {
        if (ehPrimo(num)) {
            printf("%d\n", num);
            count++;
        }
        num++;
    }

    return 0;
}
54. Faça uma algoritmo que receba 2 numeros e divida o intervalo entre eles em 3 partes iguais. Obs. Faça a consistência para que os extremos não sejam iguais.
#include <stdio.h>

int main() {
    float num1, num2;

    // Leitura dos números
    do {
        printf("Digite dois números diferentes (extremos do intervalo):\n");
        printf("Número 1: ");
        scanf("%f", &num1);
        printf("Número 2: ");
        scanf("%f", &num2);

        if (num1 == num2) {
            printf("Erro: Os números não podem ser iguais. Tente novamente.\n");
        }
    } while (num1 == num2);

    // Calcular os pontos que dividem o intervalo em 3 partes iguais
    float delta = (num2 - num1) / 3;

    float ponto1 = num1 + delta;
    float ponto2 = num1 + 2 * delta;

    printf("O intervalo [%.2f, %.2f] dividido em 3 partes iguais tem os pontos:\n", num1, num2);
    printf("Ponto 1: %.2f\n", ponto1);
    printf("Ponto 2: %.2f\n", ponto2);

    return 0;
}
55. Faça uma algoritmo que receba duas datas e retorne a diferença entre elas em dias.
#include <stdio.h>

// Função que verifica se o ano é bissexto
int bissexto(int ano) {
    if ((ano % 400 == 0) || (ano % 4 == 0 && ano % 100 != 0))
        return 1;
    else
        return 0;
}

// Função que retorna o número de dias no mês de acordo com o mês e ano
int dias_no_mes(int mes, int ano) {
    int diasMes[] = {31,28,31,30,31,30,31,31,30,31,30,31};
    if (mes == 2 && bissexto(ano)) return 29;
    return diasMes[mes - 1];
}

// Função que converte uma data em número total de dias desde 01/01/0000
long total_dias(int dia, int mes, int ano) {
    long total = 0;
    int i;

    // Conta os dias dos anos completos
    for (i = 0; i < ano; i++) {
        total += 365;
        if (bissexto(i)) total += 1;
    }

    // Conta os dias dos meses completos do ano atual
    for (i = 1; i < mes; i++) {
        total += dias_no_mes(i, ano);
    }

    // Soma os dias do mês atual
    total += dia;

    return total;
}

int main() {
    int d1, m1, a1;
    int d2, m2, a2;
    long dias1, dias2, diff;

    // Leitura da primeira data
    printf("Digite a primeira data (dia mes ano): ");
    scanf("%d %d %d", &d1, &m1, &a1);

    // Leitura da segunda data
    printf("Digite a segunda data (dia mes ano): ");
    scanf("%d %d %d", &d2, &m2, &a2);

    // Converte as datas para total de dias
    dias1 = total_dias(d1, m1, a1);
    dias2 = total_dias(d2, m2, a2);

    // Calcula a diferença absoluta
    diff = dias1 - dias2;
    if (diff < 0) diff = -diff;

    printf("Diferença entre as datas: %ld dias\n", diff);

    return 0;
}
56. Elaborar um algoritmo que lê três valores a, b, c e os escreve. A seguir, encontre
o maior dos três valores e o escreva com a mensagem : "É o maior”. 
#include <stdio.h>

int main() {
    int a, b, c, maior;

    // Leitura dos valores
    printf("Digite tres valores inteiros: ");
    scanf("%d %d %d", &a, &b, &c);

    // Mostra os valores lidos
    printf("Valores lidos: %d, %d, %d\n", a, b, c);

    // Encontrar o maior valor
    maior = a;
    if (b > maior) {
        maior = b;
    }
    if (c > maior) {
        maior = c;
    }

    // Mostrar o maior valor
    printf("%d é o maior\n", maior);

    return 0;
}
57. Elaborar um algoritmo que lê dois valores a e b e os escreve com a mensagem:
“São múltiplos” ou “Não são múltiplos”. 
#include <stdio.h>

int main() {
    int a, b;

    // Leitura dos valores
    printf("Digite dois valores inteiros: ");
    scanf("%d %d", &a, &b);

    // Mostra os valores lidos
    printf("Valores lidos: %d e %d\n", a, b);

    // Verifica se são múltiplos
    if (a % b == 0 || b % a == 0) {
        printf("São múltiplos\n");
    } else {
        printf("Não são múltiplos\n");
    }

    return 0;
}
58. Escreva um algoritmo que leia o código de um aluno e suas três notas. Calcule a
média ponderada do aluno, considerando que o peso para a maior nota seja 4 e
para as duas restantes, 3. Mostre o código do aluno, suas três notas, a média
calculada e uma mensagem: "APROVADO" se a média for maior ou igual a 5 e
"REPROVADO" se a média for menor que 5. 
#include <stdio.h>

int main() {
    int codigo;
    float n1, n2, n3, media;
    float maior, somaPesos;

    // Leitura do código e notas
    printf("Digite o código do aluno: ");
    scanf("%d", &codigo);

    printf("Digite as três notas do aluno: ");
    scanf("%f %f %f", &n1, &n2, &n3);

    // Identificar a maior nota
    maior = n1;
    if (n2 > maior) maior = n2;
    if (n3 > maior) maior = n3;

    // Calcular média ponderada: maior nota peso 4, outras peso 3
    media = (maior * 4) + ((n1 + n2 + n3) - maior) * 3;
    media = media / (4 + 3 + 3);

    // Mostrar resultados
    printf("Código do aluno: %d\n", codigo);
    printf("Notas: %.2f, %.2f, %.2f\n", n1, n2, n3);
    printf("Média ponderada: %.2f\n", media);

    if (media >= 5)
        printf("APROVADO\n");
    else
        printf("REPROVADO\n");

    return 0;
}
59. Faça um algoritmo que leia um número inteiro e mostre uma mensagem
indicando se este número é par ou ímpar e se é positivo ou negativo. 
#include <stdio.h>

int main() {
    int num;

    printf("Digite um número inteiro: ");
    scanf("%d", &num);

    // Verificar se é par ou ímpar
    if (num % 2 == 0) {
        printf("O número é par.\n");
    } else {
        printf("O número é ímpar.\n");
    }

    // Verificar se é positivo, negativo ou zero
    if (num > 0) {
        printf("O número é positivo.\n");
    } else if (num < 0) {
        printf("O número é negativo.\n");
    } else {
        printf("O número é zero.\n");
    }

    return 0;
}
60. O cardápio de uma lanchonete é o seguinte:
Especificação Preço unitário
100 Cachorro quente 1,10
101 Bauru simples 1,30
102 Bauru c/ovo 1,50
103 Hamburger 1,10
104 Cheeseburger 1,30
105 Refrigerante 1,00
Escrever um algoritmo que leia o código do item pedido, a quantidade e calcule
o valor a ser pago por aquele lanche. Considere que a cada execução somente
será calculado um item. 
#include <stdio.h>

int main() {
    int codigo, quantidade;
    float preco, total;

    printf("Digite o código do item pedido: ");
    scanf("%d", &codigo);

    printf("Digite a quantidade: ");
    scanf("%d", &quantidade);

    // Verificar o preço conforme o código
    switch(codigo) {
        case 100:
            preco = 1.10;
            break;
        case 101:
            preco = 1.30;
            break;
        case 102:
            preco = 1.50;
            break;
        case 103:
            preco = 1.10;
            break;
        case 104:
            preco = 1.30;
            break;
        case 105:
            preco = 1.00;
            break;
        default:
            printf("Código inválido!\n");
            return 1; // Sai do programa com erro
    }

    total = preco * quantidade;
    printf("Valor a pagar: R$ %.2f\n", total);

    return 0;
}
61. Um usuário deseja um algoritmo pelo qual possa escolher que tipo de média
deseja calcular a partir de três notas. Faça um algoritmo que leia as notas, a
opção escolhida pelo usuário e calcule a média:
1- aritmética
2- ponderada (pesos 3, 3, 4) 
#include <stdio.h>

int main() {
    float n1, n2, n3, media;
    int opcao;

    // Ler as três notas
    printf("Digite a primeira nota: ");
    scanf("%f", &n1);
    printf("Digite a segunda nota: ");
    scanf("%f", &n2);
    printf("Digite a terceira nota: ");
    scanf("%f", &n3);

    // Ler a opção do usuário
    printf("Escolha o tipo de média:\n");
    printf("1 - Média aritmética\n");
    printf("2 - Média ponderada (pesos 3, 3, 4)\n");
    printf("Digite a opção: ");
    scanf("%d", &opcao);

    if (opcao == 1) {
        // Média aritmética simples
        media = (n1 + n2 + n3) / 3.0;
        printf("Média aritmética: %.2f\n", media);
    } else if (opcao == 2) {
        // Média ponderada com pesos 3, 3, 4
        media = (n1*3 + n2*3 + n3*4) / 10.0;
        printf("Média ponderada: %.2f\n", media);
    } else {
        printf("Opção inválida!\n");
    }

    return 0;
}
62. Um banco concederá um crédito especial aos seus clientes, variável com o saldo
médio no último ano. Faça um algoritmo que leia o saldo médio de um cliente e
calcule o valor do crédito de acordo com a tabela abaixo. Mostre uma mensagem
informando o saldo médio e o valor do crédito.
Saldo médio Percentual
de 0 a 200 nenhum crédito
de 201 a 400 20% do valor do saldo médio
de 401 a 600 30% do valor do saldo médio
acima de 601 40% do valor do saldo médio
#include <stdio.h>

int main() {
    float saldo_medio, credito;

    printf("Digite o saldo médio do cliente: ");
    scanf("%f", &saldo_medio);

    if (saldo_medio >= 0 && saldo_medio <= 200) {
        credito = 0;
    } else if (saldo_medio <= 400) {
        credito = saldo_medio * 0.20;
    } else if (saldo_medio <= 600) {
        credito = saldo_medio * 0.30;
    } else {
        credito = saldo_medio * 0.40;
    }

    printf("Saldo médio: R$ %.2f\n", saldo_medio);
    printf("Valor do crédito concedido: R$ %.2f\n", credito);

    return 0;
}
63. Um vendedor necessita de um algoritmo que calcule o preço total devido por um
cliente. O algoritmo deve receber o código de um produto e a quantidade
comprada e calcular o preço total, usando a tabela abaixo:
Código do produto Preço unitário
 1001 5,32
 1324 6,45
 6548 2,37
 0987 5,32
 7623 6,45 
 #include <stdio.h>

int main() {
    int codigo;
    int quantidade;
    float preco_unitario = 0.0, total;

    printf("Digite o código do produto: ");
    scanf("%d", &codigo);

    printf("Digite a quantidade comprada: ");
    scanf("%d", &quantidade);

    switch (codigo) {
        case 1001:
            preco_unitario = 5.32;
            break;
        case 1324:
            preco_unitario = 6.45;
            break;
        case 6548:
            preco_unitario = 2.37;
            break;
        case 987:  // Código 0987, lendo como 987 para evitar zero à esquerda
            preco_unitario = 5.32;
            break;
        case 7623:
            preco_unitario = 6.45;
            break;
        default:
            printf("Código de produto inválido.\n");
            return 1;  // Encerra o programa com erro
    }

    total = preco_unitario * quantidade;
    printf("Preço total a pagar: R$ %.2f\n", total);

    return 0;
}
64. Um vendedor precisa de um algoritmo que calcule o preço total devido por um
cliente. O algoritmo deve receber o código de um produto e a quantidade
comprada e calcular o preço total, usando a tabela abaixo. Mostre uma
mensagem no caso de código inválido.
 Código Preço Unitário
 'ABCD' R$ 5,30
 'XYPK' R$ 6,00
 'KLMP' R$ 3,20
 'QRST' R$ 2,50
 #include <stdio.h>
#include <string.h>

int main() {
    char codigo[5];  // 4 caracteres + '\0'
    int quantidade;
    float preco_unitario = 0.0, total;
    int codigo_valido = 1;

    printf("Digite o código do produto (4 letras): ");
    scanf("%4s", codigo);

    printf("Digite a quantidade comprada: ");
    scanf("%d", &quantidade);

    if (strcmp(codigo, "ABCD") == 0) {
        preco_unitario = 5.30;
    } else if (strcmp(codigo, "XYPK") == 0) {
        preco_unitario = 6.00;
    } else if (strcmp(codigo, "KLMP") == 0) {
        preco_unitario = 3.20;
    } else if (strcmp(codigo, "QRST") == 0) {
        preco_unitario = 2.50;
    } else {
        codigo_valido = 0;
        printf("Código inválido.\n");
    }

    if (codigo_valido) {
        total = preco_unitario * quantidade;
        printf("Preço total a pagar: R$ %.2f\n", total);
    }

    return 0;
}
65. Crie um algoritmo em que o aluno digita duas notas bimestrais e informa se o
aluno foi aprovado ou não. Nota: Considere aprovado se a nota for maior que
5.0. 
#include <stdio.h>

int main() {
    float nota1, nota2, media;

    printf("Digite a primeira nota: ");
    scanf("%f", &nota1);

    printf("Digite a segunda nota: ");
    scanf("%f", &nota2);

    media = (nota1 + nota2) / 2;

    printf("Media: %.2f\n", media);

    if (media > 5.0) {
        printf("Aluno aprovado!\n");
    } else {
        printf("Aluno reprovado!\n");
    }

    return 0;
}
66. Escreva um algoritmo que leia dois números inteiros e determine qual é o menor
e qual é o maior também. 
#include <stdio.h>

int main() {
    int num1, num2;

    printf("Digite o primeiro número inteiro: ");
    scanf("%d", &num1);

    printf("Digite o segundo número inteiro: ");
    scanf("%d", &num2);

    if (num1 > num2) {
        printf("Maior: %d\n", num1);
        printf("Menor: %d\n", num2);
    } else if (num2 > num1) {
        printf("Maior: %d\n", num2);
        printf("Menor: %d\n", num1);
    } else {
        printf("Os números são iguais: %d\n", num1);
    }

    return 0;
}
67. Crie o algoritmo Funcionario para calcular o aumento salarial de um empregado.
Por padrão, o aumento será de 15%. Entretanto, deve ser aplicada uma regra
diferente para cada faixa salarial. Regras:
a) se 1.500,00 <= salarioAtual < 1.750,00: aumento igual a 12%
b) se 1.750,00 <= salarioAtual < 2.000,00: aumento igual a 10%
c) se 2.000,00 <= salarioAtual < 3.000,00: aumento igual a 7%
d) se salarioAtual acima de 3.000,00: aumento igual a 5%. 
#include <stdio.h>

int main() {
    float salarioAtual, aumento, novoSalario;

    printf("Digite o salário atual do funcionário: ");
    scanf("%f", &salarioAtual);

    if (salarioAtual >= 1500.00 && salarioAtual < 1750.00) {
        aumento = salarioAtual * 0.12;
    } else if (salarioAtual >= 1750.00 && salarioAtual < 2000.00) {
        aumento = salarioAtual * 0.10;
    } else if (salarioAtual >= 2000.00 && salarioAtual < 3000.00) {
        aumento = salarioAtual * 0.07;
    } else if (salarioAtual >= 3000.00) {
        aumento = salarioAtual * 0.05;
    } else {
        aumento = salarioAtual * 0.15; // Aumento padrão para salários abaixo de 1500
    }

    novoSalario = salarioAtual + aumento;

    printf("Salário atual: R$ %.2f\n", salarioAtual);
    printf("Aumento aplicado: R$ %.2f\n", aumento);
    printf("Novo salário: R$ %.2f\n", novoSalario);

    return 0;
}
68. Crie um algoritmo que calcula o desconto previdenciário de um funcionário. Dado
um salário, o programa deve retornar o valor do desconto proporcional ao
mesmo. O cálculo segue a regra: o desconto é de 11% do valor do salário,
entretanto, o valor máximo de desconto é 318,20. Sendo assim, ou o algoritmo
retorna o valor equivalente a 11% sobre o salário ou 318,20. 
#include <stdio.h>

int main() {
    float salario, desconto;

    printf("Digite o salário do funcionário: ");
    scanf("%f", &salario);

    desconto = salario * 0.11;  // 11% do salário

    if (desconto > 318.20) {
        desconto = 318.20;  // Valor máximo do desconto
    }

    printf("Desconto previdenciário: R$ %.2f\n", desconto);

    return 0;
}
69. Crie um algoritmo chamado Zodiaco. Este algoritmo deve ler a data do seu
aniversário e atribuir um valor para a variável inteira chamada signo, conforme
lista abaixo:
a) 1o
 signo do zodíaco: Aquário (21/jan a 19/fev)
b) 2o
 signo do zodíaco: Peixes (20/fev a 20/mar)
c) 3o
 signo do zodíaco: Áries (21/mar a 20/abr)
d) 4o
 signo do zodíaco: Touro (21/abr a 20/mai)
e) 5o
 signo do zodíaco: Gêmeos (21/mai a 20/jun)
f) 6o
 signo do zodíaco: Câncer (21/jun a 21/jul)
g) 7o
 signo do zodíaco: Leão (22/jul a 22/ago)
h) 8o
 signo do zodíaco: Virgem (23/ago a 22/set)
i) 9o
 signo do zodíaco: Libra (23/set a 22/out)
j) 10o
 signo do zodíaco: Escorpião (23/out a 21/nov)
k) 11o
 signo do zodíaco: Sagitário (22/nov a 21/dez)
l) 12o
 signo do zodíaco: Capricórnio (22/dez a 20/jan)
O algoritmo deve imprimir uma mensagem, como o exemplo: "Você é do seguinte
signo do zodíaco: Libra" 
#include <stdio.h>

int main() {
    int dia, mes;
    int signo = 0;

    printf("Digite o dia do seu aniversário: ");
    scanf("%d", &dia);
    printf("Digite o mês do seu aniversário (1 a 12): ");
    scanf("%d", &mes);

    // Verifica o signo com base na data
    if ((mes == 1 && dia >= 21) || (mes == 2 && dia <= 19))
        signo = 1; // Aquário
    else if ((mes == 2 && dia >= 20) || (mes == 3 && dia <= 20))
        signo = 2; // Peixes
    else if ((mes == 3 && dia >= 21) || (mes == 4 && dia <= 20))
        signo = 3; // Áries
    else if ((mes == 4 && dia >= 21) || (mes == 5 && dia <= 20))
        signo = 4; // Touro
    else if ((mes == 5 && dia >= 21) || (mes == 6 && dia <= 20))
        signo = 5; // Gêmeos
    else if ((mes == 6 && dia >= 21) || (mes == 7 && dia <= 21))
        signo = 6; // Câncer
    else if ((mes == 7 && dia >= 22) || (mes == 8 && dia <= 22))
        signo = 7; // Leão
    else if ((mes == 8 && dia >= 23) || (mes == 9 && dia <= 22))
        signo = 8; // Virgem
    else if ((mes == 9 && dia >= 23) || (mes == 10 && dia <= 22))
        signo = 9; // Libra
    else if ((mes == 10 && dia >= 23) || (mes == 11 && dia <= 21))
        signo = 10; // Escorpião
    else if ((mes == 11 && dia >= 22) || (mes == 12 && dia <= 21))
        signo = 11; // Sagitário
    else if ((mes == 12 && dia >= 22) || (mes == 1 && dia <= 20))
        signo = 12; // Capricórnio
    else {
        printf("Data inválida.\n");
        return 1;
    }

    // Imprime a mensagem de acordo com o signo
    switch (signo) {
        case 1: printf("Você é do seguinte signo do zodíaco: Aquário\n"); break;
        case 2: printf("Você é do seguinte signo do zodíaco: Peixes\n"); break;
        case 3: printf("Você é do seguinte signo do zodíaco: Áries\n"); break;
        case 4: printf("Você é do seguinte signo do zodíaco: Touro\n"); break;
        case 5: printf("Você é do seguinte signo do zodíaco: Gêmeos\n"); break;
        case 6: printf("Você é do seguinte signo do zodíaco: Câncer\n"); break;
        case 7: printf("Você é do seguinte signo do zodíaco: Leão\n"); break;
        case 8: printf("Você é do seguinte signo do zodíaco: Virgem\n"); break;
        case 9: printf("Você é do seguinte signo do zodíaco: Libra\n"); break;
        case 10: printf("Você é do seguinte signo do zodíaco: Escorpião\n"); break;
        case 11: printf("Você é do seguinte signo do zodíaco: Sagitário\n"); break;
        case 12: printf("Você é do seguinte signo do zodíaco: Capricórnio\n"); break;
    }

    return 0;
}
70. Crie um algoritmo que retorne verdadeiro quando um número fornecido for par. 
#include <stdio.h>
#include <stdbool.h>  // para usar o tipo bool (verdadeiro/falso)

bool ehPar(int num) {
    return (num % 2 == 0);
}

int main() {
    int numero;
    printf("Digite um número inteiro: ");
    scanf("%d", &numero);

    if (ehPar(numero)) {
        printf("O número %d é par.\n", numero);
    } else {
        printf("O número %d não é par.\n", numero);
    }

    return 0;
}
71. Crie um algoritmo que peça o nome, a altura e o peso de duas pessoas e
apresente o nome da mais pesada e o nome da mais alta. 
#include <stdio.h>
#include <string.h>

int main() {
    char nome1[50], nome2[50];
    float altura1, altura2;
    float peso1, peso2;

    // Entrada dos dados da primeira pessoa
    printf("Digite o nome da primeira pessoa: ");
    fgets(nome1, sizeof(nome1), stdin);
    nome1[strcspn(nome1, "\n")] = 0;  // remover o '\n' do final
    printf("Digite a altura da primeira pessoa (em metros): ");
    scanf("%f", &altura1);
    printf("Digite o peso da primeira pessoa (em kg): ");
    scanf("%f", &peso1);

    getchar(); // limpar buffer do teclado

    // Entrada dos dados da segunda pessoa
    printf("Digite o nome da segunda pessoa: ");
    fgets(nome2, sizeof(nome2), stdin);
    nome2[strcspn(nome2, "\n")] = 0;  // remover o '\n' do final
    printf("Digite a altura da segunda pessoa (em metros): ");
    scanf("%f", &altura2);
    printf("Digite o peso da segunda pessoa (em kg): ");
    scanf("%f", &peso2);

    // Verificando a pessoa mais pesada
    if (peso1 > peso2) {
        printf("A pessoa mais pesada é: %s\n", nome1);
    } else if (peso2 > peso1) {
        printf("A pessoa mais pesada é: %s\n", nome2);
    } else {
        printf("Ambas as pessoas têm o mesmo peso.\n");
    }

    // Verificando a pessoa mais alta
    if (altura1 > altura2) {
        printf("A pessoa mais alta é: %s\n", nome1);
    } else if (altura2 > altura1) {
        printf("A pessoa mais alta é: %s\n", nome2);
    } else {
        printf("Ambas as pessoas têm a mesma altura.\n");
    }

    return 0;
}
72. Um determinado clube de futebol pretende classificar seus atletas em categorias
e para isto ele contratou um programador para criar um programa que
executasse esta tarefa. Para isso o clube criou uma tabela que continha a faixa
etária do atleta e sua categoria. A tabela está demonstrada abaixo:
IDADE CATEGORIA
De 05 a 10 Infantil
De 11 a 15 Juvenil
De 16 a 20 Junior
De 21 a 25 Profissional
Construa um programa que solicite o nome e a idade de um atleta e imprima a
sua categoria.
#include <stdio.h>

int main() {
    char nome[50];
    int idade;

    // Entrada dos dados
    printf("Digite o nome do atleta: ");
    fgets(nome, sizeof(nome), stdin);
    nome[strcspn(nome, "\n")] = 0; // Remove o '\n' ao final

    printf("Digite a idade do atleta: ");
    scanf("%d", &idade);

    // Verifica a categoria
    printf("Atleta: %s\n", nome);

    if (idade >= 5 && idade <= 10) {
        printf("Categoria: Infantil\n");
    } else if (idade >= 11 && idade <= 15) {
        printf("Categoria: Juvenil\n");
    } else if (idade >= 16 && idade <= 20) {
        printf("Categoria: Junior\n");
    } else if (idade >= 21 && idade <= 25) {
        printf("Categoria: Profissional\n");
    } else {
        printf("Idade fora das categorias previstas.\n");
    }

    return 0;
}
73. Faça um programa, utilizando estrutura de condição, que receba um número
real, digitado pelo usuário e mostre o menu para selecionar o tipo de cálculo que
deve ser realizado:
101-Raiz quadrada
102-A metade
103-10% do número
104-O dobro
Escolha a opção: 
#include <stdio.h>
#include <math.h>

int main() {
    double num, resultado;
    int opcao;

    // Ler o número real
    printf("Digite um numero real: ");
    scanf("%lf", &num);

    // Mostrar o menu
    printf("Escolha o tipo de calculo:\n");
    printf("101 - Raiz quadrada\n");
    printf("102 - A metade\n");
    printf("103 - 10%% do numero\n");
    printf("104 - O dobro\n");
    printf("Escolha a opcao: ");
    scanf("%d", &opcao);

    // Estrutura condicional para calcular conforme a opção
    switch(opcao) {
        case 101:
            if (num >= 0) {
                resultado = sqrt(num);
                printf("Raiz quadrada de %.2lf = %.2lf\n", num, resultado);
            } else {
                printf("Numero negativo nao possui raiz quadrada real.\n");
            }
            break;
        case 102:
            resultado = num / 2;
            printf("A metade de %.2lf = %.2lf\n", num, resultado);
            break;
        case 103:
            resultado = num * 0.10;
            printf("10%% de %.2lf = %.2lf\n", num, resultado);
            break;
        case 104:
            resultado = num * 2;
            printf("O dobro de %.2lf = %.2lf\n", num, resultado);
            break;
        default:
            printf("Opcao invalida.\n");
            break;
    }

    return 0;
}
74. O programa de uma loja de móveis mostra o seguinte menu na tela de vendas:
1-Venda a Vista
2-Venda a Prazo 30 dias
3-Venda a Prazo 60 dias
4-Venda a Prazo com 90 dias
5-Venda com cartão de débito
6-Venda com cartão de crédito
Escolha a opção: 
#include <stdio.h>

int main() {
    int opcao;

    printf("Menu de vendas:\n");
    printf("1 - Venda a Vista\n");
    printf("2 - Venda a Prazo 30 dias\n");
    printf("3 - Venda a Prazo 60 dias\n");
    printf("4 - Venda a Prazo com 90 dias\n");
    printf("5 - Venda com cartao de debito\n");
    printf("6 - Venda com cartao de credito\n");
    printf("Escolha a opcao: ");
    scanf("%d", &opcao);

    switch(opcao) {
        case 1:
            printf("Venda a Vista selecionada.\n");
            break;
        case 2:
            printf("Venda a Prazo 30 dias selecionada.\n");
            break;
        case 3:
            printf("Venda a Prazo 60 dias selecionada.\n");
            break;
        case 4:
            printf("Venda a Prazo com 90 dias selecionada.\n");
            break;
        case 5:
            printf("Venda com cartao de debito selecionada.\n");
            break;
        case 6:
            printf("Venda com cartao de credito selecionada.\n");
            break;
        default:
            printf("Opcao invalida.\n");
            break;
    }

    return 0;
}
75. Faça um programa que receba o valor da venda, escolha a condição de
pagamento no menu e mostre o total da venda final conforme condições a seguir:
Venda a Vista - desconto de 10%
Venda a Prazo 30 dias - desconto de 5%
Venda a Prazo 60 dias - mesmo preço
Venda a Prazo 90 dias - acréscimo de 5%
Venda com cartão de débito - desconto de 8%
Venda com cartão de crédito - desconto de 7% 
#include <stdio.h>

int main() {
    float valorVenda, valorFinal;
    int opcao;

    printf("Digite o valor da venda: R$ ");
    scanf("%f", &valorVenda);

    printf("Escolha a condicao de pagamento:\n");
    printf("1 - Venda a Vista (desconto 10%%)\n");
    printf("2 - Venda a Prazo 30 dias (desconto 5%%)\n");
    printf("3 - Venda a Prazo 60 dias (mesmo preco)\n");
    printf("4 - Venda a Prazo 90 dias (acrescimo 5%%)\n");
    printf("5 - Venda com cartao de debito (desconto 8%%)\n");
    printf("6 - Venda com cartao de credito (desconto 7%%)\n");
    printf("Opcao: ");
    scanf("%d", &opcao);

    switch(opcao) {
        case 1:
            valorFinal = valorVenda * 0.90; // 10% desconto
            break;
        case 2:
            valorFinal = valorVenda * 0.95; // 5% desconto
            break;
        case 3:
            valorFinal = valorVenda; // mesmo preço
            break;
        case 4:
            valorFinal = valorVenda * 1.05; // 5% acréscimo
            break;
        case 5:
            valorFinal = valorVenda * 0.92; // 8% desconto
            break;
        case 6:
            valorFinal = valorVenda * 0.93; // 7% desconto
            break;
        default:
            printf("Opcao invalida!\n");
            return 1; // sai do programa com erro
    }

    printf("Valor final da venda: R$ %.2f\n", valorFinal);

    return 0;
}
76. Faça um algoritmo que receba uma data no formato DDMMAAAA e escreva qual
a estação do ano correspondente (Primavera, Verão, Outono, Inverno). 
#include <stdio.h>

int main() {
    int data, dia, mes, ano;

    printf("Digite a data no formato DDMMAAAA: ");
    scanf("%d", &data);

    // Extrair dia, mês e ano
    dia = data / 1000000;          // pega os dois primeiros dígitos (DD)
    mes = (data / 10000) % 100;    // pega os dois próximos dígitos (MM)
    ano = data % 10000;            // pega os últimos quatro dígitos (AAAA)

    // Verificar a estação
    if ((mes == 9 && dia >= 22) || (mes == 10) || (mes == 11) || (mes == 12 && dia <= 21)) {
        printf("Estacao: Primavera\n");
    }
    else if ((mes == 12 && dia >= 22) || (mes == 1) || (mes == 2) || (mes == 3 && dia <= 20)) {
        printf("Estacao: Verao\n");
    }
    else if ((mes == 3 && dia >= 21) || (mes == 4) || (mes == 5) || (mes == 6 && dia <= 21)) {
        printf("Estacao: Outono\n");
    }
    else if ((mes == 6 && dia >= 22) || (mes == 7) || (mes == 8) || (mes == 9 && dia <= 21)) {
        printf("Estacao: Inverno\n");
    }
    else {
        printf("Data invalida!\n");
    }

    return 0;
}
77. Elaborar um algoritmo para imprimir o número de dias de um dado mês e ano.
Anos bissextos deverão ser tratados convenientemente.
Dica: Anos bissextos são múltiplos de 4 e não são múltiplos de 100, exceto os
anos múltiplos de 400, que também são bissextos
#include <stdio.h>

// Função para verificar se o ano é bissexto
int ano_bissexto(int ano) {
    if ((ano % 400 == 0) || (ano % 4 == 0 && ano % 100 != 0))
        return 1;  // Ano bissexto
    else
        return 0;  // Ano normal
}

int main() {
    int mes, ano, dias;

    printf("Digite o mês (1-12): ");
    scanf("%d", &mes);

    printf("Digite o ano: ");
    scanf("%d", &ano);

    if (mes < 1 || mes > 12) {
        printf("Mês inválido!\n");
        return 1;
    }

    switch(mes) {
        case 1: case 3: case 5: case 7: case 8: case 10: case 12:
            dias = 31;
            break;
        case 4: case 6: case 9: case 11:
            dias = 30;
            break;
        case 2:
            if (ano_bissexto(ano))
                dias = 29;
            else
                dias = 28;
            break;
    }

    printf("O mês %d do ano %d tem %d dias.\n", mes, ano, dias);

    return 0;
}
78. Faça um programa que lê quatro valores: I, A, B e C, onde I é um número inteiro
e positivo e A, B, e C são quaisquer valores reais. O programa deve escrever os
valores lidos e:
• se I = 1, escrever os três valores A, B e C em ordem crescente;
• se I = 2, escrever os três valores A, B e C em ordem decrescente;
• se I = 3, escrever os três valores A, B, e C de forma que o maior valor fique
entre os outros dois;
• se I não for um dos três valores acima, dar uma mensagem indicando isto. 
#include <stdio.h>

void ordem_crescente(float *a, float *b, float *c) {
    float temp;
    if (*a > *b) { temp = *a; *a = *b; *b = temp; }
    if (*a > *c) { temp = *a; *a = *c; *c = temp; }
    if (*b > *c) { temp = *b; *b = *c; *c = temp; }
}

void ordem_decrescente(float *a, float *b, float *c) {
    float temp;
    if (*a < *b) { temp = *a; *a = *b; *b = temp; }
    if (*a < *c) { temp = *a; *a = *c; *c = temp; }
    if (*b < *c) { temp = *b; *b = *c; *c = temp; }
}

void maior_entre(float *a, float *b, float *c) {
    // Colocar maior entre os outros dois (na posição b)
    // Ordenar para facilitar
    ordem_crescente(a, b, c);

    float maior = *c;
    *c = *b;
    *b = maior;
}

int main() {
    int I;
    float A, B, C;

    printf("Digite um valor inteiro e positivo para I: ");
    scanf("%d", &I);
    printf("Digite três valores reais para A, B e C: ");
    scanf("%f %f %f", &A, &B, &C);

    printf("Valores lidos: I=%d, A=%.2f, B=%.2f, C=%.2f\n", I, A, B, C);

    if (I == 1) {
        ordem_crescente(&A, &B, &C);
        printf("Ordem crescente: %.2f %.2f %.2f\n", A, B, C);
    } 
    else if (I == 2) {
        ordem_decrescente(&A, &B, &C);
        printf("Ordem decrescente: %.2f %.2f %.2f\n", A, B, C);
    } 
    else if (I == 3) {
        maior_entre(&A, &B, &C);
        printf("Maior valor entre os outros dois: %.2f %.2f %.2f\n", A, B, C);
    } 
    else {
        printf("Valor de I inválido! Deve ser 1, 2 ou 3.\n");
    }

    return 0;
}
79. Faça um algoritmo que leia a primeira letra do estado civil de uma pessoa e
mostre uma mensagem com a sua descrição (Solteiro, Casado, Viúvo,
Divorciado, Desquitado). Mostre uma mensagem de erro, se necessário.
#include <stdio.h>

int main() {
    char estadoCivil;

    printf("Digite a primeira letra do estado civil (S, C, V, D, X): ");
    scanf(" %c", &estadoCivil);

    // Converte para maiúscula para facilitar a comparação
    if (estadoCivil >= 'a' && estadoCivil <= 'z') {
        estadoCivil = estadoCivil - ('a' - 'A');
    }

    switch (estadoCivil) {
        case 'S':
            printf("Estado civil: Solteiro\n");
            break;
        case 'C':
            printf("Estado civil: Casado\n");
            break;
        case 'V':
            printf("Estado civil: Viúvo\n");
            break;
        case 'D':
            printf("Estado civil: Divorciado\n");
            break;
        case 'X':
            printf("Estado civil: Desquitado\n");
            break;
        default:
            printf("Erro: letra inválida para estado civil.\n");
    }

    return 0;
}
80. Construa um algoritmo que leia um número inteiro de 1 a 7 e informe o dia da
semana correspondente, sendo domingo o dia de número 1. Se o número não
corresponder a um dia da semana, mostre uma mensagem de erro.
#include <stdio.h>

int main() {
    int dia;

    printf("Digite um número de 1 a 7 para o dia da semana (1=Domingo): ");
    scanf("%d", &dia);

    switch (dia) {
        case 1:
            printf("Domingo\n");
            break;
        case 2:
            printf("Segunda-feira\n");
            break;
        case 3:
            printf("Terça-feira\n");
            break;
        case 4:
            printf("Quarta-feira\n");
            break;
        case 5:
            printf("Quinta-feira\n");
            break;
        case 6:
            printf("Sexta-feira\n");
            break;
        case 7:
            printf("Sábado\n");
            break;
        default:
            printf("Erro: número inválido para dia da semana.\n");
    }

    return 0;
}
81. Crie um algoritmo para ler uma letra do alfabeto e mostrar uma mensagem: se é
vogal ou consoante. 
#include <stdio.h>

int main() {
    char letra;

    printf("Digite uma letra do alfabeto: ");
    scanf(" %c", &letra);

    // Converte para maiúscula para facilitar a comparação
    if (letra >= 'a' && letra <= 'z') {
        letra = letra - ('a' - 'A');
    }

    // Verifica se é uma letra válida
    if (letra < 'A' || letra > 'Z') {
        printf("Erro: caractere inválido.\n");
        return 1;
    }

    // Verifica se é vogal
    if (letra == 'A' || letra == 'E' || letra == 'I' || letra == 'O' || letra == 'U') {
        printf("A letra %c é uma vogal.\n", letra);
    } else {
        printf("A letra %c é uma consoante.\n", letra);
    }

    return 0;
}
82. Construa um algoritmo que, tendo como dados de entrada o preço de um
produto e um código de origem, mostre o preço junto de sua procedência (ex.
500,00 – Sul). Caso o código não seja nenhum dos especificados, o produto
deve ser encarado como importado.
Código de origem
1 – Sul 5 ou 6 – Nordeste
2 – Norte 7 ou 8 ou 9 – Sudeste
3 – Leste 10 até 20 – Centro Oeste
4 – Oeste 25 até 35 – Nordeste 
#include <stdio.h>

int main() {
    float preco;
    int codigo;

    printf("Digite o preço do produto: ");
    scanf("%f", &preco);

    printf("Digite o código de origem: ");
    scanf("%d", &codigo);

    printf("Preço: %.2f - Procedência: ", preco);

    if (codigo == 1) {
        printf("Sul\n");
    } else if (codigo == 2) {
        printf("Norte\n");
    } else if (codigo == 3) {
        printf("Leste\n");
    } else if (codigo == 4) {
        printf("Oeste\n");
    } else if (codigo == 5 || codigo == 6) {
        printf("Nordeste\n");
    } else if (codigo == 7 || codigo == 8 || codigo == 9) {
        printf("Sudeste\n");
    } else if (codigo >= 10 && codigo <= 20) {
        printf("Centro Oeste\n");
    } else if (codigo >= 25 && codigo <= 35) {
        printf("Nordeste\n");
    } else {
        printf("Importado\n");
    }

    return 0;
}
83. Crie um algoritmo para uma calculadora utilizando a instrução escolha-caso para
determinar a operação que deve ser executada, conforme o usuário escolher no
menu de opções. Conforme a opção escolhida pelo usuário, uma operação
diferente da calculadora deve ser executada. 
#include <stdio.h>

int main() {
    int opcao;
    float num1, num2, resultado;

    printf("Escolha a operação:\n");
    printf("1 - Soma (+)\n");
    printf("2 - Subtração (-)\n");
    printf("3 - Multiplicação (*)\n");
    printf("4 - Divisão (/)\n");
    printf("Digite a opção desejada: ");
    scanf("%d", &opcao);

    printf("Digite o primeiro número: ");
    scanf("%f", &num1);

    printf("Digite o segundo número: ");
    scanf("%f", &num2);

    switch(opcao) {
        case 1:
            resultado = num1 + num2;
            printf("Resultado: %.2f + %.2f = %.2f\n", num1, num2, resultado);
            break;
        case 2:
            resultado = num1 - num2;
            printf("Resultado: %.2f - %.2f = %.2f\n", num1, num2, resultado);
            break;
        case 3:
            resultado = num1 * num2;
            printf("Resultado: %.2f * %.2f = %.2f\n", num1, num2, resultado);
            break;
        case 4:
            if(num2 != 0) {
                resultado = num1 / num2;
                printf("Resultado: %.2f / %.2f = %.2f\n", num1, num2, resultado);
            } else {
                printf("Erro: Divisão por zero não é permitida.\n");
            }
            break;
        default:
            printf("Opção inválida!\n");
    }

    return 0;
}
84. Crie um algoritmo que execute as funcionalidades da conta-corrente de uma
pessoa. Toda a conta tem um número, uma pessoa vinculada e um saldo. O saldo é atualizado conforme o tipo de movimentação bancária: depósito ou
retirada. Se for um depósito, o dinheiro é creditado ao saldo; se for retirada, o
dinheiro é debitado do saldo. 
#include <stdio.h>
#include <string.h>

int main() {
    int numeroConta;
    char nomePessoa[50];
    float saldo = 0.0;
    int opcao;
    float valor;

    // Dados iniciais da conta
    printf("Digite o número da conta: ");
    scanf("%d", &numeroConta);

    printf("Digite o nome do titular da conta: ");
    getchar(); // Limpar buffer do teclado
    fgets(nomePessoa, 50, stdin);
    // Remove o '\n' do final do nome, se existir
    nomePessoa[strcspn(nomePessoa, "\n")] = 0;

    printf("Conta criada com sucesso!\n");
    printf("Número: %d\n", numeroConta);
    printf("Titular: %s\n", nomePessoa);
    printf("Saldo inicial: R$ %.2f\n\n", saldo);

    do {
        printf("Escolha a operação:\n");
        printf("1 - Depósito\n");
        printf("2 - Retirada\n");
        printf("3 - Mostrar saldo\n");
        printf("0 - Sair\n");
        printf("Opção: ");
        scanf("%d", &opcao);

        switch(opcao) {
            case 1:
                printf("Digite o valor para depósito: R$ ");
                scanf("%f", &valor);
                if(valor > 0) {
                    saldo += valor;
                    printf("Depósito realizado com sucesso!\n");
                } else {
                    printf("Valor inválido!\n");
                }
                break;
            case 2:
                printf("Digite o valor para retirada: R$ ");
                scanf("%f", &valor);
                if(valor > 0) {
                    if(valor <= saldo) {
                        saldo -= valor;
                        printf("Retirada realizada com sucesso!\n");
                    } else {
                        printf("Saldo insuficiente!\n");
                    }
                } else {
                    printf("Valor inválido!\n");
                }
                break;
            case 3:
                printf("Saldo atual: R$ %.2f\n", saldo);
                break;
            case 0:
                printf("Encerrando o programa...\n");
                break;
            default:
                printf("Opção inválida! Tente novamente.\n");
        }

        printf("\n");

    } while(opcao != 0);

    return 0;
}
85. Faça um algoritmo para o jogo “pedra-papel-tesoura”. O jogo deve imprimir
vitória, empate ou derrota conforme a opção que o jogador escolher e a opção
que for sorteada aleatoriamente pelo computador. Obs.: pedra ganha de tesoura;
que ganha de papel; que ganha de pedra. 
programa PedraPapelTesoura
var
    escolhaJogador, escolhaComputador: inteiro
inicio
    escreva("Escolha uma opção:")
    escreva("1 - Pedra")
    escreva("2 - Papel")
    escreva("3 - Tesoura")
    leia(escolhaJogador)

    aleatorio 1, 3
    leia(escolhaComputador)
    aleatorio off

    escreva("Computador escolheu: ")
    se escolhaComputador = 1 entao
        escreva("Pedra")
    senao se escolhaComputador = 2 entao
        escreva("Papel")
    senao
        escreva("Tesoura")
    fimse

    se escolhaJogador = escolhaComputador entao
        escreva("Empate!")
    senao
        se (escolhaJogador = 1 e escolhaComputador = 3) ou
           (escolhaJogador = 2 e escolhaComputador = 1) ou
           (escolhaJogador = 3 e escolhaComputador = 2) entao
            escreva("Você venceu!")
        senao
            escreva("Você perdeu!")
        fimse
    fimse
fimprograma
86. Crie um algoritmo chamado Estacoes. Este algoritmo deve ler uma data e
armazenar na variável mes um número entre 1 e 12, correspondendo a um dos
meses do ano. No final, você deve imprimir uma mensagem conforme o exemplo:
 "A estação do ano correspondente ao mês 3 é Verão"
Considere a estação prevalente para cada mês:
a) Janeiro (1): Verão
b) Fevereiro (2): Verão
c) Março (3): Verão
d) Abril (4): Outono
e) Maio (5): Outono
f) Junho (6): Outono
g) Julho (7): Inverno
h) Agosto (8): Inverno
i) Setembro (9): Inverno
j) Outubro (10): Primavera
k) Novembro (10): Primavera
l) Dezembro (10): Primavera
programa Estacoes
var
    mes: inteiro
    estacao: cadeia

inicio
    escreva("Digite o número do mês (1 a 12): ")
    leia(mes)

    escolha mes
        caso 1, 2, 3:
            estacao <- "Verão"
        caso 4, 5, 6:
            estacao <- "Outono"
        caso 7, 8, 9:
            estacao <- "Inverno"
        caso 10, 11, 12:
            estacao <- "Primavera"
        outrocaso:
            escreva("Mês inválido!")
            pare
    fimescolha

    escreva("A estação do ano correspondente ao mês ", mes, " é ", estacao)
fimprograma
87. Crie um algoritmo que solicita ao usuário para digitar um número e mostra-o por
extenso. Este número deve variar entre 1 e 10. Se o usuário introduzir um
número que não está neste intervalo, mostre: "Número inválido". 
#include <stdio.h>

int main() {
    int numero;

    // Solicita ao usuário que digite um número
    printf("Digite um número entre 1 e 10: ");
    scanf("%d", &numero);

    // Verifica o número e imprime por extenso
    switch (numero) {
        case 1:
            printf("um\n");
            break;
        case 2:
            printf("dois\n");
            break;
        case 3:
            printf("três\n");
            break;
        case 4:
            printf("quatro\n");
            break;
        case 5:
            printf("cinco\n");
            break;
        case 6:
            printf("seis\n");
            break;
        case 7:
            printf("sete\n");
            break;
        case 8:
            printf("oito\n");
            break;
        case 9:
            printf("nove\n");
            break;
        case 10:
            printf("dez\n");
            break;
        default:
            printf("Número inválido.\n");
            break;
    }

    return 0;
}
88. Some os números de 1 a 100 e imprima o valor. 
#include <stdio.h>

int main() {
    int soma = 0;

    for (int i = 1; i <= 100; i++) {
        soma += i;
    }

    printf("A soma dos números de 1 a 100 é: %d\n", soma);

    return 0;
}
89. Construa um Algoritmo que, para um grupo de 50 valores inteiros, determine:
a) A soma dos números positivos;
b) A quantidade de valores negativos;
#include <stdio.h>

int main() {
    int valor, soma_positivos = 0, qtd_negativos = 0;

    for (int i = 1; i <= 50; i++) {
        printf("Digite o %dº valor inteiro: ", i);
        scanf("%d", &valor);

        if (valor > 0) {
            soma_positivos += valor;
        } else if (valor < 0) {
            qtd_negativos++;
        }
    }

    printf("\nSoma dos números positivos: %d\n", soma_positivos);
    printf("Quantidade de valores negativos: %d\n", qtd_negativos);

    return 0;
}
90. Faça um algoritmo que imprima os múltiplos positivos de 7, inferiores a 1000
#include <stdio.h>

int main() {
    printf("Múltiplos positivos de 7 menores que 1000:\n");

    for (int i = 7; i < 1000; i += 7) {
        printf("%d\n", i);
    }

    return 0;
}
91. Faça um algoritmo que imprima todos os números pares compreendidos entre
85 e 907. O algoritmo deve também calcular a soma destes valores. 
#include <stdio.h>

int main() {
    int soma = 0;

    printf("Números pares entre 85 e 907:\n");

    for (int i = 86; i < 907; i += 2) {
        printf("%d\n", i);
        soma += i;
    }

    printf("\nSoma dos números pares entre 85 e 907: %d\n", soma);

    return 0;
}
92. Faça um algoritmo que calcule o valor de A, dado por:
N
N N A N 1 ... 3
2
2
1
+ + − + − = +
, onde N é um número inteiro positivo. 
#include <stdio.h>

int main() {
    int N;
    float A = 0.0;

    printf("Digite um número inteiro positivo N: ");
    scanf("%d", &N);

    if (N <= 0) {
        printf("N deve ser um número inteiro positivo.\n");
        return 1;
    }

    for (int i = 1; i <= N; i++) {
        float termo = (float)i / 2;

        if (i % 2 == 0) {
            A -= termo;  // sinal negativo
        } else {
            A += termo;  // sinal positivo
        }
    }

    printf("O valor de A é: %.2f\n", A);

    return 0;
}
93. Uma rainha requisitou os serviços de um monge e disse-lhe que pagaria
qualquer preço. O monge, necessitando de alimentos, indagou à rainha sobre o
pagamento, se poderia ser feito com grãos de trigo dispostos em um tabuleiro de
xadrez (que possui 64 casas), de tal forma que o primeiro quadro deveria conter
apenas um grão e os quadros subsequentes, o dobro do quadro anterior. Crie um
algoritmo para calcular o total de grãos que o monge recebeu. 
#include <stdio.h>

int main() {
    int casas = 64;
    unsigned long long graos = 1;
    unsigned long long total = 1;

    for (int i = 2; i <= casas; i++) {
        graos *= 2;
        total += graos;
    }

    printf("Total de grãos de trigo: %llu\n", total);

    return 0;
}
94. Dado o conjunto de instruções a seguir, faça um algoritmo com quatro variações,
colocando o comando de repetição adequadamente, de forma a:
a) Executar o conjunto 10 vezes;
b) Não executar nenhuma vez;
c) Executar o conjunto 100 vezes utilizando duas estruturas de repetição;
d) Executar N vezes, onde N é uma variável informada pelo usuário.
- Ler A, B
- Modulo = A mod B (calcula o resto da divisão)
  #include <stdio.h>

int main() {
    int A, B, Modulo;

    for (int i = 0; i < 10; i++) {
        printf("Iteração %d:\n", i + 1);
        printf("Digite A: ");
        scanf("%d", &A);
        printf("Digite B: ");
        scanf("%d", &B);
        Modulo = A % B;
        printf("Resto da divisão (A %% B): %d\n\n", Modulo);
    }

    return 0;
}
95. Para uma turma de 45 alunos, construa um algoritmo que determine:
a) A idade média dos alunos com menos de 1,70m de altura;
b) A altura média dos alunos com mais de 20 anos. 
#include <stdio.h>

int main() {
    int idade, contadorAlturaBaixa = 0, contadorIdadeAlta = 0;
    float altura, somaIdades = 0, somaAlturas = 0;

    for (int i = 1; i <= 45; i++) {
        printf("Aluno %d:\n", i);
        printf("Digite a idade: ");
        scanf("%d", &idade);
        printf("Digite a altura (em metros): ");
        scanf("%f", &altura);

        // (a) Idade média dos alunos com menos de 1,70m
        if (altura < 1.70) {
            somaIdades += idade;
            contadorAlturaBaixa++;
        }

        // (b) Altura média dos alunos com mais de 20 anos
        if (idade > 20) {
            somaAlturas += altura;
            contadorIdadeAlta++;
        }
    }

    // Resultados
    if (contadorAlturaBaixa > 0) {
        printf("\n(a) Idade média dos alunos com menos de 1,70m: %.2f anos\n",
               somaIdades / contadorAlturaBaixa);
    } else {
        printf("\n(a) Nenhum aluno com altura inferior a 1,70m.\n");
    }

    if (contadorIdadeAlta > 0) {
        printf("(b) Altura média dos alunos com mais de 20 anos: %.2f m\n",
               somaAlturas / contadorIdadeAlta);
    } else {
        printf("(b) Nenhum aluno com mais de 20 anos.\n");
    }

    return 0;
}
96. Escreva um algoritmo que calcule o produto dos inteiros ímpares de 1 a 15 e,
então, exiba os resultados. 
#include <stdio.h>

int main() {
    unsigned long long produto = 1;

    for (int i = 1; i <= 15; i += 2) {
        produto *= i;
    }

    printf("Produto dos inteiros ímpares de 1 a 15: %llu\n", produto);

    return 0;
}
97. Faça um algoritmo que leia um número e imprima a sua tabela de multiplicação
de 1 até 13. 
#include <stdio.h>

int main() {
    int numero;

    printf("Digite um número: ");
    scanf("%d", &numero);

    printf("Tabela de multiplicação de %d de 1 até 13:\n", numero);
    for (int i = 1; i <= 13; i++) {
        printf("%d x %d = %d\n", numero, i, numero * i);
    }

    return 0;
}
98. Escreva um algoritmo que calcule os quadrados e cubos dos números de 0 a 10
e imprima os valores resultantes no formato de tabela, como segue:
Número Quadrado Cubo
0 0 0
1 1 1
2 4 8
3 9 27
4 16 64
5 25 125
6 36 216
7 49 343
8 64 512
9 81 729
10 100 1000
#include <stdio.h>

int main() {
    printf("Número\tQuadrado\tCubo\n");

    for (int i = 0; i <= 10; i++) {
        int quadrado = i * i;
        int cubo = i * i * i;
        printf("%d\t%d\t\t%d\n", i, quadrado, cubo);
    }

    return 0;
}
99. Faça um algoritmo que calcule a média de salários de uma empresa, pedindo ao
usuário a quantidade de funcionários, o nome e o salário de cada funcionário e
devolvendo a média, o salário mais alto e o salário mais baixo. 
#include <stdio.h>
#include <string.h>

int main() {
    int n;
    char nome[100];
    float salario, soma = 0;
    float maiorSalario = 0, menorSalario = 0;

    printf("Digite a quantidade de funcionários: ");
    scanf("%d", &n);

    if (n <= 0) {
        printf("Número inválido de funcionários.\n");
        return 1;
    }

    for (int i = 1; i <= n; i++) {
        printf("\nFuncionário %d\n", i);
        printf("Nome: ");
        scanf(" %[^\n]", nome);  // Lê nome com espaços
        printf("Salário: ");
        scanf("%f", &salario);

        soma += salario;

        if (i == 1) {
            maiorSalario = menorSalario = salario;
        } else {
            if (salario > maiorSalario) {
                maiorSalario = salario;
            }
            if (salario < menorSalario) {
                menorSalario = salario;
            }
        }
    }

    float media = soma / n;

    printf("\nMédia salarial: %.2f\n", media);
    printf("Maior salário: %.2f\n", maiorSalario);
    printf("Menor salário: %.2f\n", menorSalario);

    return 0;
}
100. Crie um programa que peça 10 números inteiros e apresente: a média, o maior
e o menor. 
#include <stdio.h>

int main() {
    int numero, maior, menor, soma = 0;

    for (int i = 1; i <= 10; i++) {
        printf("Digite o %dº número inteiro: ", i);
        scanf("%d", &numero);

        soma += numero;

        if (i == 1) {
            maior = menor = numero;
        } else {
            if (numero > maior) {
                maior = numero;
            }
            if (numero < menor) {
                menor = numero;
            }
        }
    }

    float media = soma / 10.0;

    printf("\nMédia: %.2f\n", media);
    printf("Maior número: %d\n", maior)
101. Escreva um algoritmo que determine o fatorial de um número. Para este
problema, tem-se como entrada o valor do número do qual se deseja calcular o
fatorial. O fatorial de 0 é igual a 1. O fatorial de um número N(N!) é definido
conforme a seguir:
N! = 1 * 2 * 3 * 4 * ... * (N-1) * N
#include <stdio.h>

int main() {
    int N;
    unsigned long long fatorial = 1;

    printf("Digite um número inteiro não negativo: ");
    scanf("%d", &N);

    if (N < 0) {
        printf("Fatorial não definido para números negativos.\n");
        return 1;
    }

    for (int i = 1; i <= N; i++) {
        fatorial *= i;
    }

    printf("Fatorial de %d = %llu\n", N, fatorial);

    return 0;
}
102. Um hotel com 30 quartos cobra R$ 50,00 por diária e mais uma taxa de
serviços. A taxa de serviços é de:
• R$ 4,00 por diária, se o número de diárias for < 15;
• R$ 3,60 por diária, se o número de diárias for = 15;
• R$ 3,00 por diária, se o número de diárias for > 15.
Faça um algoritmo que imprima o nome e o total da conta de cada cliente do hotel.
Imprima também o total ganho pelo hotel. 
#include <stdio.h>

int main() {
    char nome[100];
    int diarias;
    float conta, taxa, totalHotel = 0;

    for (int i = 1; i <= 30; i++) {
        printf("\nHóspede %d:\n", i);
        printf("Nome: ");
        scanf(" %[^\n]", nome); // Lê nome com espaços
        printf("Número de diárias: ");
        scanf("%d", &diarias);

        // Determina taxa de serviço
        if (diarias < 15) {
            taxa = 4.00;
        } else if (diarias == 15) {
            taxa = 3.60;
        } else {
            taxa = 3.00;
        }

        conta = diarias * (50.00 + taxa);
        totalHotel += conta;

        printf("Cliente: %s - Total da conta: R$ %.2f\n", nome, conta);
    }

    printf("\nTotal ganho pelo hotel: R$ %.2f\n", totalHotel);

    return 0;
}
103. Um determinado material radioativo perde metade de sua massa a cada 50
segundos. Dada a massa inicial, em gramas, faça um programa que determine o
tempo necessário para que essa massa se torne menor que 0,05 gramas. 
#include <stdio.h>

int main() {
    float massa;
    int tempo = 0;

    printf("Digite a massa inicial (em gramas): ");
    scanf("%f", &massa);

    if (massa <= 0) {
        printf("Massa inválida. Deve ser maior que zero.\n");
        return 1;
    }

    while (massa >= 0.05) {
        massa = massa / 2;
        tempo += 50;
    }

    printf("Tempo necessário para a massa ser menor que 0,05g: %d segundos\n", tempo);

    return 0;
}
104. Sem utilizar a operação de multiplicação, escreva um programa que multiplique
dois números inteiros. Por exemplo: 2 * 2 = 2 + 2. 
#include <stdio.h>

int main() {
    int a, b, resultado = 0;

    printf("Digite o primeiro número inteiro: ");
    scanf("%d", &a);
    printf("Digite o segundo número inteiro: ");
    scanf("%d", &b);

    // Lógica para tratar sinais negativos
    int negativo = 0;
    if (a < 0 && b >= 0) {
        a = -a;
        negativo = 1;
    } else if (b < 0 && a >= 0) {
        b = -b;
        negativo = 1;
    } else if (a < 0 && b < 0) {
        a = -a;
        b = -b;
    }

    // Soma sucessiva
    for (int i = 0; i < b; i++) {
        resultado += a;
    }

    if (negativo) {
        resultado = -resultado;
    }

    printf("Resultado da multiplicação: %d\n", resultado);

    return 0;
}
105. A série de Fibonacci é formada pela sequência:
0, 1, 1, 2, 3, 5, 8, 13, 21, ...
Construa um algoritmo que gere e mostre a série até o vigésimo termo. 
#include <stdio.h>

int main() {
    int termo1 = 0, termo2 = 1, proximo;

    printf("Série de Fibonacci até o 20º termo:\n");

    for (int i = 1; i <= 20; i++) {
        printf("%d ", termo1);
        proximo = termo1 + termo2;
        termo1 = termo2;
        termo2 = proximo;
    }

    printf("\n");
    return 0;
}
106. Faça um algoritmo que leia um conjunto de números (X) e imprima sua soma
(Soma) e sua média (Media). Admita que o valor 9999 é utilizado como sentinela
para fim de leitura.
Ex.: 1, 2, 3 => Soma=6 Media=2 
#include <stdio.h>

int main() {
    int x, soma = 0, quantidade = 0;
    float media;

    printf("Digite números inteiros (9999 para encerrar):\n");

    while (1) {
        scanf("%d", &x);
        if (x == 9999)
            break;

        soma += x;
        quantidade++;
    }

    if (quantidade > 0) {
        media = (float)soma / quantidade;
        printf("Soma = %d\n", soma);
        printf("Média = %.2f\n", media);
    } else {
        printf("Nenhum número válido foi digitado.\n");
    }

    return 0;
}
107. Faça um algoritmo que leia um conjunto de dados numéricos (X) e imprima o
maior (Maximo) dentre eles. Admita que o valor 9999 é utilizado como sentinela.
Ex.: 1, 2, 3 => Maior=3 
#include <stdio.h>

int main() {
    int x, maximo;
    int primeiro = 1; // Indica se é o primeiro número válido

    printf("Digite números inteiros (9999 para encerrar):\n");

    while (1) {
        scanf("%d", &x);
        if (x == 9999)
            break;

        if (primeiro) {
            maximo = x;
            primeiro = 0;
        } else if (x > maximo) {
            maximo = x;
        }
    }

    if (primeiro) {
        printf("Nenhum número válido foi digitado.\n");
    } else {
        printf("Maior = %d\n", maximo);
    }

    return 0;
}
108. Faça um algoritmo que leia dois números inteiros positivos (Num1 e Num2) e
imprima o quociente (Quoc) e o resto (Resto) da divisão de Num1 por Num2,
utilizando apenas as operações de adição e subtração.
Ex.: N1=10; N2=2 => Q=5 R=0 
#include <stdio.h>

int main() {
    int Num1, Num2;
    int quoc = 0, resto;

    printf("Digite Num1 (inteiro positivo): ");
    scanf("%d", &Num1);
    printf("Digite Num2 (inteiro positivo): ");
    scanf("%d", &Num2);

    if (Num1 < 0 || Num2 <= 0) {
        printf("Erro: Num1 deve ser >= 0 e Num2 > 0.\n");
        return 1;
    }

    resto = Num1;

    while (resto >= Num2) {
        resto -= Num2;
        quoc++;
    }

    printf("Quociente = %d\n", quoc);
    printf("Resto = %d\n", resto);

    return 0;
}
109. Faça um algoritmo que leia um conjunto de números (X) e imprima a
quantidade de números pares (QPares) e a quantidade de números impares
(QImpares) lidos. Admita que o valor 9999 é utilizado como sentinela para fim de
leitura.
Ex.: 1,2,3,4,5 => Pares=2 Impares=3 
#include <stdio.h>

int main() {
    int x, QPares = 0, QImpares = 0;

    printf("Digite números inteiros (9999 para encerrar):\n");

    while (1) {
        scanf("%d", &x);
        if (x == 9999)
            break;

        if (x % 2 == 0)
            QPares++;
        else
            QImpares++;
    }

    printf("Pares = %d\n", QPares);
    printf("Ímpares = %d\n", QImpares);

    return 0;
}
110. Faça um algoritmo que calcule e imprime a soma dos inteiros de 1 a 10. Utilize
as estruturas ENQUANTO-FACA / REPITA-FACA para fazer um laço com as
instruções de cálculo e incremento. O laço deve terminar quando o valor de x se
tornar 11. 
#include <stdio.h>

int main() {
    int x = 1, soma = 0;

    while (x != 11) {  // ENQUANTO x != 11 FAÇA
        soma += x;
        x++;
    }

    printf("Soma dos inteiros de 1 a 10 (while): %d\n", soma);

    return 0;
}
111. Foi feita uma pesquisa com um grupo de alunos de uma universidade, na qual
se perguntou para cada aluno o número de vezes que utilizou o restaurante da
universidade no último mês. Construa um algoritmo que determine:
a) O percentual de alunos que utilizaram menos que 10 vezes o restaurante;
b) O percentual de alunos que utilizaram entre 10 e 15 vezes;
c) O percentual de alunos que utilizaram o restaurante acima de 15 vezes.
Ex.: 2, 3, 11, 12, 21, 22, 23 = a) 28%; b) 28%; c) 42% 
#include <stdio.h>

int main() {
    int total_alunos, vezes;
    int menos_10 = 0, entre_10_15 = 0, acima_15 = 0;

    printf("Digite o número total de alunos pesquisados: ");
    scanf("%d", &total_alunos);

    for (int i = 0; i < total_alunos; i++) {
        printf("Digite o número de vezes que o aluno %d usou o restaurante: ", i + 1);
        scanf("%d", &vezes);

        if (vezes < 10) {
            menos_10++;
        } else if (vezes >= 10 && vezes <= 15) {
            entre_10_15++;
        } else {
            acima_15++;
        }
    }

    if (total_alunos > 0) {
        printf("Percentual de alunos que usaram menos que 10 vezes: %.2f%%\n", (menos_10 * 100.0) / total_alunos);
        printf("Percentual de alunos que usaram entre 10 e 15 vezes: %.2f%%\n", (entre_10_15 * 100.0) / total_alunos);
        printf("Percentual de alunos que usaram acima de 15 vezes: %.2f%%\n", (acima_15 * 100.0) / total_alunos);
    } else {
        printf("Nenhum aluno foi pesquisado.\n");
    }

    return 0;
}
112. Construa um algoritmo que, para a progressão geométrica 3; 9; 27; 81; ...;
6561, determine a soma de seus termos. Construa o algoritmo de maneira a não
utilizar a fórmula de soma dos termos. Faça com que o computador gere cada
um dos termos a ser somado.
Ex.: 3; 9; 27; 81; 243; 729; 2187; 6561 => 9840 
#include <stdio.h>

int main() {
    int termo = 3;
    int soma = 0;

    while (termo <= 6561) {
        soma += termo;
        termo *= 3;  // próximo termo da PG multiplicando pela razão
    }

    printf("Soma dos termos da PG: %d\n", soma);

    return 0;
}
113. Crie um algoritmo que peça o nome, a altura e o peso de duas pessoas e
apresente o nome e peso da mais pesada e o nome e altura da mais alta.
#include <stdio.h>

int main() {
    char nome1[50], nome2[50];
    float altura1, altura2, peso1, peso2;

    // Entrada da primeira pessoa
    printf("Digite o nome da primeira pessoa: ");
    scanf(" %49[^\n]", nome1);  // lê string com espaços
    printf("Digite a altura da primeira pessoa (em metros): ");
    scanf("%f", &altura1);
    printf("Digite o peso da primeira pessoa (em kg): ");
    scanf("%f", &peso1);

    // Entrada da segunda pessoa
    printf("\nDigite o nome da segunda pessoa: ");
    scanf(" %49[^\n]", nome2);
    printf("Digite a altura da segunda pessoa (em metros): ");
    scanf("%f", &altura2);
    printf("Digite o peso da segunda pessoa (em kg): ");
    scanf("%f", &peso2);

    // Determinar mais pesada
    if (peso1 > peso2) {
        printf("\nMais pesada: %s, Peso: %.2f kg\n", nome1, peso1);
    } else if (peso2 > peso1) {
        printf("\nMais pesada: %s, Peso: %.2f kg\n", nome2, peso2);
    } else {
        printf("\nAmbas têm o mesmo peso: %.2f kg\n", peso1);
    }

    // Determinar mais alta
    if (altura1 > altura2) {
        printf("Mais alta: %s, Altura: %.2f metros\n", nome1, altura1);
    } else if (altura2 > altura1) {
        printf("Mais alta: %s, Altura: %.2f metros\n", nome2, altura2);
    } else {
        printf("Ambas têm a mesma altura: %.2f metros\n", altura1);
    }

    return 0;
}
114. Considere que, para cada um dos hotéis fazenda da região, se tenha registrado
o nome do hotel, a sua distância do centro da cidade, o número médio de
visitantes no último feriado e o tipo de acesso ao hotel (0 – acesso não asfaltado;
1 – acesso asfaltado). Construa um algoritmo que forneça:
a) O número de hoteis que distam mais de 15km do centro;
b) A quantidade média de visitantes no último feriado, nos hoteis com acesso
não asfaltado;
c) O nome e a distância do centro em Km, de todos os hoteis de acesso
asfaltado que tiveram menos de 1.000 visitantes.
Ex.: HA, DA=10, V=100, AC=0
 HB, DA=20, V=50, AC=1 
 #include <stdio.h>
#include <string.h>

int main() {
    int n, acesso;
    char nome[50];
    float distancia;
    int visitantes;

    int count_mais_15km = 0;
    int count_nao_asfaltado = 0;
    int soma_visitantes_nao_asfaltado = 0;

    printf("Digite o número de hotéis: ");
    scanf("%d", &n);

    printf("Digite os dados dos hotéis:\n");
    // Para armazenar temporariamente hotéis asfaltados com < 1000 visitantes
    char nomes_asfaltados[100][50];
    float distancias_asfaltados[100];
    int cont_asfaltados_menos_1000 = 0;

    for (int i = 0; i < n; i++) {
        printf("\nHotel %d\n", i + 1);
        printf("Nome: ");
        scanf(" %49[^\n]", nome);
        printf("Distância do centro (km): ");
        scanf("%f", &distancia);
        printf("Número médio de visitantes no último feriado: ");
        scanf("%d", &visitantes);
        printf("Tipo de acesso (0 - não asfaltado, 1 - asfaltado): ");
        scanf("%d", &acesso);

        if (distancia > 15) {
            count_mais_15km++;
        }

        if (acesso == 0) {
            count_nao_asfaltado++;
            soma_visitantes_nao_asfaltado += visitantes;
        } else if (acesso == 1 && visitantes < 1000) {
            // Armazena para imprimir depois
            strcpy(nomes_asfaltados[cont_asfaltados_menos_1000], nome);
            distancias_asfaltados[cont_asfaltados_menos_1000] = distancia;
            cont_asfaltados_menos_1000++;
        }
    }

    printf("\na) Número de hotéis a mais de 15 km do centro: %d\n", count_mais_15km);

    if (count_nao_asfaltado > 0) {
        float media = (float)soma_visitantes_nao_asfaltado / count_nao_asfaltado;
        printf("b) Média de visitantes em hotéis com acesso não asfaltado: %.2f\n", media);
    } else {
        printf("b) Não há hotéis com acesso não asfaltado.\n");
    }

    printf("c) Hotéis asfaltados com menos de 1000 visitantes:\n");
    if (cont_asfaltados_menos_1000 == 0) {
        printf("Nenhum hotel encontrado.\n");
    } else {
        for (int i = 0; i < cont_asfaltados_menos_1000; i++) {
            printf("Nome: %s, Distância: %.2f km\n", nomes_asfaltados[i], distancias_asfaltados[i]);
        }
    }

    return 0;
}
115. Faça um algoritmo que calcule a média de salários de uma empresa, pedindo
ao usuário o nome dos funcionários e os salários e devolvendo a média, o salário
mais alto e o salário mais baixo. Use nome = “fim” para encerrar a leitura. 
#include <stdio.h>
#include <string.h>

int main() {
    char nome[50];
    float salario;
    float soma = 0, salario_max = -1, salario_min = 9999999;
    int count = 0;

    printf("Digite o nome do funcionário (ou 'fim' para encerrar): ");
    scanf(" %49[^\n]", nome);

    while (strcmp(nome, "fim") != 0) {
        printf("Digite o salário de %s: ", nome);
        scanf("%f", &salario);

        soma += salario;
        if (salario > salario_max) salario_max = salario;
        if (salario < salario_min) salario_min = salario;
        count++;

        printf("\nDigite o nome do próximo funcionário (ou 'fim' para encerrar): ");
        scanf(" %49[^\n]", nome);
    }

    if (count > 0) {
        printf("\nMédia salarial: %.2f\n", soma / count);
        printf("Salário mais alto: %.2f\n", salario_max);
        printf("Salário mais baixo: %.2f\n", salario_min);
    } else {
        printf("\nNenhum salário foi informado.\n");
    }

    return 0;
}
116. Faça um algoritmo que leia um número e divida-o por dois (sucessivamente)
ate que o resultado seja menor que 1. Mostre o resultado da ultima divisão e a
quantidade de divisões efetuadas. 
#include <stdio.h>

int main() {
    float numero, resultado;
    int contador = 0;

    printf("Digite um número: ");
    scanf("%f", &numero);

    resultado = numero;

    while (resultado >= 1) {
        resultado = resultado / 2;
        contador++;
    }

    printf("Resultado da última divisão: %.4f\n", resultado);
    printf("Quantidade de divisões efetuadas: %d\n", contador);

    return 0;
}
117. Escrever um algoritmo que lê um valor N inteiro e positivo e que calcula e
escreve o valor de E.
 E = 1 + 1 / 1! + 1 / 2! + 1 / 3! + 1 / N! 
 #include <stdio.h>

// Função para calcular o fatorial de um número inteiro
long long fatorial(int n) {
    long long fat = 1;
    for (int i = 2; i <= n; i++) {
        fat *= i;
    }
    return fat;
}

int main() {
    int N;
    double E = 1.0; // começa com 1 (termo inicial)
    
    printf("Digite um número inteiro e positivo N: ");
    scanf("%d", &N);

    if (N < 0) {
        printf("Número inválido! N deve ser positivo.\n");
        return 1;
    }

    for (int i = 1; i <= N; i++) {
        E += 1.0 / fatorial(i);
    }

    printf("Valor de E para N = %d: %.6f\n", N, E);

    return 0;
}
118. Chico tem 1,50 metros e cresce 2 centímetros por ano, enquanto Zé tem 1,10
metros e cresce 3 centímetros por ano. Construa um algoritmo que calcule e
imprima quantos anos serão necessários para que Zé seja maior que Chico. 
#include <stdio.h>

int main() {
    float chico = 1.50;  // metros
    float ze = 1.10;     // metros
    float crescimento_chico = 0.02; // metros por ano (2 cm)
    float crescimento_ze = 0.03;    // metros por ano (3 cm)
    int anos = 0;

    while (ze <= chico) {
        chico += crescimento_chico;
        ze += crescimento_ze;
        anos++;
    }

    printf("Serão necessários %d anos para que Zé seja maior que Chico.\n", anos);

    return 0;
}
119. Escreva um algoritmo que leia um número n (número de termos de uma
progressão aritmética), a1 (o primeiro termo da progressão) e r (a razão da
progressão) e escreva os n termos desta progressão, bem como a soma dos
elementos. 
#include <stdio.h>

int main() {
    int n, i;
    int a1, r;
    int soma = 0;
    int termo;

    printf("Digite o número de termos (n): ");
    scanf("%d", &n);

    printf("Digite o primeiro termo (a1): ");
    scanf("%d", &a1);

    printf("Digite a razão (r): ");
    scanf("%d", &r);

    printf("Progressão Aritmética: \n");
    for (i = 0; i < n; i++) {
        termo = a1 + i * r;
        printf("%d ", termo);
        soma += termo;
    }

    printf("\nSoma dos termos: %d\n", soma);

    return 0;
}
120. Foi feita uma pesquisa entre os habitantes de uma região. Foram coletados os
dados de idade, sexo (M/F) e salário. Faça um algoritmo que informe:
a) a média de salário do grupo;
b) a maior e a menor idade do grupo;
c) a quantidade de mulheres com salário até R$100,00. 
#include <stdio.h>

int main() {
    int idade;
    char sexo;
    float salario;

    int count = 0;
    float soma_salarios = 0;
    int maior_idade = -1;
    int menor_idade = 9999;
    int mulheres_ate_100 = 0;

    printf("Digite os dados dos habitantes (idade=0 para terminar):\n");

    while (1) {
        printf("\nIdade: ");
        scanf("%d", &idade);
        if (idade == 0) break;

        printf("Sexo (M/F): ");
        scanf(" %c", &sexo);

        printf("Salário: ");
        scanf("%f", &salario);

        soma_salarios += salario;
        count++;

        if (idade > maior_idade) maior_idade = idade;
        if (idade < menor_idade) menor_idade = idade;

        if ((sexo == 'F' || sexo == 'f') && salario <= 100.0) {
            mulheres_ate_100++;
        }
    }

    if (count > 0) {
        printf("\na) Média salarial do grupo: %.2f\n", soma_salarios / count);
        printf("b) Maior idade: %d\n", maior_idade);
        printf("   Menor idade: %d\n", menor_idade);
        printf("c) Quantidade de mulheres com salário até R$100,00: %d\n", mulheres_ate_100);
    } else {
        printf("Nenhum dado foi informado.\n");
    }

    return 0;
}
121. Faça um algoritmo que leia um número inteiro N, calcule e mostre o maior
quadrado menor ou igual a N.
Por exemplo, se N for igual a 38, o Menor quadrado é 36 (quadrado de 6). 
#include <stdio.h>

int main() {
    int N, i = 0, maior_quadrado = 0;

    printf("Digite um número inteiro N: ");
    scanf("%d", &N);

    while ((i * i) <= N) {
        maior_quadrado = i * i;
        i++;
    }

    printf("O maior quadrado menor ou igual a %d é %d\n", N, maior_quadrado);

    return 0;
}
122. Faça um algoritmo que leia um número FN, calcule e mostre os N primeiros
termos da sequência de Fibonnaci (0, 1, 1, 2 , 3, 5, 8, ...). O valor lido para N
sempre será maior ou igual a 2. 
#include <stdio.h>

int main() {
    int N;
    int fib1 = 0, fib2 = 1, proximo;

    printf("Digite o número de termos (N >= 2): ");
    scanf("%d", &N);

    if (N < 2) {
        printf("N deve ser maior ou igual a 2.\n");
        return 1;
    }

    printf("Sequência de Fibonacci: %d %d", fib1, fib2);

    for (int i = 3; i <= N; i++) {
        proximo = fib1 + fib2;
        printf(" %d", proximo);
        fib1 = fib2;
        fib2 = proximo;
    }

    printf("\n");

    return 0;
}
123. Foi realizada uma pesquisa de algumas características físicas da população de
uma certa região, a qual coletaram os seguintes dados referentes a cada
habitante para serem analisados:
- sexo (masculino e feminino)
- cor dos olhos (azuis, verdes ou castanhos)
- cor dos cabelos (louros, castanhos, pretos)
- idade
Faça um algoritmo que determine e escreva:
a) a maior idade dos habitantes;
b) a quantidade de indivíduos do sexo feminino cuja idade está entre 18 e
35 anos, inclusive;
c) a quantidade de indivíduos que tenham olhos verdes e cabelos louros;
O final do conjunto de habitantes é reconhecido pelo valor -1 informado como
idade.
#include <stdio.h>
#include <string.h>

int main() {
    char sexo[10], cor_olhos[10], cor_cabelos[10];
    int idade;

    int maior_idade = -1;
    int qtd_fem_18_35 = 0;
    int qtd_olhos_verdes_cabelos_louros = 0;

    printf("Digite os dados dos habitantes (idade = -1 para terminar):\n");

    while (1) {
        printf("\nIdade: ");
        scanf("%d", &idade);
        if (idade == -1) break;

        printf("Sexo (masculino/feminino): ");
        scanf("%s", sexo);

        printf("Cor dos olhos (azuis/verdes/castanhos): ");
        scanf("%s", cor_olhos);

        printf("Cor dos cabelos (louros/castanhos/pretos): ");
        scanf("%s", cor_cabelos);

        // Atualiza maior idade
        if (idade > maior_idade) {
            maior_idade = idade;
        }

        // Conta mulheres entre 18 e 35 anos (inclusive)
        if ((strcmp(sexo, "feminino") == 0 || strcmp(sexo, "Feminino") == 0) && idade >= 18 && idade <= 35) {
            qtd_fem_18_35++;
        }

        // Conta indivíduos com olhos verdes e cabelos louros
        if ((strcmp(cor_olhos, "verdes") == 0 || strcmp(cor_olhos, "Verdes") == 0) &&
            (strcmp(cor_cabelos, "louros") == 0 || strcmp(cor_cabelos, "Louros") == 0)) {
            qtd_olhos_verdes_cabelos_louros++;
        }
    }

    if (maior_idade == -1) {
        printf("Nenhum dado foi informado.\n");
    } else {
        printf("\nResultados:\n");
        printf("a) Maior idade dos habitantes: %d\n", maior_idade);
        printf("b) Quantidade de mulheres entre 18 e 35 anos: %d\n", qtd_fem_18_35);
        printf("c) Quantidade de indivíduos com olhos verdes e cabelos louros: %d\n", qtd_olhos_verdes_cabelos_louros);
    }

    return 0;
}
124. Faça um algoritmo que leia informações de alunos (Matricula, Nota1, Nota2 ,
Nota3) com o fim das informações indicado por Matricula = 9999 . Para cada
aluno deve ser calculada a média final de acordo com a seguinte fórmula:
Média final = [(2 * Nota1) +(3* Nota2) +(4* Nota 3)] / 9
Se a média final for igual ou superior a 5, o algoritmo deve mostrar Matrícula,
Média Final e a mensagem "APROVADO" ; se a média final for inferior a 5, o
algoritmo deve mostrar Matricula, Média Final e a mensagem "REPROVADO".
Ao final devem ser mostrados o total de aprovados, o total de alunos da turma e
o total de reprovados. 
#include <stdio.h>

int main() {
    int matricula;
    float nota1, nota2, nota3, media;
    int total_alunos = 0, total_aprovados = 0, total_reprovados = 0;

    printf("Digite os dados dos alunos (Matricula=9999 para encerrar):\n");

    while (1) {
        printf("\nMatricula: ");
        scanf("%d", &matricula);
        if (matricula == 9999) break;

        printf("Nota1: ");
        scanf("%f", &nota1);

        printf("Nota2: ");
        scanf("%f", &nota2);

        printf("Nota3: ");
        scanf("%f", &nota3);

        media = ((2 * nota1) + (3 * nota2) + (4 * nota3)) / 9.0;

        printf("Matricula: %d | Média Final: %.2f | ", matricula, media);

        if (media >= 5.0) {
            printf("APROVADO\n");
            total_aprovados++;
        } else {
            printf("REPROVADO\n");
            total_reprovados++;
        }

        total_alunos++;
    }

    printf("\nTotal de alunos: %d\n", total_alunos);
    printf("Total de aprovados: %d\n", total_aprovados);
    printf("Total de reprovados: %d\n", total_reprovados);

    return 0;
}
125. Faça um algoritmo que leia o número de andares de um prédio e, a seguir, para
cada andar do prédio, leia o número de pessoas que entraram e saíram do
elevador.
Considere que o elevador está vazio e está subindo, os dados se referem a
apenas uma “subida” do elevador e que o número de pessoas dentro do
elevador sempre será maior ou igual a 0.
Se o número de pessoas, após a entrada e saída for maior que 15, deve ser
mostrada a mensagem “EXCESSO DE PASSAGEIROS . DEVEM SAIR" em
seguida, o número de pessoas que devem sair do elevador, de modo que seja
obedecido o limite de 15 passageiros.
Após a entrada de pessoas no último andar o algoritmo deve mostrar quantas
pessoas irão descer. 
#include <stdio.h>

int main() {
    int andares, pessoas_entraram, pessoas_sairam;
    int pessoas_no_elevador = 0;
    int excesso;

    printf("Digite o número de andares do prédio: ");
    scanf("%d", &andares);

    for (int i = 1; i <= andares; i++) {
        printf("\nAndar %d\n", i);

        printf("Número de pessoas que entraram: ");
        scanf("%d", &pessoas_entraram);

        printf("Número de pessoas que saíram: ");
        scanf("%d", &pessoas_sairam);

        // Atualiza o número de pessoas dentro do elevador
        pessoas_no_elevador += pessoas_entraram;
        pessoas_no_elevador -= pessoas_sairam;

        // Garantir que não seja negativo (em caso de dados inconsistentes)
        if (pessoas_no_elevador < 0) pessoas_no_elevador = 0;

        if (pessoas_no_elevador > 15) {
            excesso = pessoas_no_elevador - 15;
            printf("EXCESSO DE PASSAGEIROS. DEVEM SAIR %d\n", excesso);
            pessoas_no_elevador = 15;
        }
    }

    printf("\nNo último andar, %d pessoas irão descer.\n", pessoas_no_elevador);

    return 0;
}
126. Faça um algoritmo que copie o conteúdo de um vetor em um segundo vetor. 
#include <stdio.h>

int main() {
    int n;

    printf("Digite o tamanho do vetor: ");
    scanf("%d", &n);

    int vetor1[n], vetor2[n];

    printf("Digite os %d elementos do vetor:\n", n);
    for (int i = 0; i < n; i++) {
        scanf("%d", &vetor1[i]);
    }

    // Copiando o conteúdo do vetor1 para vetor2
    for (int i = 0; i < n; i++) {
        vetor2[i] = vetor1[i];
    }

    printf("Conteúdo do segundo vetor copiado:\n");
    for (int i = 0; i < n; i++) {
        printf("%d ", vetor2[i]);
    }
    printf("\n");

    return 0;
}
127. Faça um algoritmo que some o conteúdo de dois vetores e armazene o
resultado em um terceiro vetor. 
#include <stdio.h>

int main() {
    int n;

    printf("Digite o tamanho dos vetores: ");
    scanf("%d", &n);

    int vetor1[n], vetor2[n], vetorSoma[n];

    printf("Digite os elementos do primeiro vetor:\n");
    for (int i = 0; i < n; i++) {
        scanf("%d", &vetor1[i]);
    }

    printf("Digite os elementos do segundo vetor:\n");
    for (int i = 0; i < n; i++) {
        scanf("%d", &vetor2[i]);
    }

    // Soma os elementos dos vetores
    for (int i = 0; i < n; i++) {
        vetorSoma[i] = vetor1[i] + vetor2[i];
    }

    printf("Resultado da soma dos vetores:\n");
    for (int i = 0; i < n; i++) {
        printf("%d ", vetorSoma[i]);
    }
    printf("\n");

    return 0;
}
128. Faça um algoritmo que faça a união de dois vetores de mesmo tamanho e
mesmo tipo em um terceiro vetor com dobro do tamanho. 
#include <stdio.h>

int main() {
    int n;

    printf("Digite o tamanho dos vetores: ");
    scanf("%d", &n);

    int vetor1[n], vetor2[n], vetorUniao[2 * n];

    printf("Digite os elementos do primeiro vetor:\n");
    for (int i = 0; i < n; i++) {
        scanf("%d", &vetor1[i]);
    }

    printf("Digite os elementos do segundo vetor:\n");
    for (int i = 0; i < n; i++) {
        scanf("%d", &vetor2[i]);
    }

    // Copiando vetor1 para vetorUniao
    for (int i = 0; i < n; i++) {
        vetorUniao[i] = vetor1[i];
    }

    // Copiando vetor2 para vetorUniao, a partir da posição n
    for (int i = 0; i < n; i++) {
        vetorUniao[n + i] = vetor2[i];
    }

    printf("Vetor união:\n");
    for (int i = 0; i < 2 * n; i++) {
        printf("%d ", vetorUniao[i]);
    }
    printf("\n");

    return 0;
}
129. Escrever um algoritmo que lê um vetor N(20) e o escreve. Troque, a seguir, o 1º
elemento com o último, o 2º com o penúltimo etc. até o 10º com o 11º e escreva
o vetor N assim modificado. 
#include <stdio.h>

int main() {
    int N[20];

    printf("Digite 20 números para o vetor:\n");
    for (int i = 0; i < 20; i++) {
        scanf("%d", &N[i]);
    }

    // Mostra o vetor original
    printf("Vetor original:\n");
    for (int i = 0; i < 20; i++) {
        printf("%d ", N[i]);
    }
    printf("\n");

    // Troca elementos: 1º com último, 2º com penúltimo, ... até 10º com 11º
    for (int i = 0; i < 10; i++) {
        int temp = N[i];
        N[i] = N[19 - i];
        N[19 - i] = temp;
    }

    // Mostra o vetor modificado
    printf("Vetor modificado (invertido):\n");
    for (int i = 0; i < 20; i++) {
        printf("%d ", N[i]);
    }
    printf("\n");

    return 0;
}
130. Escrever um algoritmo que lê um vetor G(13) que é o gabarito de um teste de
loteria esportiva, contendo os valores 1 (coluna 1), 2 (coluna 2) e 3 (coluna do
meio). Ler, a seguir, para cada apostador, o número de seu cartão e um vetor
Resposta R (13). Verificar para cada apostador o número de acertos e escrever o
número do apostador e seu número de acertos. Se tiver 13 acertos, acrescentar
a mensagem: "GANHADOR, PARABENS".
#include <stdio.h>

int main() {
    int G[13]; // Gabarito
    int R[13]; // Respostas do apostador
    int numCartao;
    int acertos;
    char continuar;

    // Leitura do gabarito
    printf("Digite o gabarito do teste (13 valores, cada um 1, 2 ou 3):\n");
    for (int i = 0; i < 13; i++) {
        do {
            scanf("%d", &G[i]);
            if (G[i] < 1 || G[i] > 3) {
                printf("Valor inválido. Digite 1, 2 ou 3 para a posição %d:\n", i+1);
            }
        } while (G[i] < 1 || G[i] > 3);
    }

    do {
        // Leitura do número do cartão
        printf("\nDigite o número do cartão do apostador (digite 0 para sair): ");
        scanf("%d", &numCartao);
        if (numCartao == 0) break;

        // Leitura das respostas do apostador
        printf("Digite as 13 respostas do apostador (1, 2 ou 3):\n");
        for (int i = 0; i < 13; i++) {
            do {
                scanf("%d", &R[i]);
                if (R[i] < 1 || R[i] > 3) {
                    printf("Valor inválido. Digite 1, 2 ou 3 para a posição %d:\n", i+1);
                }
            } while (R[i] < 1 || R[i] > 3);
        }

        // Verifica o número de acertos
        acertos = 0;
        for (int i = 0; i < 13; i++) {
            if (R[i] == G[i]) {
                acertos++;
            }
        }

        // Imprime resultado
        printf("Apostador %d acertou %d\n", numCartao, acertos);
        if (acertos == 13) {
            printf("GANHADOR, PARABENS\n");
        }

        // Pergunta se deseja continuar (opcional)
        printf("Deseja inserir outro apostador? (s/n): ");
        getchar(); // para limpar o '\n' do buffer
        scanf("%c", &continuar);

    } while (continuar == 's' || continuar == 'S');

    printf("Fim do programa.\n");
    return 0;
}
131. Faça um algoritmo para somar duas matrizes. 
#include <stdio.h>

int main() {
    int linhas, colunas;
    printf("Digite o número de linhas da matriz: ");
    scanf("%d", &linhas);
    printf("Digite o número de colunas da matriz: ");
    scanf("%d", &colunas);

    int matriz1[linhas][colunas];
    int matriz2[linhas][colunas];
    int soma[linhas][colunas];

    // Leitura da primeira matriz
    printf("Digite os elementos da primeira matriz:\n");
    for (int i = 0; i < linhas; i++) {
        for (int j = 0; j < colunas; j++) {
            scanf("%d", &matriz1[i][j]);
        }
    }

    // Leitura da segunda matriz
    printf("Digite os elementos da segunda matriz:\n");
    for (int i = 0; i < linhas; i++) {
        for (int j = 0; j < colunas; j++) {
            scanf("%d", &matriz2[i][j]);
        }
    }

    // Soma das matrizes
    for (int i = 0; i < linhas; i++) {
        for (int j = 0; j < colunas; j++) {
            soma[i][j] = matriz1[i][j] + matriz2[i][j];
        }
    }

    // Exibir matriz soma
    printf("Matriz resultante da soma:\n");
    for (int i = 0; i < linhas; i++) {
        for (int j = 0; j < colunas; j++) {
            printf("%d ", soma[i][j]);
        }
        printf("\n");
    }

    return 0;
}
132. Faça um algoritmo para calcular a transposta de uma matriz. 
#include <stdio.h>

int main() {
    int linhas, colunas;
    printf("Digite o número de linhas da matriz: ");
    scanf("%d", &linhas);
    printf("Digite o número de colunas da matriz: ");
    scanf("%d", &colunas);

    int matriz[linhas][colunas];
    int transposta[colunas][linhas];

    // Leitura da matriz
    printf("Digite os elementos da matriz:\n");
    for (int i = 0; i < linhas; i++) {
        for (int j = 0; j < colunas; j++) {
            scanf("%d", &matriz[i][j]);
        }
    }

    // Calcula a transposta
    for (int i = 0; i < linhas; i++) {
        for (int j = 0; j < colunas; j++) {
            transposta[j][i] = matriz[i][j];
        }
    }

    // Exibe a matriz transposta
    printf("Matriz transposta:\n");
    for (int i = 0; i < colunas; i++) {
        for (int j = 0; j < linhas; j++) {
            printf("%d ", transposta[i][j]);
        }
        printf("\n");
    }

    return 0;
}
133. Faça um algoritmo que leia uma matriz mat 2 x 3 e imprima na tela a soma de
todos os elementos da matriz mat. 
#include <stdio.h>

int main() {
    int mat[2][3];
    int soma = 0;

    // Leitura da matriz 2x3
    printf("Digite os elementos da matriz 2x3:\n");
    for (int i = 0; i < 2; i++) {
        for (int j = 0; j < 3; j++) {
            scanf("%d", &mat[i][j]);
        }
    }

    // Soma dos elementos da matriz
    for (int i = 0; i < 2; i++) {
        for (int j = 0; j < 3; j++) {
            soma += mat[i][j];
        }
    }

    // Imprimir a soma
    printf("A soma dos elementos da matriz é: %d\n", soma);

    return 0;
}
134. Faça um algoritmo que leia uma matriz mat 4 x 4, e imprima na tela a soma dos
elementos abaixo da diagonal principal da matriz mat. 
#include <stdio.h>

int main() {
    int mat[4][4];
    int soma = 0;

    // Leitura da matriz 4x4
    printf("Digite os elementos da matriz 4x4:\n");
    for (int i = 0; i < 4; i++) {
        for (int j = 0; j < 4; j++) {
            scanf("%d", &mat[i][j]);
        }
    }

    // Soma dos elementos abaixo da diagonal principal
    // Na diagonal principal i == j, abaixo dela i > j
    for (int i = 0; i < 4; i++) {
        for (int j = 0; j < i; j++) {
            soma += mat[i][j];
        }
    }

    // Imprimir a soma
    printf("A soma dos elementos abaixo da diagonal principal é: %d\n", soma);

    return 0;
}
135. Escreva um algoritmo que lê uma matriz M(5,5) e calcule as somas:
a) da linha 4 de M;
b) da coluna 2 de M;
c) da diagonal principal;
d) da diagonal secundária;
e) de todos os elementos da matriz;
f) Escreva estas somas e a matriz 
#include <stdio.h>

int main() {
    int M[5][5];
    int somaLinha4 = 0, somaColuna2 = 0;
    int somaDiagonalPrincipal = 0, somaDiagonalSecundaria = 0;
    int somaTotal = 0;

    // Leitura da matriz 5x5
    printf("Digite os elementos da matriz 5x5:\n");
    for (int i = 0; i < 5; i++) {
        for (int j = 0; j < 5; j++) {
            scanf("%d", &M[i][j]);
        }
    }

    // Cálculo das somas
    for (int i = 0; i < 5; i++) {
        somaLinha4 += M[3][i];        // linha 4 (índice 3)
        somaColuna2 += M[i][1];       // coluna 2 (índice 1)
        somaDiagonalPrincipal += M[i][i];
        somaDiagonalSecundaria += M[i][4 - i];
        for (int j = 0; j < 5; j++) {
            somaTotal += M[i][j];
        }
    }

    // Imprime a matriz
    printf("\nMatriz 5x5:\n");
    for (int i = 0; i < 5; i++) {
        for (int j = 0; j < 5; j++) {
            printf("%d ", M[i][j]);
        }
        printf("\n");
    }

    // Imprime as somas
    printf("\nSoma da linha 4: %d\n", somaLinha4);
    printf("Soma da coluna 2: %d\n", somaColuna2);
    printf("Soma da diagonal principal: %d\n", somaDiagonalPrincipal);
    printf("Soma da diagonal secundaria: %d\n", somaDiagonalSecundaria);
    printf("Soma de todos os elementos: %d\n", somaTotal);

    return 0;
}
136. Com base em seu conhecimento defina os registros abaixo. Crie um algoritmo
que solicite ao usuário informar os dados do registro e imprima os mesmos na
tela:
a) cheque bancário;
b) livro;
c) aluno;
d) endereço;
e) cadastro de
pessoa;
#include <stdio.h>

typedef struct {
    char banco[50];
    char titular[50];
    char data[11];  // formato: dd/mm/yyyy
    double valor;
    int numero;
} Cheque;
137. Escreva um programa para cadastrar dois clientes de uma loja. As informações
necessárias são: nome, endereço e telefone. Deve ser usada uma estrutura de
registro para a construção deste cadastro, usando Type para a declaração do
registro. 
#include <stdio.h>

typedef struct {
    char nome[100];
    char endereco[150];
    char telefone[20];
} Cliente;

int main() {
    Cliente clientes[2];

    for (int i = 0; i < 2; i++) {
        printf("Cadastro do cliente %d:\n", i + 1);

        printf("Nome: ");
        scanf(" %[^\n]", clientes[i].nome);

        printf("Endereco: ");
        scanf(" %[^\n]", clientes[i].endereco);

        printf("Telefone: ");
        scanf(" %[^\n]", clientes[i].telefone);

        printf("\n");
    }

    printf("Dados cadastrados:\n");
    for (int i = 0; i < 2; i++) {
        printf("Cliente %d:\n", i + 1);
        printf("Nome: %s\n", clientes[i].nome);
        printf("Endereco: %s\n", clientes[i].endereco);
        printf("Telefone: %s\n\n", clientes[i].telefone);
    }

    return 0;
}
138. O mesmo exercício 137, mas o programa deverá suportar até 50 clientes. Ao
final do cadastro de cada cliente deverá ser perguntado: "Novo Cliente (S/N)?".
Deve-se utilizar um vetor do tipo declarado como um registro para a solução
deste programa. 
#include <stdio.h>

typedef struct {
    char nome[100];
    char endereco[150];
    char telefone[20];
} Cliente;

int main() {
    Cliente clientes[50];
    int count = 0;
    char resposta;

    do {
        printf("Cadastro do cliente %d:\n", count + 1);

        printf("Nome: ");
        scanf(" %[^\n]", clientes[count].nome);

        printf("Endereco: ");
        scanf(" %[^\n]", clientes[count].endereco);

        printf("Telefone: ");
        scanf(" %[^\n]", clientes[count].telefone);

        count++;

        if (count == 50) {
            printf("Limite de 50 clientes atingido.\n");
            break;
        }

        printf("Novo Cliente (S/N)? ");
        scanf(" %c", &resposta);

    } while (resposta == 'S' || resposta == 's');

    printf("\nDados cadastrados:\n");
    for (int i = 0; i < count; i++) {
        printf("Cliente %d:\n", i + 1);
        printf("Nome: %s\n", clientes[i].nome);
        printf("Endereco: %s\n", clientes[i].endereco);
        printf("Telefone: %s\n\n", clientes[i].telefone);
    }

    return 0;
}
139. O mesmo exercício 138, mas após o término de todos os cadastros, ou seja,
quando o usuário digitar "N" na pergunta para novo cliente ou quando preencher
o vetor com 50 clientes, a tela deverá ser limpa e deverá ser montada uma tela
para permitir a consulta aos clientes por código (que é o índice do vetor). Deverá
ser digitado o código 999 para encerrar o programa.
A tela de consulta deverá ter o seguinte formato:
Digite o código do cliente: _
Nome:
Endereço:
Telefone:
<Digite 999 para sair...>
Observação1: Estas informações só deverão ser impressas uma vez, e não a
 cada execução do programa.
Observação2: O fundo deve ser azul e as letras amarelas. 
#include <stdio.h>
#include <conio.h>  // Para clrscr, textcolor, textbackground

typedef struct {
    char nome[100];
    char endereco[150];
    char telefone[20];
} Cliente;

int main() {
    Cliente clientes[50];
    int count = 0;
    char resposta;

    // Cadastro dos clientes
    do {
        clrscr();
        printf("Cadastro do cliente %d:\n", count + 1);

        printf("Nome: ");
        fflush(stdin);
        gets(clientes[count].nome);

        printf("Endereco: ");
        fflush(stdin);
        gets(clientes[count].endereco);

        printf("Telefone: ");
        fflush(stdin);
        gets(clientes[count].telefone);

        count++;

        if (count == 50) {
            printf("Limite de 50 clientes atingido.\n");
            break;
        }

        printf("Novo Cliente (S/N)? ");
        resposta = getche();  // lê e já mostra
    } while (resposta == 'S' || resposta == 's');

    // Configurar cores e limpar tela
    textbackground(BLUE);
    textcolor(YELLOW);
    clrscr();

    int codigo;

    while (1) {
        printf("Digite o codigo do cliente (0 a %d): ", count - 1);
        printf("\n<Digite 999 para sair...>\n");
        scanf("%d", &codigo);

        if (codigo == 999)
            break;

        if (codigo < 0 || codigo >= count) {
            printf("Codigo invalido! Tente novamente.\n\n");
        } else {
            printf("\nNome: %s\n", clientes[codigo].nome);
            printf("Endereco: %s\n", clientes[codigo].endereco);
            printf("Telefone: %s\n\n", clientes[codigo].telefone);
        }
    }

    // Restaurar cores padrão antes de sair (opcional)
    textbackground(BLACK);
    textcolor(WHITE);
    clrscr();

    return 0;
}
140. Fazer um programa que tenha um registro com os campos nome, endereco,
telefone, email, salário, leia os dados de entrada e processe o total dos salários e
imprima o valor do maior salário, e a quem pertence (nome).
Observação: ler os MAX registros ou até que o nome seja "fim". 
#include <stdio.h>
#include <string.h>

#define MAX 100

typedef struct {
    char nome[100];
    char endereco[150];
    char telefone[20];
    char email[100];
    float salario;
} Pessoa;

int main() {
    Pessoa pessoas[MAX];
    int count = 0;
    float totalSalarios = 0;
    float maiorSalario = -1.0;
    int indiceMaior = -1;

    while (count < MAX) {
        printf("Digite o nome (ou 'fim' para terminar): ");
        fflush(stdin);
        fgets(pessoas[count].nome, sizeof(pessoas[count].nome), stdin);
        // Remove \n do fgets
        pessoas[count].nome[strcspn(pessoas[count].nome, "\n")] = 0;

        if (strcmp(pessoas[count].nome, "fim") == 0)
            break;

        printf("Endereco: ");
        fflush(stdin);
        fgets(pessoas[count].endereco, sizeof(pessoas[count].endereco), stdin);
        pessoas[count].endereco[strcspn(pessoas[count].endereco, "\n")] = 0;

        printf("Telefone: ");
        fflush(stdin);
        fgets(pessoas[count].telefone, sizeof(pessoas[count].telefone), stdin);
        pessoas[count].telefone[strcspn(pessoas[count].telefone, "\n")] = 0;

        printf("Email: ");
        fflush(stdin);
        fgets(pessoas[count].email, sizeof(pessoas[count].email), stdin);
        pessoas[count].email[strcspn(pessoas[count].email, "\n")] = 0;

        printf("Salario: ");
        scanf("%f", &pessoas[count].salario);
        getchar(); // para consumir o \n após o scanf

        totalSalarios += pessoas[count].salario;

        if (pessoas[count].salario > maiorSalario) {
            maiorSalario = pessoas[count].salario;
            indiceMaior = count;
        }

        count++;
        printf("\n");
    }

    if (count == 0) {
        printf("Nenhum dado foi informado.\n");
    } else {
        printf("Total dos salarios: R$ %.2f\n", totalSalarios);
        printf("Maior salario: R$ %.2f\n", maiorSalario);
        printf("Pertence a: %s\n", pessoas[indiceMaior].nome);
    }

    return 0;
}
141. Escreva um programa para cadastrar até 30 alunos de uma turma. As
informações necessárias são: nome do aluno, nome da disciplina e média
final.
Deve ser usada uma estrutura de registro para a construção deste cadastro,
usando Type para a declaração do registro.
Ao final do cadastro de cada aluno deverá ser perguntado: "Novo Aluno
(S/N)?".
Deve-se utilizar um vetor do tipo declarado como registro para a solução deste
programa.
Após o término de todos os cadastros, ou seja, quando o usuário digitar "N" na
pergunta para novo aluno ou quando preencher o vetor com 30 alunos, a tela
deverá ser limpa e deverá ser montada uma tela para permitir a consulta aos
alunos por nome. Deverá ser digitada a palavra FIM para o nome para encerrar o
programa. Você poderá fazer uma tela de consulta com o formato que achar
adequado. 
#include <stdio.h>
#include <string.h>
#include <ctype.h>
#ifdef _WIN32
#include <windows.h>
#else
#include <unistd.h>
#endif

#define MAX 30

typedef struct {
    char nome[100];
    char disciplina[100];
    float mediaFinal;
} Aluno;

// Função para limpar a tela (Windows e Unix)
void limparTela() {
#ifdef _WIN32
    system("cls");
#else
    system("clear");
#endif
}

// Função para converter string para maiúsculas para facilitar comparação
void toUpperStr(char *str) {
    for(int i = 0; str[i]; i++)
        str[i] = toupper((unsigned char) str[i]);
}

int main() {
    Aluno alunos[MAX];
    int count = 0;
    char opcao[3];

    // Cadastro
    do {
        if (count >= MAX) {
            printf("Limite de alunos atingido.\n");
            break;
        }

        printf("Cadastro do aluno %d\n", count+1);

        printf("Nome do aluno: ");
        fflush(stdin);
        fgets(alunos[count].nome, sizeof(alunos[count].nome), stdin);
        alunos[count].nome[strcspn(alunos[count].nome, "\n")] = 0;

        printf("Nome da disciplina: ");
        fflush(stdin);
        fgets(alunos[count].disciplina, sizeof(alunos[count].disciplina), stdin);
        alunos[count].disciplina[strcspn(alunos[count].disciplina, "\n")] = 0;

        printf("Media final: ");
        scanf("%f", &alunos[count].mediaFinal);
        getchar(); // consome o '\n' após scanf

        count++;

        if (count < MAX) {
            printf("Novo Aluno (S/N)? ");
            fgets(opcao, sizeof(opcao), stdin);
            opcao[strcspn(opcao, "\n")] = 0;
        } else {
            printf("Limite máximo de alunos cadastrado.\n");
            break;
        }

    } while (strcasecmp(opcao, "S") == 0);

    // Limpa a tela
    limparTela();

    // Consulta
    char nomeBusca[100];
    printf("Consulta de alunos. Digite 'FIM' para encerrar.\n");

    while (1) {
        printf("\nDigite o nome do aluno para consulta: ");
        fflush(stdin);
        fgets(nomeBusca, sizeof(nomeBusca), stdin);
        nomeBusca[strcspn(nomeBusca, "\n")] = 0;

        if (strcasecmp(nomeBusca, "FIM") == 0) {
            printf("Programa encerrado.\n");
            break;
        }

        int encontrado = 0;
        for (int i = 0; i < count; i++) {
            if (strcasecmp(alunos[i].nome, nomeBusca) == 0) {
                printf("\nAluno encontrado:\n");
                printf("Nome: %s\n", alunos[i].nome);
                printf("Disciplina: %s\n", alunos[i].disciplina);
                printf("Media Final: %.2f\n", alunos[i].mediaFinal);
                encontrado = 1;
                break;
            }
        }
        if (!encontrado) {
            printf("Aluno nao encontrado.\n");
        }
    }

    return 0;
}
142. Refaça o algoritmo do exercício 35 usando registro
#include <stdio.h>
#include <string.h>

typedef struct {
    char nome[100];
    float portugues;
    float matematica;
    float conhecimentos;
} Candidato;

int main() {
    Candidato c;
    float media;

    // Ler dados do candidato
    printf("Digite o nome do candidato: ");
    fgets(c.nome, 100, stdin);
    // Remover o \n que o fgets adiciona
    c.nome[strcspn(c.nome, "\n")] = 0;

    printf("Digite a nota de Portugues: ");
    scanf("%f", &c.portugues);
    printf("Digite a nota de Matemática: ");
    scanf("%f", &c.matematica);
    printf("Digite a nota de Conhecimentos Gerais: ");
    scanf("%f", &c.conhecimentos);

    // Calcular média
    media = (c.portugues + c.matematica + c.conhecimentos) / 3;

    // Mostrar dados
    printf("\nNome: %s\n", c.nome);
    printf("Notas:\n Portugues: %.2f\n Matemática: %.2f\n Conhecimentos Gerais: %.2f\n", 
           c.portugues, c.matematica, c.conhecimentos);
    printf("Média: %.2f\n", media);

    // Verificar aprovação
    if (media > 7.0 && c.portugues >= 5.0 && c.matematica >= 5.0 && c.conhecimentos >= 5.0) {
        printf("Resultado: APROVADO\n");
    } else {
        printf("Resultado: REPROVADO\n");
    }

    return 0;
}
143. Refaça o algoritmo do exercício 42 usando registro
#include <stdio.h>

typedef struct {
    int idade;
    char sexo;
    float salario;
} Pessoa;

int main() {
    int N, i;
    Pessoa p;
    float somaSalarioMulheres = 0;
    int countMulheres = 0;
    int somaIdadeHomens = 0;
    int countHomens = 0;
    int homensSalarioMais1000 = 0;

    printf("Digite o número de pessoas: ");
    scanf("%d", &N);

    for (i = 0; i < N; i++) {
        printf("\nPessoa %d:\n", i + 1);

        printf("Idade: ");
        scanf("%d", &p.idade);

        printf("Sexo (M/F): ");
        scanf(" %c", &p.sexo);  // espaço antes de %c para consumir \n anterior

        printf("Salário: ");
        scanf("%f", &p.salario);

        if (p.sexo == 'F' || p.sexo == 'f') {
            somaSalarioMulheres += p.salario;
            countMulheres++;
        } else if (p.sexo == 'M' || p.sexo == 'm') {
            somaIdadeHomens += p.idade;
            countHomens++;
            if (p.salario > 1000) {
                homensSalarioMais1000++;
            }
        }
    }

    printf("\nResultados:\n");

    if (countMulheres > 0) {
        printf("Média dos salários das mulheres: %.2f\n", somaSalarioMulheres / countMulheres);
    } else {
        printf("Nenhuma mulher cadastrada.\n");
    }

    if (countHomens > 0) {
        printf("Média das idades dos homens: %.2f\n", (float)somaIdadeHomens / countHomens);
        printf("Quantidade de homens com salário superior a 1000: %d\n", homensSalarioMais1000);
    } else {
        printf("Nenhum homem cadastrado.\n");
    }

    return 0;
}
144. Refaça o algoritmo do exercício 43 usando registro. 
#include <stdio.h>
#include <string.h>

typedef struct {
    char nome[50];
    int idade;
    char sexo;
    float salario;
} Pessoa;

int main() {
    int N, i;
    Pessoa p;

    char nomeMaiorSalario[50];
    float maiorSalario = -1.0;

    float somaSalarioMulheres = 0;
    int countMulheres = 0;

    int homensMais30 = 0;

    printf("Digite o número de pessoas: ");
    scanf("%d", &N);

    for (i = 0; i < N; i++) {
        printf("\nPessoa %d:\n", i + 1);

        printf("Nome: ");
        scanf(" %[^\n]", p.nome);  // lê linha até \n

        printf("Idade: ");
        scanf("%d", &p.idade);

        printf("Sexo (M/F): ");
        scanf(" %c", &p.sexo);

        printf("Salário: ");
        scanf("%f", &p.salario);

        // Verifica maior salário
        if (p.salario > maiorSalario) {
            maiorSalario = p.salario;
            strcpy(nomeMaiorSalario, p.nome);
        }

        // Soma salários das mulheres
        if (p.sexo == 'F' || p.sexo == 'f') {
            somaSalarioMulheres += p.salario;
            countMulheres++;
        }

        // Conta homens com idade > 30
        if ((p.sexo == 'M' || p.sexo == 'm') && p.idade > 30) {
            homensMais30++;
        }
    }

    printf("\nResultados:\n");

    if (maiorSalario >= 0)
        printf("Pessoa com maior salário: %s (R$ %.2f)\n", nomeMaiorSalario, maiorSalario);
    else
        printf("Nenhuma pessoa cadastrada.\n");

    if (countMulheres > 0)
        printf("Média dos salários das mulheres: %.2f\n", somaSalarioMulheres / countMulheres);
    else
        printf("Nenhuma mulher cadastrada.\n");

    printf("Quantidade de homens com mais de 30 anos: %d\n", homensMais30);

    return 0;
}
145. Refaça o algoritmo do exercício 58 usando registro
#include <stdio.h>
#include <string.h>

typedef struct {
    char modelo[50];
    int ano;
    float preco;
} Veiculo;

int main() {
    int N, i;
    Veiculo v;

    printf("Quantos veículos serão cadastrados? ");
    scanf("%d", &N);

    if (N <= 0) {
        printf("Número inválido de veículos.\n");
        return 1;
    }

    Veiculo maisCaro, maisBarato;
    float somaPrecos = 0;

    for (i = 0; i < N; i++) {
        printf("\nVeículo %d:\n", i + 1);

        printf("Modelo: ");
        scanf(" %[^\n]", v.modelo);

        printf("Ano de fabricação: ");
        scanf("%d", &v.ano);

        printf("Preço: ");
        scanf("%f", &v.preco);

        if (i == 0) {
            maisCaro = v;
            maisBarato = v;
        } else {
            if (v.preco > maisCaro.preco) {
                maisCaro = v;
            }
            if (v.preco < maisBarato.preco) {
                maisBarato = v;
            }
        }

        somaPrecos += v.preco;
    }

    printf("\nRelatório:\n");
    printf("Veículo mais caro: %s - R$ %.2f\n", maisCaro.modelo, maisCaro.preco);
    printf("Veículo mais barato: %s - R$ %.2f\n", maisBarato.modelo, maisBarato.preco);
    printf("Preço médio dos veículos: R$ %.2f\n", somaPrecos / N);

    return 0;
}
146. Refaça o algoritmo do exercício 113 usando registro.
#include <stdio.h>
#include <string.h>

typedef struct {
    char nome[50];
    float altura;
    float peso;
} Pessoa;

int main() {
    Pessoa p[2];
    int i;
    int maisPesada = 0, maisAlta = 0;

    for (i = 0; i < 2; i++) {
        printf("Digite o nome da pessoa %d: ", i + 1);
        scanf(" %[^\n]", p[i].nome);

        printf("Digite a altura da pessoa %d (em metros): ", i + 1);
        scanf("%f", &p[i].altura);

        printf("Digite o peso da pessoa %d (em kg): ", i + 1);
        scanf("%f", &p[i].peso);
    }

    // Encontrar a pessoa mais pesada e mais alta
    for (i = 1; i < 2; i++) {
        if (p[i].peso > p[maisPesada].peso) {
            maisPesada = i;
        }
        if (p[i].altura > p[maisAlta].altura) {
            maisAlta = i;
        }
    }

    printf("\nPessoa mais pesada: %s - Peso: %.2f kg\n", p[maisPesada].nome, p[maisPesada].peso);
    printf("Pessoa mais alta: %s - Altura: %.2f m\n", p[maisAlta].nome, p[maisAlta].altura);

    return 0;
}
147. Refaça o algoritmo do exercício 114 usando registro. 
#include <stdio.h>
#include <string.h>

typedef struct {
    char nome[50];
    float distancia;       // distância do centro (km)
    int visitantes;        // média de visitantes no último feriado
    int tipoAcesso;        // 0 = não asfaltado, 1 = asfaltado
} Hotel;

int main() {
    int n, i;
    printf("Digite a quantidade de hoteis a registrar: ");
    scanf("%d", &n);

    Hotel hoteis[n];

    for (i = 0; i < n; i++) {
        printf("\nHotel %d\n", i + 1);
        printf("Nome: ");
        scanf(" %[^\n]", hoteis[i].nome);
        printf("Distancia do centro (km): ");
        scanf("%f", &hoteis[i].distancia);
        printf("Numero medio de visitantes no ultimo feriado: ");
        scanf("%d", &hoteis[i].visitantes);
        printf("Tipo de acesso (0 - nao asfaltado, 1 - asfaltado): ");
        scanf("%d", &hoteis[i].tipoAcesso);
    }

    // a) Número de hotéis que distam mais de 15 km do centro
    int countDistancia = 0;
    // b) Soma e contagem para calcular média de visitantes em hotéis com acesso não asfaltado
    int somaVisitantesNA = 0, countNA = 0;

    printf("\nHotéis asfaltados com menos de 1000 visitantes:\n");
    for (i = 0; i < n; i++) {
        if (hoteis[i].distancia > 15) {
            countDistancia++;
        }

        if (hoteis[i].tipoAcesso == 0) {
            somaVisitantesNA += hoteis[i].visitantes;
            countNA++;
        }

        if (hoteis[i].tipoAcesso == 1 && hoteis[i].visitantes < 1000) {
            printf("Nome: %s - Distancia: %.2f km\n", hoteis[i].nome, hoteis[i].distancia);
        }
    }

    printf("\nNumero de hoteis que distam mais de 15 km: %d\n", countDistancia);

    if (countNA > 0) {
        printf("Media de visitantes nos hoteis com acesso nao asfaltado: %.2f\n", (float)somaVisitantesNA / countNA);
    } else {
        printf("Nao ha hoteis com acesso nao asfaltado.\n");
    }

    return 0;
}
148. Refaça o algoritmo do exercício 120 usando registro.
#include <stdio.h>
#include <string.h>

typedef struct {
    int idade;
    char sexo;    // 'M' ou 'F'
    float salario;
} Habitante;

int main() {
    int n, i;
    printf("Digite a quantidade de habitantes pesquisados: ");
    scanf("%d", &n);

    Habitante habitantes[n];

    // Leitura dos dados
    for (i = 0; i < n; i++) {
        printf("\nHabitante %d\n", i + 1);
        printf("Idade: ");
        scanf("%d", &habitantes[i].idade);
        printf("Sexo (M/F): ");
        scanf(" %c", &habitantes[i].sexo);
        habitantes[i].sexo = toupper(habitantes[i].sexo);  // para garantir maiúscula
        printf("Salario: ");
        scanf("%f", &habitantes[i].salario);
    }

    // Inicializações para cálculo
    float somaSalarios = 0;
    int maiorIdade = habitantes[0].idade;
    int menorIdade = habitantes[0].idade;
    int qtdMulheresSalario100 = 0;

    for (i = 0; i < n; i++) {
        somaSalarios += habitantes[i].salario;

        if (habitantes[i].idade > maiorIdade)
            maiorIdade = habitantes[i].idade;

        if (habitantes[i].idade < menorIdade)
            menorIdade = habitantes[i].idade;

        if (habitantes[i].sexo == 'F' && habitantes[i].salario <= 100.0)
            qtdMulheresSalario100++;
    }

    printf("\nMedia de salario do grupo: %.2f\n", somaSalarios / n);
    printf("Maior idade do grupo: %d\n", maiorIdade);
    printf("Menor idade do grupo: %d\n", menorIdade);
    printf("Quantidade de mulheres com salario ate R$100,00: %d\n", qtdMulheresSalario100);

    return 0;
}
149. Refaça o algoritmo do exercício 123 usando registro.
#include <stdio.h>
#include <string.h>

typedef struct {
    int idade;
    char sexo;    // 'M' ou 'F'
    float salario;
} Habitante;

int main() {
    int n, i;
    printf("Digite a quantidade de habitantes pesquisados: ");
    scanf("%d", &n);

    Habitante habitantes[n];

    // Leitura dos dados
    for (i = 0; i < n; i++) {
        printf("\nHabitante %d\n", i + 1);
        printf("Idade: ");
        scanf("%d", &habitantes[i].idade);
        printf("Sexo (M/F): ");
        scanf(" %c", &habitantes[i].sexo);
        habitantes[i].sexo = toupper(habitantes[i].sexo);  // para garantir maiúscula
        printf("Salario: ");
        scanf("%f", &habitantes[i].salario);
    }

    // Inicializações para cálculo
    float somaSalarios = 0;
    int maiorIdade = habitantes[0].idade;
    int menorIdade = habitantes[0].idade;
    int qtdMulheresSalario100 = 0;

    for (i = 0; i < n; i++) {
        somaSalarios += habitantes[i].salario;

        if (habitantes[i].idade > maiorIdade)
            maiorIdade = habitantes[i].idade;

        if (habitantes[i].idade < menorIdade)
            menorIdade = habitantes[i].idade;

        if (habitantes[i].sexo == 'F' && habitantes[i].salario <= 100.0)
            qtdMulheresSalario100++;
    }

    printf("\nMedia de salario do grupo: %.2f\n", somaSalarios / n);
    printf("Maior idade do grupo: %d\n", maiorIdade);
    printf("Menor idade do grupo: %d\n", menorIdade);
    printf("Quantidade de mulheres com salario ate R$100,00: %d\n", qtdMulheresSalario100);

    return 0;
}
150. Refaça o algoritmo do exercício 124 usando registro. 
#include <stdio.h>

typedef struct {
    int matricula;
    float nota1;
    float nota2;
    float nota3;
    float mediaFinal;
} Aluno;

int main() {
    Aluno aluno;
    int totalAlunos = 0;
    int totalAprovados = 0;
    int totalReprovados = 0;

    while (1) {
        printf("Informe a matrícula do aluno (9999 para encerrar): ");
        scanf("%d", &aluno.matricula);

        if (aluno.matricula == 9999) {
            break;
        }

        printf("Informe a nota 1: ");
        scanf("%f", &aluno.nota1);

        printf("Informe a nota 2: ");
        scanf("%f", &aluno.nota2);

        printf("Informe a nota 3: ");
        scanf("%f", &aluno.nota3);

        aluno.mediaFinal = (2 * aluno.nota1 + 3 * aluno.nota2 + 4 * aluno.nota3) / 9.0;

        printf("Matrícula: %d\n", aluno.matricula);
        printf("Média Final: %.2f\n", aluno.mediaFinal);

        if (aluno.mediaFinal >= 5.0) {
            printf("Status: APROVADO\n\n");
            totalAprovados++;
        } else {
            printf("Status: REPROVADO\n\n");
            totalReprovados++;
        }

        totalAlunos++;
    }

    printf("Total de alunos: %d\n", totalAlunos);
    printf("Total de aprovados: %d\n", totalAprovados);
    printf("Total de reprovados: %d\n", totalReprovados);

    return 0;
}
