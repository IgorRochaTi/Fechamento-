#include <stdio.h>

int main()
{
    char operador[50], motorista[50], continuar;
    float diaria1, diaria2, diaria3, totalValorDiaria, valorEntregaExtra;
    float extras, desconto, totalFechamento;
    int quantDiaria1, quantDiaria2, quantDiaria3, totalEntregas;
    int totalDiarias, entregasExtra, diariaPorEntrega;

    printf("\nInsira o nome do operador:\n");
    scanf("%s", operador);

    do {
        printf("\n------Novo fechamento------\n");
        printf("\nOlÃ¡ %s!\n", operador);

        printf("\nInsira o nome do motorista\n");
        scanf("%s", motorista);

        printf("\nInsira o valor (em R$) da diaria 1:\n");
        scanf("%f", &diaria1);
        printf("\nQuantas diÃ¡rias nesse valor?:\n");
        scanf("%d", &quantDiaria1);

        printf("\nInsira o valor (em R$) da diaria 2:\n");
        scanf("%f", &diaria2);
        printf("\nQuantas diÃ¡rias nesse valor?:\n");
        scanf("%d", &quantDiaria2);

        printf("\nInsira o valor (em R$) da diaria 3:\n");
        scanf("%f", &diaria3);
        printf("\nQuantas diÃ¡rias nesse valor?:\n");
        scanf("%d", &quantDiaria3);

        printf("\nInsira a quantidade de entregas que o/a %s fez no perÃ­do:\n", motorista);
        scanf("%d", &totalEntregas);

        printf("\nHÃ¡ algum valor a adicionar? (ex: nf de remÃ©dio, caso nÃ£o tenha coloque 0):\n");
        scanf("%f", &extras);

        printf("\nHÃ¡ algum valor pra descontar? (caso nÃ£o tenha, coloque 0):\n");
        scanf("%f", &desconto);

        totalDiarias = quantDiaria1 + quantDiaria2 + quantDiaria3;
        totalValorDiaria = (diaria1 * quantDiaria1) + (diaria2 * quantDiaria2) + (diaria3 * quantDiaria3);
        diariaPorEntrega = totalDiarias * 50;
        entregasExtra = totalEntregas - diariaPorEntrega;
        if (entregasExtra < 0) entregasExtra = 0;

        valorEntregaExtra = entregasExtra * 2;
        totalFechamento = totalValorDiaria + valorEntregaExtra + extras - desconto;

        printf("\n------Resultado do Fechamento------\n");
        printf("\nOperador: %s\n", operador);
        printf("\nMotorista: %s\n", motorista);
        printf("\nTotal das diÃ¡rias 1: %.2f\n", diaria1 * quantDiaria1);
        printf("\nTotal das diÃ¡rias 2: %.2f\n", diaria2 * quantDiaria2);
        printf("\nTotal das diÃ¡rias 3: %.2f\n", diaria3 * quantDiaria3);
        printf("\nTotal de dias trabalhados: %d\n", totalDiarias);
        printf("\nTotal das entregas a mais das diÃ¡ria: %.2f\n", valorEntregaExtra);
        printf("\nValor total do fechamento: %.2f\n", totalFechamento);
        printf("\n\nObrigado por usar esse programa!!!\n");
        printf("\n\nDeseja realizar outro fechamento? (S-sim/N-nÃ£o):\n\n");
        scanf(" %c", &continuar);

    } while (continuar == 'S' || continuar == 's');

    return 0;
}
