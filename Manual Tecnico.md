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
| A*HD      | ![ProblemaAHeuristicaD](C:\Users\Zorg\Desktop\Lisp-Sol\PROBA\A_HD_PROBA-2.png) |
| IDA* HA   | ![ProblemaA IDA* Heuristica A](C:\Users\Zorg\Desktop\Lisp-Sol\PROBA\IDA_HA_PROBA-2.png) |
| IDA* HB   | ![ProblemaA IDA* Heuristica B](C:\Users\Zorg\Desktop\Lisp-Sol\PROBA\IDA_HB_PROBA-2.png) |
| IDA* HC   | ![ProblemaA IDA* HeuristicaC](C:\Users\Zorg\Desktop\Lisp-Sol\PROBA\IDA_HC_PROBA_2.png) |
| IDA* HD   | ![ProblemaA IDA* Heuristica D](C:\Users\Zorg\Desktop\Lisp-Sol\PROBA\IDA_HD_PROBA_2.png) |



##### Problema B:

| Algoritmo |                                          |
| --------- | ---------------------------------------- |
| BFS       | ![ProblemaB BFS](C:\Users\Zorg\Desktop\Lisp-Sol\PROBB\BFS_PROBB_2.png) |
| DFS       | ![ProblemaB DFS](C:\Users\Zorg\Desktop\Lisp-Sol\PROBB\DFS_PROBB_2.png) |
| A* HA     | ![ProblemaB HeuristaA](C:\Users\Zorg\Desktop\Lisp-Sol\PROBB\A_HA_PROBB_2.png) |
| A* HB     | ![ProblemaB HeuristicaB](C:\Users\Zorg\Desktop\Lisp-Sol\PROBB\A_HB_PROBB_2.png) |
| A* HC     | ![ProblemaB HeuristicaC](C:\Users\Zorg\Desktop\Lisp-Sol\PROBB\A_HC_PROBB_2.png) |
| A* HD     | ![ProblemaB HeuristicaB](C:\Users\Zorg\Desktop\Lisp-Sol\PROBB\A_HD_PROBB_2.png) |
| IDA* HA   | ![ProblemaB IDA* HA](C:\Users\Zorg\Desktop\Lisp-Sol\PROBB\IDA_HA_PROBB_2.png) |
| IDA* HB   | ![ProblemaB IDA* HeuristicaB](C:\Users\Zorg\Desktop\Lisp-Sol\PROBB\IDA_HB_PROBB_2.png) |
| IDA* HC   | ![ProblemaB IDA* Heuristica C](C:\Users\Zorg\Desktop\Lisp-Sol\PROBB\IDA_HC_PROBB_2.png) |
| IDA* HD   | ![ProblemaB IDA* Heuristica D](C:\Users\Zorg\Desktop\Lisp-Sol\PROBB\IDA_HD_PROBB_2.png) |

##### Problema C:

| Algoritmo |                                          |
| --------- | ---------------------------------------- |
| BFS       | ![ProblemaC BFS](C:\Users\Zorg\Desktop\Lisp-Sol\PROBC\BFS_PROBC_2.png) |
| DFS       | ![ProblemaC DFS](C:\Users\Zorg\Desktop\Lisp-Sol\PROBC\DFS_PROBC_2.png) |
| A* HA     | ![ProblemaC A* HeuristicaA](C:\Users\Zorg\Desktop\Lisp-Sol\PROBC\A_HA_PROBC_2.png) |
| A* HB     | ![ProblemaC A Heuristica B](C:\Users\Zorg\Desktop\Lisp-Sol\PROBC\A_HB_PROBC_2.png) |
| A* HC     | ![ProblemaC A* Heuristica C](C:\Users\Zorg\Desktop\Lisp-Sol\PROBC\A_HC_PROBC_2.png) |
| A* HD     | ![ProblemaC A* Heuristica D](C:\Users\Zorg\Desktop\Lisp-Sol\PROBC\A_HD_PROBC_2.png) |
| IDA* HA   | ![ProblemaC IDA* Heuristica A](C:\Users\Zorg\Desktop\Lisp-Sol\PROBC\IDA_HA_PROBC_2.png) |
| IDA* HB   | ![](C:\Users\Zorg\Desktop\Lisp-Sol\PROBC\IDA_HB_PROBC_2.png) |
| IDA* HC   | ![ProblemaC IDA* Heuristica C](C:\Users\Zorg\Desktop\Lisp-Sol\PROBC\IDA_HC_PROBC_2.png) |
| IDA* HD   | ![ProblemaC IDA* Heuristica D](C:\Users\Zorg\Desktop\Lisp-Sol\PROBC\IDA_HD_PROBC_2.png) |

