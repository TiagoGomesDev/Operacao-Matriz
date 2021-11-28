# Operacao-Matriz
Menu Principal  1 - Adicionar Elementos na matriz.  2 - Operações na Matriz  3 - Exibir todos os elementos da Matriz   Menu Operações  1 - Somar todos os valores de uma linha especifica. (solicitar a linha que deve ser somada)  2 - Media de todos os valores de uma coluna especifica. (solicitar a coluna que deve ser calculada)  3 - Soma total dos valores.  4 - Voltar para o menu principal 

#include<stdio.h>
#include <stdlib.h>
#include <time.h>
  int matriz[10][10],i, j,d, soma=0, somaLinhas[10], somaColunas[10];

      void adicionar()
      {
        printf ("\nDigite valor para os elementos da matriz\n\n");
        
        for ( i=0; i<10; i++ )
          for ( j=0; j<10; j++ )
          {
            printf ("\nElemento[%d][%d] = ", i, j);
            scanf ("%d", &matriz[ i ][ j ]);
          }
      }
      void linha(){
        srand(time(NULL));
          // soma das linhas
          for(i = 0; i < 10; i++){
              soma = 0;
              for(j = 0; j < 10; j++){
                  soma += matriz[i][j];
              }
              somaLinhas[i] = soma;
          }
           // impressão das estruturas

          printf("\nMatriz:\n");
          for(i = 0; i < 10; i++){
              for(j = 0; j < 10; j++){
                  printf("%2d ", matriz[i][j]);
              }
              printf("\n");
          }
            
          printf("\n\nVetor com a soma das linhas:\n");
          for(i = 0; i < 10; i++){
              printf("Linha %d: %d\n", i, somaLinhas[i]);
          }
          //imprime vetor com os numeros da linha
          // printf("escolha a linha desejada: ");
          // scanf("%d",&d);

          // printf(" \n ");
          // for(i = 0; i<2; i++){
          // for(int j=0; j<2; j++){
          //   // printf ("\nElemento[%d][%d] = ", i, j);
          //   soma += matriz[i][j];
          //   // Soma total da linha:
          // printf("%d ", soma);
          
      // }printf(" \n ");}
      }
      void media(){
        srand(time(NULL));
          for(j = 0; j < 10; j++){
              soma = 0;
              for(i = 0; i < 10; i++){
                  soma += matriz[i][j];
              }
              somaColunas[j] = soma /10;
          }
          // impressão das estruturas
          printf("\nMatriz:\n");
          for(i = 0; i < 10; i++){
              for(j = 0; j < 10; j++){
                  printf("%2d ", matriz[i][j]);
              }
              printf("\n");
          }
          
          printf("\n\nVetor com a soma das colunas:\n");
          for(j = 0; j < 10; j++){
              printf("Coluna %d: %d\n", j, somaColunas[j]);
          }
      }
      void somar(){
         for(i = 0; i<10; i++){
                    for(j=0; j<10; j++){
                      soma += matriz[i][j];
                      printf("%2d ", matriz[i][j]);
                      }
                      printf("\n");
                      }

                      printf("\n\n Soma total: %d\n\n", soma);
      }
      void operacao()
      {
        int continuar=1;
          do
          {
              printf("\n\tMenu Operações\n\n");
             
              printf("1. Somar todos os valores de uma linha especifica. (solicitar a linha que deve ser somada)\n");
              printf("2. Media de todos os valores de uma coluna especifica. (solicitar a coluna que deve ser calculada)\n");
              printf("3. Soma total dos valores\n");
              printf("0. Voltar para o menu principal\n");

              scanf("%d", &continuar);
              system("cls || clear");

              switch(continuar)
              {
                  case 1:
                      linha();
                      break;

                  case 2:
                      media();
                      break;

                  case 3:
                      somar();
                      break;

                  case 0:
                      // sair();
                      break;

                  default:
                      printf("Digite uma opcao valida\n");
              }
          } while(continuar);
      }

      void exibir()
      {
          printf("\n\n******************* Saida de Dados ********************* \n\n");

          for ( i=0; i<10; i++ )
            for ( j=0; j<10; j++ )
            {
              printf ("\nElemento[%d][%d] = %d\n", i, j,matriz[ i ][ j ]);
            }

      }

      void sair()
      {
          printf("Ja vai??? Nao! Nao! Espere! Naa...\n");
      }


      int main()
      {
        int continuar=1;
          do
          {
              printf("\n\tMenu Principal\n\n");
        
              printf("1. Adicionar Elementos na matriz\n");
              printf("2. Operações na Matriz\n");
              printf("3. Exibir todos os elementos da Matriz\n");
              printf("0. Sair\n");

              scanf("%d", &continuar);
              system("cls || clear");

              switch(continuar)
              {
                  case 1:
                      adicionar();
                      break;

                  case 2:
                      operacao();
                      break;

                  case 3:
                      exibir();
                      break;

                  case 0:
                      sair();
                      break;

                  default:
                      printf("Digite uma opcao valida\n");
              }
          } while(continuar);
      }
