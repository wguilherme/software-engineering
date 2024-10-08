## APRESENTAÇÃO

A modelagem de sistemas orientados a objetos possibilita a representação dos requisitos e das soluções de análise e projeto de sistemas de qualquer porte e finalidade. A linguagem de modelagem unificada (UML) é a ferramenta utilizada para criar modelos, na forma de diagramas padronizados, que auxiliam a equipe de desenvolvimento a compreender o que o sistema deve fazer em um primeiro momento e como o sistema deve fazer em um momento posterior.


# Objetivos

## Módulo 1
Modelos na exposição de requisitos e soluções sistêmicas

## Módulo 2
Conceitos e pilares de análise e projeto orientados a objetos

## Módulo 3
Linguagem unificada de modelagem (UML)



# Módulo 1

## Utilizando modelos

O entendimento teórico sobre o conceito de modelos e sua aplicabilidade é fundamental em diversas disciplinas. Os modelos são representações simplificadas da realidade, permitindo aos pesquisadores e profissionais analisarem, entenderem e preverem o comportamento de sistemas complexos. Eles servem como ferramentas poderosas para explorar cenários, testar hipóteses e tomar decisões embasadas. Ao compreender a natureza e a função dos modelos, os indivíduos podem empregar essas ferramentas de forma mais eficaz, contribuindo para o avanço do conhecimento em campos tão diversos quanto a ciência, a engenharia, a economia e a medicina.

### O que são modelos e para que eles servem

Uma família decide adquirir um imóvel na planta para moradia. Eles vão a um lançamento imobiliário a convite de um corretor conhecido. Ao chegarem, encontram um terreno vazio e um stand de vendas. Imediatamente surge a dúvida: como escolher o bloco e o apartamento de forma a garantir privacidade, considerando a vizinhança?

O corretor inicia seu trabalho e leva a todos para conhecerem a maquete do empreendimento − que nada mais é do que a representação do empreendimento em bloco único − e a infraestrutura do parque aquático.

A maquete é simplesmente uma representação em miniatura do condomínio real, ou seja, um modelo do empreendimento real. O empreendimento real será construído à imagem e semelhança da maquete. Assim, podemos estabelecer a primeira finalidade de um modelo: antecipar a existência de uma realidade para avaliar sua estrutura e comportamento.

No exemplo a seguir, encontramos maquetes de um empreendimento imobiliário, mostrando a perspectiva externa, dando a visão clara da vizinhança, do posicionamento do imóvel, da piscina e área de lazer e da entrada.

Analisando a maquete e o posicionamento do empreendimento no terreno, os integrantes da família verificam o bloco e a posição do imóvel que mais lhes interessam, avaliando a vizinhança e respectivas distâncias entre eles.

A família seleciona três unidades e pergunta sobre a disposição dos cômodos. O corretor, então, apresenta a planta baixa de cada unidade selecionada. Veja!

Em seguida, eles se sentam à mesa com o corretor para escolher a unidade no bloco selecionado. O corretor então apresenta a tabela de preços de cada unidade do bloco selecionado, informando a metragem, o valor da unidade e as condições de pagamento.

A planta ilustrativa da unidade é um segundo exemplo de modelo usado no mercado imobiliário, que possibilita ao comprador avaliar o posicionamento e a dimensão de cada cômodo.

A família decide-se pelo imóvel, fecha o negócio e recebe um pen drive contendo outras plantas da unidade: elétrica, hidráulica, dentre outras. Cada uma dessas plantas representa um modelo sob uma diferente perspectiva.

Outro exemplo de modelo muito comum atualmente são os protótipos, usados para aumentar a chance de sucesso dos produtos. A partir de um protótipo inicial, outros modelos podem ser demandados e aprimoramentos podem ser desenvolvidos. Os setores automobilístico e o de desenvolvimento de sistemas usam com eficácia protótipos como modelos.

Um modelo é uma representação abstrata e simplificada da realidade, que pode variar conforme a perspectiva de observação. A principal finalidade de um modelo é antecipar a existência de uma realidade específica, permitindo avaliar sua estrutura e comportamento de maneira eficaz. Portanto, diferentes realidades podem exigir a criação de múltiplos modelos para atender às diversas necessidades de análise e compreensão.

### Modelos se aplicam ao contexto de desenvolvimento de sistemas?

Na construção ou desenvolvimento de sistemas computacionais, assim como na construção imobiliária, há uma gradação da complexidade no processo de construção, que depende de alguns fatores, sendo o tamanho (do sistema ou do empreendimento) um deles.

