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

COBOL possuí uma estrutura hierárquica:

- Programa
  - Divisões
    - Seções
      - Parágrafos
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

Pode ser explicito ou implícito, o explicito marca o fim de um comando Procedure Division utilizando o `END-`. Todo verbo condicional (IF, EVALUATE) ou uma clausula condicional (COMPUTE, PERFORM, READ) terá um finalizador de escopo. O implícito é um ponto final (.), ele termina todos os escopos anteriores que ainda não foram finalizados.

## Frases

Em COBOL frases - *sentences*  são um ou mais declarações seguidas por um ponto final (.), onde o ponto indica o fim do escopo.

## Parágrafo

Parágrafo pode ser definido pelo usuário ou predefinido e seguido por um ponto final (.). O parágrafo consiste em 0 ou mais frases e é uma subdivisão da Seção ou Divisão.

<img width= "350" src="https://github.com/BrunoOlivei/12in23/blob/main/Anexos/Pasted%20image%2020230115115818.png">

## Seção

Uma seção pode ser definida pelo usuário ou predefinida seguida por um ponto final, possui 0 ou muitas frases. Uma seção é uma coleção de parágrafos.

## Divisão

Divisões são subdivididas em Seções.
Seções são subdivididas em Parágrafos.
Parágrafos são subdivididos em Frases.
Frases consistem em Comandos.
Comandos começam com palavras reservadas do COBOL e podem ser subdivididos em frases.

## Quatro tipos de divisões

### 1. IDENTIFICATION DIVISION

Identifica o programa com o nome, opcionalmente pode conter outras informações como nome do autor, data da compilação, etc.

### 2. ENVIROMENT DIVISION

Descreve os aspectos do programa que dependem de variáveis de ambiente como tipo de configuração e as entradas e saídas.

### 3. DATA DIVISION

São as características dos dados definidas nas seguintes seções:

- FILE SECTION: Define os dados usados nas operações de entrada e saída.
- LINKAGE SECTION: Descreve os dados de outros programas que serão processados no programa em questão.
- WORKING-STORAGE SECTION: Armazenamento alocado para o programa.
- LOCAL-STORAGE SECTION: Armazenamento alocado cada vez que o programa é rodado até o fim.

### 4. PROCEDURE DIVISION

Contém instruções relacionadas a manipulação dos dados e interfaces com outros procedimentos.

## PROCEDURE DIVISION explicada

A `PROCEDURE DIVISION` é onde a mágica acontece, onde os comandos são executados pelo programa. O `PROCEDURE DIVISION` de um programa é dividido em seções e parágrafos, que contém frases e comandos:

- Seção: subdivisão lógica. Opcionalmente pode conter um cabeçalho e seguido por um ou mais parágrafos. A seção pode ser um contexto para a declaração `PERFORM`. Um tipo de seção é a declarativa que é um conjunto de uma ou mais seções com **propósitos especiais**. As seções com propósito especial contêm descrições sobre entradas e saídas, por exemplo. São escritas no começo do `PROCEDURE DIVISION` e começam com a palavra reservada `DECLARATIVES` e finaliza com `END DECLARATIVES`.
- Parágrafos: são subdivisões das seções o parágrafo pode ser o assunto (subject) de um comando (statement).
- Frases: uma série de um ou mais comandos COBOL finalizados por um ponto final (.).
- Comandos: uma ação que precisa ser executada no pelo programa como por exemplo adicionar dois números.