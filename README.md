# Calculo do valor da variável soma

public class SomaIndice {
    public static void main(String[] args) {
        int INDICE = 13;
        int SOMA = 0;

        for (int K = 1; K <= INDICE; K++) {
            SOMA += K;
        }

        System.out.println(SOMA);
    }
}


##  Sequência de Fibonacci

import java.util.Scanner;

public class FibonacciRecursivo {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.println("Informe um número:");
        int numero = scanner.nextInt();
        
        if (isFibonacci(numero, 0, 1)) {
            System.out.println("O número " + numero + " pertence à sequência de Fibonacci.");
        } else {
            System.out.println("O número " + numero + " não pertence à sequência de Fibonacci.");
        }
    }

    public static boolean isFibonacci(int n, int a, int b) {
        if (n == a || n == b) return true;
        int c = a + b;
        if (c > n) return false;
        return isFibonacci(n, b, c);
    }
}


## Faturamento diário de uma distribuidora

import java.util.OptionalDouble;
import java.util.stream.DoubleStream;

public class FaturamentoDiario {
    public static void main(String[] args) {
        double[] faturamento = {1000, 2000, 3000, 4000, 5000};  // exemplo de dados de faturamento

        double menor = DoubleStream.of(faturamento).min().orElse(Double.MAX_VALUE);
        double maior = DoubleStream.of(faturamento).max().orElse(Double.MIN_VALUE);
        OptionalDouble mediaOpt = DoubleStream.of(faturamento).average();
        double media = mediaOpt.orElse(0);
        long diasComFaturamentoSuperior = DoubleStream.of(faturamento)
                                                      .filter(valor -> valor > media)
                                                      .count();

        System.out.println("Menor faturamento: " + menor);
        System.out.println("Maior faturamento: " + maior);
        System.out.println("Dias com faturamento superior à média: " + diasComFaturamentoSuperior);
    }
}


## Percentual de representação por estado

import java.util.HashMap;
import java.util.Map;

public class FaturamentoMensal {
    public static void main(String[] args) {
        Map<String, Double> faturamento = new HashMap<>();
        faturamento.put("SP", 67836.43);
        faturamento.put("RJ", 36678.66);
        faturamento.put("MG", 29229.88);
        faturamento.put("ES", 27165.48);
        faturamento.put("Outros", 19849.53);

        double total = faturamento.values().stream().mapToDouble(Double::doubleValue).sum();

        faturamento.forEach((estado, valor) -> {
            double percentual = (valor / total) * 100;
            System.out.printf("%s: %.2f%%\n", estado, percentual);
        });
    }
}


## Inversão de caracteres de uma string

import java.util.Scanner;

public class InverterString {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.println("Digite uma string:");
        String original = scanner.nextLine();

        String invertida = new StringBuilder(original).reverse().toString();

        System.out.println("String invertida: " + invertida);
    }
}


