# Conversão de Decimal para Outras Bases Numéricas

Para converter um número decimal para outra base numérica, siga os seguintes passos:

1. Escolha a base numérica desejada (2 para binário, 8 para octal, 16 para hexadecimal).
2. Divida o número decimal pela base numérica escolhida e anote o resto.
3. Divida o resultado da divisão anterior pela base numérica escolhida e anote o resto.
4. Repita o passo anterior até que o resultado da divisão seja igual a zero.
5. Escreva os restos das divisões em ordem inversa para obter o resultado na nova base numérica.

Por exemplo, para converter o número decimal 57 para a base octal:

1. Base numérica escolhida: 8
2. 57 ÷ 8 = 7, resto 1
3. 7 ÷ 8 = 0, resto 7
4. Resultado final: 71 (leitura dos restos em ordem inversa)

Para converter o número decimal 231 para a base hexadecimal:

1. Base numérica escolhida: 16
2. 231 ÷ 16 = 14, resto 7
3. 14 ÷ 16 = 0, resto 14
4. Resultado final: E7 (leitura dos restos em ordem inversa)

## Exemplos:

- Decimal (base 10): 27 convertido para binário (base 2)

1. Dividindo 27 por 2: 27 / 2 = 13 com resto 1.
2. Resto: 1
3. Dividindo 13 por 2: 13 / 2 = 6 com resto 1.
4. Dividindo 6 por 2: 6 / 2 = 3 com resto 0.
5. Dividindo 3 por 2: 3 / 2 = 1 com resto 1.
6. Dividindo 1 por 2: 1 / 2 = 0 com resto 1.
7. Resultado final: 11011 (escrevendo os restos na ordem inversa).

- Decimal (base 10): 51 convertido para octal (base 8)

1. Dividindo 51 por 8: 51 / 8 = 6 com resto 3.
2. Resto: 3
3. Dividindo 6 por 8: 6 / 8 = 0 com resto 6.
4. Resultado final: 63 (escrevendo os restos na ordem inversa).

- Decimal (base 10): 120 convertido para hexadecimal (base 16)

1. Dividindo 120 por 16: 120 / 16 = 7 com resto 8.
2. Resto: 8
3. Dividindo 7 por 16: 7 / 16 = 0 com resto 7.
4. Resultado final: 78 (escrevendo os restos na ordem inversa).

- Decimal (base 10): 255 convertido para quinário (base 5)

1. Dividindo 255 por 5: 255 / 5 = 51 com resto 0.
2. Resto: 0
3. Dividindo 51 por 5: 51 / 5 = 10 com resto 1.
4. Dividindo 10 por 5: 10 / 5 = 2 com resto 0.
5. Dividindo 2 por 5: 2 / 5 = 0 com resto 2.
6. Resultado final: 4010 (escrevendo os restos na ordem inversa).

- Decimal (base 10): 1023 convertido para ternário (base 3)

1. Dividindo 1023 por 3: 1023 / 3 = 341 com resto 0.
2. Resto: 0
3. Dividindo 341 por 3: 341 / 3 = 113 com resto 2




_________________________________________________________________________________________________________________________________

# Conversão de Outras Bases Numéricas para Decimal

Para converter um número em outra base numérica para decimal, siga os seguintes passos:

1. Identifique a base numérica do número original.
2. Multiplique cada dígito do número pela potência correspondente da base numérica (começando da direita para a esquerda, com a potência zero).
3. Some os resultados das multiplicações para obter o valor decimal equivalente.

Por exemplo, para converter o número binário 1011 para decimal:

1. Base numérica identificada: 2 (binário)
2. 1 * 2^0 = 1, 1 * 2^1 = 2, 0 * 2^2 = 0, 1 * 2^3 = 8
3. Resultado final: 11 (soma dos resultados das multiplicações)

Para converter o número hexadecimal A3 para decimal:

1. Base numérica identificada: 16 (hexadecimal)
2. A = 10, 3 = 3
   10 * 16^1 = 160, 3 * 16^0 = 3
3. Resultado final: 163 (soma dos resultados das multiplicações)

Observação: Para converter números octais para decimais, basta seguir os mesmos passos, considerando a base numérica 8 em vez de 2 ou 16.

## MAIS EXEMPLOS: 
- Binário (base 2): 101101

1. Base numérica identificada: 2 (binário)
2. 1 * 2^0 = 1, 0 * 2^1 = 0, 1 * 2^2 = 4, 1 * 2^3 = 8, 0 * 2^4 = 0, 1 * 2^5 = 32
3. Resultado final: 45 (soma dos resultados das multiplicações)

- Ternário (base 3): 2012

1. Base numérica identificada: 3 (ternário)
2. 2 * 3^0 = 2, 1 * 3^1 = 3, 0 * 3^2 = 0, 2 * 3^3 = 54
3. Resultado final: 59 (soma dos resultados das multiplicações)

- Quaternário (base 4): 332

1. Base numérica identificada: 4 (quaternário)
2. 2 * 4^0 = 2, 3 * 4^1 = 12, 3 * 4^2 = 48
3. Resultado final: 62 (soma dos resultados das multiplicações)