Os modelos, além da finalidade inicial, funcionam também como instrumento de gerenciamento da complexidade, considerando a limitação humana em lidar com ela. Os sistemas grandes e complexos carecem de ser modelados para sua melhor compreensão em sua totalidade.

> Modelos são capazes de revelar as propriedades essenciais de um sistema, ajudando no processo de abstração (concentração nos pontos de interesse) e permitindo que foquem o que é relevante.


Entre os benefícios do uso de modelos no desenvolvimento de sistemas computacionais, além de prever o comportamento do sistema e gerenciar sua complexidade, destacam-se estes aqui. Veja!

- Comunicação entre as pessoas envolvidas
  - O modelo serve como elemento de comunicação ou difusão de informações entre as pessoas envolvidas em sua construção.
- Redução nos custos do desenvolvimento
  - A construção de modelos é bem mais barata que a construção do sistema em si. A descoberta de erros e falhas em modelos é bem menos onerosa e contribui para a redução dos custos finais do sistema computacional. Isso também vale para as eventuais necessidades de ajustes e melhorias no sistema.
- Facilidade para alterações do sistema
  - A análise de melhorias, seja na fase de construção ou de manutenção, tende a ser mais efetiva quando elaborada sobre os modelos construídos, aumentando a assertividade e diminuindo seus custos. Daí a relevância e a necessidade de manter os modelos sempre atualizados.
- Documentação do sistema
  - Os modelos servem de consulta e orientação a toda a equipe na construção e na manutenção do sistema, incluindo pessoas que sejam integradas após o início do desenvolvimento do sistema. Servem ainda para documentar as decisões tomadas.
- Delimitação do escopo do sistema
  - A modelagem ajuda na delimitação do escopo, ou seja, abrangência do sistema, definindo o que será ou não tratado pelo sistema.

Agora, vamos conhecer mais a seguir sobre modelagem. Acompanhe!


### Modelagem de sistemas

Assim como exemplificamos no mercado imobiliário, no contexto de desenvolvimento de sistemas computacionais podem ser usados diferentes modelos de um mesmo sistema, em que cada um apresenta uma perspectiva (uma visão).

Por exemplo, um sistema armazena e manipula dados por meio de funcionalidades e possui determinados controles. Podemos, então, considerar três diferentes perspectivas e construir modelos que representem cada uma delas, tais como:


- Os dados
- As funcionalidades
- Os controles

Outra perspectiva seria a visão externa, a de um usuário, que enxerga as funcionalidades necessárias, mas desconhece o que ocorre internamente. Essa seria mais uma perspectiva e mais um modelo que ajudaria nessa compreensão.

Confira algumas formas de abordar os sistemas computacionais por meio de visões.

**Externa**
Modela-se o ambiente em que o sistema está inserido, mostrando sua relação com os usuários e demais sistemas com que interage.

**Comportamental**
Modela-se o comportamento dinâmico do sistema e como ele reage aos eventos que o afetam.

**Estrutural**
Modela-se sua estrutura organizacional ou os dados que o sistema processa.

**Interacional**
Modela-se as interações de seus componentes ou ainda do sistema e seu ambiente externo.

A construção dos diferentes modelos para um sistema compreende o que denominamos modelagem de sistemas, em que:

- Os modelos são abstratos, deixando de lado os detalhes e concentrando-se nos aspectos de interesse que são relevantes. A esse processo chamamos de abstração.
- Cada modelo apresenta o sistema sob uma diferente visão ou perspectiva da realidade.
- Os modelos são descritos em notações gráficas, que denominamos diagramas.

Com base no que acabamos de estudar, observe!

> Modelagem de sistema de software consiste na utilização de notações gráficas e textuais com o objetivo de construir modelos que representam as partes essenciais de um sistema, considerando-se várias perspectivas diferentes e complementares.   (Bezerra, 2015)


Como veremos mais adiante, a UML é uma linguagem unificada de modelagem que permite a construção de um conjunto de modelos, na forma de diagramas, sob diferentes visões ou perspectivas que, em conjunto, integram a solução de modelagem do sistema quando desenvolvido usando o paradigma orientado a objetos.



# Módulo 2

## Desenvolvimento de sistemas computacionais

Conhecer a teoria do desenvolvimento de sistemas computacionais é fundamental para a revolução digital contemporânea. Ao entender os princípios fundamentais da criação de software, os profissionais são capacitados a projetar, implementar e otimizar sistemas computacionais complexos e eficientes.