##### Problema D:

| Algoritmo |                                          |
| --------- | ---------------------------------------- |
| BFS       | ![ProblemaD BFS](C:\Users\Zorg\Desktop\Lisp-Sol\PROBD\BFS_PROBD_2.png) |
| DFS       | ![ProblemaD DFS](C:\Users\Zorg\Desktop\Lisp-Sol\PROBD\DFS_PROBD_2.png) |
| A* HA     | ![ProblemaD A* Heuristica A](C:\Users\Zorg\Desktop\Lisp-Sol\PROBD\A_HA_PROBD_2.png) |
| A* HB     | ![ProblemaD A* Heuristica B](C:\Users\Zorg\Desktop\Lisp-Sol\PROBD\A_HB_PROBD_2.png) |
| A* HC     | ![ProblemaD A* Heuristica C](C:\Users\Zorg\Desktop\Lisp-Sol\PROBD\A_HC_PROBD_2.png) |
| A* HD     | ![ProblemaD A* Heuristica D](C:\Users\Zorg\Desktop\Lisp-Sol\PROBD\A_HD_PROBD_2.png) |
| IDA* HA   | ![ProblemaD IDA* Heuristica A](C:\Users\Zorg\Desktop\Lisp-Sol\PROBD\IDA_HA_PROBD_2.png) |
| IDA* HB   | ![](C:\Users\Zorg\Desktop\Lisp-Sol\PROBD\IDA_HB_PROBD_2.png) |
| IDA* HC   | ![ProblemaD IDA* Heuristica C](C:\Users\Zorg\Desktop\Lisp-Sol\PROBD\IDA_HC_PROBD_2.png) |
| IDA* HD   | ![ProblemaD IDA* Heuristica D](C:\Users\Zorg\Desktop\Lisp-Sol\PROBD\IDA_HD_PROBD_2.png) |

##### Problema E:

| Algoritmo |                                          |
| --------- | ---------------------------------------- |
| BFS       | ![ProblemaE BFS](C:\Users\Zorg\Desktop\Lisp-Sol\PROBE\BFS_PROBE_2.png) |
| DFS       | ![ProblemaE DFS](C:\Users\Zorg\Desktop\Lisp-Sol\PROBE\DFS_PROBE_2.png) |
| A* HA     | ![Problema A* Heuristica A](C:\Users\Zorg\Desktop\Lisp-Sol\PROBE\A_HA_PROBE_3.png) |
| A* HB     | ![ProblemaE A* Heuristica B](C:\Users\Zorg\Desktop\Lisp-Sol\PROBE\A_HB_PROBE_3.png) |
| A* HC     | ![ProblemaE A* Heuristica C](C:\Users\Zorg\Desktop\Lisp-Sol\PROBE\A_HC_PROBE_2.png) |
| A* HD     | ![ProblemaE A* Heuristica D](C:\Users\Zorg\Desktop\Lisp-Sol\PROBE\A_HD_PROBE_2.png) |
| IDA* HA   | ![ProblemaE IDA* Heuristica A](C:\Users\Zorg\Desktop\Lisp-Sol\PROBE\IDA_HA_PROBE_3.png) |
| IDA* HB   | ![ProblemaE IDA* Heuristica B](C:\Users\Zorg\Desktop\Lisp-Sol\PROBE\IDA_HB_PROBE_3.png) |
| IDA* HC   | ![ProblemaE IDA* Heuristica C](C:\Users\Zorg\Desktop\Lisp-Sol\PROBE\IDA_HC_PROBE_2.png) |
| IDA* HD   | ![ProblemaE IDA* Heuristica D](C:\Users\Zorg\Desktop\Lisp-Sol\PROBE\IDA_HD_PROBE_2.png) |

