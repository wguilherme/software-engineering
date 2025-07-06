# Algoritmos e Complexidade — Tema 2

## Descrição
Conceitos de análise de algoritmos, tipos de estruturas de dados homogêneas, heterogêneas e ponteiros, análise da complexidade dos algoritmos, notação O, como avaliar a complexidade dos algoritmos.

## Propósito
Apresentar os conceitos básicos para o entendimento da construção de algoritmos, empregando os tipos de estrutura de dados básicos. Compreender a importância da análise de algoritmos, permitindo a construção de programas com desempenho adequado à necessidade dos usuários. Empregar a notação O e utilizar exemplos práticos para entender a análise de algoritmo.

## Preparação
Antes de iniciar o conteúdo deste tema, tenha em mãos um livro de Matemática do ensino médio que apresente os conceitos de funções matemáticas, como funções lineares, funções quadráticas, exponenciais e logarítmicas.

## Objetivos
- **Módulo 1:** Definir os conceitos básicos para construção de algoritmos
- **Módulo 2:** Definir as estruturas de dados manipuladas pelos algoritmos
- **Módulo 3:** Definir a notação O e suas aplicações práticas
- **Módulo 4:** Empregar a análise da complexidade dos algoritmos

---

# Módulo 1 — Conceitos Básicos para Construção de Algoritmos

## Introdução
Algoritmos são a estrutura básica para a criação de soluções para problemas computacionais. A modularização de algoritmos é a principal forma para diminuir a complexidade desses problemas.

Os módulos ou subprogramas tratam partes menores da complexidade do problema, facilitando a compreensão e futuras manutenções. A modularização também diminui o retrabalho, pois permite que trechos de códigos sejam reutilizados em outros locais no mesmo sistema.

Após a definição de um algoritmo, é necessário otimizá-lo para garantir desempenho adequado, mesmo com o aumento da capacidade computacional dos computadores.

A complexidade dos problemas cresceu tão rápido quanto a capacidade computacional, portanto é fundamental analisar diversos algoritmos para um problema complexo e chegar ao algoritmo mais otimizado.

---

## Conceitos Fundamentais

Segundo Forbellone e Eberspacher (2005):
- Um problema matemático é mais complexo quanto maior a quantidade de variáveis.
- Um problema algorítmico é mais complexo quanto maior a quantidade de situações diferentes a serem tratadas.

A complexidade pode ser reduzida dividindo problemas maiores em menores, tratados por sub-rotinas (técnica top-down).

### Sub-rotinas
Sub-rotinas (ou subprogramas) são blocos de instruções que realizam tarefas específicas, simplificando o entendimento do programa principal e diminuindo a complexidade.

**Objetivos das sub-rotinas:**
- Dividir e estruturar um algoritmo em partes logicamente coerentes
- Facilitar testes em separado
- Aumentar a legibilidade
- Evitar repetição de código
- Permitir criação de bibliotecas reutilizáveis

**Vantagens:**
- Clareza e legibilidade
- Construção independente
- Testes individualizados
- Simplificação da manutenção
- Reaproveitamento de algoritmos

### Decomposição de Problemas
A decomposição é feita com programação estruturada, geralmente usando o método top-down, que divide o problema em refinamentos sucessivos (módulos ou sub-algoritmos).

---

## Declaração de Sub-rotinas

Uma sub-rotina é um bloco com início e fim, identificado por um nome. Pode executar operações como entrada, processamento e saída.

**Sintaxe genérica:**
```pseudo
sub-rotina <nome_da_sub-rotina> [(tipo dos parâmetros : <declarações de parâmetros>)] : <tipo de retorno>
var
  <declaração de variáveis locais>;
início
  comandos que formam o corpo da sub-rotina
  retorne(<valor>); /* ou retorne; ou nada */
fim sub-rotina
```

**Glossário:**
- **tipo de retorno:** Tipo de dado retornado pela sub-rotina
- **parâmetros:** Variáveis recebidas pela sub-rotina
- **variáveis locais:** Declaradas e usadas apenas na sub-rotina
- **corpo da sub-rotina:** Sequência de comandos
- **nome da sub-rotina:** Segue regras de declaração de variáveis

---

## Exemplo: Soma de Dois Números Inteiros
```pseudo
Algoritmo somaInteiros;
var
  n, m: inteiro;
// declaração de sub-rotina
sub-rotina soma(inteiro: a, b): inteiro
  var resultado: inteiro;
  início
    resultado <- a + b;
    retorne resultado;
  fim sub-rotina
início
  n <- 8;
  m <- 4;
  escreva(soma(n, m)); // chamada da sub-rotina (soma)
fim Algoritmo.
```

### Chamada de Sub-rotina
Uma sub-rotina pode ser acionada de qualquer ponto do algoritmo principal ou de outra sub-rotina. O acionamento de uma sub-rotina é conhecido por chamada ou ativação.

Quando ocorre uma chamada, o fluxo de controle é desviado para a sub-rotina, quando ela é ativada no algoritmo principal. Ao terminar a execução dos comandos da sub-rotina, o fluxo de controle retorna ao comando seguinte àquele onde ela foi ativada.

**Exemplo:**
```pseudo
algoritmo()
{
  ...
  <chamada da sub-rotina>
  ...
}
sub-rotina(...)
{
  ...
  retorne(...);
}
```

Pode ocorrer que um algoritmo tenha mais de uma sub-rotina. Desta forma, teremos várias chamadas a partir do programa principal a cada uma das sub-rotinas.

**Exemplo com Duas Sub-rotinas:**
```pseudo
Algoritmo exemplo;
var
  a, b, c: inteiro;
// declaração de sub-rotina 1
sub-rotina soma(inteiro: x, y): inteiro
  var resultado: inteiro;
  início
    resultado <- x + y;
    retorne resultado;
  fim sub-rotina
// declaração de sub-rotina 2
sub-rotina produto(inteiro: x, y): inteiro
  var resultado: inteiro;
  início
    resultado <- x * y;
    retorne resultado;
  fim sub-rotina
início
  a <- 10;
  b <- 5;
  c <- soma(a, b); // chamada da sub-rotina soma
  escreva("Soma: ", c);
  c <- produto(a, b); // chamada da sub-rotina produto
  escreva("Produto: ", c);
fim Algoritmo.
```

### Parametrização de Sub-rotinas
É possível tornar uma sub-rotina mais genérica e reutilizável através da utilização de parâmetros. Parâmetros são os valores que uma sub-rotina pode receber antes de iniciar a sua execução.

**Exemplo: Troca de Valores**
```pseudo
Algoritmo trocaValores;
var
  a, b: inteiro;
// declaração de sub-rotina
sub-rotina troca(inteiro: x, y)
var
  auxiliar: inteiro;
início
  auxiliar <- x;
  x <- y;
  y <- auxiliar;
  escreva("Valor de a: ", x, " Valor de b: ", y);
fim sub-rotina
início
  a <- 10;
  b <- 5;
  troca(a, b); // chamada da sub-rotina
fim Algoritmo.
```

Na passagem de parâmetros por valor, o valor da variável na chamada é copiado para a variável da função. As alterações realizadas dentro da função não são refletidas na variável original.

Se a passagem de parâmetros da sub-rotina troca (inteiro: x, y) fosse por referência, os valores das variáveis teriam sido comutados entre si.

Existem sub-rotinas que podem receber parâmetros e retornar um valor para o programa principal ou ainda sub-rotinas que recebem parâmetros e não retornam nenhum valor para o programa principal.

As primeiras são chamadas de funções enquanto as últimas, além de receberem a denominação de funções, são também chamadas de procedimentos em algumas linguagens de programação.

---