Nesse contexto, o processo de desenvolvimento de sistemas em fases é uma abordagem estruturada para criar software. Começa com a análise dos requisitos do sistema, na qual as necessidades dos usuários são identificadas e documentadas. Em seguida, vem a fase de projeto, em que a arquitetura do sistema é planejada e as especificações técnicas são elaboradas. Após o projeto, entra-se na fase de implementação, quando o código é escrito e o sistema começa a ganhar vida. Finalmente, ocorre a fase de teste, na qual o software é submetido a uma série de testes para garantir sua funcionalidade e qualidade antes da implantação.


- ### Processo de desenvolvimento: Novas features ou refactoring
	- Análise de requisitos do sistema
		- Necessidades do usuário
			- Identificar e documentar
	- Refinamento (Análise)
		- Estrutura para atender os requisitos
	- Planejamento da arquitetura
		- Arquiteutra detalhada
			- Define a estrutura do software
			- incluindo componentes, módulos, interfaces e algorítmos
			- Padrões de design
			- escolha de tecnologia
			- Elaboração de diagramas que representam visualmente a organização e o funcionamento do sistema
	- Implementação feature
		- Codificação do que foi definido anteriormente
		- Implementação de bibliotecas, frameworks externos e aspectos de otimização
	- Implementação testes
		- Unidade,
		- Integração (harmonia)
		- Sistema (comportamento do software)
		- Teste de Aceitação para verificar se o software cumpre as expectativas dos usuários finais
	- Fase de testes e polimento
	- Submeter à um ambiente não produtivo
	- Release (Implantação)
		- Configuração ambiente
		- Testes finais
		- Treinamento usuário
		- Divulgação
		- Manutenção
			- Correção de bugs
			- Melhorias
			- Segurança
			- Patches de vulnerabilidades, etc...
			- Testes regulares para garantir se nada foi afetado
	- Changelog
  

### O processo de desenvolvimento de sistemas em fases

O desenvolvimento de sistemas computacionais é um processo que envolve pessoas e a necessidade de compreensão de uma realidade muitas vezes complexa e obscura, principalmente no início do desenvolvimento, quando o nível de abstração é alto e pouco se conhece da realidade. Podemos visualizar isso na imagem a seguir.

Conforme as fases em que o processo de desenvolvimento é particionado se sucedem, o conhecimento sobre o sistema aumenta, diminuindo, consequentemente, o nível de abstração da realidade. Essa complexidade aumenta à medida que o tamanho do sistema cresce, requerendo um maior planejamento dos recursos a serem usados. O principal recurso no desenvolvimento de um sistema são pessoas, profissionais capacitados.

Primeiramente, precisamos entender as necessidades das pessoas que utilizarão o sistema e o que elas precisam que o sistema faça para desempenharem suas funções. Esse entendimento também requer que os profissionais responsáveis pela construção do sistema confirmem essa compreensão.


#### Mas como entender e confirmar a compreensão em uma linguagem ambígua como a nossa, tanto a falada como a escrita?

**Resposta**

Se criarmos o sistema diretamente na linguagem de programação com base em uma compreensão suposta da realidade, certamente enfrentaremos problemas de interpretação inadequada. O sistema provavelmente não atenderá às necessidades dos usuários e acabará sendo abandonado. Para representar a realidade de maneira adequada e entender o contexto do sistema a ser desenvolvido, precisamos traduzir a realidade em modelos.



### Fases comuns e mais relevantes do processo de desenvolvimento

Desde a década de 1960, muitos processos, métodos e diversas técnicas de desenvolvimento de sistemas foram criados e postos em prática, visando à construção de sistemas computacionais robustos, eficientes e de fácil manutenção.

Para gerenciar melhor a complexidade, os processos e metodologias de desenvolvimento de sistemas geralmente são divididos em fases. Embora cada processo ou metodologia possa ter sua própria divisão, de maneira geral, podemos identificar as seguintes fases (com algumas exceções). Confira!

- Identificação dos requisitos
  - São as necessidades que os usuários têm e que devem estar contidos nas funcionalidades e propriedades do sistema a ser construído.
- Análise
  - Envolve compreender o que o sistema deve fazer para atender às necessidades de seus usuários.
- Projeto
  - Envolve a adequação dos requisitos à forma como serão implementados, utilizando a tecnologia adequada. Define-se a arquitetura e os componentes do sistema, bem como toda a infraestrutura do ambiente computacional necessária para sua construção, incluindo redes de computadores, banco de dados, linguagem de programação e outros elementos.
- Implementação
  - Refere-se à identificação dos programas necessários e sua codificação na linguagem de programação selecionada na fase de projeto, bem como o banco de dados que será usado.
  

### Modelos como elementos de comunicação

