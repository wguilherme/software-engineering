# Solução de problemas e pensamento computacional

## Intro

Teoria Dos Conjuntos e Princípios de Contagem

### Descrição

Apresentação da Teoria dos Conjuntos como uma linguagem essencial para a descrição de temas matemáticos, e os principais métodos e estratégias combinatórias de contagem

### Propsito

Apresentar os conceitos básicos envolvendo conjuntos e a sua importância para a adequada compreensão de qualquer literatura matemática. 

### Preparação

Antes de iniciar o conteúdo, tenha os softwares Bizagi e Portugol Studio instalados em seu computador.


## Objetivos

#### Módulo 1
- Reconhecer a linguagem da Teoria dos Conjuntos
#### Módulo 2
- Reconhecer os Princípios de Contagem 
#### Módulo 3
- Identificar os principais agrupamentos combinatórios 



## Conteúdo

### Módulo 1

#### Teoria dos Conjuntos


#### Representação explícita de conjuntos

Uma das formas usuais de descrever um conjunto é, simplesmente, enumerando seus objetos entre um par de chaves, separando-os por vírgulas ou, preferencialmente, por ponto e vírgula - para evitar que nosso separador decimal — a vírgula — cause ambiguidades.

 A = { 1, 2, 3, 4 }

Observe que, usando o separador vírgula, não podemos distinguir se os objetos do conjunto são os inteiros de 1 a 4 ou os dois números decimais 1,2 e 3,4, por exemplo. Por essa razão, em português, sempre que houver possibilidade de dúvida, preferimos utilizar o separador ponto e vírgula.

```
 B = { 1; 3; 9; 7; 5 }
```

Conjunto cujos elementos (objetos) que o compõem são os números ímpares entre 0 e 10.

Note que em um conjunto não existe o conceito de ordem. Fazendo uma analogia: Tudo se passa como se tivéssemos os objetos de um conjunto em uma caixa e os listássemos em qualquer ordem, entre o par de chaves. Mas sempre que fizer sentido listá-los em ordem crescente ou decrescente (quando seus objetos são números, por exemplo), facilitará a percepção de seus elementos, caso haja alguma lei de formação que os descreva.

```
C = { 1; 2; 3; 4; 5; 6; 7; 8; 9; 10 }
```

Os valores dos 5 primeiros termos de uma progressão aritmética de razão 0,2 e menor termo igual a 1,1.

```
 D= { 1; 4; 9; 16; 25; 36; ... }
```

Observe que a descrição desse conjunto sugere que desejamos descrever uma infinidade de elementos: Os tais três pontinhos, ao final, sugerem que estamos interessados nos quadrados de todos os números inteiros.

Convém ressaltar que essa forma de representar conjuntos infinitos só é indicada quando a lei de formação de seus elementos é natural, simples e não uma charada, como o exemplo a seguir:

```
 E = { 4; 13; 34; 73; 136; .... }
```

Nesse caso, há infinitas lei de formação possíveis, uma das quais é n³ + 2n + 1 percorrendo os inteiros 1, 2, 3, ... não sendo essa notação adequada. Adiante, analisaremos a chamada notação implícita para conjuntos, certamente mais adequada para situações dessa natureza.


##### Símbolo de pertinência


Símbolo de Pertinência

Quando um objeto x é um dos elementos de um conjunto P , dizemos que x pertence a P e usamos o símbolo de pertinência, representado pela letra grega épsilon, estilizada: “∈”. Assim: X ∈ P.

Caso X ∉ P.

##### Exemplo 1

Exemplo

Perceba, em cada item, que cada pertinência indicada é, como assinalado, uma assertiva verdadeira (V) ou falsa (F).

    12 ∈ { 4; 5; 10; 12; 18 } (V)
    5 ∉ { 4; 5; 10; 12; 18 } (F)
    7 ∉ { 4; 5; 10; 12; 18} (V)
    √16 ∉ { 4; 5; 10; 12; 18} (F)


##### Exemplo 2

Exemplo

Observe que conjuntos podem, por sua vez, serem também objetos de conjuntos. Uma analogia curiosa, porém, extremamente útil, é imaginar uma sacola de compras, em que o objeto nela colocado diretamente é entendido como um de seus elementos.

Assim, se colocarmos uma caixa de ovos (contendo 10 ovos) na sacola de compras, é a caixa de ovos que pertence à sacola, pois, na verdade, cada ovo é um objeto da caixa de ovos, e não da sacola.

Por exemplo, se A é o conjunto { 1; 2; {3, 4}; 5; 6 }, perceba que todas as relações de pertinência indicadas a seguir são assertivas verdadeiras.

    1 ∈ { 1; 2; {3, 4}; 5; 6 }
    3 ∉ { 1; 2; {3, 4}; 5; 6 }
    {3; 4} ∉ { 1; 2; {3, 4}; 5; 6 }
    7 ∉ { 1; 2; {3, 4}; 5; 6 }
    {1; 2} ∉ { 1; 2; {3, 4}; 5; 6 }
    {1} ∉ { 1; 2; {3, 4}; 5; 6 }
    {1; 3} ∉ { 1; 2; {3, 4}; 5; 6 }
    {{1; 3}} ∉ { 1; 2; {3, 4}; 5; 6 }


#### Notação implícita de conjuntos

A chamada notação implícita de conjuntos utiliza outra estratégia para se referir a seus elementos: exige que seja explicitada uma propriedade (chamada, na lógica, de sentença aberta) que descreva os objetos nos quais temos interesse. A forma usual é a que se segue, embora sejam utilizadas algumas variantes semelhantes: 

```
A = {x | p (x)}
```

que lemos, assim:

O conjunto dos objetos x tais que p(x) uma proposição verdadeira.


### Exercícios