## Verificando o Aprendizado
1. Funções são usadas para criar pequenos pedaços de códigos separados do programa principal. Elas são importantes porque retornam valores, ajudam a fragmentar o código em partes menores - mais fáceis de lidar - e ainda podem ser utilizadas mais de uma vez no mesmo programa, poupando preciosos minutos de programação e inúmeras linhas de código. Na definição de uma função, precisamos escrever suas partes, sendo algumas obrigatórias e outras, facultativas.
```
sub-rotina <nome_da_sub-rotina> [(tipo dos parâmetros : <declarações de parâmetros>)] : <tipo de retorno>
var
   <declaração de variáveis locais>;
início
     comandos que formam o corpo da sub-rotina
 retorne(<valor>); /* ou retorne; ou nada */
Fim sub-rotina
```
Das opções apresentadas abaixo, marque a que apresenta apenas partes obrigatórias de forma que a função execute alguma tarefa, sem levar em consideração os símbolos (chaves, parênteses, parâmetros, dentre outros).
- Tipo de retorno, nome e corpo da função
- Tipo de retorno, parâmetro e corpo da função
- Tipo de retorno, nome e parâmetros
- Tipo de retorno, nome, parâmetros e corpo da função

2. A modularização de algoritmos é importante para organizar melhor o código, facilitar a manutenção, entre outras coisas. Sobre funções e procedimentos, assinale a alternativa correta sobre a modularização:
- O procedimento sempre retorna um valor ao programa.
- A função retorna um valor ao programa.
- As variáveis definidas no escopo de cada função são acessíveis em todo o programa.
- As variáveis locais são declaradas no escopo do programa inteiro.

---

# Módulo 2 — Estruturas de Dados Manipuladas pelos Algoritmos

## Introdução
Os tipos primitivos (inteiro, real, caractere e lógico) não são suficientes para representar todos os tipos de informação, particularmente quando temos mais de uma informação relacionada, por exemplo, uma lista dos nomes dos alunos de uma sala, endereço de alguém, dentre outros. Os tipos primitivos serão utilizados para construir outras estruturas de dados mais complexas, como vetores, matrizes e registros.

A partir de agora, apresentaremos uma técnica de programação que permitirá trabalhar com o agrupamento de várias informações dentro de uma mesma variável. Vale salientar que este agrupamento ocorrerá obedecendo sempre ao mesmo tipo de dado, a menos que se trabalhe com uma estrutura de dados do tipo registro.

---

## Arranjo Unidimensional Homogêneo
O tipo de dado homogêneo recebe diversos outros nomes, tais como: variáveis indexadas, variáveis compostas, variáveis subscritas, arranjos, vetores, tabelas em memória ou arrays.

Os vetores são tipos de dados que são construídos à medida que forem necessários, pois não é sempre que os tipos básicos (real, inteiro, caractere ou lógico) e/ou variáveis simples são suficientes para representar a estrutura de dados utilizada em um programa.

Um vetor é uma variável homogênea que repete um tipo de dado um número específico de vezes. Ou seja, é um arranjo de elementos armazenados na memória principal, um após o outro, todos com o mesmo nome. A ideia é a mesma de uma matriz linha da matemática, isto é, várias colunas e uma linha. Este tipo de estrutura, em particular, é também denominado como arranjo unidimensional.

**Exemplo de vetor de valores inteiros:**
```
Fonte: O Autor
```
Esse é um vetor de 10 elementos, isto é, tem 10 variáveis, todas com o mesmo nome e diferentes por sua posição dentro do arranjo que é indicada por um índice.

Quando se tem somente uma linha, podemos omiti-la e colocar somente a coluna. Em algoritmos, expressamos da seguinte forma:



```
Fonte: O Autor
```

### Declaração
A declaração de um vetor caracteriza-se por ser definida uma única variável dimensionada com um determinado tamanho. A dimensão de um vetor é constituída por constantes inteiras e positivas. Os nomes dados aos vetores seguem as mesmas regras de nomes utilizados em variáveis simples.

```
tipo <nome_do_vetor> [tamanho] ;
```

Uma variável simples somente pode conter um valor por vez. No caso dos vetores, estes poderão armazenar mais de um valor por vez, pois são dimensionados exatamente para este fim. Lembrando que a manipulação dos elementos de um vetor ocorrerá de forma individualizada, pois não é possível efetuar a manipulação de todos os elementos do conjunto ao mesmo tempo.

Tanto a entrada como a saída de dados manipuladas em um vetor são processadas passo a passo, um elemento por vez. Estes processos são executados com o auxílio de estruturas de repetição, um looping.

**Objetivo de Apresentar o Benefício do Emprego de Vetores:**
Vamos imaginar que é necessário criar um algoritmo para calcular a média geral de uma turma de dez alunos. Na implementação abaixo, vamos utilizar um algoritmo sem empregar um vetor.

```pseudo
Algoritmo media_1;
var
  n1, n2, n3, n4, n5, n6, n7, n8, n9, n10, media: real;
Início
  escreva("Entre com a nota do 1º aluno: ");
  ler(n1);
  escreva("Entre com a nota do 2º aluno: ");
  ler(n2);
  escreva("Entre com a nota do 3º aluno: ");
  ler(n3);
  escreva("Entre com a nota do 4º aluno: ");
  ler(n4);
  escreva("Entre com a nota do 5º aluno: ");
  ler(n5);
  escreva("Entre com a nota do 6º aluno: ");
  ler(n6);
  escreva("Entre com a nota do 7º aluno: ");
  ler(n7);
  escreva("Entre com a nota do 8º aluno: ");
  ler(n8);
  escreva("Entre com a nota do 9º aluno: ");
  ler(n9);
  escreva("Entre com a nota do 10º aluno: ");
  ler(n10);
  media ← (n1 + n2 + n3 + n4 + n5 + n6 + n7 + n8 + n9 + n10)/10;
  escreva("A média da turma é: ", media);
Fim.
```

**Comentário:**
Percebe-se que, neste algoritmo, para calcular a média da turma, foi preciso declarar dez variáveis contendo a média de cada aluno.

Com tanta variável, fica difícil a manipulação delas. E se no caso, a média fosse de uma turma de 100 alunos? Vamos reescrever esse algoritmo usando a estrutura de um vetor.

```pseudo
Algoritmo media_2;
var
  notas[10], soma, media : real;
  i: inteiro;
Início
  soma ← 0;
  Para i ← 0 até 9 faça
  início
    escreva("Digite a"’, i+1 , "ª. nota:");
    leia(notas[I]);
    soma ← soma + notas[i];
  fim;
  media ← soma / 10;
  escreva("A média dos alunos é : ", media);
Fim.
```

Observe que agora foi utilizada uma única variável com 10 valores diferentes armazenados e identificados com a ajuda de um índice, tornando o programa menor e mais fácil o seu entendimento.

---

## Registros
A utilização da estrutura de dados registro consiste em trabalhar vários dados de tipos diferentes (campos), em uma mesma estrutura. Por esta razão, este tipo de dado é considerado heterogêneo. Essa múltipla alocação de variáveis é chamada de dados compostos heterogêneos, estruturas ou registros, na qual os elementos de um registro são alocados em posições de memória adjacentes.

Para poder informar o nome de um aluno e de suas quatro notas, isto nos obrigaria a utilizar dois vetores: um para armazenar os nomes dos alunos e o outro para conter as notas (os valores armazenados em ambos são de tipos diferentes).

A utilização dos registros vem facilitar essa representação, conforme a Figura:


```
Fonte: Autor
Figura – Estrutura de um registro. Fonte: O Autor.
```

Essa estrutura do tipo registro é formada pelos campos: nome, 1ª nota, 2ª nota, 3ª nota, 4ª nota, e poderia ser chamado de Aluno. Para selecionar e guardar os dados de um determinado aluno (na memória), seriam necessárias tantas variáveis quantos campos existam no formulário de cadastro. E o tempo para manipular tais dados será muito maior se não se dispuser de uma forma simplificada de serem acessados e manipulados.

### Definição
Os registros são conjuntos de informações relacionadas entre si, que podem ser referenciadas como uma unidade(o Registro) e, normalmente, são conjuntos de informações(campos) de tipos diferentes.

Assim sendo, um registro é uma estrutura de dados composta e heterogênea, ou seja, formada por um conjunto de variáveis(campos) que podem assumir tipos diferentes de dados, inclusive os tipos compostos(vetores, matrizes e registros).

Ao contrário das variáveis já estudadas, uma variável do tipo registro, quando definida, pode ocupar muitas posições da memória principal, que ficam reservadas para o uso.

