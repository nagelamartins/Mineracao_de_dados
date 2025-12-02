# Semana 5: Análise de agrupamento

## 📽️ Videoaulas:
* [Videoaula 12 - Agrupamento de dados](https://www.youtube.com/watch?v=VpN7WlADiJE)
* [Videoaula 13 - Algoritmos de agrupamento](https://www.youtube.com/watch?v=B2ytgwqDvwY)

---

## 📖 Texto-base:
* **Capítulo 4:** CASTRO, Daniel Gomes; FERRARI, Leandro Nunes de. **Introdução à Mineração de Dados:** Conceitos Básicos, Algoritmos e Aplicações. Rio de Janeiro: Saraiva Uni, 2016;

---

## ✍️ Resumos e anotações:  
O agrupamento de dados pode ser definido como a organização de um conjunto de objetos de acordo com a similaridade existente entre eles, com o objetivo de facilitar a 
compreensão e a pesquisa, bem como "[...] para realizar tarefas muito mais sofisticadas, como tomada de decisão em processos críticos" (CASTRO; FERRARI, 2016, p. 88).  

Um grupo, portanto, "[...] pode ser definido em função da coesão interna (homogeneidade) e do isolamento externo (separação) de seus objetos". (CASTRO; FERRARI, 2016, p. 88).  

Essa tarefa se difere da classificação pois, diferentemente dela, os objetos não são rotulados, de modo que os rótulos "[...] são obtidos apenas a partir do algoritmo 
de agrupamento e não são usados durante o processo de treinamento do algoritmo". (CASTRO; FERRARI, 2016, p. 89).  

O processo de agrupamento de dados se divide em cinco etapas, conforme a figura:  

<img width="1252" height="410" alt="Etapas do agrupamento: pré-processamento, definição da medida de similaridade, execução do método de agrupamento, representação dos grupos, avaliação do agrupamento" src="https://github.com/user-attachments/assets/a5f544fb-d32d-48cb-ab0d-d3f8c6922412" />  

*Fonte: CASTRO; FERRARI, 2016, p. 96*  

As três primeiras etapas podem ser refeitas de acordo com o feedback obtido na avaliação do agrupamento, ajustando-as a fim de melhorar o agrupamento resultante.   

"É importante salientar que nenhuma técnica de agrupamento é universalmente aplicável e, além disso, diferentes técnicas podem permitir a extração de 
diferentes informações (agrupamentos) de uma mesma base de dados." (CASTRO; FERRARI, 2016, p. 96).  

### Definição da medida de similaridade:  

Para realizar o agrupamento, em geral, é utilizada uma medida de similaridade (proximidade) ou dissimilaridade (distância) entre os objetos. A maioria dos métodos
assume uma matriz de dados *X* como ponto de partida, que representa *n* objetos, cada um com *m* atributos:  

<img width="376" height="202" alt="matriz de dados X" src="https://github.com/user-attachments/assets/01d8faf9-6002-406c-b846-f54d94107512" />  

*Fonte: CASTRO; FERRARI, 2016, p. 97*  

É também muito comum o uso de uma *matriz de dissimilaridade* ou *distância* (*D*), onde cada elemento representa uma medida quantitativa da proximidade entre pares de 
objetos. Nela, é feito o cruzamento desses pares e marcada a distância existente entre eles.  

<img width="678" height="297" alt="Matriz de dissimilaridade" src="https://github.com/user-attachments/assets/5c8f989c-0db6-4b1f-b242-545cd54574ed" />  

*Fonte: CASTRO; FERRARI, 2016, p. 97*  

"Grande parte dos algoritmos de agrupamento utiliza medidas de dissimilaridade para avaliar, de modo indireto, a proximidade entre objetos. Para isso, é preciso 
identificar primeiramente se a base de dados possui dados do tipo **categórico, numérico ou ambos**". (CASTRO; FERRARI, 2016, p. 97).  

* Dados categóricos: as medidas são normalizadas entre intervalos [0,1] ou [0, 100%];
* Dados numéricos: utilizados os valores dos próprios atributos;
* Dados binários: são os tipos mais comuns de dados categóricos. A medida de distância mais utilizada nesses casos é a *distância de Hamming(H)*.  
  Essa medida verifica, em uma comparação entre dois objetos, quais atributos os objetos possuem (1) ou não (0). Após isso, é feita a soma dos atributos de valor 1,
  de forma a delimitar a distância de um conjunto de atributos;
* Dados nominais: a medida mais simples utilizada para esses casos é o *Coeficiente de similaridade*, que utiliza uma matriz de confusão, inserindo os atributos de
  um objeto nas linhas, e de outro objetos nas colunas. Os resultados 1 ou 0 representam a existência ou não daquele atributo e, ao final, faz-se a somatória dos 
  valores obtidos a fim de utilizar um dos coeficientes de similaridade;
* Dados ordinais: utiliza-se o *cálculo de dissimilaridade*, que representa a diferença entre o número total de atributos e o número de atributos iguais entre
  os objetos;
* Dados híbridos: a maioria das bases de dados reais possuí mais de um tipo de dado e, uma possível abordagem, "[...] é separar cada tipo de atributo e fazer uma análise isolada para cada um deles". (CASTRO; FERRARI, 2016, p. 104).

### Execução do método de agrupamento:  

Os métodos de agrupamento podem ser divididos em:  

* Hierárquicos: criam uma decomposição hierárquica dos dados, podem ser:
  
    * Aglomerativos: "[...]  começam com cada objeto pertencendo a um grupo e unem sucessivamente objetos em grupos de acordo com a proximidade entre eles até que um critério de parada seja atingido". (CASTRO; FERRARI, 2016, p.105);
    * Divisivos: "[...] começam com todos os objetos fazendo parte do mesmo grupo e particionam sucessivamente os grupos em grupos menores, até que um critério de parada seja atingido". (CASTRO; FERRARI, 2016, p.105).
      
* Particionais: funcionam dividindo um conjunto de *n* objetos em *k* partições (clusters), onde *k* é menor ou igual a *n*. O algoritmo inicia com uma partição inicial e usa a realocação iterativa para otimizar os clusters, movendo objetos entre os grupos até atingir o critério de parada. Podem ser exclusivos ou não exclusivos.
  
    * Não exclusivos (*overlapping*): "[...] permitem que um objeto pertença completamente (métodos conhecidos como *soft*) ou parcialmente (métodos conhecidos como *fuzzy*) a mais de um grupo ao mesmo tempo". (CASTRO; FERRARI, 2016, p.105);

<img width="1962" height="1800" alt="Outras características para classificar algoritmos de agrupamento" src="https://github.com/user-attachments/assets/32006e48-39d0-4854-89c6-4805ac258815" />  

*Fonte: Gerado com Napkin.AI a partir do texto-base e anotações da aula.*  

### Representação dos grupos:  

Trata-se do "[...] processo de extrair uma representação simples e compacta dos grupos obtidos a partir do agrupamento da base". (CASTRO; FERRARI, 2016, p. 106). São típicamente representados em:  

<img width="1815" height="1505" alt="Tipos de representação" src="https://github.com/user-attachments/assets/652990ac-e07f-4036-be5c-ee7362dc6222" />  

*Fonte: Gerado com Napkin.AI a partir do texto-base e anotações da aula.*  

### Avaliação do agrupamento:  

A qualidade de um agrupamento é avaliado seguindo dois critérios:  

1. Compactação (intragrupo): "os objetos de cada grupo devem estar o mais próximo possível um dos outros". (CASTRO; FERRARI, 2016, p. 108);
2. Separação (extragrupo): "os grupos devem estar o mais distante possível uns dos outros". (CASTRO; FERRARI, 2016, p. 108).

Os grupos formados podem ser avaliados por dois tipos de medidas:

1. Internas: "são medidas que utilizam apenas informações intrínsecas aos objetos do agrupamento, baseando-se em medidas de similaridade e avaliando as distâncias 
intragrupos e/ou intergrupos". (CASTRO; FERRARI, 2016, p. 108);
2. Externas: "são medidas que avaliam quão correto está um agrupamento dado um agrupamento ideal que se deseja alcançar. O cálculo dessas medidas requer o 
   conhecimento prévio do grupo ao qual cada objeto pertence". (CASTRO; FERRARI, 2016, p. 108).

### Algoritmos de Agrupamento:  

<img width="2867" height="1427" alt="_Algoritmos de agrupamento" src="https://github.com/user-attachments/assets/04231755-051c-413e-bcb5-ef8b3c7a6b19" />  

*Fonte: Gerado com Napkin.AI a partir do texto-base e anotações da aula.*   

* **Algoritmo K-Médias**: O K-Médias divide os dados em "k" grupos pré-definidos. Ele funciona encontrando os centroides (pontos médios) de cada grupo e atribuindo 
cada objeto ao centroide mais próximo. O processo é iterativo: os centroides são recalculados e os objetos realocados até que os grupos se estabilizem, buscando 
alta similaridade interna e baixa similaridade entre os grupos;  

* **Algoritmo K-Medoides**: Similar ao K-Médias, o K-Medoides também divide os dados em "k" grupos. A diferença crucial é que ele usa medoides, que são objetos 
reais da base de dados que representam o centro do grupo, ao invés de centroides calculados (que podem não ser pontos reais). Isso o torna mais resistente a 
valores discrepantes e ruídos;

* **Algoritmo Fuzzy K-Médias**: Uma extensão do K-Médias, o Fuzzy K-Médias permite que um objeto pertença a mais de um grupo ao mesmo tempo, porém com diferentes 
graus de pertinência (porcentagens). Em vez de uma alocação "tudo ou nada", ele considera o quão fortemente um objeto pertence a cada cluster, ideal para situações 
onde os limites entre os grupos são menos rígidos;

* **Árvore Geradora Mínima (MST)**: Este método constrói uma Árvore Geradora Mínima dos seus dados, onde os objetos são nós e as distâncias são as arestas. Ele 
identifica e remove as arestas "inconsistentes" (as mais longas ou que conectam regiões de baixa densidade), e as subárvores resultantes formam os grupos. A grande 
vantagem é que ele define o número de grupos automaticamente e pode encontrar formas de cluster complexas;

* **DBSCAN**: O DBSCAN agrupa objetos com base na densidade de pontos em uma região. Ele identifica "objetos de núcleo" (que têm muitos vizinhos próximos) e 
expande os clusters a partir deles, conectando todos os pontos densamente alcançáveis. Pontos que não são conectados a nenhum cluster denso são classificados como 
ruído, e o algoritmo não precisa que o número de grupos seja definido previamente;

* **Single-Linkage**: O Single-Linkage é um método aglomerativo que começa com cada objeto em seu próprio grupo. A cada passo, ele une os dois grupos mais próximos, 
onde a "proximidade" é definida pela menor distância entre qualquer par de objetos de cada grupo. Ele forma "cadeias" de grupos e é bom para identificar clusters 
alongados;

* **Complete-Linkage**: Assim como o Single-Linkage, o Complete-Linkage é um método aglomerativo. Ele também começa com objetos individuais e une os dois grupos 
mais próximos em cada passo. No entanto, a "proximidade" é calculada pela maior distância entre qualquer par de objetos de cada grupo. Isso tende a formar clusters 
mais compactos e esféricos.








