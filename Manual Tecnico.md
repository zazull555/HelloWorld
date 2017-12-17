# Projecto Nº1 Blokus - Inteligência Artificial #


## Docentes ##
### Professor Joaquim Filipe ###
###	Professor Hugo Silva ###

## Alunos ##

### Pedro Ribeiro       nº 140221043 ##
### Rafael Carpinteiro  nº 150221009 ##


## Indice ##

  * Introdução
  * Projecto.lisp
  * Procura.lisp
  * Puzzle.lisp
  * Análise crítica de resultados
  * Análise comparativa dos problemas
  * Objectivos não atingidos


## Introdução ##
>Este documento tem a finalidade de informar o utilizador dos aspetos mais técnicos do projeto. Tendo assim como tópicos o algoritmo geral utilizado, a descrição dos objetos que compõem o projeto  como os dados e procedimentos que utiliza, identificação das limitações e opções técnicas. 
>
>Tem também análises críticas de resultados das execuções do programa, análises comparativas do conjunto de execuções do programa para cada algoritmo e cada problema. 
>
>Por fim, tem os requisitos não implementados no programa. 
>Foi-nos solicitado pelos docentes a separação do projeto em 3 ficheiros (projeto.lisp, procura.lisp e puzzle.lisp) diferentes para garantir que a procura seja independente do domínio do problema. 
>
>Sendo a procura.lisp destinada aos objetos que fazem parte da implementação dos algoritmos, o puzzle.lisp tem os objetos que dependem do domínio do problema e o projeto.lisp tem a parte da interação com o utilizador, escrita e leitura de ficheiros, e importa os outros 2 ficheiros. 
>
>Este manual destina-se a utilizadores que compreendam minimamente a linguagem Lisp, visto que é a linguagem que foi sugerida para a implementação do projeto.

## Projecto.lisp ##

### Objectos de interação/input com utilizador

- algoritmo-desejado

- heuristica-desejada

  ​

### Objectos de escrita/output em ficheiro

- ler-tabuleiros-desejada
- le-ficheiro-aux


## Procura.lisp ##


### Algoritmos ###
	* bfs
	* dfs
	* a*
	* correr-ida*
	* ida*

## Puzzle.lisp ##

#### Construtor ####
	*  no-teste

#### Seletores ####
	* linha
	* coluna
	* celula
	* no-estado
	* no-pai
	* no-profundidade
	* tabuleiro
	* pecas
	* pecas-1x1
	* pecas-2x2
	* pecas-cruz
	* get-valor-heuristica
	* get-valor-funcao
	* coordenadas-inicio-vazio-1x1
	* coordenadas-inicio-vazio-2x2
	* tamanho-tabuleiro

#### Operadores ####

- sucessores-aux-quadrado-1x1
- sucessores-aux-quadrado-2x2
- sucessores-aux-cruz
- operadores

####  Tabuleiro ####
	* tabuleiro-vazio
	* todas-coordenadas


#### Funções Auxiliares de Procura ####

* sucessores

* sucessores-aux1

* fechar-no

* abertos-bfs

* abertos-dfs

* abertos-a*

* substituir

* substituir-posicao

* quadrado-1x1

* quadrado-2x2

* cruz

* verificar-tabuleiro-vazio

* verifica-tabuleiro-vazio-auxiliar

* nao-e-um

* na-tem-nils

* verificar-posicao-laterais

* verificar-posicao-diagonal

* verificar-posicoes

* verificar-posicoes-peca

* verificar-posicoes-peca-completo

* peca-casas-ocupadas

* nos-existem

* nos-existep

* retirar-peca

* remover-nills

* buscar-indices-de-linha-com-1

* no-solucaop

* solucao-na-lista

* calcula-espacos-ocupados

* calcula-espacos-vazios

* ida*-sucessores-aprovados

* ida*-sucessores-reprovados-valor-minimo

* ida*-sucessores-reprovados

* fator-ramificacao-medio

* criar-no

* numero-nos-gerados

* numero-nos-expandidos

* contar-pecas

* verificar-posicoes-peca-1x1

* verificar-posicoes-peca-2x2

* verificar-posivoes-peca-cruz

* is-1

* pecas-restantes

  ​

#### Heuristicas ####

* heuristica-A
* heuristica-B
* heuristica-C
* heuristica-D