### Atenção
Logo, ao se definir uma variável do tipo registro, deve-se definir também quais serão as partes componentes desta variável (os campos), por exemplo: nome, idade, sexo, altura, junto ao seu tipo básico.

Um registro poderá ter tantos campos quanto o Analista deseje. Para facilitar, recomenda-se um máximo de 10 campos por registro. Quando forem necessárias estruturas de dados maiores, pode-se utilizar registros previamente definidos dentro de outros registros.

### Declaração
Um registro deve ser declarado da seguinte forma:

```
tipo r = registro
{Descrição dos campos e seus tipos}
fim registro;
r = REG;
```

Tomando como exemplo a proposta de se criar um registro denominado Aluno, será declarado da seguinte forma:

```
tipo r = registro
texto: NOME;
real: NOTA1;
real: NOTA2;
real: NOTA3;
real: NOTA4;
fim registro;
r = ALUNO.
```

Vejamos agora a definição de uma estrutura registro com outra estrutura registro embutida.

```
FUNC

Nome

Endereço

RUA

NRO

CEP

Cidade

Estado

Salario
```

### Atenção
Será declarado da seguinte forma:

```
Tipo r = registro
texto: NOME;
ender: ENDEREÇO;
texto: CIDADE;
texto: ESTADO;
real: SALARIO;
fim registro;
r = FUNC;
```

Observe que o tipo ender ainda não foi definido (não é tipo básico), logo a definição está incompleta. Portanto, devemos definir o tipo ender que está embutido no registro r, da seguinte forma:

```
Tipo ender = registro
texto: RUA;
inteiro: NRO;
inteiro: CEP;
fim registro;
```

---

## Atribuição
As operações realizadas sobre uma variável registro são as mesmas de uma variável comum. A atribuição em registros será feita da seguinte forma, considerando o registro FUNC:

```
FUNC . NOME ← “Joana Curadora”;
FUNC . ENDEREÇO . RUA ← “Avenida das Americas”;
FUNC . ENDEREÇO . NRO← 4200;
FUNC . ENDEREÇO . CEP← 22640102;
FUNC . CIDADE ← “Rio de Janeiro”;
FUNC . ESTADO ← “RJ”;
FUNC . SALARIO ← 1.00;
```

A utilização do ponto ( . ) indica que a variável FUNC possui campos e que NOME é um deles. Desta forma, devemos indicar o nome da variável seguido de um ponto ( . ) e logo após segue-se o nome do campo.

---

## Ponteiros
Ponteiro é um tipo especial de variável para conter o endereço de memória de outra variável. O endereço de memória é a localização de uma outra variável que já foi declarada anteriormente no programa.

Dizemos que uma variável aponta para outra variável quando a primeira contém o endereço de memória ocupado pela segunda. Seu endereço indica em que parte da memória do computador a variável está alocada, mais especificamente, o endereço do primeiro byte ocupado.

Os ponteiros proporcionam um modo de acesso à variável sem referenciá-la diretamente (modo indireto de acesso).

**Exemplo:**
```
Fonte: O Autor
```

Seguem algumas razões para a utilização de ponteiros:

- Fornecem maneiras com as quais as funções podem realmente modificar os argumentos que recebem (passagem por referência).
- Passam matrizes e strings mais convenientemente de uma função para outra (usá-los no lugar de matrizes).
- Manipular os elementos de matrizes mais facilmente, por meio da movimentação de ponteiros, no lugar de índices entre colchetes.
- Criar estruturas de dados complexas, como listas encadeadas e árvores binárias, em que um item deve conter referências a outro.
- Alocar e desalocar memória dinamicamente do sistema.
- Passar para uma função o endereço de outra função.

### Declaração
Quando se declara um ponteiro, deve-se declará-lo com o mesmo tipo (int, char, etc.) do bloco a ser apontado. Por exemplo, se queremos que um ponteiro aponte para uma variável int (bloco de 4 bytes em alguns ambientes), devemos declará-lo como int também.

**Você sabia**
Cada informação é representada por um certo conjunto de bytes, de acordo com as características da arquitetura e do compilador empregados.

Por exemplo, podemos ter em uma determinada arquitetura os seguintes valores para os tipos abaixo:

```
char:1 byte;
int:4 bytes;
float: 4 bytes;
short: 2 bytes;
long: 4 bytes;
double: 8 bytes.
```

Cada um destes conjuntos de bytes, que chamaremos de bloco, tem um nome e um endereço de localização específico na memória.

**Exemplo de Declaração de Ponteiros:**
```c
int *p;
float *ptr1, *ptr2;
```

A primeira instrução declara um ponteiro chamado p que aponta para um inteiro. Este ponteiro aponta para o primeiro endereço de um bloco de quatro bytes.

A segunda instrução declara dois ponteiros (ptr1 e ptr2) do tipo float, que apontará para o primeiro endereço da posição de memória ocupada por cada variável.

---

## Verificando o Aprendizado
1. Analise o trecho de código abaixo e selecione entre as alternativas o que será exibido após a execução.
```pseudo
Algoritmo questão;
var
    a, b, d : inteiro;
    v[4] : inteiro;
inicio
       a <- 3;
        b <- 2;
        v[4] <- {6,7,8,9}; // inicialização do vetor, de forma correta.
        a = (v[2] – v[0]) + a;
        d <- a * v[b]; //o caractere * significa multiplicação
        escreva(“ a saída é: “, d, “ “, v[1], a+2);
fim.
```
- A saída é: 24 75
- A saída é: 40 77
- A saída é: 21 67
- A saída é: 40 75

2. Em relação aos ponteiros nas linguagens de programação, selecione, das opções seguintes, aquela que justifica sua aplicação:
- Flexibilidade de endereçamento e controle do gerenciamento de armazenamento dinâmico.
- Aumento da legibilidade dos programas.
- Facilidade de implementação no gerenciamento dinâmico.
- Dificuldade na implementação de tipos primitivos.

---

# Módulo 3 — Notação O e Suas Aplicações Práticas

## Introdução
Considerando um determinado problema que deve ser resolvido computacionalmente, é necessário criar um algoritmo que precisa ser implementado em um computador como um conjunto de passos para a resolução do problema.

A estratégia para a definição de um algoritmo deve se basear nas seguintes atividades:
- Especificar um algoritmo através das suas propriedades.
- Definir sua arquitetura através das suas estruturas de dados.
- Definir sua complexidade considerando o tempo de execução e espaço ocupado na memória.
- Implementação em uma linguagem de programação.
- Execução de testes caixa-branca para submeter entradas e verificar se as saídas obtidas estão de acordo com as propriedades especificadas de forma que se prove a corretude do algoritmo.

Segundo Moacir (2002), um algoritmo definido para um problema deve possuir as seguintes características:
- Desempenho: Crucial para qualquer software.
- Simplicidade: Menor chance de gerar erros na implementação.
- Clareza: Escrito de forma clara e documentada para facilitar a manutenção.
- Segurança: Deve ser seguro para manipulação de dados.
- Funcionalidades: Implementar as funcionalidades requeridas.
- Modularidade: Permite manutenção e reuso.
- Interface amigável: Importante para a usabilidade dos usuários.

A corretude é uma característica fundamental para algoritmos, segundo Cormen et al. (2002): Um algoritmo é dito correto se, para cada instância de entrada, ele para de executar com a saída correta (ou informa que não há solução para aquela entrada). É desejável que um algoritmo termine e seja correto.

A corretude levanta algumas questões como: o algoritmo é correto, porém pode levar 3 anos para finalizar uma determinada execução. Isto pode levar a uma classe de problemas conhecidos como intratáveis, pois não existe um algoritmo que solucione o problema com demanda de recursos e tempo adequado. Esses problemas são conhecidos como NP-Difícil ou NP-Completo.

---

## Resumindo
Analisando as atividades do desenvolvimento de algoritmos, pode-se chegar à conclusão de que a análise de algoritmos se baseia na avaliação de algoritmos para a resolução de um problema que possua a melhor relação entre o tempo de execução e o espaço em memória utilizado para a execução do algoritmo.

Adicionalmente, a análise de algoritmos se preocupa com a corretude do algoritmo.

