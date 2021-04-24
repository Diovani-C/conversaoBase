# Conversão de Bases

O programa abaixo tem como objetivo converter números decimais inteiros e positivos, para outras bases como binário, octal ou hexadecimal.

## Como funciona o algoritimo

Para converter a base decimal em outras bases basta você pegar o numero decimal e dividir pelo numero da base (binária 2, octal 8 ou hexadecimal 16) e enfileirar o restante da divisão inteira da direita para a esquerda até que o não haja mais um número inteiro para dividir.

**Ex: decimal 8 para binario**

| Decimal | Base |   Divisão |     Resto     |
| ------- | :--: | --------: | :-----------: |
| 8       |  2   | 8 / 2 = 4 | 8 % 2 = **0** |
| 4       |  2   | 4 / 2 = 2 | 4 % 2 = **0** |
| 2       |  2   | 2 / 2 = 1 | 2 % 2 = **0** |
| 1       |  2   | 1 / 2 = 0 | 1 % 2 = **1** |

**Resultado: 1000**

## Implementação do algoritimo em codigo

Primeiro já que o resultado será armazenado em um array de caracteres gente acha o tamanho necessário para armazenar o resultado, pra fazer isso basta rodar a parte da divisão e contar quantas vezes foram divididas.

```c
  int resto, i, tamanho = 0;

  for (i = decimal; i > 0; i /= base)
  {
    tamanho++;
  }

  char resultado[tamanho]
```

Depois já que nós sabemos o tamanho do número e que a ordem dos resultados são da direita para esquerda, fazemos um loop inverso usando o tamanho do array para que o resultado fique na ordem certa no final, por último já que vamos mostrar o número como um caractere precisamos multiplicá lo por um valor para corresponder a tabela ASCII, (números vão de 48 a 57 e letras maiúsculas de 65 a 90)

```c
for (i = tamanho - 1; i >= 0; i--)
  {
    resto = decimal % base;

    resultado[i] = resto < 10 ? resto + 48 : resto + 55;

    decimal /= base;
  }
```

## Execução

Você pode compilar o projeto usando **gcc** ele não depende de nenhuma biblioteca externa, ou pode acessar esse [link](https://onlinegdb.com/BkiCveMDu) que vai te levar a um editor de códigos online onde o projeto também se encontra hospedado, e então pode rodar o código direto do navegador.
