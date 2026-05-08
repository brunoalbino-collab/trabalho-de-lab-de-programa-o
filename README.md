#include <stdio.h>
#include <string.h>

int main() {
    // Declaração das variáveis
    char placa[8];
    int tipo;
    int horas;
    float preco_hora;
    float valor_base;
    float desconto;
    float multa;
    float valor_final;
    printf("=== SISTEMA DE ESTACIONAMENTO ROTATIVO ===\n");
    printf("Digite a placa do veiculo (ex: ABC1234): ");
    scanf("%s", placa);
    printf("Tipo do veiculo:\n");
    printf("1 - Carro (R$ 5/h)\n");
    printf("2 - Moto (R$ 3/h)\n");
    printf("3 - Caminhonete (R$ 8/h)\n");
    printf("Escolha (1/2/3): ");
    scanf("%d", &tipo);
    printf("Digite o tempo de permanencia (em horas inteiras): ");
    scanf("%d", &horas);
      switch(tipo) {
        case 1:
            preco_hora = 5.0;
            break;
        case 2:
            preco_hora = 3.0;
            break;
        case 3:
            preco_hora = 8.0;
            break;
        default:
            printf("Tipo invalido! Encerrando programa.\n");
            return 1; // Sai do programa com erro
    }
    valor_base = preco_hora * horas;
    
  desconto = 0.0;
    multa = 0.0;
    
  if (horas > 5) {
        desconto = valor_base * 0.10;   // 10% de desconto
        valor_base = valor_base - desconto;
    }
    
  if (horas > 10) {
        multa = 20.0;
        valor_final = valor_base + multa;
    } else {
        valor_final = valor_base;
    }
    
   
  if (valor_final < 0) {
        valor_final = 0;
    }
    
   printf("\n=== EXTRATO DO ESTACIONAMENTO ===\n");
   printf("Placa: %s\n", placa);
   printf("Tipo: ");
   switch(tipo) {
   case 1: printf("Carro\n"); break;
   case 2: printf("Moto\n"); break;
   case 3: printf("Caminhonete\n"); break;
    }
   printf("Tempo de permanencia: %d hora(s)\n", horas);
   printf("Valor base (antes descontos/multas): R$ %.2f\n", preco_hora * horas);
   printf("Desconto aplicado: R$ %.2f\n", desconto);
   printf("Multa aplicada: R$ %.2f\n", multa);
   printf("Valor final a pagar: R$ %.2f\n", valor_final);
    
  return 0;
}