### O que é eficiência?
Segundo a Lei de Moore (1965), o poder computacional das máquinas dobra a cada 18 meses. Portanto, a princípio, pode-se considerar que um computador poderia resolver qualquer problema em um espaço de tempo curto. No entanto, os problemas crescem mais rápido que a capacidade computacional existente.

**Exemplo:**
Por exemplo, conforme Enrooth (2020), o Google indexa bilhões de páginas através de seu indexador e esse volume de páginas cresce diariamente. Com o crescente volume, o algoritmo do Google deve conseguir indexar as páginas em um tempo adequado, ou seja, eficiente.

A eficiência pode ser associada aos recursos computacionais da seguinte forma:
- A quantidade de espaço de armazenamento que utiliza.
- A quantidade de tráfego que gera em uma rede de computadores.
- A quantidade de dados que precisam ser movidos do disco ou para o disco.

**Complete a frase**
```
No entanto, para a maior parte dos problemas, a eficiência está relacionada ao 
----------
 de execução em função do 
----------
 da entrada a ser processada. Considerando o exemplo de 
----------
 do Google, o tamanho da entrada é grande e em constante 
----------
. Por esse motivo, de acordo com Enrooth (2020), o algoritmo de indexação do Google é 
----------
 de 350 a 400 vezes em um ano.
```

**Resposta:**
A sequência correta é:

No entanto, para a maior parte dos problemas, a eficiência está relacionada ao tempo de execução em função do tamanho da entrada a ser processada. Considerando o exemplo de indexação do Google, o tamanho da entrada é grande e em constante crescimento. Por esse motivo, de acordo com Enrooth (2020), o algoritmo de indexação do Google é alterado de 350 a 400 vezes em um ano.

De acordo com Toscani e Veloso (2012), nos algoritmos de multiplicação de matrizes, pode-se ver claramente que um algoritmo mais simples pode ser uma escolha ineficiente com o crescimento muito rápido no tempo de execução conforme ocorre o aumento do tamanho do problema.

A tabela 1 mostra o desempenho desses dois algoritmos que calculam o determinante de uma matriz n x n, considerando tempos de operações de um computador real (Toscani e Veloso, 2012).

```
N

Método de Cramer (n!)

Método de Gauss (n3)

2

22
µ
s

50
µ
s

3

102
µ
s

159
µ
s

4

456
µ
s

353
µ
s

5

2,35s

666
µ
s

10

1,19min

4,95s

20

15225 séculos

38,63s

40

5.1033 séculos

0,315min
```

**Complete a frase**
```
Analisando a tabela 1, percebe-se que o Método de Cramer possui um algoritmo mais 
----------
 , porém se torna rapidamente 
----------
 para tamanhos de entrada a partir de 
----------
 (ordem da matriz), enquanto o Método de Gauss se mantém um tempo 
----------
 de resolução para um crescimento até 
----------
 na ordem da matriz.
```

**Resposta:**
A sequência correta é:

Analisando a tabela 1, percebe-se que o Método de Cramer possui um algoritmo mais simples , porém se torna rapidamente inviável para tamanhos de entrada a partir de 20 (ordem da matriz), enquanto o Método de Gauss se mantém um tempo estável de resolução para um crescimento até 40 na ordem da matriz.

Outra motivação para o estudo é que mesmo com toda a evolução tecnológica da capacidade computacional das máquinas, não diminui a importância da análise do algoritmo mais eficiente.

Na tabela 2, é apresentado um algoritmo executando em uma máquina X na coluna 2 e em outra máquina Y com 10 vezes o poder de processamento da máquina:

```
Complexidade de tempo

Tamanho máximo de problema resolvível na máquina lenta

Tamanho máximo de problema resolvível na máquina rápida

log2n

X0

(X0)10

N

X1

10X1

N . log2n

X2

10 X2  (p/ X2 grande)

N2

X3

3,16 X3

N3

X4

2,15 X4

2n

X5

X5  + 3,3

3n

X6

X6  + 2,096
```

**Complete a frase**
```
Analisando a tabela 2, para um problema com complexidade 
----------
, como log2n, a máquina mais 
----------
 quase resolve uma entrada elevada à 
----------
 mais rápido que uma máquina mais 
----------
.

Em valores práticos, enquanto a máquina lenta resolve uma entrada de 
----------
, a máquina mais rápida consegue executar 1010 
----------
 no mesmo tempo.
```

**Resposta:**
A sequência correta é:

Analisando a tabela 2, para um problema com complexidade baixa, como log2n, a máquina mais rápida quase resolve uma entrada elevada à décima potência mais rápido que uma máquina mais lenta.

Em valores práticos, enquanto a máquina lenta resolve uma entrada de 10 elementos, a máquina mais rápida consegue executar 1010 elementos no mesmo tempo.

Para um problema com complexidade polinomial, a máquina mais lenta resolve uma entrada para 10 elementos, a máquina mais rápida consegue executar 3,16 x 10 elementos. O ganho na execução já não está diretamente ligado à capacidade da máquina (10 x mais rápida).

Analisando o caso de um problema com complexidade exponencial, 3n, a máquina mais lenta executa uma entrada de 10 elementos e a máquina mais rápida executa apenas 10 + 2,096 elementos.

A conclusão é que se a escolha do algoritmo for errada, uma máquina 10 vezes mais rápida não consegue ser eficiente proporcionalmente à sua capacidade computacional. Isto demonstra a importância da análise de algoritmos para se encontrar o mais eficiente possível, mesmo com máquinas poderosas computacionalmente.

---

## Análise de Algoritmos
O objetivo principal é ser capaz de, dado um problema, mapeá-lo em uma classe de algoritmos e encontrar a melhor escolha entre os algoritmos, com base em sua eficiência.

Como pode ser feita a análise de um algoritmo para se chegar à conclusão se é eficiente ou não?
**RESPOSTA:**
O cálculo é feito através do número de passos básicos necessários em função do tamanho da entrada que o algoritmo recebe.

Como vimos na seção anterior, o desempenho do algoritmo deve ser desassociado do desempenho da máquina que executará o algoritmo. O foco principal é a redução da análise do número de operações realizadas em função do tamanho de entrada dos elementos.

Um tamanho de entrada geralmente é relativo ao número de elementos da entrada que são processados pelo algoritmo, como, por exemplo, o número de elementos em um arranjo, lista, árvore etc. Em alguns algoritmos, pode ser também o tamanho de um inteiro que é passado por parâmetro.

Os passos básicos se referem às operações primitivas utilizadas pela máquina para realizar uma determinada atividade. As atividades básicas são:
- Operações aritméticas.
- Comparações.
- Atribuições.
- Resolver um ponteiro ou referência.
- Indexação em um arranjo.
- Chamadas e retornos de funções e métodos.

**Exemplo de Algoritmo com 8 Passos Básicos:**
```pseudo
I = 0; achou = F // Passo Básico 1
Repita
  I = i + 1 // Passo Básico 2
  Se tab[i] = ch // Passo Básico 3
  então achou = V // Passo Básico 4
até achou ou i = n // Passo Básico 5
se achou // Passo Básico 6
  então pos = i // fim-se Passo Básico 7
retorne-saida (achou, pos) // Passo Básico 8
fim-procedimento
```

A análise da complexidade de um algoritmo se baseia em dois tipos de complexidade:
- **Espacial:** Representa o espaço de memória usado para executar o algoritmo.
- **Temporal:** Pode ser dividido em dois grupos:
  - Tempo (real) necessário à execução do algoritmo.
  - Número de instruções necessárias à execução.

A análise temporal é a mais utilizada para estudo dos algoritmos.

### Análise Assintótica
Para se realizar a análise assintótica de um algoritmo, deve-se considerar que para um algoritmo com tamanho de entrada n:
- Cada operação (passo básico) leva o mesmo tempo constante.
- A memória da máquina é eficiente.

A eficiência de um algoritmo é representada por uma função f(n) para uma entrada de tamanho n. A eficiência assintótica descreve a eficiência de um algoritmo quando n torna-se grande.

**Exemplo:**
Neste caso, o exemplo de um bot de indexação de páginas é interessante, pois deve-se analisar a complexidade de um algoritmo para indexação de páginas web. Este algoritmo possui um tamanho de entrada de bilhões de elementos. Não faz sentido analisar a complexidade desse algoritmo para um tamanho de entrada de dez elementos.