#### Estatísticas ####

## Análise crítica de resultados ##

Neste projecto foi-nos solicitado a implementação dos algoritmos BFS, DFS, A* e IDA*. Cada um destes algoritmos tem a sua logica de encontrar uma solução, tendo como consequência que cada um dos algoritmos demora o seu tempo, gastando quantidades diferentes de memória da maquina para tentar encontrar uma solução para o problema.

### Breadth-First ####

O Breadth-First-Search é um algoritmo que faz procura em largura, o algoritmo tem como objectivo encontrar a solução de menor profundidade mas também é o que utiliza mais recursos da maquina.

### Depth-First ####

O Depth-First-Search é um algortimo que encontra a solução primeiro a chegar aos últimos ramos das árvores, isto é devido às soluções de maior profundidade, se pusermos diferentes profundidades máximas nos exercícios pode-se verificar várias soluções diferentes. 

### A* ####

O A* é um algoritmo informado, ou seja utiliza uma heurística que depende do domínio do problema, as heurísticas podem ser admissíveis ou não, no caso deste projecto utilizamos a heuristica forneceida pelo docente, e mais duas heurísticas criadas pelos alunos.

### IDA* ####

O IDA* é um algoritmo informado que encontrar o caminho mais curto entre o nó inicial e o nó final,  o algoritmo vai guardar um minimo e a medida que é executado vai encontrar um novo minimo entre o minimo dos ultimos sucessores gerados, executando novamente o algoritmo com o novo minimo ate encontrar o nó solução.



## Análise comparativa

### Algoritmos

Em baixo vão estar as tabelas com os resultados dos problemas do enunciado. Mostra o problema inicial, algoritmo escolhido, estado do nó final, tempo de execução, o fator de ramificação, o número de nós gerados, número de nós expandidos, a penetrância , nó pai , profundidade e heurística(caso o algoritmo não necessite será de 0). 

#### Experiencias

##### Problema A:

