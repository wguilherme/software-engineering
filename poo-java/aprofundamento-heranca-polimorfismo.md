
## Herança e a instanciação de objeto em Java

A palavra herança não é uma criação do paradigma de programação orientada a objetos (POO). Você deve estar familiarizado com o termo que, na área do Direito, designa a transmissão de bens e valores entre pessoas. Na Biologia, o termo significa a transmissão de características aos descendentes.


### Independentemente da aplicação do seu conceito, a palavra herança tem em comum o entendimento de que envolve legar algo a alguém.

Em OO, herança é, também, a transmissão de características aos descendentes. Visto de outra forma, é a capacidade de uma “entidade” legar a outra seus métodos e atributos. Por legar, devemos entender que os métodos e atributos estarão presentes na classe derivada. Para melhor compreendermos, vamos entender a criação de um objeto em Java.

- Quando definimos uma classe, definimos um mecanismo de criação de objetos.
- Uma classe define um tipo de dado, e cada objeto instanciado pertence ao conjunto formado pelos objetos daquela classe.
- Nesse conjunto, todos os objetos são do tipo da classe que lhes deu origem.




Uma classe possui métodos e atributos. Os métodos modelam o comportamento do objeto e atuam sobre o seu estado, que é definido pelos atributos. Quando um objeto é instanciado, uma área de memória é reservada para acomodar os métodos e os atributos que o objeto deve possuir.

Todos os objetos do mesmo tipo terão os mesmos métodos e atributos, porém cada objeto terá sua própria cópia destes.

Consideremos, a título de ilustração, a definição de classe mostrada no Código 1.

```java
//Pacotes
package com.mycompany.GereEscola;

//Classe
public class Pessoa {
	//Atributos
	protected String nome , nacionalidade , naturalidade;

	//Métodos
	public Pessoa ( String nome , String nacionalidade , String naturalidade ) {
		this.nome = nome;
		this.nacionalidade = nacionalidade;
		this.naturalidade = naturalidade;
	}
	protected void atualizarNome ( String nome ) {
		this.nome = nome;
	}
	protected String recuperarNome ( ) {
		return this.nome;
	}
	protected String recuperarNacionalidade ( ) {
		return this.nacionalidade;
	}
	protected String recuperarNaturalidade ( ) {
		return this.naturalidade;
	}
}
```



Qualquer objeto instanciado a partir dessa classe terá os atributos “nome”, “nacionalidade” e “naturalidade”, além de uma cópia dos métodos mostrados. Na verdade, como “String” é um objeto de tamanho desconhecido em tempo de programação, as variáveis serão referências que vão guardar a localização em memória dos objetos do tipo “String”, quando esses forem criados.

Quando objetos se relacionam por associação, por exemplo, essa relação se dá de maneira horizontal. Normalmente são relações do tipo “contém” ou “possui”. A herança introduz um novo tipo de relacionamento, inserindo a ideia de “é tipo” ou “é um”. Esse relacionamento vertical origina o que se chama de “hierarquia de classes”.


> “Uma hierarquia de classe é um conjunto de classes que guardam entre si uma relação de herança (verticalizada), na qual as classes acima generalizam as classes abaixo ou, por simetria, as classes abaixo especializam as classes acima.”


Vamos analisar a classe derivada mostrada no Código 2.

```java
//Pacotes
package com.mycompany.GereEscola;

//Classe
public class Aluno extends Pessoa {
	public Aluno ( String nome , String nacionalidade , String naturalidade ) {
		super ( nome , nacionalidade , naturalidade );
	}
}
```




A classe “Aluno” estende a classe “Pessoa”, ou seja, “Aluno” é uma subclasse de “Pessoa”, formando assim uma relação hierárquica (“Aluno” deriva de “Pessoa”). Podemos aplicar a ideia introduzida com o conceito de herança para deixar mais claro o que estamos falando: “Aluno” é um tipo de/é uma “Pessoa”. Um objeto do tipo “Aluno” também é do tipo “Pessoa”.

Nesse sentido, como vimos, a classe “Pessoa” lega seus métodos e atributos à classe “Aluno”.

Verificando o Código 2, notamos que a classe “Aluno” não possui métodos e atributos definidos em sua declaração, exceto pelo seu construtor. Logo, ela terá apenas os componentes legados por “Pessoa”. A instanciação de um objeto do tipo “Aluno”, nesse caso, levará à reserva de um espaço de memória para guardar apenas os atributos “nome”, “nacionalidade” e “naturalidade”, e os métodos de “Pessoa” e o construtor de “Aluno”. No nosso exemplo, o objeto seria virtualmente igual a um objeto do tipo “Pessoa”.


> “Esse exemplo, porém, tem apenas um fim didático e busca mostrar na prática, ainda que superficialmente, o mecanismo de herança. Como os tipos do exemplo são praticamente idênticos, nenhuma utilidade prática se obtém – “Aluno” não especializa “Pessoa”.”