Para comparar algoritmos, determinamos suas ordens de crescimento (eficiência assintótica). O algoritmo com a menor ordem de crescimento deverá executar mais rápido para tamanhos de entradas maiores.

O resultado da análise assintótica é a geração da complexidade assintótica do algoritmo, que é definida pelo crescimento da complexidade para entradas suficientemente grandes.

O fundamental da análise de algoritmos é a preocupação da análise de valores extremamente grandes, ou seja, tendendo ao infinito. Conforme apresentado, a computação está preocupada com a resolução de problemas com tamanho de entrada grande, que é a realidade atual dos softwares.

Então, um algoritmo assintoticamente mais eficiente é melhor para todas as entradas, exceto para entradas relativamente pequenas. Estas entradas pequenas são desprezadas para a análise de algoritmos. Na figura, é apresentado um exemplo do descarte de entradas pequenas.


```
Fonte: O Autor
Figura – Análise assintótica. Fonte: O Autor.
```

Analisando a figura, qual o algoritmo mais eficiente para a área de análise de algoritmos?
**Resposta 1** 
Por exemplo, considerando a entrada de tamanho 2 elementos, a quantidade de operações realizadas por f(n) = (6) é maior que a quantidade de operações realizadas por g(n) = (4).

**Resposta 2** 
No entanto, considerando a entrada de tamanho 5 elementos, a quantidade de operações realizadas por f(n) = (9) é menor que a quantidade de operações realizadas por g(n) = (25). Portanto, para valores muito grandes (ordem assintótica), f(n) é mais eficiente que g(n).

Em outras palavras, respeitando a análise assintótica, o algoritmo f(n) tem ordem de crescimento menor para tamanhos grandes de entrada n.

---

## Como Realizar uma Comparação Assintótica entre Funções?
Para tornar isto possível, é preciso introduzir uma simplificação do modo de comparar funções.

Essa comparação só leva em conta a “velocidade de crescimento” das funções. Assim, ela despreza fatores multiplicativos (pois a função 2n2, por exemplo, cresce tão rápido quanto 10n2) e despreza valores pequenos do argumento (a função n2 cresce mais rápido que 100n, embora n2 seja menor que 100n quando n é pequeno).


```
autor
```

A análise assintótica de algoritmos gera um conjunto de funções, conforme a figura


```
autor/shutterstock
```

Considerando a forma de comparação assintótica de funções, podemos ordenar as funções, conforme a figura

Considerando a figura, nessa matemática, as funções são classificadas em "ordens" e todas as funções de uma mesma ordem são "equivalentes". Então, por exemplo, 100 n2, 100 + 3 n2, 80 + n2/3 são equivalentes. Todas as funções possuem a ordem n2.

---

## Notação O (Big oh)
Existem formas de se analisar cada função matemática de um algoritmo para se provar que uma função é assintoticamente superior a outra. Desta forma, pode-se definir qual algoritmo é melhor que o outro para se resolver um determinado problema.

Cada algoritmo possui um comportamento para cada entrada de dados e sempre existirá determinado conjunto de dados de entrada em que o algoritmo se comportará da pior forma possível. A pior forma possível, segundo Cormen et al. (2012), indica que o algoritmo realizará um conjunto maior de passos básicos para se chegar ao resultado correto.

Um exemplo prático são os algoritmos ordenação, como, por exemplo, o Quicksort (Cormen et al., 2012). Se for inserido para o algoritmo do Quicksort um conjunto de entrada com os dados quase ordenados, este se comporta da pior forma possível, que, para a área de análise de algoritmos, é chamado do pior caso para o algoritmo.

A notação O é a forma matemática de se prever o pior caso para cada algoritmo para determinada solução de um problema.

### Definição
Dadas as funções assintoticamente não negativas f e g, dizemos que f está na ordem Ο de g e escrevemos f = Ο(g) se f(n) ≤ c · g(n) para algum c positivo e para todo n suficientemente grande.

Em outras palavras, existe um número positivo c e um número n0 tais que f(n) ≤ c · g(n) para todo n maior que n0. (Cormen, 2012).

Podemos dizer que f (n) pertence O(g(n)), mas em geral se escreve f (n) = O(g(n)). Para n suficientemente grande, g(n) é cota superior para f(n) com um fator constante.


```
Fonte: Autor
Figura – Definição Notação O – f(n) = O(g(n)). Fonte: Cormen et al., 2002.
```

Para todos os valores de n à direita de n0, o valor de f (n) reside em c * g(n) ou abaixo desse. Formalmente, a função g(n) é um limitante assintótico superior para f (n).

**Exemplo: 4n2 = O(n3)**

Analisando o exemplo acima, pode-se inferir nessa equação como sendo 4n2 ≤ O(n3).  A taxa de crescimento de 4n2 é menor ou igual à taxa de n3, ou seja, n3 é assintoticamente superior a 4n2.

---

## Exemplos de Funções O
Para todos os exemplos, de acordo com a definição, é preciso encontrar c que seja sempre maior ou igual a n para todo valor de n0. Assim, eu provo que g(n) é limitante superior à função f(n).

**Teoria na Prática**
**Exemplo 1:** Provar que f(n)= n2 é O(n)

**RESOLUÇÃO**
```
n2 ≤ c . n => n ≤ c é impossível, pois c deve ser constante
```

**Conclusão:** Não existe um c multiplicado por g(n) que torne g(n) superior assintoticamente a f(n)

**Exemplo 2:** 3n3 + 20n2 + 5 é O(n3)

**RESOLUÇÃO**
É preciso encontrar c > 0 e n >= 1 tais que 3n3 + 20 n2 + 5 ≤ c . n3 para n ≥ n0 
⇔
 como 3n3 + 20n2 + 5  (3 + 20 + 5)  n3, podemos tomar c = 28 e qualquer n0 > 1

**Conclusão:** Existe um c (28) que multiplicado por g(n)(n3) torna g(n) superior assintoticamente a f(n) a partir de n0 = 1

**Exemplo 3:** 2n+2 é O(2n)

**RESOLUÇÃO**
É preciso c > 0 e n0 > 1 tais que 2n+2 ≤ c * 2n para todo n ≥ n0 note que 2n+2 = 22 . 2n = 4 * 2n ó assim, basta tomar, por exemplo, c = 4 e qualquer n

**Conclusão:** Existe um c (4) que multiplicado por g(n) (n2n) torna g(n) superior assintoticamente a f(n) a partir de n0 = 1

---

## Cota Superior de Problemas
Seja dado um problema, por exemplo, multiplicação de duas matrizes quadradas n x n. Conhecemos um algoritmo para resolver este problema (pelo método trivial) de complexidade O(n3). Sabemos, assim, que a complexidade deste problema não deve superar O(n3), uma vez que existe um algoritmo que o resolve com esta complexidade.

**Exemplo:**
Uma cota superior ou limite superior (upper bound) deste problema é O(n3). A cota superior de um problema pode mudar se alguém descobrir outro algoritmo melhor. Outro exemplo são os problemas de ordenação de dado cuja cota superior do problema é O(n log n). Caso, por exemplo, seja descoberto um algoritmo que resolva em n, o problema mudará sua cota superior, poderá ser alterada O (n).

Resumidamente, o objetivo é se conseguir, através de análise matemática de diversos algoritmos, qual o algoritmo mais eficiente para a resolução do problema.

---

## Verificando o Aprendizado
1. Numa competição de programação, ganhava mais pontos o time que apresentasse o algoritmo mais eficiente para resolver o pior caso de um determinado problema. A complexidade assintótica (notação Big O) dos algoritmos elaborados está ilustrada na tabela abaixo. Escolha a alternativa que indique a colocação dos times na competição:
```
Time

Competição

Branco

O(n20)

Amarelo

O(nlogn)

Azul

O(1)

Verde

O(n!)

Vermelho

O(2n)
```
- Amarelo, Azul, Branco, Vermelho, Verde
- Vermelho, Verde, Branco, Amarelo
- Azul, Amarelo, Vermelho, Branco, Verde
- Azul, Amarelo, Branco, Vermelho, Verde