| Algoritmo |                                          |
| --------- | ---------------------------------------- |
| BFS       | ![Imgur](https://i.imgur.com/NirJAXY.png) |
| DFS       | ![Imgur](https://i.imgur.com/Zizr80u.png) |
| A* HA     | ![Imgur](https://i.imgur.com/R5d4jox.png) |
| A*HB      | ![Imgur](https://i.imgur.com/xFwZtoJ.png) |
| A*HC      | ![Imgur](https://i.imgur.com/YKi8Y3I.png) |
| A*HD      | ![Imgur](https://i.imgur.com/a2S7kdH.png) |
| IDA* HA   | ![Imgur](https://i.imgur.com/kDv08OF.png) |
| IDA* HB   | ![Imgur](https://i.imgur.com/xFwZtoJ.png) |
| IDA* HC   | ![Imgur](https://i.imgur.com/jtGJ0Zr.png) |
| IDA* HD   | ![Imgur](https://i.imgur.com/l1TeKED.png) |



##### Problema B:

| Algoritmo |                                          |
| --------- | ---------------------------------------- |
| BFS       | ![Imgur](https://i.imgur.com/0bau9VT.png) |
| DFS       | ![Imgur](https://i.imgur.com/3Su0BGq.png) |
| A* HA     | ![Imgur](https://i.imgur.com/HTOS6nr.png) |
| A* HB     | ![Imgur](https://i.imgur.com/iE4KeZz.png) |
| A* HC     | ![Imgur](https://i.imgur.com/MnxSlkq.png) |
| A* HD     | ![Imgur](https://i.imgur.com/1rL85tC.png) |
| IDA* HA   | ![Imgur](https://i.imgur.com/2YIDXSA.png) |
| IDA* HB   | ![Imgur](https://i.imgur.com/64iSnT7.png) |
| IDA* HC   | ![Imgur](https://i.imgur.com/JUtahWj.png) |
| IDA* HD   | ![Imgur](https://i.imgur.com/KjQIhqs.png) |

##### Problema C:

| Algoritmo |                                          |
| --------- | ---------------------------------------- |
| BFS       | ![Imgur](https://i.imgur.com/2IxgVMF.png) |
| DFS       | ![Imgur](https://i.imgur.com/hJUUPNe.png) |
| A* HA     | ![Imgur](https://i.imgur.com/SFW1cbc.png) |
| A* HB     | ![Imgur](https://i.imgur.com/5UxTBZK.png) |
| A* HC     | ![Imgur](https://i.imgur.com/SlKtMAf.png) |
| A* HD     | ![Imgur](https://i.imgur.com/xj7uKwN.png) |
| IDA* HA   | ![Imgur](https://i.imgur.com/slJZXE6.png) |
| IDA* HB   | ![Imgur](https://i.imgur.com/dQtySkC.png) |
| IDA* HC   | ![Imgur](https://i.imgur.com/Hw5UHjE.png) |
| IDA* HD   | ![Imgur](https://i.imgur.com/xexCDA8.png) |

##### Problema D:

| Algoritmo |                                          |
| --------- | ---------------------------------------- |
| BFS       | ![Imgur](https://i.imgur.com/SVRQkRJ.png) |
| DFS       | ![Imgur](https://i.imgur.com/E3jyCQG.png) |
| A* HA     | ![Imgur](https://i.imgur.com/RZwj3pH.png) |
| A* HB     | ![Imgur](https://i.imgur.com/q3egEBV.png) |
| A* HC     | ![Imgur](https://i.imgur.com/n29P99y.png) |
| A* HD     | ![Imgur](https://i.imgur.com/5pCbQIb.png) |
| IDA* HA   | ![Imgur](https://i.imgur.com/gl3ZK0j.png) |
| IDA* HB   | ![Imgur](https://i.imgur.com/gl3ZK0j.png) |
| IDA* HC   | ![Imgur](https://i.imgur.com/n29P99y.png) |
| IDA* HD   | ![Imgur](https://i.imgur.com/VxaPIHE.png) |

##### Problema E:

| Algoritmo |                                          |
| --------- | ---------------------------------------- |
| BFS       | ![Imgur](https://i.imgur.com/Bni8QWW.png) |
| DFS       | ![Imgur](https://i.imgur.com/xP23LAs.png) |
| A* HA     | ![Imgur](https://i.imgur.com/m9u6bjj.png) |
| A* HB     | ![Imgur](https://i.imgur.com/jYsGDhO.png) |
| A* HC     | ![Imgur](https://i.imgur.com/PS6RvnN.png) |
| A* HD     | ![Imgur](https://i.imgur.com/bh8fJr2.png) |
| IDA* HA   | ![Imgur](https://i.imgur.com/u7FPamJ.png) |
| IDA* HB   | ![Imgur](https://i.imgur.com/u7FPamJ.png) |
| IDA* HC   | ![Imgur](https://i.imgur.com/fJmRwNS.png) |
| IDA* HD   | ![Imgur](https://i.imgur.com/Crvt6SR.png) |

##### Problema F:

| Algoritmo |                                          |
| :-------- | ---------------------------------------- |
| BFS       | Não encontra solução                     |
| DFS       | ![Imgur](https://i.imgur.com/Fw73S6O.png) |
| A* HA     | ![Imgur](https://i.imgur.com/i7LmSm4.png) |
| A* HB     | ![Imgur](https://i.imgur.com/nBJT912.png) |
| A* HC     | ![Imgur](https://i.imgur.com/9Hac3Tv.png) |
| A* HD     | ![Imgur](https://i.imgur.com/1pgPMrB.png) |
| IDA* HA   | ![Imgur](https://i.imgur.com/blgXW46.png) |
| IDA* HB   | ![Imgur](https://i.imgur.com/My0Mhqx.png) |
| IDA* HC   | ![Imgur](https://i.imgur.com/SoVv5cL.png) |
| IDA* HD   | ![Imgur](https://i.imgur.com/jrsjqkh.png) |

#### Caminho ate ao nó objectivo

##### Problema A:

| BFS     | ![Imgur](https://i.imgur.com/KQc0EQp.png) |
| ------- | ---------------------------------------- |
| DFS     | ![Imgur](https://i.imgur.com/QdAfO5x.png) |
| A* HA   | ![Imgur](https://i.imgur.com/chtmRE6.png) |
| A* HB   | ![Imgur](https://i.imgur.com/XWcE5hB.png) |
| A* HC   | ![Imgur](https://i.imgur.com/dkqJRz9.png) |
| A* HD   | ![Imgur](https://i.imgur.com/x7wdHLw.png)) |
| IDA* HA | ![Imgur](https://i.imgur.com/ObpDUw5.png) |
| IDA* HB | ![Imgur](https://i.imgur.com/J8NjTG9.png) |
| IDA* HC | ![Imgur](https://i.imgur.com/2DfnSpl.png) |
| IDA* HD | ![Imgur](https://i.imgur.com/hQ9zwra.png) |

Problema B:

| BFS     | ![Imgur](https://i.imgur.com/AwCHGjC.png) |
| ------- | ---------------------------------------- |
| DFS     | ![Imgur](https://i.imgur.com/TEvGCCc.png) |
| A* HA   | ![Imgur](https://i.imgur.com/F42pqyl.png) |
| A* HB   | ![Imgur](https://i.imgur.com/LRDbDhs.png) |
| A* HC   | ![Imgur](https://i.imgur.com/TB1FNkg.png) |
| A* HD   | ![Imgur](https://i.imgur.com/3NPJJ68.png) |
| IDA* HA | ![Imgur](https://i.imgur.com/G52rQGX.png) |
| IDA* HB | ![Imgur](https://i.imgur.com/WYwA4d5.png) |
| IDA* HC | ![Imgur](https://i.imgur.com/DifZjx0.png) |
| IDA* HD | ![Imgur](https://i.imgur.com/ZoD9SmU.png) |

Problema C:

| BFS     | ![Imgur](https://i.imgur.com/yBseS72.png) |
| ------- | ---------------------------------------- |
| DFS     | ![Imgur](https://i.imgur.com/8vKUIjp.png) |
| A* HA   | ![Imgur](https://i.imgur.com/jdmTNkq.png) |
| A* HB   | ![Imgur](https://i.imgur.com/Y0CnqaL.png) |
| A* HC   | ![Imgur](https://i.imgur.com/mQn1hll.png) |
| A* HD   | ![Imgur](https://i.imgur.com/0IRTrBK.png) |
| IDA* HA | ![Imgur](https://i.imgur.com/9Hx2IM9.png) |
| IDA* HB | ![Imgur](https://i.imgur.com/DF1gBlg.png) |
| IDA* HC | ![Imgur](https://i.imgur.com/Xh5s0bS.png) |
| IDA* HD | ![Imgur](https://i.imgur.com/ZbhtLDn.png) |

Problma D:

| BFS     | ![Imgur](https://i.imgur.com/DCI54CF.png) |
| ------- | ---------------------------------------- |
| DFS     | ![Imgur](https://i.imgur.com/7rUZySf.png) |
| A* HA   | ![Imgur](https://i.imgur.com/l9UQucS.png) |
| A* HB   | ![Imgur](https://i.imgur.com/Zk5gcGk.png) |
| A* HC   | ![Imgur](https://i.imgur.com/DfKHbCy.png) |
| A* HD   | ![Imgur](https://i.imgur.com/4HHPopY.png) |
| IDA* HA | ![Imgur](https://i.imgur.com/BSxdjqq.png) |
| IDA* HB | ![Imgur](https://i.imgur.com/8G8HR6S.png) |
| IDA* HC | ![Imgur](https://i.imgur.com/YaEiaof.png) |
| IDA* HD | ![Imgur](https://i.imgur.com/DJMEXPx.png) |

Problema E:



Problema F:



### Heuristicas

Nesta parte do manual, vai ser explicada a admissibilidade de cada heurística implementada.

#### 1º Heuristica 

A heuristica fornecida pelo docente, tem em consideração o objectivo que é o número de quadrados a ocupar no tabuleiro e o numero de quadrados que ja se encontram preenchidos no tabuleiro **(obj - numero)** ,  logo a consequência disto é que alguns nós objectivos ficarem com uma heurística negativa ou seja a heuristica não é admissivel.

NOTA COLOCAR IMAGEM 



#### 2º Heuristica 

A heuristica b que foi desenvolvida pelos alunos, tem em consideração o objectivo que é as peças totais e o numero de peças colocadas no tabuleiro no estado atual **(obj - numero)**<-alterar  ,  Como consequencia esta heuristica ao contrario da heuristica anterior nunca assume um valor negativo, mantendo-se admissivel **h' <= h**.

NOTA COLACAR IMAGEM

#### 3º Heuristica 



#### 4º Heuristica



## Objectivos  Não Antigidos



