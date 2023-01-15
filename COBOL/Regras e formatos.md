# Conhecimentos básicos

## Regras e formatos

O código fonte é column-dependent, o que significa que há regras específicas para cada coluna, cada linha de código COBOL possuí 5 áreas, cada área tem um começo e fim.

### 1. Sequence Number Area

As colunas 1 a 6 são reservadas para sequencia de números ou podem também ficar em branco.

### 2. Indicator Area

Coluna 7 possui multiplos propósitos:

- Comentário de linha (utilizando um asterisco)
- Continuação da linha anterior (utilizando um hífen)
- Debbug (D ou d)
- Source listing formatting (underline)

### 3. Area A

Alguns itens precisam começar a partir das colunas 8 a 11:

- Indicador de nível
- Divisões, seções cabeçalho de parágrafos
- Declarações
- Nome de parágrafos

### 4. Area B

Alguns itens precisam começar a partir das colunas 12 a 72:

- Entradas, sentenças, declarações e clausulas
- Continuação das linhas

### 5. Area identificação

Ignorada pelo compilador pode ficar em branco ou ser usada para qualquer propósito.

## Estrutura

COBOL possuí uma estrutura hierarquica:

- Programa
  - Divisões
    - Seções
      - Paragrafos
        - Frase
          - Comandos

## Palavras reservadas

[Reserved words - IBM Documentation](https://www.ibm.com/docs/en/cobol-zos/6.4?topic=appendixes-reserved-words)

## Declaração COBOL

Algumas palavras reservadas usadas para alterar a sequencia de execução baseada em condições. Declarações só existem no Procedure Division:

- IF
- Evaluate
- Perform

## Scope Terminator

Pode ser explicito ou implicito, o explicito marca o fim de uma declaração Procedure Division utilizando o `END-`. Todo verbo condicional (IF, EVALUATE) ou uma clausula condicional (COMPUTE, PERFORM, READ) terá um finalizador de escopo. O implicito é um ponto final (.), ele termina todos os escopos anteriores que aind não foram finalizados.

## Frases

Em COBOL frases - *sentences*  são um ou mais declarações seguidas por um ponto final (.), onde o ponto indica o fim do escopo.

## Parágrafo

Parágrafo pode ser definido pelo usuário ou predefinido e seguido por um ponto final (.). O parágrafo consiste em 0 ou mais frases e é uma subdivisão da Seção ou Divisão.

![[Pasted image 20230115115818.png]]

