# SEMANA 2: Pré-processamento de dados e redução de dados

## 📽️ Videoaulas:
* [Videoaula 3 - Preparação e limpeza dos dados](https://www.youtube.com/watch?v=10kmcTfoxiM)
* [Videoaula 4 - Redução e transformação dos dados](https://www.youtube.com/watch?v=BpsR21apXuM)

---

## 📖 Texto-base:
* **Capítulo 2:** CASTRO, Daniel Gomes; FERRARI, Leandro Nunes de. **Introdução à Mineração de Dados:** Conceitos Básicos, Algoritmos e Aplicações. Rio de Janeiro: Saraiva Uni, 2016;

---

## ✍️ Resumos e anotações:

### Termos e definições:

* Objeto: instância ou registro. Geralmente, cada linha de uma tabela é um objeto (para dados estruturados);
* Atributo: característica ou variável. Nos dados estruturados, costumam ser as colunas da tabela; 
* Dados de treinamento (dados de entrada): dados utilizados na tarefa de mineração;
* Atributos dependentes (variável alvo / variável meta / saída desejada): atributos que representam uma saída, um efeito ou um valor que se deseja testar;
* Atributos independentes: atributos que representam as entradas (a partir deles, se obtém as saídas).

### Pré-processamento dos dados (o processo de preparação da base de dados)

Existem três tipos de problemas com dados em bases de dados:
1. Incompletude: Quando faltam valores de um dado, um objeto ou um atributo de interesse;
2. Inconsistência: Quando existem versões diferentes e conflitantes do mesmo dado, quando o valor do dado está fora do domínio do atributo
  ou quando o valor tem grande discrepância em relação aos outros dados;
3. Ruído: "Um dado ruidoso é aquele que apresenta alguma variação em relação ao seu valor sem ruído e, portanto, ruídos na base de dados
  podem levar a inconsistências." (CASTRO; FERRARI, 2016, p. 27).

<img width="1034" height="382" alt="Problemas com Dados" src="https://github.com/user-attachments/assets/5b8b63e4-0665-4e47-a9fe-851aaaccd877" />  

*Fonte: Gerado com Napkin.AI a partir dos slides e anotações da aula.*  

O **pré-processamento de dados**, portanto, é a etapa de KDD que permite ao analista conhecer e preparar os dados para a mineração. Uma mineração eficiente
e eficaz depende de um bom pré-processamento de dados.  

"A melhor maneira de pré-processar os dados depende de três fatores centrais: os problemas (incompletude, inconsistência e ruído) existentes na base bruta; quais respostas pretendem-se obter das bases, ou seja, qual problema deve ser resolvido; e como operam as técnicas de mineração de dados que serão empregadas". (CASTRO; FERRARI, 2016, p. 34).   

**Etapas do processo de preparação dos dados:**
<img width="1276" height="417" alt="etapas do processo de preparação dos dados" src="https://github.com/user-attachments/assets/73ff89f1-2012-4287-9657-ff42b61eee54" />  
*Fonte: CASTRO; FERRARI, 2016, p. 35*  

* Na etapa de **limpeza**, valores ausentes são imputados, ruídos são removidos e inconsistências são tratadas.  
* O processo de unir dados de diferentes fontes em uma única base de dados faz parte da etapa de **integração**.  
* A **redução** é utilizada para reduzir a dimensão da base de dados.  
* Durante a **transformação** os dados são padronizados para que possam ser aplicadas diferentes técnicas de mineração.  
* Por fim, a etapa de **discretização** permite que os métodos que trabalham somente com atributos nominais possam ser utilizados.  

### Limpeza dos dados

"[...] as ferramentas para a limpeza de dados atuam no sentido de imputar valores ausentes, suavizar ruídos, identificar valores discrepantes (*outliers*) e corrigir inconsistências". (CASTRO; FERRARI, 2016, p. 36).

* Valores ausentes:
Tratam-se de valores ignorados, e costumam ser representados por um código de ausência. Imputar um valor ausente significa substituí-lo por outro valor que possa representá-lo. Esse valor não pode enviesar a base de dados.

  **Métodos tradicionais de imputação de valores ausentes:**
    - Ignorar o objeto: remover, da base de dados, os objetos que possuem valores ausentes. Se a quantidade de valores ausentes for grande, pode causar uma redução significativa da base;
    - Imputar manualmente os valores ausentes: escolher, de forma empírica, um valor a ser imputado para cada valor ausente. Pode ser impraticável se a base de dados for muito grande;
    - Usar uma constante global para imputar o valor ausente: substituir todos os valores ausentes de um atributo por uma constante única. Deve ser feito com cautela pois, no momento da mineração, o algoritmo pode considerar esse valor como um conceito relevante, podendo causar enviesamento da análise;
    - Imputação do tipo *hot-deck*: utiliza-se o valor de outro objeto selecionado aleatoriamente para preencher um valor ausente. Esse objeto deve pertencer ao mesmo atributo do valor ausente;
    - Imputar de acordo com a última observação: é necessário ordenar a base de dados de acordo com um ou mais atributos. Após isso, o valor ausente é imputado com o valor do objeto imediatamente anterior à ele;
    - Usar a média ou a moda de um atributo ou de todos os valores da mesma classe: utilizar a média (para valores numéricos) ou a moda (para valores categóricos) para imputar valores ausentes. É uma técnica muito utilizada, porém, bastante sensível à *outliers*; 
    - Usar modelos preditivos para imputar um valor ausente: qualquer modelo preditivo pode ser usado para estimar e imputar um valor ausente.
 
  **O tratamento de valores ausentes deve considerar quatro passos:**
  <img width="1291" height="287" alt="passos para o tratamento de valores ausentes" src="https://github.com/user-attachments/assets/c26e80f4-45f3-40b0-aef5-d2dfc92b2e40" />
  *Fonte: CASTRO; FERRARI, 2016, p. 38*

* Valores ruídosos:
"Os erros acumulados e outras formas de distorção dos dados em relação aos seus valores 'reais' são chamados de ruído". (CASTRO; FERRARI, 2016, p. 38). É ideal que os algoritmos de mineração consigam aprender a caracterizar os dados sem aprender o ruído existente neles. Para isso, são utilizadas as técnicas de **suavização** de atributos numéricos: encaixotamento, agrupamento e aproximação.
  - Encaixotamento (*binning*): nesta técnica, os valores de um atributo são distribuídos em um conjunto de caixas (*bins*). Esse encaixotamento pode ser feito utilizando dois métodos: encaixotamento de mesma largura ou de mesma frequência. "No encaixotamento de mesma largura, o intervalo de cada caixa tem o mesmo tamanho, ao passo que, no encaixotamento de mesma frequência, a quantidade de objetos em cada caixa é a mesma". (CASTRO; FERRARI, 2026, p. 40);
  - Agrupamento: o objetivo é encontrar grupos de objetos similares entre si. Cada um desses grupos pode ser identificado por um objeto que o represente. Se esse objeto for o mais central do grupo, ele é chamado de *medoide*, se for um objeto artificial usado para representar o valor médio daquele grupo, então, é chamado de *centroide*;
  - Aproximação: é feita utilizando algum tipo de função ou modelo de aproximação. Após definir e aplicar esse modelo, o valor da função para o ponto desejado é selecionado (esse valor é utilizado no lugar do valor real do atributo).

* Dados inconsistentes:
  "[...] a consistência de um dado está relacionada à sua discrepância em relação a outros dados ou a um atributo, e tal consistência influencia na validade, na utilidade e na integridade da aplicação de mineração de dados". (CASTRO; FERRARI, 2016, p. 42). São formas de resolver inconsistências:
  - A análise manual dos dados através de rotinas que verificam, por exemplo, se os valores de todos os objetos de um atributo pertencem a um domínio específico;
  - A utilização de gráficos que facilitam a visualização e identificação de dados inconsistentes. 

### Integração dos dados

Antes de aplicar alguma técnica de mineração de dados é essencial concatenar todos os dados necessários à análise em uma única base. Essa integração, no entanto, pode acabar resultando em alguns problemas, como:

* Redundância: quando o mesmo dado aparece em dois locais diferentes da base, ou quando um determinado objeto ou atributo pode ser obtido através de outro objeto ou atributo desta base (por exemplo: idade é um atributo que pode ser obtido através da data de nascimento);
* Duplicidada: é um tipo de redundância. Ocorre quando objetos ou atributos estão repetidos na base de dados;
* Conflitos: acontecem quando diferentes valores aparecem em diferentes fontes de dados, porém, estes representam a mesma entidade (por exemplo: uma distância pode ser dada em quilometros em uma base e em metros em outra).

### Redução dos dados

"[...] o aumento do número de objetos e da dimensão do espaço (número de atributos na base) pode fazer com que os dados disponíveis se tornem esparsos e as medidas matemáticas usadas na análise tornem-se numericamente instáveis. Além disso, uma quantidade muito grande de objetos e atributos pode tornar o processamento dos algoritmos de mineração muito complexo, assim como os modelos gerados". (CASTRO; FERRARI, 2016, p. 44).  
As tecnicas de redução, portanto, são necessárias e podem ser utilizadas tanto para reduzir a quantidade de objetos de uma base de dados, quanto para reduzir sua dimensionalidade (quantidade de atributos). São métodos de resução de dados:
* Seleção de atributos (características): reduz a dimensionalidade ao remover atributos pouco relevantes ou redundantes;
* Compreensão de atributos: reduz a dimensionalidade ao aplicar algoritmos de codificação ou transformação de dados. Um método de compreensão de atributos conhecido é a *análise de componentes principais* (*Principal Component Analysis - **PCA***), "[...] um procedimento estatístico que converte um conjunto de objetos com atributos possivelmente correlacionados em um conjunto de objetos com atributos linearmente descorrelacionados, chamados de componentes principais" (CASTRO; FERRARI, 2016, p. 45);
* Redução do número de dados: dados são removidos, substituídos ou estimados por representações mais simples. Essas representações podem ser feitas através de modelos paramétricos (apenas os parâmetros do modelo são armazenados, e não os dados) ou não paramétricos (são usados agrupamentos, amostragens ou histogramas);
* Discretização: os valores são substituídos por intervalos ou níveis conceituais.

### Transformação dos dados

"Outro tipo comum de problema das bases de dados brutas é a não uniformidade dos atributos, ou seja, alguns atributos podem ser numéricos, outros categóricos, e os domínios de cada atributo podem ser muito diferentes. [...] Os métodos de transformação de dados visam modificar ou consolidar os dados em formas apropriadas aos processos de mineração". (CASTRO; FERRARI, 2016, p. 50). 
* Padronização: o principal objetivo é padronizar diferentes unidades e escalas dos dados. Para isso, é usual padronizar as fontes, capitalizando elas, não utilizar caracteres especiais, padronizar formatos de datas e documentos, e converter unidades de medida de forma que somente uma seja utilizada;
* Normalização: é empregada de forma que transforme os dados para que sejam mais apropriados à aplicação de algum algoritmo de mineração. São exemplos: Normalização Min-Max, Normalização pelo escore-z, Normalização pelo escalonamento decimal, Normalização pelo range-interquartil.

### Discretização

"Alguns algoritmos de mineração operam apenas com atributos categóricos e, portanto, não podem ser aplicados a dados numéricos. Nesses casos, atributos numéricos podem ser discretizados, dividindo o domínio do atributo em intervalos e ampliando a quantidade de métodos de análise disponíveis para aplicação. Além disso, a discretização reduz a quantidade de valores de um dado atributo contínuo, facilitando, em muitos casos, o processo de mineração". (CASTRO; FERRARI, 2016, p. 52). São métodos de discretização:
* Dividir o domínio de um atributo em um número predeterminado de intervalos iguais;
* Encaixotamento;
* Análise de Histograma (similar ao encaixotamento, porém são utilizadas as faixas do histograma para definir os intervalos de valores);
* Agrupamento;
* Discretização baseada em entropia ("A discretização baseada em entropia pode reduzir a quantidade de dados usando informações sobre as classes dos dados disponíveis, aumentando a chance de que os limites dos intervalos ocorram em regiões que podem contribuir para a acurácia da classificação". (CASTRO; FERRARI, 2016, p. 54).). 
