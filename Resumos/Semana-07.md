# Semana 7: Detecção de anomalias

## 📽️ Videoaulas:
* [Videoaula 18 - Detecção de anomalias](https://www.youtube.com/watch?v=Qa1TSaoJh14)
* [Videoaula 19 - Métodos para detecção de anomalias](https://www.youtube.com/watch?v=P_6DztW-19M)

---

## 📖 Texto-base:
* **Capítulo 8:** CASTRO, Daniel Gomes; FERRARI, Leandro Nunes de. **Introdução à Mineração de Dados:** Conceitos Básicos, Algoritmos e Aplicações. Rio de Janeiro: Saraiva Uni, 2016;

---

## ✍️ Resumos e anotações:  

* **Anomalia (*outlier*)**: "[...] um objeto que difere do padrão normal esperado, ou, dito de outra forma, um objeto que se diferencia substancialmente de outros objetos da 
  mesma amostra ou grupo. [...] uma anomalia não necessariamente é um erro ou um ruído, ela pode caracterizar um valor ou uma classe bem definida, porém de baixa 
  ocorrência, às vezes indesejada, ou que reside fora de agrupamentos ou classes típicas. [...] A importância da detecção de anomalias deve-se ao fato de que elas 
  normalmente correspondem a dados significativos, às vezes críticos, para a análise". (CASTRO; FERRARI, 2016, p. 269).

* **Principais aplicações da detecção de anomalias**:

  <img width="2376" height="2005" alt="Aplicações de detecção de anomalias" src="https://github.com/user-attachments/assets/4e7e0f3b-1f9c-42b8-b892-428914f17ccf" />

  *Fonte: Gerado com Napkin.AI a partir do texto-base e anotações da aula.* 

### Processo de detecção de anomalias:  

<img width="1266" height="360" alt="Etapas da detecção de anomalias" src="https://github.com/user-attachments/assets/9bfac172-8b45-4ab1-8b31-4f40cb2ccc9c" />  

*Fonte: CASTRO; FERRARI, 2016, p. 273*  

* **Definição de anomalia**: "a maior parte dos algoritmos de detecção de anomalias define algum contorno ou vizinhança ao redor de uma das classes (normal ou 
  anomalia) e, a partir deste, estabelece um limiar de normalidade ou anomalia". (CASTRO; FERRARI, 2016, p. 273).

  As anomalias podem ser detectadas utilizando métodos estatísticos ou algorítmicos.

    * **Métodos estatísticos**: "Os métodos estatísticos para detecção de anomalias normalmente geram um modelo probabilístico dos dados e testam se determinado 
    objeto foi gerado por tal modelo ou não. [...] Se a probabilidade de certo objeto ter sido gerado por esse modelo for muito baixa, então ele é rotulado como
    uma anomalia". (CASTRO; FERRARI, 2016, p. 277). Esses métodos podem ser paramétricos ou não paramétricos:

      * **Métodos paramétricos**: "[...] assumem que os dados são gerados por uma distribuição conhecida e, na maioria das vezes, ajustam um modelo específico 
      aos dados [...]". (CASTRO; FERRARI, 2016, p. 277). São exemplos: Diagrama de caixa; Teste estatístico de Grubbs; Estatística χ2; e Regressão linear.
      * **Métodos não paramétricos**: "[...] não assumem uma distribuição predefinida dos dados nem um modelo específico que deverá ser ajustado aos dados [...]"
      (CASTRO; FERRARI, 2016, p. 285). A análise de histograma é um exemplo desse método.
      
  * **Métodos algorítmicos**: geralmente são baseados em algoritmos para mineração de dados, como aqueles "[...] baseados em medidas de proximidade, em redes neurais 
  artificiais e em algoritmos de aprendizagem de máquina". (CASTRO; FERRARI, 2016, p. 288)


* **Definição do tipo de abordagem**: "Essa escolha normalmente depende da disponibilidade de rótulos dos dados, ou seja, se há objetos rotulados da classe normal 
  e anomalias, em geral se emprega uma abordagem **supervisionada**; além disso, empregamos aprendizagem **não supervisionada** quando não há rótulos conhecidos 
  para os objetos da base. (CASTRO; FERRARI, 2016, p. 273).

    * **Tipo 1 - não supervisionada**: as anomalias são identificadas sem um conhecimento prévio sobre quais classes são normais e quais são anômalas. Normalmente,
    após o processamento dos dados, os pontos que se encontram mais distantes são apontados como potenciais anomalias. Existem duas abordagens comumente empregadas
    neste tipo:
      * **Diagnóstico**: remove as anomalias da base e readéqua o modelo;
      * **Acomodação**: incorpora as anomalias ao modelo e, após isso, emprega um método de classificação.

    * **Tipo 2 - supervisionada**: as técnicas para objetos de classes normais e anômalas são modeladas. As bases de dados precisam ser representativas para ambas       as classes, já que, no geral, as anomalias acontecem com menor frequência (por isso, pode ser necessário inserir anomalias artificiais para balancear o modelo).
    
* **Separação do conjunto de treinamento e teste**: os dados são separados de acordo com os rótulos;

* **Treinamento e teste**: gera-se o modelo;

* **Avaliação de saída**: a anomalia é a classe alvo. Para fazer a avaliação, pode-se usar uma matriz de confusão, bem como alguns indicadores:
  * Taxa de detecção (TVP, ou sensibilidade): porcentagem de anomalias detectadas corretamente (VP/(VP+FN));
  * Taxa de alarmes falsos (TFP): porcentagem de objetos normais detectados incorretamente (FP/(FP+VN));
  * Valor preditivo de uma anomalia (Pr): probabilidade de um objeto ser uma anomalia (VP/(VP+FP));
  * Acurácia (ACC): porcentagem global de objetos corretos ((VP+VN)/(VP+FP+VN+FN));
  * Erro (E): porcentagem global de objetos errados (1-ACC)
  * Curva ROC: Verifica a relação entre a taxa de detecção e a taxa de alarmes falsos. Quando ela é convexa (positiva), significa que o modelo está classificando bem, já que, a taxa de detecção, em geral, é maior que a taxa de alarmes falsos. O exemplo é representado pela figura abaixo:  
  

  <img width="1022" height="625" alt="Curva ROC" src="https://github.com/user-attachments/assets/08b2f808-5c2b-41b1-82c8-10a3b5807f72" />

  *Fonte: CASTRO; FERRARI, 2016, p. 277.*



