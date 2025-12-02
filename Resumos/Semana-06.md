# Semana 6: Análise de associação

## 📽️ Videoaulas:
* [Videoaula 15 - Regras de associação](https://www.youtube.com/watch?v=OhR4wZV0DPA)
* [Videoaula 16 - Algoritmos para mineração de regras de associação](https://www.youtube.com/watch?v=_15nUAC_dBE)

---

## 📖 Texto-base:
* **Capítulo 7:** CASTRO, Daniel Gomes; FERRARI, Leandro Nunes de. **Introdução à Mineração de Dados:** Conceitos Básicos, Algoritmos e Aplicações. Rio de Janeiro: Saraiva Uni, 2016;

---

## ✍️ Resumos e anotações:  

* Regras de associação: "[...] buscam relações entre os atributos dos objetos, ou seja, os itens que compõem a base". (CASTRO; FERRARI, 2016, p. 235).
* Mineração de regras de associação: "[...] técnica usada na construção de relações sob a forma de regras entre itens de uma base de dados transacional". (CASTRO; FERRARI, 2016, p. 235).
* Associação entre dois itens: "[...] um [item] implica o outro, ou seja, quando um ocorre o outro também ocorre". (CASTRO; FERRARI, 2016, p. 235).
* Problema das regras de associação: "[...]  os atributos das bases transacionais são os itens que aparecem nas transações, o que faz com que tais bases de dados 
  facilmente apresentem alta dimensionalidade, da ordem de centenas e até milhares de itens (atributos)". (CASTRO; FERRARI, 2016, p. 235).

As transações são transformadas em uma tabela de representação binária, onde atributos relacionados ganham o valor 1.  

Para exemplificar, a tabela abaixo apresenta diferentes transações que representam compras feitas em um supermercado (O *TID* é um valor de identificação da transação):  

<img width="837" height="258" alt="Base de dados transacional" src="https://github.com/user-attachments/assets/b822167b-b483-4e34-9f1e-10731c2fa263" />  

*Fonte: CASTRO; FERRARI, 2016, p. 234*  

Essa tabela pode ser representada em uma base binária, inserindo os valores 1 para itens que foram adquiridos na transação, e 0 para os itens que não foram:  

<img width="1372" height="301" alt="Base binária da tabela transacional" src="https://github.com/user-attachments/assets/93a38779-dc18-4580-93d0-8befb293e12b" />  

*Fonte: CASTRO; FERRARI, 2016, p. 235*   

"Dado um conjunto de transações, em que cada transação é composta por um conjunto de itens, uma regra de associação é uma regra X ⟶ Y, na qual X e Y são conjuntos 
de itens. O significado intuitivo de uma regra de associação é que as transações em uma base de dados que contêm itens em X também contêm itens em Y. Assim, as 
regras de associação podem ser vistas como padrões descritivos que representam a probabilidade de que um conjunto de itens apareça em uma transação, dado que outro 
conjunto está presente". (CASTRO; FERRARI, 2016, p. 235).  

### Conceitos centrais em mineração de regras de associação:  

* Suporte: número de transações para as quais uma regra faz a predição correta (utilidade da regra);
* Confiança: número de transações que a regra prediz corretamente entre as transações para as quais ela se aplica (certeza de uma regra);
* Minsup: valor mínimo pré-definido de suporte;
* Minconf: valor mínimo pré-definido de confiança;
* Regra forte: regra que respeita o *minsup* e o *minconf*. 

### Processo de mineração de regras de associação:

<img width="1297" height="407" alt="Processo de mineração de regras de associação" src="https://github.com/user-attachments/assets/1d260078-e316-47dd-9246-2959a4c96583" />  

*Fonte: CASTRO; FERRARI, 2016, p. 240*  

* **Pré-processamento dos dados**: além de todas as outras etapas típicas do pré-processamento, na mineração de regras de associação também se faz necessário transformar
os dados em uma base binária, ou baseada em frequência;

* **Geração do conjunto de itens frequentes**: "itens frequentes são aqueles que satisfazem algum critério mínimo de frequência, por exemplo, itens que aparecem ao menos em determinado número de transações". (CASTRO; FERRARI, 2016, p. 240);

* **Mineração das regras**: "Minerar regras de associação significa encontrar um conjunto de regras de associação entre itens de uma base transacional que 
  satisfazem critérios de qualidade específicos". (CASTRO; FERRARI, 2016, p. 244).
  
  <img width="1692" height="1044" alt="Algoritmos de mineração de regras" src="https://github.com/user-attachments/assets/68700b30-313a-4ab6-9141-24c6716a5abb" />  

  *Fonte: Gerado com Napkin.AI a partir do texto-base e anotações da aula.*  

    * **Algoritmo Apriori**: O Apriori é o método clássico que opera em duas fases: primeiro, a Geração dos Conjuntos de Itens Frequentes e, segundo, a Geração das 
    Regras de Associação. A primeira fase é a mais crítica e funciona de forma iterativa, utilizando o Princípio Apriori: se um conjunto de itens é frequente, todos 
    os seus subconjuntos também devem ser. O algoritmo começa encontrando itens frequentes de tamanho 1, e depois, usa esses resultados para gerar candidatos de 
    tamanho 2, e assim por diante. Essa propriedade permite podar candidatos que contenham subconjuntos infrequentes, reduzindo drasticamente o esforço computacional. 
    O Apriori rastreia a base de dados repetidamente para contar o suporte de cada novo conjunto de candidatos;
    
    * **Algoritmo FP-Growth**: O FP-Growth (Frequent Pattern Growth) foi criado para superar a principal limitação do Apriori: as múltiplas varreduras da base de 
    dados e a grande quantidade de conjuntos de itens candidatos. Ele comprime a informação dos itens frequentes em uma estrutura eficiente baseada em árvore, 
    chamada FP-Tree (Frequent Pattern Tree), em apenas duas varreduras da base. Em seguida, ele minera essa árvore com uma estratégia de "dividir para conquistar" 
    (bottom-up, das folhas à raiz) que evita completamente a geração explícita de conjuntos candidatos. Isso torna o FP-Growth muito mais rápido, especialmente em 
    bases de dados densas e com baixo suporte mínimo.

* **Avaliação**: praticamente todas as regras de associação utilizam o suporte e a confiança das regras para avaliar sua qualidade. O suporte (significância estatística) 
  é utilizado para eliminar regras pouco interessantes ou itens que não atendam a um critério mínimo; já a confiança (acurácia) verifica a ocorrência da parte 
  consequente da regra.  
  Para casos em que as regras, apesar de possuírem pouco suporte, são úteis para a avaliação, utiliza-se o *lift* e a *convicção*.  
  O *lift* incluí a contagem do consequente na medida de confiança, e a *convicção* refere-se à razão entre a diferença do suporte do consequente e o erro de 
  confiança.  
  Além disso, pode-se utilizar a *compreensibilidade* e o *grau de interesse* para avaliar a quantidade relativa de uma regra considerando o tamanho do conjunto de 
  itens (e não apenas a quantidade de transações presentes). O *grau de interesse* se refere à proporção de suporte no antecedente e consequente da regra.

  *OBS: O resumo dos algoritmos de mineração de regras de associação foi feito com auxílio de Inteligência Artificial.*

