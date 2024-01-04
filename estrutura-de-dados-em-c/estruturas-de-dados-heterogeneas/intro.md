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



# Módulo 1

## Definição

Segundo Schildt (1996), ponteiro é uma variável que contém um endereço de memória. Podemos ainda definir o ponteiro como um tipo especial de variável, na qual o valor atribuído é um endereço de memória.

Ou seja, ponteiro ou apontador é uma variável capaz de armazenar um endereço de memória ou o endereço de outra variável.

Para entendermos melhor essa definição, precisamos compreender como a memória de um programa é organizada e o que é um endereço de memória.

## Memória

### Organização da memória

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

### Alocação de memória em C

Agora que já sabemos o que é memória e como ela está organizada internamente, vamos entender as três formas de alocação de memória usando a linguagem C.

- Alocação `estática` (geralmente aloca em `DATA`).
- Alocação `automática` (geralmente aloca em `STACK`).
- Alocação `dinâmica` (geralmente aloca em `HEAP`).

### Alocação estática

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

### Alocação automática

Na alocação automática, ocorre a declaração de variáveis locais e parâmetros de função. Sendo assim, a alocação dessas variáveis é realizada quando a função é invocada e liberada quando a função termina.

Neste caso, o valor da variável “b” não se preserva durante a chamada da função incrementa, isto é, o valor alocado à variável não se mantém durante toda a vida do programa.

### Alocação dinâmica

Na alocação dinâmica, é requisitada explicitamente pelo programa uma área de memória para armazenamento de dados. O controle das áreas alocadas dinamicamente pode ser manual ou semiautomático, desta maneira o programa as utiliza e depois as libera quando não forem mais necessárias ou quando o programa encerrar. A liberação das áreas alocadas dinamicamente é realizada pelo programador. 

A alocação dinâmica manual pode ser realizada de forma simples ou por vetor.

```c
#include < stdlib.h >
void * malloc (size_t size)
```

A função “malloc” aloca um determinado número de bytes na memória e retorna um ponteiro para o primeiro byte alocado. Se não for possível alocar, a função retorna “NULL”.

A liberação é realizada pela função “free”. Esta função libera o espaço alocado, isto é, libera a área de memória previamente alocada dinamicamente.

```c
#include < stdlib.h >
void free (void *ptr)
```

A função “free” libera o número de bytes alocados previamente na memória, apontado por “ptr”. O ponteiro “ptr” continua apontando para a área liberada e por isso é aconselhável mudar seu valor para “NULL” após a liberação.


```c
ptr = malloc (1024);
...
free (ptr);
ptr = NULL; // não é obrigatório, mas aconselhável
```

O redimensionamento da área alocada é realizado pela função “realloc”.

```c
#include < stdlib.h >
void * realloc (void *ptr, size_t newsize)
```

A função “realloc” redimensiona a área previamente alocada, apontada por “ptr”, para o novo tamanho “newsize”. A função retorna o novo endereço da área de memória, que pode ser diferente do anterior, caso tenha sido necessário mudar de lugar.

Em resumo, podemos visualizar cada função com seu objetivo na Tabela 2.

Tabela 2 – Funções de alocação dinâmica

| Função | Ação | Sintaxe |
|--------|------|---------|
| malloc | A função “malloc” aloca um determinado número de bytes na memória e retorna um ponteiro para o primeiro byte alocado. Se não for possível alocar, a função retorna NULL. | void * malloc (size_t size) |
| free |A função “free” libera o número de bytes alocados previamente na memória, apontado por “ptr”. | void free (void *ptr) |
| realloc | A função “realloc” redimensiona a área previamente alocada, apontada por “ptr”, para o novo tamanho “newsize”. | void * realloc (void *ptr, size_t newsize) |

Na alocação por vetor, utilizam-se ponteiros para a alocação.

Sendo assim, basta especificar o tamanho desse vetor no momento da alocação. Após a alocação de uma área com vários elementos, ela pode ser acessada exatamente como se fosse um vetor.