- Quintal (base 5): 1243

1. Base numérica identificada: 5 (quintal)
2. 3 * 5^0 = 3, 4 * 5^1 = 20, 2 * 5^2 = 50, 1 * 5^3 = 125
3. Resultado final: 198 (soma dos resultados das multiplicações)

- Senário (base 6): 532

1. Base numérica identificada: 6 (senário)
2. 2 * 6^0 = 2, 3 * 6^1 = 18, 5 * 6^2 = 180
3. Resultado final: 200 (soma dos resultados das multiplicações)

- Heptal (base 7): 625

1. Base numérica identificada: 7 (heptal)
2. 5 * 7^0 = 5, 2 * 7^1 = 14, 6 * 7^2 = 294
3. Resultado final: 313 (soma dos resultados das multiplicações)

- Octal (base 8): 372

1. Base numérica identificada: 8 (octal)
2. 2 * 8^0 = 2, 7 * 8^1 = 56, 3 * 8^2 = 192
3. Resultado final: 250 (soma dos resultados das multiplicações)


________________________________________________________________________________________________________________________________________________



# Conversão de Hexadecimal para Outras Bases Numéricas

Para converter um número hexadecimal para outra base numérica, siga os seguintes passos:

1. Converta o número hexadecimal para binário.
2. Divida o número binário pela base numérica desejada.
3. Anote o resto da divisão (o dígito menos significativo).
4. Divida o resultado inteiro da divisão anterior novamente pela base numérica e anote o resto.
5. Continue dividindo o resultado inteiro pelas bases numéricas até que o quociente seja zero.
6. Escreva os restos (começando pelo último) para obter o número equivalente na base numérica desejada.


## Para converter um número hexadecimal para binário, basta substituir cada dígito hexadecimal por sua representação em binário de 4 bits. Por exemplo:

  ```
  Hexadecimal (base 16): AF
  Binário (base 2): 10101111
  ```

  Note que "A" em hexadecimal é 1010 em binário (2^3 + 0 + 1), e "F" em hexadecimal é 1111 em binário (2^3 + 2^2 + 2^1 + 2^0).

- Para converter um número hexadecimal para octal, basta agrupar os dígitos hexadecimais de 3 em 3 e substituí-los pela sua representação em octal. Por exemplo:

  ```
  Hexadecimal (base 16): 9C
  Octal (base 8): 234
  ```

  Note que "9" em hexadecimal é 1001 em binário, e "C" em hexadecimal é 1100 em binário. Agrupando os dígitos de 3 em 3, temos: 001 001 100, que em octal é 2 3 4.

- Para converter um número hexadecimal para decimal, basta multiplicar cada dígito hexadecimal pela sua potência de 16 correspondente e somar os resultados. Por exemplo:

  ```
  Hexadecimal (base 16): BC
  Decimal (base 10): 188
  ```

  Note que "B" em hexadecimal é 11 em decimal (16^1 + 1), e "C" em hexadecimal é 12 em decimal (16^0 + 12). Multiplicando cada dígito pela sua potência de 16 correspondente e somando os resultados, temos: 11 * 16^1 + 12 * 16^0 = 176 + 12 = 188.


______________________________________________________________________________________________________________________________________________________________

# Outras bases para Hexadecimal

Para converter um número em outra base para hexadecimal, siga os seguintes passos:

1. Divida o número em grupos de 4 dígitos, da direita para a esquerda, adicionando zeros à esquerda, se necessário.
2. Converta cada grupo de 4 dígitos em um único dígito hexadecimal, de acordo com a tabela de conversão abaixo.
3. Junte os dígitos hexadecimais obtidos no passo anterior, da esquerda para a direita, para obter o número equivalente em hexadecimal.

Tabela de Conversão de 4 Dígitos para Hexadecimal:

| 4 Dígitos | Hexadecimal |
| --- | --- |
| 0000 | 0 |
| 0001 | 1 |
| 0010 | 2 |
| 0011 | 3 |
| 0100 | 4 |
| 0101 | 5 |
| 0110 | 6 |
| 0111 | 7 |
| 1000 | 8 |
| 1001 | 9 |
| 1010 | A |
| 1011 | B |
| 1100 | C |
| 1101 | D |
| 1110 | E |
| 1111 | F |

Exemplos:

1. Converter o número binário 11011011 para hexadecimal:

- Dividindo em grupos de 4 dígitos: 1101 1011
- Convertendo cada grupo para hexadecimal: D B
- Juntando os dígitos hexadecimais: DB
- Resultado: DB

2. Converter o número octal 7532 para hexadecimal:

- Convertendo para binário: 111 101 010 010
- Dividindo em grupos de 4 dígitos: 0111 1010 1001 0010
- Convertendo cada grupo para hexadecimal: 7 A 9 2
- Juntando os dígitos hexadecimais: 7A92
- Resultado: 7A92

Espero que essa explicação seja mais clara. Se ainda tiver dúvidas, fique à vontade para perguntar.
