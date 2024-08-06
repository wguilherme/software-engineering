# O modelo relacional de banco de dados

**Overview**

- Foi criado por Edgar Codd em 1970
- Modelo dominante nos SGDBs Comerciais
- Possui uma extensão chamada Objeto relacional (que junta as características do modelo relacional com o modelo orientado à objeto)


## Modelo Relacional - Características

1 - Uma tabela não pode conter linhas repetidoas; (aplica o conceito de chave primária)
2 - Uma tabela pode ser acessada por qualquer coluna;
3 - O relacionamento entre tabelas não existe fisicamente, as tabelas são distintas e o relacionamento é lógico;
4 - Utilização de linguagens auto-contidas e não procedurais;
5 - Os ambientes relacionais possuem um otimizados para escolher o melhor caminho para recuperação dos dados;


Em matemática tabela se chama relação, daí vem o termo: modelo relacional, porque os dados são armazenados em relações (ou seja, em tabelas).

Uma tabela possui linhas e colunas.

As colunas são atributos da relação (ex.: ID, NOME, ID_REGIAO)
Cada atributo possui um domínio (Valores dos atributos = Domínio)

Exemplos:

ID possui como domínio os números inteiros, a mesma coisa pra o ID_REGIAO
NOME possui como domínio strings, conjuntos de caracteres que formam palavras.
Esse é o mínimo para definir o tipo da coluna.

Posso limitar strings
Conjuntos de atributos = Schema (esquema)
Esquema é relativamente estável

Tupla = Linha da tabela
Onde ficam os dados, conjunto de linhas formam sua instancia
Conjunto de instancias de todas tabelas que tenho no banco, formam o banco de dados em si.


Campo = Encontro de linha e coluna
Valor = Conteúdo do campo

Exemplo: NOME = OPERAÇÕES
Valor = OPERAÇÕES
Campo = Local onde tenho esse valor

Nulo = Campo que não tem valor (ausência de valor)
Chave primária (PK) = Identifica de forma única uma tupla
Chave primária = Atributo Unico
Integridade de chave primária
Chave primária é obrigatório = Integridade de Entidade
Chave primária simples: Único atributo eu consigo identificar
Chave primária composta: Responmsável (101) e ID (1) = 101 1 (par único, me permite identificar uma tupla)
Chave candidata, atributo que tem característica de ser único e preenchimento obrigatório, então posso escolhê-lo como chave primária de um documento. Posso eleger um pra ser a chave primária.
Chave estrangeira (FK), ligação de uma tabela com outra tabela (relacionamento)
Uma FK aponta pra uma PK de outra tabela (é a chave primária de uma tabela que foi exportada pra outra tabela)


# Módulo 2

Identificar as características dos sistemas de banco de dados (SBD)


### DIFERENÇAS ENTRE SISTEMA DE ARQUIVOS E SISTEMA DE BANCO DE DADOS





