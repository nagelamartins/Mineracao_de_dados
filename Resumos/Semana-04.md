# Semana 4: Métodos de classificação supervisionada

## 📽️ Videoaulas:
* [Videoaula 9 - Classificação de dados](https://www.youtube.com/watch?v=MU14rYb3l8c)
* [Videoaula 10 - Algoritmos de classificação](https://www.youtube.com/watch?v=de_lvW0VMMw)

---

## 📖 Texto-base:
* **Capítulo 5:** CASTRO, Daniel Gomes; FERRARI, Leandro Nunes de. **Introdução à Mineração de Dados:** Conceitos Básicos, Algoritmos e Aplicações. Rio de Janeiro: Saraiva Uni, 2016;

---

## ✍️ Resumos e anotações:

A tarefa de **predição** pode ser definida através do ato de construir um modelo capaz de predizer os valores de saída de novos registros, 
utilizando como base os registros históricos que já possuem um rótulo de classe. Ela pode ser classificada em dois tipos: **classificação** ou 
**estimação**.   

<img width="1596" height="576" alt="Tipos de predição" src="https://github.com/user-attachments/assets/6ae6fecb-b62f-492b-ac85-215980053df5" />   

*Fonte: Gerado com Napkin.AI a partir do texto-base e anotações da aula.*  

O desenvolvimento de um **modelo preditivo** possuí duas etapas principais:
* Treinamento: um preditor é gerado a partir de um conjunto de dados rotulados (a saída desejada já é conhecida). Esse preditor deve ser capaz de descrever e distinguir um conjunto predeterminado de classes e valores;
* Teste: o desempenho do preditor é avaliado a partir do seu uso em dados não utilizados durante a etapa de treinamento.

Na prática, existe uma função que relaciona aquilo que é observado ao resultado que se deseja prever. Caso se conheçam apenas amostras dentro
dessa função, haverá um conjunto limitado de dados de treinamento, que muitas vezes podem possuir ruídos. Durante a **Aprendizagem Supervisionada** procura-se uma função substituta chamada de **modelo de aproximação**, que seja o mais próximo possível da função real e desconhecida, medindo a distância entre a função real e o modelo de aproximação. Essa distância é chamada de **erro**.  

Existem dois erros importantes para a Aprendizagem Supervisionada:
* Erro de representação: "[...] o erro vai depender da adequação e do nível de flexibilidade do modelo preditivo em relação aos dados de treinamento, pois nem sempre ele é suficientemente adequado para representar os dados". (CASTRO; FERRARI, 2016, p. 150);
* Erro de generalização: "Esse erro surge, por exemplo, quando o modelo é treinado em excesso e absorve os ruídos dos dados de treinamento, sofrendo de uma sobregeneralização dos resultados". (CASTRO; FERRARI, 2016, p. 151).

A figura exemplifica esses erros. A figura (a) apresenta um erro de representação, onde o modelo não é flexível o suficiente para representar o
conjunto dos objetos. A figura (b) indica um erro de generalização: o modelo pode absorver os ruídos contidos nos dados e apresentar baixa 
capacidade de generalização. Por fim, a figura (c) apresenta um bom equílibrio entre *bias-variância*, ou seja, "[...] possui um baixo erro de 
treinamento graças à flexibilidade do modelo e ao mesmo tempo não 'interpola' os ruídos da base". (CASTRO; FERRARI, 2016, p. 151)  

<img width="1285" height="472" alt="Erros na aprendizagem supervisionada" src="https://github.com/user-attachments/assets/31aa4033-9591-425a-a0e6-cd32bb1f9536" />  

*Fonte: CASTRO; FERRARI, 2016, p. 151*  

"Esse equilíbrio entre o erro de representação e o erro de generalização é conhecido como o *dilema bias-variância* ou *efeito bias-variância*,
e constitui um problema central em aprendizagem supervisionada. O treinamento, portanto, feito de modo que o modelo capture as regularidades 
estatísticas dos dados de treinamento, mas também generalize bem para dados desconhecidos". (CASTRO; FERRARI, 2016, p. 151). O método mais usual
para manter esse equilíbrio é o uso da **validação cruzada**.  

Nesse método, os dados são divididos em conjuntos de treinamento e teste. O modelo é treinado iterativamente com o conjunto de 
treinamento e avaliado periodicamente no conjunto de teste. O treinamento é interrompido se o erro de teste aumentar em iterações consecutivas, e os parâmetros do modelo com o melhor desempenho até o momento da interrupção são escolhidos como o resultado final.  

"Uma forma bastante comum de validação cruzada em mineração de dados é a chamada **validação cruzada em k-pastas** (k-fold cross-validation), 
que consiste em dividir a base de dados em k subconjuntos, sendo k–1 pastas para treinamento e 1 pasta para teste. Esse processo de treinamento 
e teste é repetido com todos os k subconjuntos, e a média dos desempenhos para as bases de treinamento e as bases de teste é adotada como 
indicador de qualidade do modelo". (CASTRO; FERRARI, 2016, p. 157). É usual utilizar 10 pastas para estimar o erro, embora ainda existirem debatessobre o número adequado de pastas. "[...] também é usual executar a validação em 10-pastas 10 vezes, o que implica treinar o algoritmo 100 vezes para uma base que corresponde a 9/10 da base completa e testá-lo 100 vezes para uma base que corresponde a 1/10 da base completa". (CASTRO; FERRARI, 2016, p. 158).   

Outra forma comum de validação, especialmente em bases de dados com poucos objetos, é a **validação cruzada leave-one-out** (LOOCV). Nela, apenas um objeto por vez é utilizado para teste, enquanto os outros objetos são utilizados para treinamento.   

### Avaliação de desempenho da tarefa de Classificação

"Classificação é a tarefa preditiva de identificação da classe à qual um objeto pertence. Para que isso seja possível, um modelo de classificação precisa ser construído, o que é feito com base em um conjunto de treinamento previamente rotulado. O desempenho do classificador depende fortemente de sua flexibilidade (bias) e da qualidade de seu treinamento (variância). Entretanto, não existe um classificador que seja melhor que todos os outros para todos os problemas de classificação". (CASTRO; FERRARI, 2016, ps. 158 e 159).   

Para isso, as medidas de desempenho dos classificadores poderão fornecer um valor quantitativo de sua qualidade, e devem considerar duas 
categorias de divisão de problemas: **problemas binários** e **problemas multiclasses**.

* **Problemas binários:** Existem apenas duas classes e, no geral, existe uma classe cujo valor se pretende predizer, chamada de *classe-alvo*.
  A classe-alvo, muitas vezes é chamada de *classe positiva* e, em oposição, leva ao surgimento de uma *classe negativa*. Essas classes permitem
  definir alguns termos referentes à elas:

   <img width="1357" height="490" alt="VP, VN, FP, FN" src="https://github.com/user-attachments/assets/cda7cea9-f524-4091-ae54-113cae83352b" />
  
  *Fonte: CASTRO; FERRARI, 2016, p. 160*

  A **Matriz de confusão** é uma forma de representar essas classes, apresentando o desempenho de um algoritmo de classificação binária:

   <img width="1186" height="287" alt="Matriz de confusão" src="https://github.com/user-attachments/assets/af97e31d-03eb-48bf-a10c-a9f60c42ba0b" />

  *Fonte: CASTRO; FERRARI, 2016, p. 160*

  A partir dos valores apresentados na matriz de confusão, algumas taxas são obtidas:
    - Taxa de verdadeiros positivos (TVP): percentual de objetos positivos classificados corretamente (TVP = VP / VP + FN);
    - Taxa de falsos positivos (TFP): percentual de objetos negativos classificados como positivos (TFP = FP / FP + VN);
    - Acurácia (ACC): taxa global de sucesso do algoritmo (número de classificações corretas dividido pelo número total de classificações);
    - Taxa de Erro (E): 1 - ACC;
    - Precisão (precision-Pr): foca na confiabilidade das previsões, mede a qualidade ou exatidão do algoritmo;
    - Revocação (recall-Re): foca na cobertura ou completude de um algoritmo;
      
      (Para entender melhor as medidas de Precisão e Revocação, imagine que uma equipe de buscas está procurando por pessoas perdidas dentro de uma floresta onde, ao mesmo tempo, existem também turistas acampando. A *precisão* responderá a pergunta: *"De todos os que a equipe de buscas trouxe de volta, quantos eram os que realmente estavam perdidos?"*; enquanto a *revocação* responderá: "*De todas as pessoas que estavam realmente desaparecidas, quantas a equipe conseguiu encontrar?"*);
    - Score-F: medida que busca equilibrar a Precisão e a Revocação (F = 2 * Pr * Re / (Pr + Re));
    - Estatística Kappa: mede a concordância entre as previsões do seu modelo e os valores reais, descontando a concordância que ocorreria puramente por acaso.

* **Problemas Multiclasses:** Bases de dados com múltiplas classes. "Em um problema de predição multiclasse, a matriz de confusão possui nas linhas as classes originais e nas colunas, as classes preditas, sendo uma linha e uma coluna para cada classe. [...] um bom classificador deve apresentar números maiores na diagonal principal e números pequenos, idealmente zero, fora dela". (CASTRO; FERRARI, 2016, p. 164).

  A figura apresenta uma Matriz de confusão para um problema de classificação pra múltiplas classes:

  <img width="1363" height="387" alt="Matriz de confusão múltiplas classes" src="https://github.com/user-attachments/assets/1b4d2ece-efee-4c81-b15c-713c4ba04418" />

  *Fonte: CASTRO; FERRARI, 2016, p. 164*