2. Gere a complexidade pessimista do algoritmo de ordenação abaixo:
```pseudo
Ordena(int vet[], int n){
(1) int i, pos, aux;
(2) para (i = 0;i < n; i++) {
(3) pos = i;
(4) para (j = i + 1;j < n;j++ )
(5) se (vet [pos] > vet [j])
(6) pos = j;
(7) se (pos <> i) {
(8) aux = vet[i];
(9) vet[i] = vet[pos];
(10) vet[pos] = aux;
}
}
}
```
- O(n)
- O(n2)
- O(n3)
- O(nlogn)

---

# Módulo 4 — Análise da Complexidade dos Algoritmos

## Introdução
A análise prática de algoritmos está associada diretamente ao cálculo do desempenho de cada algoritmo definido para a solução de um determinado problema. Esse cálculo irá gerar um big O para cada algoritmo. Desta forma, deverá ser escolhido o algoritmo que gera o menor big O de acordo com a ordenação apresentada na figura.


```
Fonte: Shutterstock
```

Segundo Moacir (2010), algumas premissas importantes podem ser utilizadas para análise prática, como:
- Se f (n) for um polinômio de grau d, então f (n) é O (nd ), devem ser desprezados os termos de menor ordem e desprezados os fatores constantes. Por exemplo, uma função como f(n) = 3 n3+ 2 n2 + 10, seguindo a premissa, transformar-se-á em O(n3).
- Use a menor classe de funções possível, para simplificação. Por exemplo, a função f(n)=2n é O(n), ao invés de 2n ser O(2n).
- Use a expressão mais simples possível, para simplificação. Por exemplo, a função f(n)= 3n + 5 é O(n), ao invés de f(n) = 3n + 5 possuir O(3n).
- Ao comparar dois algoritmos com tempo de execução: f (n) = 10100n, e g(n) = 10n log n. Pela análise assintótica, o primeiro é mais eficiente No entanto, 10100 é o número estimado (por alguns astrônomos) como o limite superior para a quantidade de átomos no universo observável 10n log n > 10100n apenas para n > (210)99

---

## Princípios Básicos
A complexidade do algoritmo é baseada na quantidade de passos básicos executados para o resultado final do algoritmo.

Um algoritmo geralmente tem componentes que são formados por passos básicos que dão suas contribuições para o desempenho e para a complexidade do algoritmo.

Conforme Laira (2010), algumas componentes de um algoritmo são sempre executadas. Outras componentes definem alternativas, que são executadas conforme o caso. Além disso, pode ser conveniente encarar uma componente como a restrição de um algoritmo a certas entradas (fornecidas por outras componentes).

### Componentes Conjuntivas
Uma componente de um algoritmo é dita conjuntiva quando ela é sempre executada em qualquer execução do algoritmo.

Consideremos um algoritmo a com duas componentes conjuntivas f(n) e g(n), o desempenho do algoritmo A sobre a entrada n é dado por O(h(n)) = O(f(n)) + O(g(n)).

Considerando o princípio das componentes conjuntivas, se duas componentes são conjuntivas, deve ser considerada a soma da cota superior entre os dois componentes conforme a fórmula:

```
O
(
h
(
n
)
)
 
=
 
O
(
f
(
n
)
)
 
+
 
O
(
g
(
n
)
)
.
```

Resumidamente, como se trata do big O, complexidade do pior caso, deve ser considerado o pior caso dos dois componentes. Como são sempre executados, deve ser a soma do O das duas componentes.

### Componentes Disjuntivas
Uma componente de um algoritmo é dita disjuntiva quando são executadas dependendo do conjunto entrada de valores do algoritmo. Consideremos um algoritmo

A com duas componentes disjuntivas f(n) e g(n), o desempenho do algoritmo A sobre entrada n é dado por O(h(n)) = max(O(f(n)),O(g(n))).

Considerando o princípio das componentes disjuntivas, se duas componentes são disjuntivas, deve ser considerada a maior cota superior entre os dois componentes conforme a fórmula:

```
O
(
h
(
n
)
)
 
=
 
m
a
x
(
O
(
f
(
n
)
)
,
O
(
g
(
n
)
)
)
.
```

Resumidamente, como se trata do big O, complexidade do pior caso, deve ser considerado o pior caso da execução entre os dois componentes que não são obrigatoriamente executados a cada execução.

### Princípio da Absorção
Se f é absorvida por g, sua soma pontual f + g é O( g ).

O máximo assintótico em ordem, max (f(n), g(n)) de duas funções f e g deve ser sua cota superior - em sentido assintótico - para as ordens de ambas.

**Etapa 1**
Por exemplo, duas componentes disjuntivas f(n) = O(1) e g(n) = O(n),

**Etapa 2**
Que geram a soma de componentes O(1) + O(n).

**Etapa 3**
Pelo princípio da absorção, a complexidade final será O(n), ou seja o max(O(1),O(n)).

Frequentemente, toma-se como máximo assintótico a soma ou o máximo pontual, que foi o caso do exemplo.

---

## Complexidades Pessimistas de Estruturas Algorítmicas
Para realizar a análise do pior caso, ou a chamada complexidade pessimista, algumas regras básicas devem ser consideradas conforme tabela 3:

```
f(n) = O(f(n))

c * O(f(n)) = O(f(n)) , c = constante

O(f(n)) + O(f(n)) = O(f(n))

O(O(f(n)) = O(f(n))

O(f(n)) + O(g(n)) = O(max(f(n),g(n)))

O(f(n))O(g(n)) = O(f(n)g(n))

f(n)O(g(n)) = O(f(n)g(n))
```

### Tabela 3 – Regras da Complexidade de O. Fonte: Barrere, 2020.
A seguir, serão analisadas as complexidades para algumas operações.

**Atribuição:** O tempo de execução é o tempo do comando da atribuição. Se a operação de atribuição for dentro de uma estrutura de repetição, deve ser multiplicada pelo número de vezes que é executada.

**Exemplo 1:** A complexidade da atribuição é O(1)
```
(1) a = a * i (1)
```

**Conclusão:**
Na linha (1) é executada uma vez a atribuição de valores para a, isto gera O(1).

**Exemplo 2:** A complexidade da atribuição neste caso é O(n)
```
(1) VetA[] = VetI[];
```

**Conclusão:**
Na linha (1) é executado O(n) vezes para a atribuição de todos os elementos (i) do VetI para o VetA. Isto gera O(n) passos para essa atribuição.

**Repetições:** O tempo de execução é pelo menos o tempo dos comandos dentro da repetição multiplicada pelo número de vezes que é executada.

**Exemplo 1:** A complexidade da repetição é O(n)
```pseudo
(1) para i de 1 ate n faca (n)
(2)a = a * i (1)
```

**Conclusão:**
Na linha (1) é executado O(n) vezes na linha(2) o tempo do comando interno (1). Isto gera O(n).O(1) para essa repetição número de execuções internas.

**Exemplo 2:** A complexidade da repetição é O(n)
```pseudo
(1) para i de 1 ate n faca (O(n) - repetição)
(2) a = a * i (O(1) - Atribuição)
(3) c = c + a (O(1) - Atribuição)
```

**Conclusão:**
Na linha (1) é executado O(n) vezes o tempo do comando interno de atribuição (2) e o tempo do comando interno de atribuição (3). Isto gera O(n) . O(1) . O(1) que equivale a O(n) repetições da execução interna.

### Repetições Aninhadas
Análise feita de dentro para fora, o tempo total é o tempo de execução dos comandos multiplicado pelo produto do tamanho de todas as repetições internas (aninhadas).

**Exemplo 1:** A complexidade da repetição é O(n2)
```pseudo
(1) para i de 1 ate n faca – O(n)
(2) para j de 0 ate n-1 faca – O(n-1)
(3) a = a*(i+j) – O(1)
```

**Conclusão Resolução:**
Na linha (1) é executado O(n) vezes a estrutura de repetição. Na linha (2) é executada O(n – 1) vezes a estrutura de repetição. Na linha (3) é O(1) a atribuição de atribuição. A complexidade final será a multiplicação da complexidade a linha (3) pela linha (2) e pela linha (1) – de dentro para fora.

