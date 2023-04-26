# Criando códigos em assembly RISK-V

**O código Assembly começa lendo linha a linha. O que está escrito primeiro, é executado primeiro, e segue a rota, linha a linham a não ser que o caminho seja desbiado por uma label.**

____________________________________________________________________________________________________________________________________________________________

### DECLARANDO VARIÁVEIS

Para começar o código em assembly RISK-V, assim como outras linguagens de programação, o primeiro passo é declarar as variáveis. 
Para isso, pode-se criar a seção de dados, escrevendo ```.data``` e carregar dados que serão usados por muito tempo na memória, alocando espaço para esses dados: 

| Código em C | Código em RISK-V|
|--------|--------|
| <br>int i = 10;<br> float f = 10.5;<br> char c = 'k';<br> string s = "olá mundo"; | .data <br> i: .word 10 <br> f: .float 10.5 <br> c: .byte 'k' <br> s: .asciiz "olá mundo" |

Porém, essa é a forma menos comum utilizada, pois o ```.data``` armazena os dados em espaços físicos da memória. A outra forma, mais utilizada para declarar variáveis 
é carregando os números em registradores. Como exemplo, será feita a soma de 5 + 3:

```li a0, 5```  #Carregando o valor 5 em a0

```li a1, 5```  #Carregando os valor 3 em a1;

```add t0, a0, a1```  #Somando os valores e armazenando no registrador t0;

- O comando "li" é uma instrução em assembly RISC-V que carrega um valor imediato (um valor fixo especificado na própria instrução) em um registrador. 
- Já os registradores a0 e a1, são para uso geral, muito utilizados em armazenar retorno de função ou valores temporários.


Existe uma terceira forma de atribuit valor a um registrador, que é fazendo a soma do registrador zero a um número ou outro registrador. 

```li t0, 5```      # Carrega o valor 5 em t0

```add x, t0, zero```  # Adiciona 0 a t0 (inicializa x com o valor 5)


ou também:

```addi x, zero, 5```

____________________________________________________________________________________________________________________________________________________________

### SOMANDO E SUBTRAINDO NÚMEROS

Existem dois comandos para fazer somas e subtrações em Assembly RISK-V

- add #faz somas entre registradores

  ```add x, t0, t1 ``` #soma o valor de t0 com o valor de t1
  
  
- addi #soma um registrador a um inteiro, mas o tamanho tem que ser menor que 12 bits, ou seja, o valor imediato deve estar entre -2048 a 2047

  ```addi x, t0, 2047 ``` #soma o valor de t0 com o número 2047
  
  
- sub #faz subtração entre os registradores. 

  ```sub x, t0, t1 ``` #subtrai o valor de t0 ao valor de t1, por exemplo, se t0=5 e t1=3, x = 5-3 = 2


- subi #o mesmo do addi vale para o subi. O tamanho do valor do número que pode ser passado tem que ser menor que 12 bits (-2048 a 2047)

  ```subi x, t0, 2047 ``` #soma o valor de t0 com o número 2047
  

____________________________________________________________________________________________________________________________________________________________

### UTILIZANDO OPERADORES LÓGICOS (AND, OR, XOR)

Para realizar operações com operadores lógicos, é necessário trabalhar com a base binária, pois as operações são feitas bit a bit, ou seja, cada número é comparado com o número que está na mesma posição. Para ficar mais claro, vamos fazer uma operação entre os números 00011001 AND 10010001, para isso colocaremos os números 00011001 na primeira coluna,10010001 na segunda coluna e o resultado na terceira coluna:
```0 AND 1 = 0
0 AND 0 = 0
0 AND 0 = 0
1 AND 1 = 1
1 AND 0 = 0
0 AND 0 = 0
0 AND 0 = 0
1 AND 1 = 1
-----------
00010001
```
O mesmo vale para as portas OR e XOR. Para fazer as operações, será feito bit a bit, comparando 1 byte inteiro, ou seja, números de 8 bits (8 posições).
Para relembrar: 1 palavra tem 32 bits, que é um valor interiro da memória, ou seja 4 bytes. 

____________________________________________________________________________________________________________________________________________________________

### COMPARADORES DE VALORES:
  
  #### SLT ( Set Less Than )
  
  - **slt** em RISC-V é utilizado para definir se um valor em um registrador é menor que outro valor.
  
    ```slt rd, rs1, rs2```
    
    onde rd é o registrador de destino (que armazenará o resultado da comparação), rs1 e rs2 são os registradores com os valores a serem comparados.
    A instrução slt coloca o valor 1 no registrador rd se o valor em rs1 < rs2. Caso contrário, o valor 0 é colocado em rd. 
    É importante destacar que a comparação é feita considerando números com sinal (signed), ou seja, valores negativos também podem ser comparados.

    O uso mais comum do slt é em desvios condicionais, em conjunto com o comando bne ou beq, permitindo que o programa escolha qual caminho seguir de acordo com o         resultado da comparação.
    
    Exemplo: 
    *Carrega o valor 10 no registrador s0*
    
    ```li s0, 10```


    *Carrega o valor 20 no registrador s1*
    
    ```li s1, 20```

    *Compara s0 com s1 usando a instrução slt e armazena o resultado em s2*
    
    ```slt s2, s0, s1   # s2 = (s0 < s1) ? 1 : 0v ```


    *Verifica o resultado da comparação usando a instrução bne*
    *bne s2, zero, menor # se s2 for diferente de 0, ramifica para a label menor*

    *Se chegou aqui, s0 não é menor que s1, então faz outra coisa*

    *Define a label menor*
    ```menor:```
    ```# Se chegou aqui, s0 é menor que s1, então faz outra coisa```
    ```# ... ```
    
    ***Também é possivel utilizar slti, que utiliza um número de até 12 bits no rs2 (no lugar do segundo registrador com valores da operação)***

