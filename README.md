# Senai_LLP_Switch_DiasDoMes

import java.util.Scanner;

public class DiasDoMes {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Informe o mês (nome ou número): ");
        String entradaMes = scanner.nextLine().toLowerCase().trim();

        int numeroMes = -1;

        // Verifica se foi digitado número ou nome
        switch (entradaMes) {
            case "1": case "janeiro":     numeroMes = 1; break;
            case "2": case "fevereiro":   numeroMes = 2; break;
            case "3": case "março":       numeroMes = 3; break;
            case "4": case "abril":       numeroMes = 4; break;
            case "5": case "maio":        numeroMes = 5; break;
            case "6": case "junho":       numeroMes = 6; break;
            case "7": case "julho":       numeroMes = 7; break;
            case "8": case "agosto":      numeroMes = 8; break;
            case "9": case "setembro":    numeroMes = 9; break;
            case "10": case "outubro":    numeroMes = 10; break;
            case "11": case "novembro":   numeroMes = 11; break;
            case "12": case "dezembro":   numeroMes = 12; break;
            default:
                System.out.println("Mês inválido.");
                return;
        }

        int dias = 0;

        switch (numeroMes) {
            case 1: case 3: case 5: case 7: case 8: case 10: case 12:
                dias = 31;
                break;
            case 4: case 6: case 9: case 11:
                dias = 30;
                break;
            case 2:
                System.out.print("Informe o ano: ");
                int ano = Integer.parseInt(scanner.nextLine());
                if ((ano % 4 == 0 && ano % 100 != 0) || (ano % 400 == 0)) {
                    dias = 29; // Bissexto
                } else {
                    dias = 28;
                }
                break;
        }

        System.out.println("Quantidade de dias: " + dias);
    }
}