##### Problema F:

| Algoritmo |                                          |
| :-------- | ---------------------------------------- |
| BFS       | Não encontra solução                     |
| DFS       | ![ProblemaF DFS](C:\Users\Zorg\Desktop\Lisp-Sol\PROBF\DFS_PROBF_3.png) |
| A* HA     | ![ProblemaA A* Heuristica A](C:\Users\Zorg\Desktop\Lisp-Sol\PROBF\A_HA_PROBF_3.png) |
| A* HB     | ![ProblemaF A* HeuristicaB](C:\Users\Zorg\Desktop\Lisp-Sol\PROBF\A_HB_PROBF_3.png) |
| A* HC     | ![ProblemaF A* Heuristica C](C:\Users\Zorg\Desktop\Lisp-Sol\PROBF\A_HC_PROBF_3.png) |
| A* HD     | ![](C:\Users\Zorg\Desktop\Lisp-Sol\PROBF\DFS_PROBF_3.png) |
| IDA* HA   | ![ProblemaF IDA* Heuristica A](C:\Users\Zorg\Desktop\Lisp-Sol\PROBF\IDA_HA_PROBF_3.png) |
| IDA* HB   | ![ProblemaF IDA* Heuristica B](C:\Users\Zorg\Desktop\Lisp-Sol\PROBF\IDA_HB_PROBF_3.png) |
| IDA* HC   | ![](C:\Users\Zorg\Desktop\Lisp-Sol\PROBF\IDA_HC_PROBF_3.png) |
| IDA* HD   | ![ProblemaF IDA* Heuristica D](C:\Users\Zorg\Desktop\Lisp-Sol\PROBF\IDA_HD_PROBF_2.png) |

#### Caminho ate ao nó objectivo

##### Problema A:

| BFS     | ![Problema A BFS](C:\Users\Zorg\Desktop\Lisp-Sol\PROBA\BFS_PROBA.png) |
| ------- | ---------------------------------------- |
| DFS     | ![Problema A DFS](C:\Users\Zorg\Desktop\Lisp-Sol\PROBA\DFS_PROBA.png) |
| A* HA   | ![ProblemaA A* Heuristica A](C:\Users\Zorg\Desktop\Lisp-Sol\PROBA\A_HA_PROBA.png) |
| A* HB   | ![ProblemaA A* Heuristica B](C:\Users\Zorg\Desktop\Lisp-Sol\PROBA\A_HB_PROBA.png) |
| A* HC   | ![ProblemaA A* Heuristica C](C:\Users\Zorg\Desktop\Lisp-Sol\PROBA\A_HA_PROBA.png) |
| A* HD   | ![ProblemaA A* Heuristica d](C:\Users\Zorg\Desktop\Lisp-Sol\PROBA\A_HD_PROBA.png) |
| IDA* HA | ![ProblemaA Heuristica A](C:\Users\Zorg\Desktop\Lisp-Sol\PROBA\IDA_HA_PROBA.png) |
| IDA* HB | ![ProblemaA Heuristica B](C:\Users\Zorg\Desktop\Lisp-Sol\PROBA\IDA_HB_PROBA.png) |
| IDA* HC | ![ProblemaA IDA* Heuristica C ](C:\Users\Zorg\Desktop\Lisp-Sol\PROBA\IDA_HC_PROBA.png) |
| IDA* HD | ![ProblemaA IDA* Heuristica D](C:\Users\Zorg\Desktop\Lisp-Sol\PROBA\IDA_HD_PROBA.png) |



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