Mas aí também atingimos outro fim: mostramos que a versatilidade da herança está na possibilidade de realizarmos especializações e generalizações no modelo a ser implementado. A especialização ocorre quando a classe derivada particulariza comportamentos. Assim, são casos em que as subclasses alteram métodos da superclasse.

No caso do Código 3, a classe “Aluno” definida possui um novo atributo – “matrícula” – que é gerado automaticamente quando o objeto for instanciado. Apesar de esse objeto possuir os métodos e atributos de “Pessoa”, ele agora tem um comportamento particular: na instanciação, além dos atributos definidos em “Pessoa”, ocorre também a definição de “matrícula”.

```java
//Pacotes
package com.mycompany.GereEscola;

//Importações
import java.util.UUID;

//Classe
public class Aluno extends Pessoa {

	//Atributos
	private String matricula;

	//Métodos
	public Aluno ( String nome , String nacionalidade , String naturalidade ) {
	super ( nome , nacionalidade , naturalidade );
	matricula = UUID.randomUUID( ).toString( );
	}
}
```



Vejamos a hierarquia de classes mostrada na imagen a seguir.

Já sabemos que o atributo “identificador” e os métodos que operam sobre ele (“atualizarID” e “recuperarID”) são herdados pelas classes filhas.

Também sabemos que um objeto da classe “Fisica” é também do tipo “Pessoa”.

Mas vale destacar que a relação de herança se propaga indefinidamente, isto é, um objeto da classe “Aluno” também é um objeto das classes “Fisica” e “Pessoa”.


```
_________________________________________
Pessoa
#identificador: string
+atualizarID(identificador: string): void
+recuperarID(): string
_________________________________________
                    |
                    |
____________________|____________________________
                |                               |
              Fisica                         Juridica
                |
|___________________________________
|           |           |          |
Aluno   Empregado   Professor   Diretor

```
Especialização de comportamento. 



A classe “Pessoa” implementa o comportamento mais genérico de todos. Ela possui um atributo de identificação definido como do tipo “String” (assim ele aceita letras, símbolos e números); e métodos que operam sobre esse atributo (veja o Código 4).

As classes “Fisica”, “Juridica” e “Aluno” especializam o método que define o atributo “Identificador”, particularizando-o para suas necessidades específicas, como observamos no Código 5, no Código 6 e no Código 7, que mostram as respectivas implementações.

```java
// Código 4: código parcial da classe "Pessoa" – métodos genéricos.
//Classe
public class Pessoa {
	//...
	private String identificador;
	//...
	protected void atualizarID ( String identificador ) {
		this.identificador = identificador;
	}
	protected String recuperarID ( ) {
		return this.identificador;
	}
	//...
}
```


```java
// Código 5: método "atualizarID" da classe “Fisica”.
protected void atualizarID ( String CPF ) {
	if ( validaCPF ( CPF ) )
		this.identificador = CPF;
	else
		System.out.println ( "ERRO: CPF invalido!" );
}
```

```java
// Código 6: método "atualizarID" da classe “Juridica”.
protected void atualizarID ( String CNPJ ) {
	if ( validaCNPJ ( CNPJ ) )
		this.identificador = CNPJ;
	else
		System.out.println ( "ERRO: CNPJ invalido!" );
}
```

```java
// Código 7: método "atualizarID" da classe "Aluno".
public void atualizarID ( ) {
	if ( this.identificador.isBlank() )
		this.identificador = UUID.randomUUID( ).toString( );
	else
		System.out.println ( "ERRO: Codigo matricula ja existente!" );
}
```

Repare que cada código possui um comportamento específico. Apesar de não exibirmos a implementação do método “validaCPF” e “validaCNPJ”, fica claro que os comportamentos são distintos entre si e entre as demais implementações de “atualizarID”, pois o Cadastro de Pessoas Físicas (CPF) e o Cadastro Nacional de Pessoas Jurídicas (CNPJ) possuem regras de formação diferentes.


### Explorando a hierarquia de herança

O exemplo anterior de especialização de comportamento pode ter despertado em você alguns questionamentos. Nele, “Aluno” está especializando o método “atualizarID”, que é da superclasse “Pessoa”.

Ao mesmo tempo, um objeto “Aluno” também é um tipo de “Fisica”, pois esta classe busca modelar o conceito de “pessoa física” (é razoável esperar que um aluno possua CPF além de seu código de matrícula). Será que essa situação não seria melhor modelada por meio de herança múltipla, com “Aluno” derivando diretamente de “Pessoa” e “Fisica”?

Já falamos que Java não permite herança múltipla e que é possível solucionar tais casos modificando a modelagem. Agora, entenderemos o problema da herança múltipla que faz a Java evitá-la. Para isso, vamos modificar o modelo mostrado na figura “Especialização de comportamento”, criando a classe “ProfessorJuridico”, que modela os professores contratados como pessoa jurídica.