**Resolução:**
```
O(O(1).O(n).O(n))
⇔
 O(1.n.n)  
⇔
 O(n2).
```

**Comentário:** Por que O(n – 1) se transforma em O(n)? Devido às regras de análise assintótica, o mais importante é considerar a ordem desprezando os fatores multiplicadores e as constantes. Com isso, O(n -1) possui a ordem n, portanto se simplifica em O(n).

**Exemplo 2:** A complexidade da repetição é O(n3)
```pseudo
(1) para i de 1 ate n faca – O(n)
(2) para j de 0 ate n-1 faca – O(n-1)
(3) para k de 0 ate n-2 faca – O(n-2)
(4) a = a*(i+j) – O(1)
```

**Conclusão Resolução:**
Na linha (1) é executado O(n) vezes a estrutura de repetição. Na linha (2) é executada O(n – 1) vezes a estrutura de repetição. Na linha (3) é executada O(n – 2) vezes a estrutura de repetição. Na linha (4) é O(1) a atribuição de atribuição. A complexidade final será a multiplicação da complexidade a linha (4), pela linha (3), pela linha (2) e pela linha (1) – de dentro para fora.

**Resolução:**
```
O(O(1).O(n).O(n).O(n)) 
⇔
 O(1.n.n.n) 
⇔
 O(n3).
```

**Comentário:** Por que O(n – 2) se transforma em O(n)? Devido às regras de análise assintótica, o mais importante é considerar a ordem desprezando os fatores multiplicadores e as constantes. Desta forma, O(n-2) possui a ordem n, portanto se simplifica em O(n).

---

