## Intro

- Aplicação de ponteiros
- Alocação dinâmica de memória
- Estruturas de dados heterogêneas usando a linguagem de programação C.

## Propósito

Compreender o conceito de estruturas de dados heterogêneas e aplicá-las usando a linguagem de programação C, declarando e manipulando os dados a partir de structs, structs aninhadas e array de structs.

## Objetivos


## [Modulo 1](#módulo-1)

- Empregar ponteiros com a utilização da linguagem de programação C

## [Modulo 2](#módulo-2)

- Definir estrutura de dados heterogênea

## [Modulo 3](#módulo-3)

- Aplicar structs com a utilização da linguagem de programação C

## [Modulo 4](#módulo-4)

- Empregar as estruturas de dados aninhadas, os vetores de estruturas e a instrução typedef usando a linguagem de programação C


#### Neste tema, iniciaremos pelo emprego dos ponteiros e, a seguir, conceituaremos estruturas heterogêneas, relembrando a definição de estruturas de dados e as diferenças entre as estruturas homogêneas e heterogêneas. 



## Módulo 1

### Definição

Segundo Schildt (1996), ponteiro é uma variável que contém um endereço de memória. Podemos ainda definir o ponteiro como um tipo especial de variável, na qual o valor atribuído é um endereço de memória.

Ou seja, ponteiro ou apontador é uma variável capaz de armazenar um endereço de memória ou o endereço de outra variável.

Para entendermos melhor essa definição, precisamos compreender como a memória de um programa é organizada e o que é um endereço de memória.

### Memória

#### Organização da memória

Memória é um componente do computador responsável pelo armazenamento de dados e instruções. Ela é composta por palavras, sendo cada palavra identificada unicamente a partir de um endereço, ou seja, um endereço de memória.

Cada palavra tem uma capacidade de armazenamento da informação, isto é, uma quantidade de bytes que a palavra representa.

Sendo assim, aprendemos que uma memória é composta por palavras e que toda palavra possui um endereço único, conforme é visto na Tabela 1.


Tabela 1 – Exemplo de endereços de memória

|   Endereço  |  Palavras  |
|-------------|------------|
| 0 (00)      | Palavra 0  |
| 1 (001)     | Palavra 1  |
| 2 (010)     | Palavra 2  |
| 3 (011)     | Palavra 3  |
| 4 (100)     | Palavra 4  |
| 5 (101)     | Palavra 5  |
| 6 (110)     | Palavra 6  |

O endereço de memória de um processo em execução é dividido em vários segmentos lógicos. Destacamos alguns dos mais importantes:

<!-- 
- Text: Contém o código do programa e suas constantes. Este segmento é alocado durante a criação do processo `exec` e permanece do mesmo tamanho durante toda a vida do processo. -->

| Segmento | Descrição |
|----------|-----------|
| Text     | Contém o código do programa e suas constantes. Este segmento é alocado durante a criação do processo `exec` e permanece do mesmo tamanho durante toda a vida do processo. |
| Data     | Este segmento é a memória de trabalho do processo, na qual ficam alocadas as variáveis globais e estáticas. Tem tamanho fixo ao longo da execução do processo. |
| Stack     | Contém a pilha de execução, na qual são armazenados os parâmetros, endereços de retorno e variáveis locais de funções. Pode variar de tamanho durante a execução do processo. |
| Heap     | Contém a pilha de execução, na qual são armazenados os parâmetros, endereços de retorno e variáveis locais de funções. Pode variar de tamanho durante a execução do processo. |

#### Alocação de memória em C

Agora que já sabemos o que é memória e como ela está organizada internamente, vamos entender as três formas de alocação de memória usando a linguagem C.

- Alocação `estática` (geralmente aloca em `DATA`).
- Alocação `automática` (geralmente aloca em `STACK`).
- Alocação `dinâmica` (geralmente aloca em `HEAP`).

##### Alocação estática

Na alocação estática, ocorre a declaração de variáveis globais (alocadas fora de uma função) ou estáticas (alocadas dentro de uma função), usando o modificador “static”. Neste caso, o valor alocado à variável se mantém durante toda a vida do programa, exceto quando explicitamente é modificado.

Exemplo:

```c

#include <stdio.h> 

 	static int a = 0;  // variável global, alocação estática

 	void incrementa(void)
 	{
 		int b = 0; // variável local, alocação automática
 		static int c = 0; // variável local, alocação estática
 
 		printf ("a: %d, b: %d, c: %d\n", a, b, c);
		a++;
 		b++;
 		c++;
 	}

 	int main(void)
 	{
		int i;
		for (i = 0; i < 5; i++)
		incrementa();
 		system("pause");
 		return(0);
	}

```