Os modelos facilitam a compreensão e a representação da realidade, tanto para os membros da equipe de desenvolvimento quanto para os usuários finais. Eles servem como ferramentas eficazes para traduzir os requisitos e as necessidades dos usuários em uma linguagem compreensível para os desenvolvedores, garantindo que o sistema atenda adequadamente às expectativas e às demandas. Além disso, os modelos auxiliam na validação e na verificação dos requisitos, contribuindo para o sucesso do projeto de desenvolvimento de software.

Compreenderemos neste vídeo a utilização de modelos como elementos de comunicação no processo de desenvolvimento de sistemas computacionais. Assista!


#### Entendimento e validação dos modelos com os usuários

A partir dos modelos, compreendemos e nos certificamos do correto entendimento da realidade dos usuários.

**Momento 1**
A equipe de desenvolvimento se reúne com os usuários e, usando técnicas de levantamento de dados, compreende a realidade e as necessidades dos usuários, visando implementá-las no sistema. Os dados levantados são registrados e usados na construção dos modelos. Esse momento acontece com maior intensidade na fase de requisitos, mas também está presente nas fases de análise e de projeto.

**Momento 2**
A equipe de desenvolvimento constrói os modelos que julga pertinentes para que se possa compreender e destacar os aspectos relevantes da realidade. Esse momento acontece nas fases de requisitos, análise e projeto.

**Momento 3**
A equipe de desenvolvimento se reúne com os usuários, apresentando e discutindo os modelos construídos, visando validá-los e responder à pergunta base: os modelos que construímos representam de fato a realidade dos usuários? Em caso positivo, prossegue-se no desenvolvimento; caso contrário, os modelos são ajustados e confirmados novamente com os usuários, até que estejam adequados. Esse momento acontece nas fases de requisitos, análise e projeto.


## Conceitos e pilares de análise e projeto orientados a objetos

### Orientação a objetos

Compreender os princípios fundamentais desse paradigma de desenvolvimento permite aos profissionais de tecnologia criarem sistemas modulares, flexíveis e de fácil manutenção. Além disso, a adoção de uma abordagem orientada a objetos promove a reutilização de código, a modularidade e a escalabilidade dos sistemas, contribuindo significativamente para a qualidade e a eficácia dos projetos de software. O conhecimento teórico nessa área é essencial para impulsionar a excelência na engenharia de software.

Entenda neste vídeo o paradigma orientado a objetos, que visualiza um sistema de software como uma coleção de agentes interconectados chamados objetos.

### Paradigma orientado a objetos

Vamos analisar agora os conceitos, pilares, princípios e as orientações do paradigma orientado a objetos. Veremos também as visões, os objetivos e as entregas dos momentos de análise, projeto e implementação (em camadas), independentemente de processo ou metodologia de desenvolvimento de software.

Com o aumento do tamanho do código e da complexidade dos programas, o paradigma estruturado, que antecedeu o paradigma orientado a objetos, começou a apresentar limitações nos sistemas sob o ponto de vista da dificuldade de manutenção e reúso de programas e rotinas padronizadas.

Vamos, inicialmente, definir o termo paradigma como a maneira de abordar um problema.

A orientação a objetos surge como solução para esses problemas, possibilitando uma maior organização, reutilização e extensibilidade de código por meio de propriedades como abstração, encapsulamento, herança e polimorfismo. Isso resulta em programas mais fáceis de serem escritos e mantidos.

O principal foco do paradigma orientado a objetos é permitir o desenvolvimento de sistemas de forma mais rápida e confiável.

Um dos pioneiros do paradigma orientado a objetos, Alan Kay, imaginou um sistema como um conjunto de agentes autônomos, os objetos, que interagem entre si. Ele estabeleceu os princípios centrais da orientação a objetos. Vejamos!

1 - Qualquer coisa do mundo real é um objeto.
2 - Objetos realizam tarefas requisitando serviços a outros objetos.
3 - Os objetos similares são agrupados em classes e cada objeto pertence a uma classe.

A seguir, observe a definição sobre o paradigma da orientação a objetos.

> O paradigma da orientação a objetos visualiza um sistema de software como uma coleção de agentes interconectados chamados objetos. Cada um deles é responsável por realizar tarefas específicas e, para cumprir com algumas das tarefas sob sua responsabilidade, um objeto pode ter que interagir com outros. É pela interação entre eles que uma tarefa computacional é executada. Um sistema de software orientado a objetos consiste, portanto, em objetos colaborando para realizar as funcionalidades desse sistema. É graças à cooperação entre os objetos que a computação do sistema se desenvolve. (Bezerra, 2015)

