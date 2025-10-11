# Semana 3: Análise descritiva de dados

## 📽️ Videoaulas:
* [Videoaula 6 - Análise descritiva de dados](https://www.youtube.com/watch?v=42ArF0YCWm8)
* [Videoaula 7 - Exemplos de análise de dados](https://www.youtube.com/watch?v=wQ8aVVF3Dgo)

---

## 📖 Texto-base:
* **Capítulo 3:** CASTRO, Daniel Gomes; FERRARI, Leandro Nunes de. **Introdução à Mineração de Dados:** Conceitos Básicos, Algoritmos e Aplicações. Rio de Janeiro: Saraiva Uni, 2016;

---

## ✍️ Resumos e anotações:

"A análise descritiva de dados (ADD) é utilizada para **descrever, simplificar ou sumarizar** as principais características de uma base de dados, 
formando o princípio de qualquer análise quantitativa de dados. A diferença entre a análise descritiva e a mineração propriamente dita é que a
ADD visa **descrever e encontrar** o que há nos dados, ao passo que os algoritmos de mineração buscam conclusões que extrapolam os dados e permitem 
inferir algo a partir deles". (CASTRO; FERRARI, 2016, p. 60).  

Essas análises se dividem em:
* Univariadas: descrição da distribuição de um único atributo. Seu principal objetivo é organizar os dados em distribuições de frequências,
 visualizar o atributo através de gráficos, ou determinar os valores de tendência central e de variação;
* Bivariadas: descrição da relação entre dois atributos, buscando explicar as causas e relações entre eles.

### Processo de análise descritiva dos dados

<img width="1213" height="182" alt="processo de ADD" src="https://github.com/user-attachments/assets/d82d917b-4e0f-4102-8c42-740e0f0080de" />  

*Fonte: CASTRO; FERRARI, 2016, p. 62*   

* **Organizar os dados usando distribuições de frequência:**
  
  "Uma distribuição de frequências mostra um resumo dos dados agrupados em classes mutuamente exclusivas e o número de ocorrências (frequência)
  em cada faixa, e pode ser utilizada tanto com dados numéricos quanto categóricos". (CASTRO; FERRARI, 2016, p. 63).
  Algumas **definições** são importantes para construir uma distribuição de frequência:
    - Classes: intervalos (grupos) que dividem os valores dos atributos;
    - Limites inferiores de classes: os menores números que podem pertencer às classes;
    - Limites superiores de classes: os maiores números que podem pertender às classes;
    - Fronteiras de classes: números usados para separar as classes;
    - Pontos médios das classes: média dos valores que pertencem à uma classe;
    - Amplitude de classes: "diferença entre dois limites inferiores de classe consecutivos ou duas fronteiras inferiores de classes consecutivas"
    (CASTRO; FERRARI, 2016, p. 63);
    - Frequência relativa: "frequência absoluta de classe dividida pela soma de todas as frequências absolutas". (CASTRO; FERRARI, 2016, p. 63);
    - Frequência acumulada: "soma de uma frequência e todas que a antecedem na distribuição de frequências". (CASTRO; FERRARI, 2016, p. 63).
 
  **Procedimento básico** para construir uma distribuição de frequências:
  <img width="1808" height="1368" alt="Processo de Criação de Distribuições de frequência" src="https://github.com/user-attachments/assets/4943dfd4-fdfb-43ce-83f1-3c1c542ba410" />
  *Fonte: Gerado com Napkin.AI a partir do texto-base e anotações da aula.*

* **Apresentar os dados usando técnicas de visualização:**

  "Visualização dos dados corresponde à apresentação de dados em forma pictórica ou gráfica (representações visuais) com o objetivo de se
  entender a natureza das distribuições dos dados, extrair conhecimento mais fácil e rapidamente e permitir o compartilhamento desse
  conhecimento de maneira mais direta entre diferentes pessoas e entidades". (CASTRO; FERRARI, 2016, p. 65).
  Algumas técnicas de visualização dos dados incluem: histogramas, polígonos de frequência, ogivas, gráficos de Pareto, gráficos de setores,
  e gráficos de dispersão.
    - Histograma: representação das frequências tabuladas por meio de um gráfico de barras. Sua base é dividida em intervalos que correspondem às classes da distribuição de frequência. Pode ser utilizado para frequência relativa ou absoluta.
      
      Exemplo:
  
      <img width="400" height="auto" alt="histograma" src="https://github.com/user-attachments/assets/8fc9028a-f2cf-4c12-8129-6252256ac5c2" />
    
      *Fonte: CASTRO; FERRARI, 2016, p. 65*
    - Polígono de frequências: trata-se de segmentos de reta ligados pelos pontos médios de cada classe. Também representam uma distribuição de dados. São úteis para comparar um conjunto de dados e analisar a forma da distribuição de frequência.
     
      Exemplo:
   
      <img width="400" height="auto" alt="Polígono de frequências" src="https://github.com/user-attachments/assets/07d6a1b3-c282-45d2-a357-df7931a4d536" />
  
       *Fonte: CASTRO; FERRARI, 2016, p. 66*

    - Ogiva: gráfico de linhas que representa as frequências acumuladas.
 
      Exemplo:

      <img width="400" height="auto" alt="Ogiva" src="https://github.com/user-attachments/assets/cb956582-8662-4a78-8860-32dd0f18d205" />

      *Fonte: CASTRO; FERRARI, 2016, p. 66*

    - Gráfico de Pareto: gráfico de barras dispostas em ordem decrescente de frequências. Usado para dados qualitativos.  

       Exemplo:

      <img width="400" height="auto" alt="Gráfico de Pareto" src="https://github.com/user-attachments/assets/c182aee3-6aef-4d86-ad9c-bae72db32a00" />

      *Fonte: CASTRO; FERRARI, 2016, p. 67*

    - Gráfico de setores: gráfico circular dividido em setores de tamanhos correspondentes ao valor da variável. Também conhecido como gráfico de torta ou pizza.
 
      Exemplo:

      <img width="400" height="auto" alt="Gráfico de setores" src="https://github.com/user-attachments/assets/dc092376-bcf6-414e-b40f-061a2a01a701" />

      *Fonte: CASTRO; FERRARI, 2016, p. 67*

  - Gráfico de dispersão: "[...] tipo de diagrama matemático que usa coordenadas cartesianas para apresentar os valores de dois atributos de uma base de dados, que são apresentados como uma coleção de pontos, cada um contendo o valor de um atributo no eixo horizontal e o valor de outro atributo no eixo vertical". (CASTRO; FERRARI, 2016, p. 67)
 
    Exemplo:

    <img width="400" height="auto" alt="Gráfico de dispersão" src="https://github.com/user-attachments/assets/3a46d221-0d9d-48eb-8c58-033a60aa62a2" />

    *Fonte: CASTRO; FERRARI, 2016, p. 68*

* **Calcular medidas de tendência central, variação e associação:**
  
  Usadas para resumir as informações de uma distribuição ou sumarizar a informação contida em uma base de dados.
    - Medidas de tendência central: valor central ou típico de um atributo. As mais comuns são: média, mediana, ponto médio e moda;
    - Medidas de dispersão: "[...] expressam quantitativamente a variabilidade, ou dispersão, dos dados. Dito de outra forma, as medidas de dispersão denotam quanto uma distribuição está compacta ou alongada". (CASTRO; FERRARI, 2016, p. 70). As medidas mais importantes relacionadas à dispersão são: amplitude e desvio padrão;
    - Medidas de forma: trazem informações sobre o formato da distribuição. Por exemplo, quando uma assimetria é negativa, o formato da distribuição tende à direita e, quando positiva, tende à esquerda. Outro conceito importante para a forma da distribuição é a *curtose*, "[...] a medida de dispersão que caracteriza o pico ou achatamento da curva da função de distribuição de probabilidade de um atributo. Se a curtose for igual a zero, então o pico da curva possui achatamento similar à distribuição normal; se for positiva, então o pico da função é mais afunilado e a função é mais concentrada; e se ela for negativa, então o pico da função é mais achatado e a função é mais dispersa". (CASTRO; FERRARI, 2016, p. 73);
    - Medidas de posição relativa: usadas para comparar valores entre dois conjuntos de dados, ou entre valores de um mesmo conjunto de dados. Para conjuntos de dados diferentes, utiliza-se o *escore z*, para o mesmo conjunto de dados, utiliza-se os *quartis*;
    - Medidas de associação: determina a existência de uma dependência entre dois atributos diferentes. "[...] se dois atributos desviam de suas respectivas médias de maneira similar, é possível dizer que eles são covariantes [...]" (CASTRO; FERRARI, 2016, p. 76). Essa covariância pode ser representada em uma *Matriz de covariância*, onde "[...] as variâncias aparecem na diagonal principal da matriz, que é quadrada e simétrica, e as covariâncias aparecem fora da diagonal". (CASTRO; FERRARI, 2016, p. 76).
      
      Exemplos:

      <img width="1000" height="auto" alt="Correlação positiva" src="https://github.com/user-attachments/assets/6b4dca05-d734-41d3-a6a5-192f0326cae5" />

      <img width="1000" height="auto" alt="Correlação positiva e negativa" src="https://github.com/user-attachments/assets/93e6ec8c-49e0-40c8-8016-e069f8a410e3" />

      <img width="1000" height="auto" alt="Correlação negativa" src="https://github.com/user-attachments/assets/6987f2ac-baad-499a-a8aa-03870b126cae" />

      <img width="1000" height="auto" alt="Correlação não linear e ausência de correlação" src="https://github.com/user-attachments/assets/44b6dd6b-0ae8-44ff-942e-956518d3df7b" />

      *Fonte: CASTRO; FERRARI, 2016, ps. 77 e 78*

      




   

      

  

    




