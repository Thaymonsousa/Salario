import java.util.Scanner;

public class ReajusteSalarial {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        // Entrada do salário atual
        System.out.print("Digite o salário atual do colaborador: R$ ");
        double salarioAtual = input.nextDouble();

        double percentualAumento = 0;

        // Definindo o percentual de aumento
        if (salarioAtual <= 280.00) {
            percentualAumento = 20;
        } else if (salarioAtual <= 700.00) {
            percentualAumento = 15;
        } else if (salarioAtual <= 1500.00) {
            percentualAumento = 10;
        } else {
            percentualAumento = 5;
        }

        // Cálculos
        double valorAumento = salarioAtual * (percentualAumento / 100);
        double novoSalario = salarioAtual + valorAumento;

        // Descontando inflação de 3,8%
        double inflacao = 3.8;
        double aumentoReal = percentualAumento - inflacao;
        double valorAumentoReal = salarioAtual * (aumentoReal / 100);

        // Saída
        System.out.println("\n--- Resultado ---");
        System.out.printf("1. Salário antes do reajuste: R$ %.2f\n", salarioAtual);
        System.out.printf("2. Percentual de aumento aplicado: %.1f%%\n", percentualAumento);
        System.out.printf("3. Valor do aumento: R$ %.2f\n", valorAumento);
        System.out.printf("4. Novo salário, após o aumento: R$ %.2f\n", novoSalario);
        System.out.printf("5. Valor do aumento real, descontada a inflação: R$ %.2f\n", valorAumentoReal);

        input.close();
    }
}