A alocação utiliza a função ''calloc()'' para alocar um bloco de memória de tamanho suficiente para conter um vetor com ''count'' elementos de tamanho ''eltSize'' cada um. 

```c
#include < stdlib.h >
void * calloc (size_t count, size_t eltSize)
```

## Ponteiro

Na linguagem C, cada variável tem um nome, um tipo, um valor e um endereço. Por exemplo, nas variáveis abaixo:

```c
int x = 5;
char c = ’D’;
```

Temos que o nome da variável é “x”, o tipo é inteiro, o valor é 5 e essa variável está armazenada na memória no endereço 10. A variável “x” usa dois bytes de memória e quando um objeto usa mais de um byte, seu endereço é onde ele começa, no caso, 10.

Assim como o nome da outra variável é “c”, o tipo char, o valor “D”, está armazenada no endereço de memória 13 e usa um byte de memória.

Na Figura 3, podemos observar a alocação dos valores das variáveis x e c na memória.

Figura 3 – Alocação de variáveis na memória:

| Variável | Tipo | Valor | Endereço |
|----------|------|-------|----------|
| x | int | 5 | 10 |
| c | char | D | 13 |

Já sabemos que todo dado armazenado em memória possui um endereço e que a definição de um ponteiro é uma variável que guarda o endereço de memória, ou seja, a localização do dado.

Sendo assim, um ponteiro armazena o endereço de outra variável, isto é, uma variável que aponta para outra. 

Ex.:
```mermaid
graph LR
		A[Variável X - Endereço 300]
		C[Ponteiro P - Endereço 320 ] --> A[Variável X - Endereço 300]
```

A figura acima apresenta uma memória que armazena a variável “x” e o ponteiro para a variável “x”. Como o conteúdo do ponteiro é um endereço, a seta indica a relação entre o ponteiro e a variável que ele aponta. 

No exemplo, o valor da variável “x” é 100 e esse dado está armazenado no endereço de memória 300. Como o ponteiro também ocupa espaço, o endereço de memória da variável “x” está armazenado no endereço 320 da memória, que é a posição de memória alocada para o ponteiro.

Uma das características importantes de um ponteiro é que, utilizando ponteiros, podemos realizar o acesso indireto a outras variáveis, isto é, podemos ler ou alterar o conteúdo de uma variável sem utilizar o nome desta variável.


### Declaração

Os ponteiros são declarados pelo símbolo “*” entre o tipo e o nome da variável. A forma geral da declaração é:

```
Tipo_da_variável * Nome_da_Variável;
```

Exemplos:

- int *p;
- float *q;
- char *r;

As variáveis p, q e r são apontadores (ponteiro) para um inteiro, float e caractere, respectivamente.


### Operadores

Vejamos dois tipos de operadores:

- Operador unário “&” ou ponteiro constante ‒ Tem a função de obter o endereço de memória de uma variável.
- Operador unário “*” de indireção ‒ É usado para fazer a deferência

Para entendermos melhor, observe o Exemplo 2. Neste trecho de código, temos a definição de uma variável inteira e de um ponteiro para o tipo de dados inteiro.

```c
int x = 5;
int *pt_x;

/* Ponteiro pt_x recebe o endereço de memória da variável x */
pt_x = &x;
```

O ponteiro “pt_x” recebe o endereço de memória da variável “x” pela instrução: 

```c
pt_x = &x;
```

Agora, o ponteiro pt_x terá armazenado o endereço de memória da variável x. Portanto, manusear o ponteiro pt_x estará manipulando, indiretamente, a variável x.

Para acessar o conteúdo do endereço armazenado no ponteiro, basta utilizar o operador ‘*’ antes do nome do ponteiro.

```c
*pt_x
```

Agora, considere a instrução apresentada abaixo. Note que o valor da variável “x” é alterado pelo ponteiro “pt_x”.

```c
*pt_x = 50;
```

Podemos observar que o conteúdo da variável “x” foi alterado de forma indireta, ou seja, não foi feita referência ao nome da variável “x”. Neste caso, o ponteiro é chamado de ponteiro variável, pois assim é possível armazenar qualquer endereço.


#### Indireção múltipla