____________________________________________________________________________________________________________________________________________________________

### DESLOCAMENTOS

 #### SLL ( Set Less Than )
  
  - **sll** em RISC-V realiza um deslocamento lógico para a esquerda em um registrador de 32 bits. O deslocamento é especificado por um valor imediato de 5 bits que       pode variar de 0 a 31.
    
    A operação SLL é usada para multiplicar um número por uma potência de 2. Por exemplo, para multiplicar o número armazenado no registrador x2 por 4, pode-se usar a     seguinte instrução Assembly RISC-V:
  
    x11 = 2 | a2 = 2
  
    ```sll x2, x2, x11```  ou ```sll sp, sp, x11``` ou  ```sll a1, a1, a2```
    
    Isso desloca o conteúdo do registrador x2 ou sp ou a1 em 2 posições para a esquerda, o que equivale a multiplicá-lo por 4.
    Em resumo, a operação SLL é uma instrução básica em Assembly RISC-V que é usada para realizar deslocamentos lógicos para a esquerda em um registrador de 32 bits.


    
    onde rd é o registrador de destino (que armazenará o resultado da comparação), rs1 e rs2 são os registradores com os valores a serem comparados.
    A instrução slt coloca o valor 1 no registrador rd se o valor em rs1 < rs2. Caso contrário, o valor 0 é colocado em rd. 
    É importante destacar que a comparação é feita considerando números com sinal (signed), ou seja, valores negativos também podem ser comparados.

    O uso mais comum do slt é em desvios condicionais, em conjunto com o comando bne ou beq, permitindo que o programa escolha qual caminho seguir de acordo com o         resultado da comparação.
    
    Exemplo: 
    *Carrega o valor 10 no registrador s0*
    
    ```li s0, 10```
    
    ****Exemplo:****
    Suponha que o registrador x10 contenha o valor decimal 5, representado em binário como 00000000000000000000000000000101. Se quisermos realizar um deslocamento lógico para a esquerda de 2 bits em x10 usando a instrução SLL, podemos escrever a seguinte instrução Assembly RISC-V:
    
    x11 = 2
    
    ```sll x10, x10, x11```
    
    Isso resultaria em um valor de 20 (decimal), representado em binário como 00000000000000000000000000010100, armazenado no registrador x10 após a execução da instrução SLL.
    
    00000000000000000000000000000101 -> 00000000000000000000000000010100 -> deslocou duas casa, colocando 00
    
    
    Também é possivel usar **ssli ( (Shift Right Logical Immediate )**, onde em vez de receber um registrador, recebe-se um número com um tamanho de no máximo 5 bits. Isso significa que pode representar um valor entre 0 e 31 (2^5 - 1). Portanto, o valor imediato especificado na instrução SLLI deve estar no intervalo de 0 a 31, indicando a quantidade de bits a serem deslocados.
    

____________________________________________________________________________________________________________________________________________________________

### ESTRUTURAS CONDICIONAIS

 #### BEQ ( Branch if Equal )
 
  - O **beq** é uma instrução de desvio condicional que permite que um programa execute diferentes partes do código com base na comparação de dois registradores. O BEQ compara os valores de dois registradores e, se eles forem iguais, salta para uma instrução especificada, que é um deslocamento de um número de instruções a partir da instrução atual.
  
  A sintaxe da instrução BEQ é a seguinte:
  
  ```beq t0, t1, label```
  
  Nesse comando, comparamos o número armazenado em t0 e t1. Se t0 == t1, então o código para de executar o que está em baixo, e salta para a instrução denominada "label". E então, é executado o que está em "label" para baixo.
  
  #### BNE ( Branch if Not Equal )
  
   - Já o **bne**, como o nome já diz, faz o contrário do **beq**. Essa instrução permite que o programa execute diferentes partes do código, desviando o caminho, caso os valores dos registradores sejam diferentes.

    ```beq t0, t1, label```
    
   Considerando a instrução acima, caso t0 != t1, então o código irá ignorar as linhas debaixo até o momento que ler a instrução "label". Então, pode-se dizer que o caminho é desviado diretamente para instrução label.

____________________________________________________________________________________________________________________________________________________________  
  
  lw - Carrega um valor da memória para um registrador
  sw - Armazena um valor de um registrador na memória	
  jal - Jump and Link	
  