Essa situação é vista na próxima imagem. Nela, as classes “Fisica” e “Juridica” especializam o método “atualizarID” de “Pessoa” e legam sua versão especializada à classe “ProfessorJuridico”.

A questão que surge agora é: quando “atualizarID” for invocado em um objeto do tipo “ProfessorJuridico”, qual das duas versões especializadas será executada?

Essa é uma situação que não pode ser resolvida automaticamente pelo compilador. Por causa dessa ambiguidade, a próxima imagem é também chamada de “Diamante da morte”.


```
_________________________________________
Pessoa
#identificador: string
+atualizarID(identificador: string): void
+recuperarID(): string
_________________________________________
                    |
                    |
____________________|____________________________
                |                               |
              Fisica                         Juridica
                |
          Professor Juridico

```

Linguagens que admitem herança múltipla deixam para o desenvolvedor a solução desse problema.

- Em C++, por exemplo, a desambiguação é feita fazendo-se um cast explícito para o tipo que se quer invocar.
- Entretanto, deixar a cargo do programador é potencializar o risco de erro, o que Java tem como meta evitar.
- ortanto, em Java, tal situação é proibida, obrigando a se criar uma solução de modelagem distinta.

### Herança, subtipos e o princípio da substituição de Liskov

Nas seções anteriores, você compreendeu melhor o mecanismo de herança e como ele afeta os objetos instanciados. Falamos sobre especialização e generalização, mostrando como tais conceitos funcionam dentro de uma hierarquia de classes.

!Atenção!
Se você estava atento, deve ter notado que o método “atualizarID” das classes “Pessoa”, “Fisica” e “Juridica” possui a mesma assinatura. Isso está alinhado ao princípio de Projeto por Contrato (Design by Contract). 




No Projeto por Contrato, os métodos de uma classe definem o contrato que se estabelece com a classe ao consumir os serviços que esta disponibiliza. Assim, para o caso em questão, o contrato “reza” que, para atualizar o campo “identificador” de um objeto, deve-se invocar o método “atualizarID”, passando-lhe um objeto do tipo “String” como parâmetro. E não se deve esperar qualquer retorno do método.

O método “atualizarID” da classe “Aluno” é diferente. Sua assinatura não admite parâmetros, o que altera o contrato estabelecido pela superclasse. Não há erro que seja conceitual ou formal, isto é, trata-se de uma situação perfeitamente válida na linguagem e dentro do paradigma OO, de maneira que “Aluno” é subclasse de “Fisica”. Porém, “Aluno” não define um subtipo de “Pessoa”, apesar de, corriqueiramente, essa distinção não ser considerada.

Rigorosamente falando, subtipo e subclasse são conceitos distintos.

- Uma subclasse é estabelecida quando uma classe é derivada de outra. 
- Um subtipo tem uma restrição adicional. 


Para que uma subclasse seja um subtipo da superclasse, faz-se necessário que todas as propriedades da superclasse sejam válidas na subclasse.

Isso não ocorre para o caso que acabamos de descrever. Nas classes “Pessoa”, “Fisica” e “Juridica”, a propriedade de definição do identificador é a mesma: o campo “identificador” é definido a partir de um objeto “String” fornecido. Na classe “Aluno”, o campo “identificador” é definido automaticamente.


A consequência imediata da mudança de propriedade feita pela classe “Aluno” é a modificação do contrato estabelecido pela superclasse. Com isso, um programador que siga o contrato da superclasse, ao usar a classe “Aluno”, terá problemas pela alteração no comportamento esperado.



Essa situação nos remete ao princípio da substituição de Liskov. Esse princípio foi primeiramente apresentado por Barbara Liskov, em 1987, e faz parte dos chamados princípios SOLID (Single responsibility, Open-closed, Liskov substitution, Interface segregation and Dependency inversion).

Ele pode ser encontrado com diversos enunciados, sempre afirmando a substitutibilidade de um objeto da classe base pela classe derivada, sem prejuízo para o funcionamento do software.

Podemos enunciá-lo da seguinte forma:

- Seja um programa de computador P e os tipos B e D, tal que D deriva de B.
- Se D for subtipo de B, então qualquer que seja o objeto B do tipo B, ele pode ser substituído por um objeto d do tipo D sem prejuízo para P.

Voltando ao exemplo em análise, as classes “Fisica” e “Juridica” estão em conformidade com o contrato da classe “Pessoa”, pois não o modificam, embora possam adicionar outros métodos.

Assim, em todo ponto do programa no qual um objeto de “Pessoa” for usado, objetos de “Fisica” e “Juridica” podem ser aplicados sem quebrar o programa, mas o mesmo não se dá com objetos do tipo “Aluno”.