#### Conceitos fundamentais da orientação a objetos

A orientação a objetos enfatiza a identificação, a representação e a organização dos objetos necessários ao funcionamento de um sistema. Tem por base os conceitos de objetos, classes, operação, mensagem e estado, e está calcada em quatro pilares fundamentais: abstração, encapsulamento, herança e polimorfismo, discutidos na sequência.


##### Objetos e classes

Um objeto pode referenciar qualquer coisa do mundo real, por exemplo, um aluno, uma disciplina, um curso, um professor, entre outros, considerando um sistema acadêmico como contexto. Ou seja, um objeto é qualquer coisa do mundo real, de interesse no contexto em estudo.

Quando analisamos os objetos pertinentes a um contexto, não estamos preocupados com um objeto específico, como o aluno José Carlos Aragão, e sim com todos os alunos envolvidos no estudo. Surge, então, o conceito de classe que, conceitualmente, reúne um conjunto de objetos com as mesmas propriedades. Ou seja, estamos interessados em todos os alunos e não apenas em José Carlos Aragão. Aplicando o princípio da abstração (que será detalhado posteriormente), uma classe reúne objetos com características ou propriedades semelhantes, que consistem em seus dados (atributos) e procedimentos (métodos) que implementam os serviços que essa classe oferece.

A classe Aluno agrupa “José Carlos Aragão” e os demais alunos envolvidos. Um objeto é um elemento específico de uma classe, ou ainda uma instância de uma classe.

As classes são, portanto, abstrações que definem uma estrutura que encapsula dados (chamados de atributos) e um conjunto de operações possíveis de serem usados, chamados de métodos. Por exemplo, a classe Aluno encapsula um conjunto de dados que identifique os alunos − matrícula, nome, endereço (rua, número, complemento, estado e CEP), CPF e identidade − e um conjunto de métodos: Incluir Aluno, Matricular Aluno, Cancelar Matrícula, entre outros.

Resumindo, podemos definir classe e objeto da seguinte forma. Observe!

**Classe**
É abstração das características de um grupo de coisas do mundo real.

**Objeto**
É um elemento específico de uma classe ou uma instância de uma classe.

Confira a representação de uma classe em três compartimentos: o nome da classe (Aluno), seus atributos (Matrícula... Identidade) e métodos (Incluir Aluno... Cancelar Matrícula).

![Classe Aluno](image.png)


Agora, veja a representação de dois objetos da classe Aluno.

![Objetos (Aluno1 e Aluno2) da classe Aluno](image-1.png)


##### Operação, mensagem e estado

Um sistema orientado a objetos consiste na cooperação entre seus objetos. Cada um tem uma responsabilidade no sistema, correspondendo à parte das funcionalidades que lhes são atribuídas. Em outras palavras, uma tarefa computacional é realizada pela interação entre seus objetos, cada um executa parte da tarefa. Acompanhe!

**Operação**
É o nome dado a cada ação (função) que o objeto sabe realizar. Mas um objeto não realiza nenhuma ação sem uma motivação, sem um estímulo.

**Mensagem**
Estímulo que chega a um objeto e solicita que ele realize uma de suas operações. Uma operação pode ser implementada através de pelo menos um método. Em outras palavras, cada objeto presta um serviço. Quando um objeto precisa de um serviço da responsabilidade de outro, ele precisa enviar uma mensagem a ele. Cada mensagem ativa uma das operações do objeto.

**Estado**
Chama-se estado do objeto o conjunto de valores de seus atributos em dado momento. Uma mensagem enviada a um objeto pode (ou não) alterar o seu estado, na medida em que pode alterar um ou mais valores de seus atributos.

Um sistema orientado a objetos funciona pela cooperação entre objetos, cada um responsável por parte das funcionalidades. Objetos realizam ações chamadas operações em resposta a estímulos chamados mensagens. O estado de um objeto é determinado pelos valores de seus atributos, que podem ser alterados pelas mensagens recebidas.


###### Objeto

Imagine, por exemplo, que o objeto Notas_Aluno contenha as notas do aluno em determinada disciplina. Em dado momento, é recebida uma mensagem informando uma nova nota a ser armazenada. O estado desse objeto foi alterado, pois um de seus atributos recebeu a nova nota.

Agora, suponha que determinado objeto enviou uma mensagem a Notas_Aluno solicitando que seja exibida a média atual; nesse caso, não houve alteração de estado, pois as notas foram consultadas, e a média foi calculada (não fica armazenada) e exibida.

Observe a seguir como se comporta as partes de um objeto ao receber a mensagem.

![Partes de um objeto.](image-2.png)