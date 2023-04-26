**COMANDOS**

| Instrução | Descrição | Exemplo explicado |
| --------- | --------- | ----------------- |
| `add`     | Adiciona dois valores e armazena o resultado | `add x1, x2, x3` adiciona o valor dos registradores `x2` e `x3` e armazena o resultado em `x1`. |
| `addi`    | Adiciona um valor imediato a um registrador e armazena o resultado | `addi x1, x2, 10` adiciona o valor imediato 10 ao valor do registrador `x2` e armazena o resultado em `x1`. |
| `sub`     | Subtrai dois valores e armazena o resultado | `sub x1, x2, x3` subtrai o valor do registrador `x3` do valor do registrador `x2` e armazena o resultado em `x1`. |
| `and`     | Realiza a operação lógica AND em dois valores e armazena o resultado | `and x1, x2, x3` realiza a operação lógica AND entre os valores dos registradores `x2` e `x3` e armazena o resultado em `x1`. |
| `andi`    | Realiza a operação lógica AND entre um valor imediato e um registrador e armazena o resultado | `andi x1, x2, 5` realiza a operação lógica AND entre o valor imediato 5 e o valor do registrador `x2` e armazena o resultado em `x1`. |
| `or`      | Realiza a operação lógica OR em dois valores e armazena o resultado | `or x1, x2, x3` realiza a operação lógica OR entre os valores dos registradores `x2` e `x3` e armazena o resultado em `x1`. |
| `ori`     | Realiza a operação lógica OR entre um valor imediato e um registrador e armazena o resultado | `ori x1, x2, 5` realiza a operação lógica OR entre o valor imediato 5 e o valor do registrador `x2` e armazena o resultado em `x1`. |
| `xor`     | Realiza a operação lógica XOR em dois valores e armazena o resultado | `xor x1, x2, x3` realiza a operação lógica XOR entre os valores dos registradores `x2` e `x3` e armazena o resultado em `x1`. |
| `xori`    | Realiza a operação lógica XOR entre um valor imediato e um registrador e armazena o resultado | `xori x1, x2, 5` realiza a operação lógica XOR entre o valor imediato 5 e o valor do registrador `x2` e armazena o resultado em `x1`. |
| `slt`     | Compara dois valores e armazena o resultado como um valor lógico | `slt x1, x2, x3` compara os valores dos registradores `x2` e `x3` e armazena 1 em `x1` se `x2` for menor que `x3` ou 0 caso contrário. |
| `slti`    | Compara um valor imediato com um registrador e armazena o resultado como um valor lógico | `slti x1, x2, 10` compara o valor imediato 10 com o valor do registrador `x2` e armazena 1 em `x1` se `x2` for menor que 10 ou 0 caso contrário. |
| `sll`     | Desloca um valor para a esquerda e armazena o resultado | `sll x1, x2, 4` desloca o valor do registrador `x2` 4 bits para a esquerda e armazena o resultado em `x1`. |
| `slli`    | Desloca um valor para a esquerda usando um valor imediato como quantidade de deslocamento e armazena o resultado | `slli x1, x2, 4` desloca o valor do registrador `x2` 4 bits para a esquerda e armazena o resultado em `x1`. |
| `srl`     | Desloca um valor para a direita e armazena o resultado | `srl x1, x2, 4` desloca o valor do registrador `x2` 4 bits para a direita e armazena o resultado em `x1`. |
| `srli`    | Desloca um valor para a direita usando um valor imediato como quantidade de deslocamento e armazena o resultado | `srli x1, x2, 4` desloca o valor do registrador `x2` 4 bits para a direita e armazena o resultado em `x1`. |
| `lw`      | Carrega um valor da memória para um registrador | `lw x1, 0(x2)` carrega o valor armazenado no endereço `0 + x2` da memória e armazena o resultado em `x1`. |
| `sw`      | Armazena um valor de um registrador na memória | `sw x1, 0(x2)` armazena o valor do registrador `x1` no endereço `0 + x2` da memória. |
| `beq`     | Branch se dois registradores forem iguais | `beq x1, x2, label` verifica se os valores dos registradores `x1` e `x2` são iguais e, se sim, salta para o endereço da etiqueta `label`. |
| `bne`     | Branch se dois registradores forem diferentes | `bne x1, x2, label` verifica se os valores dos registradores `x1` e `x2` são diferentes e, se sim, salta para o endereço da etiqueta `label`. |
| `jal`     | Jump and Link |