## Condições
A complexidade nunca é maior do que o tempo do teste mais o tempo do maior entre os comandos dentro do bloco do “então” e do “senão”. A complexidade gera a seguinte fórmula: O(O(condicional) + max (O(então), O(senão))

**Exemplo 1:** A complexidade da condição é O(1)
```pseudo
(1) se (a < b) então - O(1)
(2) a = a + 1 - O(1)
```

**Detalhamento: Solução**
Na linha (1) é executada a comparação com complexidade constante O(1). A linha (2) é executada somente caso a condição na linha (1) seja verdadeira. Se for executada, possui complexidade constante O(1) por ser um comando de atribuição.

**Resolução:**
```
O(O(condicional) + max (O(então), O(senão)) 
⇔
 O(O(condicional) + O(então)) 
⇔
 O( O(1) + (O(1)) 
⇔
 O(1)
```

**Exemplo 2:** A complexidade da condição é O(n)
```pseudo
(3) se (a < b) então - O(1)
(4) a = a + 1 - O(1)
(5) senao
(6) para i de 1 ate n-1 faca - O(n - 1)
(7) a = a*i - O(1)
```

**Detalhamento Resolução:**
Detalhamento:
Na linha (1) é executada a comparação com complexidade constante O(1). A linha (2) é executada somente caso a condição na linha (1) seja verdadeira. Se for executada, possui complexidade constante O(1) por ser um comando de atribuição. A linha (4) é executada somente caso a condição na linha (1) seja falsa. A linha (4) possui complexidade O(n - 1) por ser uma repetição de n – 1 passos básicos. A linha (5) possui complexidade constante O(1) por ser um comando de atribuição.

Resolução:
```
O(O(condicional) + max (O(então), O(senão)) 
⇔
 O(senão) = O(n). O(1) 
⇔
 O(senão) = O(n) 
⇔
 O( O(1) + max(O(1),O(n)) –
⇔
 O(O(1) + O(n)) 
⇔
 O(n)
```

**Comentários:**
1 - Por que o max(O(1), O(n)) resultou em O(n)? Esse é um caso de componentes disjuntivas, conforme visto em Princípio da absorção . Como está sendo tratado sempre o pior caso, precisa-se obter o pior caso entre o “então” e o “senão”, no caso é O(n).

2 – Por que O(O(1) + O(n)) resultou em O(n)? Pelo princípio da absorção apresentado em Componentes disjuntivas, o O(1) pode ser absorvida pelo O(n) pela maior ordem.

---

## Repetições Indefinidas
A complexidade nunca é maior do que o tempo do teste da condição multiplicado pelo número máximo possível de execução da iteração e pela complexidade de cada iteração A complexidade gera a seguinte fórmula: O(O(condicionalrepetição) + O(O(númerorepeticoes).O(comandosrepeticao)))

**Exemplo 1:** A complexidade da repetição é O(n)
```pseudo
(1) enqto a < n faça - O(1) comparação e O(n) da repetição
(2) a = a*(i+j) – O(1)
```

**Detalhamento Resolução:**
Detalhamento:
Na linha (1) é executada a comparação da repetição como valor constante O(1) e O(n) vezes o máximo de execução da estrutura de repetição. Na linha (2) é executada a atribuição com valor constante O(1).

Resolução
```
O(O(1) + O(O(n).O(1))) 
⇔
 O(1 + O(n)) 
⇔
 O(1 + n) 
⇔
 O(n)
```

---

## Chamadas às Sub-rotinas
A sub-rotina deve ser analisada primeiro e depois ter suas unidades de tempo incorporadas ao programa que a chamou.

**Exemplo 1:** A complexidade da chamada é O(n)
```pseudo
(1) a = a + 1 - O(1)
Soma (a,b) - O(n)
```

**Detalhamento Resolução:**
Detalhamento
Na linha (1) é executada a atribuição com complexidade constante O(1). Na linha (2) é executada a chamada da sub-rotina Soma(a,b) com complexidade O(n).

Resolução
```
O(O(linha1) + O(Soma(a,b)) 
⇔
 O(O(1) + (O(n)) 
⇔
 O(n)
```

---

## Exemplo de Cálculo de Complexidades
A partir das regras definidas para cada estrutura algorítmica da Complexidades pessimistas de estruturas algorítmicas, serão apresentados diversos exemplos práticos para o cálculo do O para a complexidade de pior caso dos algoritmos.

**Exemplo Função MinMax:**
Veja esse algoritmo para o cálculo dos valores mínimo e máximo de um vetor, foi adaptado de Laira, 2013.
```pseudo
Funcão MinMax(tabela : Inteiros)
(1) p = 0
(2) min = tabela [p]
(3) max = tabela [p]
(4) para i de p + 1 até q faça
(5) se tabela[ i ] > max
(6) então max = tabela[ i ]
(7) se tabela[ i ] < min
(8) então min = tabela[ i ]
(9) fim-para
(10) retorne MinMax(min,max)
```

**O ideal é dividir por componentes do algoritmo para se obter o valor da complexidade.**
```
O(O(linha1), O(linha2), O(linha3) = O(1) + O (1) + O (1) 
⇔
 O (1 + 1 + 1) 
⇔
 O(3) 
⇔
 O(1)
O(linha5) + O(linha6) = O(1) + O(1) 
⇔
O(2) 
⇔
 O(1)
O(linha7) + O(linha8) = O(1) + O(1) 
⇔
O(2) 
⇔
 O(1)
O(para linha4 … linha8) = O( q - p) . O(linha5...linha8) 
⇔
 O (q – p) equivale a O(n) pois são n passos da iteração 
⇔
 O(n).O(1) 
⇔
 O(n)
O(linha10) = O(1)
O(minxmax) = O(para linha1...linha3) + O(para linha4 … linha8) + O(linha10) 
⇔
 O(1) + O(n) + O(1) 
⇔
O(1+n+1) 
⇔
 O(n+ 2) 
⇔
 O(n)
```

**Exemplo de Operação com Matrizes:**
```pseudo
Procedimento OperacaoMatriz()
(1)i, j: inteiro
(2)A: vetor inteiro de n posicoes
(3)i = 1
(4)enquanto (i < n) faca
(5)A[i] = 0
(6)i = i + 1
(7)para i = 1 ate n faca
(8)para j = 1 ate n faca
(9)A[i] = A[i] + (i*j)
(10)fim
```

**Cálculo da Complexidade:**
```
O(linha3) = O(1)
O(para linha4...linha6) – O(linha4) . (O(linha5) + O(linha6)) 
⇔
 O(linha4) = O(n) 
⇔
 O(linha5) + O(linha6) 
⇔
 O(1) + O(1) 
⇔
 O(1) 
⇔
 O(n).
O(1) 
⇔
 O(n)
O(para linha7...linha9) – O(linha7) . O(linha8) . O(linha9) 
⇔
 O(linha7) = O(n)  O(linha8) = O(n) 
⇔
 O(linha9) = O(1) 
⇔
 O(n) . O(n) . O(1) 
⇔
 O(n.n.1) 
⇔
 O(n2)
O(operacaomatriz) = O(linha3) + O(para linha4...linha6) + O(para linha7...linha9) 
⇔
 O(1) + O(n) + O(n2) 
⇔
O(1 + n + n2) 
⇔
 Considerando apenas a variável com maior ordem, o resultado é O(n2).
```

---

## Funções Importantes na Complexidade
Após a análise do algoritmo, é importante entender as complexidades obtidas para se buscar algoritmos mais otimizados para o problema. Sempre considerar n como o tamanho das entradas.

- **Constante:** O(1)
  - O algoritmo, independentemente do tamanho de n, operações executadas um número fixo de vezes.
- **Logarítmica:** O(logb N)
  - Essa complexidade, segundo Cormen (2012), é típica de algoritmos que resolvem um problema transformando-o em problemas menores (dividir para conquistar). Para dobrar log2 n é preciso fazer log2 n2. A base também muda pouco os valores: log2 n = 20 e log10 n =  6 para n = 1.000.000.
- **Linear:** O(n)
  - Algoritmos com essa complexidade, em geral, executam uma certa quantidade de operações sobre cada um dos elementos de entrada. A melhor situação para quando é preciso processar n elementos de entrada e obter n elementos de saída.
- **Log Linear (ou n-log-n):** n.logb N
  - Essa complexidade é comum em algoritmos que resolvem um problema transformando-o em problemas menores, resolvem cada um de forma independente e depois juntam as soluções.
- **Quadrática:** O(N2)
  - Essa complexidade ocorre frequentemente quando os dados são processados aos pares, com laços de repetição aninhados. Sempre que n dobra, o tempo de execução é multiplicado por 4. Esses algoritmos podem ser úteis para resolver problemas de tamanho relativamente pequeno.
- **Cúbica:** O(N3)
  - Ocorre em multiplicações de matrizes, com três estruturas de repetição aninhadas. Sempre que n dobra, o tempo de execução é multiplicado por 8. Podem ser úteis para resolver problemas de tamanho relativamente pequeno (ou quando não se tem outra opção!).
- **Exponencial:** O(An)
  - Essa complexidade geralmente ocorre quando se usa um algoritmo como uma solução de força bruta. Para o caso 2n, sempre que n dobra, o tempo de execução é elevado ao quadrado. Esses algoritmos não têm utilidade do ponto de vista prático.
- **Fatorial:** O(N!)
  - Normalmente, é apresentado como complexidade exponencial, apesar de o fatorial ter comportamento muito pior. Geralmente, ocorre quando se usa uma solução de força bruta. Para n = 20, o fatorial de n! é igual 2.41018, para o dobro n = 40, o fatorial de n! é igual  8.21047. Definitivamente, não são úteis do ponto de vista prático.

---

## Verificando o Aprendizado
1. Numa competição de programação, ganhava mais pontos o time que apresentasse o algoritmo mais eficiente para resolver o pior caso de um determinado problema. A complexidade assintótica (notação Big O) dos algoritmos elaborados está ilustrada na tabela abaixo. Escolha a alternativa que indique a colocação dos times na competição:
```
Time

Competição

Branco

O(n20)

Amarelo

O(nlogn)

Azul

O(1)

Verde

O(n!)

Vermelho

O(2n)
```
- Amarelo, Azul, Branco, Vermelho, Verde
- Vermelho, Verde, Branco, Amarelo
- Azul, Amarelo, Vermelho, Branco, Verde
- Azul, Amarelo, Branco, Vermelho, Verde

2. Gere a complexidade pessimista do algoritmo de ordenação abaixo:
```pseudo
Ordena(int vet[], int n){
(1) int i, pos, aux;
(2) para (i = 0;i < n; i++) {
(3) pos = i;
(4) para (j = i + 1;j < n;j++ )
(5) se (vet [pos] > vet [j])
(6) pos = j;
(7) se (pos <> i) {
(8) aux = vet[i];
(9) vet[i] = vet[pos];
(10) vet[pos] = aux;
}
}
}
```
- O(n)
- O(n2)
- O(n3)
- O(nlogn)

---

# Conclusão
## Considerações Finais
Os algoritmos são considerados a estrutura base para o aprendizado do desenvolvimento de software. Um bom desenvolvedor conhece bem algoritmos e pode traduzir para qualquer linguagem de programação.

As estruturas de dados apresentadas são importantes para resolver uma grande parte de problemas reais, além de terem fortes aplicações para a resolução de problemas matemáticos. São estruturas de fácil aprendizado e de implementação, tornando-se uma ferramenta poderosa para a solução de problemas computacionais.

A análise de algoritmos é uma área largamente utilizada para o apoio a soluções de problemas computacionalmente complexos, como escolha da melhor rota entre diversos pontos, menor caminho entre dois pontos em um mapa, busca de soluções para equações, ordenação de grandes conjuntos de elementos, entre outros.

A partir da análise de algoritmos, pode-se chegar, em um tempo adequado, à solução ótima para o problema, considerando parâmetros como tempo e espaço de memória consumidos. Importante ressaltar que a análise de algoritmos objetiva estudar a solução de um problema para quantidade muita alta de elementos de entrada. Como, por exemplo, um algoritmo para escolher a melhor rota para um ônibus, considerando dez bairros com mais de trinta ruas em cada bairro de uma metrópole.

---

## Avaliação do Tema:
- [ ] Muito bom
- [ ] Bom
- [ ] Regular
- [ ] Ruim

## Referências
Ascencio, A. F. G.; Campos, E. A. V. de. Fundamentos da Programação de Computadores: Algoritmos, Pascal, C, C++. 3. ed. São Paulo: Pearson, 2012.

Barrere, E. Análise e Projeto de Algoritmos, Notas de Aula. In: UFJF. Consultado em meio eletrônico em: 24 set. 2020.

Cormen, T. H. et al. Algoritmos: Teoria e Prática. 3. ed. São Paulo: LTC, 2017, cap. 1 ‒ 3.

Enrooth, E. How often does Google update search results?. In: HDWebPros. Consultado em meio eletrônico em: 24 set. 2020.

Feofiloff, P. Análise de Algoritmos. In: IME. Consultado em meio eletrônico em: 24 set. 2020.

Forbellone, A. L; Eberspacher, H. Lógica de Programação: A construção de Algoritmos e Estruturas de Dados. 3. ed. São Paulo: Pearson, 2005.

Manzano, J. A. N. G.; Oliveira, J. F. de. Algoritmos – Lógica para Desenvolvimento de Programação de Computadores. 28. ed. São Paulo: Érica, 2016.

Ponti, M. Análise de Algoritmos, Notas de Aula. In: ICMC.USP. Consultado em meio eletrônico em: 24 set. 2020.

QCONCURSOS. Questões de Concursos. In: QConcursos. Consultado em meio eletrônico em: 24 set. 2020.

Toscani, L.; Veloso, P. et al. Complexidade de Algoritmos. (Coleção Livros Didáticos UFRGS, v. 13). 3. ed. São Paulo: Bookman, 2012, cap. 1 ‒ 3.

---

## Explore+
Para saber mais sobre os assuntos tratados neste tema, leia:
- Sobre algoritmos aplicados a uma linguagem de programação, Projeto de Algoritmos com Implementações em Java e C++, na página DCC.UFMG.
- Sobre o cálculo de complexidade dos algoritmos, listas de exercícios dos livros Algoritmos: Teoria e Prática, de Cormen et al.  e Complexidade de Algoritmos, de Toscani e Veloso.
- Sobre pior caso, melhor caso e caso médio, os livros de Cormen et al.  e Toscani e Veloso utilizados neste tema.

---

## Conteudista
**Marcelo Nascimento Costa**

[Currículo Lattes](http://lattes.cnpq.br/)
