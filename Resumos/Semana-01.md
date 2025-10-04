# SEMANA 1: Introdução à mineração de dados e descoberta de conhecimento

## 📽️ Videoaulas:
* [Videoaula 1 - Introdução à Mineração de Dados](https://www.youtube.com/watch?v=S8eEPpLyTIA)
* [Videoaula 2 - Descoberta de conhecimento em bases de dados (KDD)](https://www.youtube.com/watch?v=61Di3FSRiG8)

---

## 📖 Textos-base:
* **Capítulo 1:** CASTRO, Daniel Gomes; FERRARI, Leandro Nunes de. **Introdução à Mineração de Dados:** Conceitos Básicos, Algoritmos e Aplicações. Rio de Janeiro: Saraiva Uni, 2016;
* **Capítulo 12:** MORAIS, Izabelly Soares de; GONÇALVES, Priscila de F.; LEDUR, Cleverson L.; *et al*. **Introdução a Big Data e Internet das Coisas (IoT)**. Porto Alegre: SAGAH, 2018.

---

## ✍️ Resumos e anotações:

A primeira semana da disciplina focou em explorar a diferença entre **dado, informação e conhecimento**. Um **dado** é um valor bruto e sem contexto. 
Quando inserimos um contexto a esse dado, ele se torna uma **informação**. Já o **conhecimento** é gerado a partir de insights e padrões extraídos dessa informação.  
Além disso, a aula apresentou os diferentes tipos de dados:  
* Dados Estruturados: organizados em um formato pré-definido, como tabelas. Eles são os mais fáceis de organizar e trabalhar.
* Dados Semiestruturados: possuem alguma organização, mas não uma estrutura rígida. Um bom exemplo são arquivos XML ou JSON.
* Dados Não Estruturados: não possuem uma estrutura específica, como textos, áudios e vídeos.
<img width="786" height="390" alt="Tipos de Dados" src="https://github.com/user-attachments/assets/9de0feee-0600-45a0-b21a-14d205ebaa12" />

*Fonte: Gerado com Napkin.AI a partir dos slides e anotações da aula.*

Com o avanço da tecnologia, a capacidade de coletar e armazenar dados superou nossa capacidade de analisá-los, resultando em um problema de superabundância de dados.
Como apontado por Castro e Ferrari (2016, p. 4), "[...] frequentemente os dados não podem ser analisados manualmente em virtude de fatores como grande quantidade de registros, elevado número
de atributos, valores ausentes, presença de dados qualitativos e não quantitativos, entre outros."  

Nesse contexto, surge o KDD (*Knowledge Discovery in Databases*), um processo usado para transformar grandes volumes de dados em conhecimento. 
Esse processo é composto por etapas que podem ser revisitadas e modificadas.  
<img width="1092" height="528" alt="Etapas de KDD" src="https://github.com/user-attachments/assets/8dba6b74-418d-4112-be0a-4b5771a00feb" />  
*Fonte: Gerado com Napkin.AI a partir dos slides e anotações da aula.*  

A **Mineração de Dados** é, portanto, uma das etapas do processo KDD. Seu objetivo é aplicar algoritmos para extrair conhecimento de dados que já foram pré-processados. 
Fazendo um paralelo com a mineração tradicional:  
* A mina é o **banco de dados**.
* A substância a ser extraída são os **dados**.
* Os **algoritmos** são as ferramentas para fazer essa extração.
* O mineral é a **informação**.
* O resultado de todo o processo é o **conhecimento**.  

### Principais tarefas da Mineração de Dados:  
<img width="865" height="280" alt="Tipos de Tarefas" src="https://github.com/user-attachments/assets/88739ba6-9b1a-4daa-86f9-5e1138ec16c1" />  

*Fonte: Gerado com Napkin.AI a partir dos slides e anotações da aula.*  

A **Análise Descritiva dos Dados** utiliza "[...] ferramentas capazes de medir, explorar e descrever características intrínsecas aos dados" (CASTRO; FERRARI, 2016, p. 8). Elas permitem, portanto, sumarizar e compreender os objetos da base de dados, bem como seus atributos.

Já a **Predição** se refere à "[...] construção e ao uso de um modelo para avaliar a classe de um objeto não rotulado ou para estimar o valor de um ou mais atributos de dado objeto."(CASTRO; FERRARI, 2016, p. 8). Quando se trata de construir e usar um modelo para classificar o objeto, então, utiliza-se da **Classificação**, já quando o modelo é utilizado para estimar o valor desse objeto, então, a tarefa é a **Regressão** ou **Estimação**.  

*"Exemplos de tarefas de classificação incluem identificação de spams, classificação de objetos, atribuição de crédito e detecção de fraudes. Exemplos de tarefas de estimação incluem predição de produtividade de grãos, estimativa de desempenho de atletas, estimativa de crédito, estimativa de valores futuros em bolsas de valores e previsão do clima".* (CASTRO; FERRARI, 2016, p. 8).  

A tarefa de **Agrupamento** consiste em "[...] separar (particionar ou segmentar) um conjunto de objetos em grupos (do inglês clusters) de objetos similares." (CASTRO; FERRARI, 2016, p. 9). Um exemplo de aplicação dessa tarefa, apresentado na aula, é a idenfificação de perfis de clientes para a análise de crédito: eles podem ser agrupados de acordo com a idade, a renda ou o histórico de pagamentos, por exemplo. 

Já na tarefa de **Associação** o principal objetivo é "[...] encontrar relações entre os atributos (ou variáveis), e não entre os objetos". (CASTRO; FERRARI, 2016, p. 9). Um exemplo prático disso é no comércio eletrônico: se clientes que compram sapatos também costumam comprar meias, um algoritmo de associação pode sugerir meias para todos que adicionaram sapatos ao carrinho de compras.  

Por fim, a **Detecção de Anomalias** se preocupa em identificar "[...] objetos que não seguem o comportamento ou não possuem a característica comum dos dados ou de um modelo que os represente". (CASTRO; FERRARI, 2016, p. 10). Essa tarefa é comumente usada na identificação de fraudes em cartões de crédito.

### Dicas para uma Mineração de Dados eficiente e eficaz:
Para uma mineração de dados eficiente e eficaz, os autores Castro e Ferrari (2016, ps. 11 e 12) oferecem um guia prático. Eles explicam que, embora o guia sirva como uma base, ele não inclui todas as dicas possíveis para o processo:  
1. Estabelecer significância da mineração: Avalie se os resultados são confiáveis e úteis. A confiabilidade (significância estatística) depende da qualidade dos seus dados e métodos, enquanto a utilidade (significância prática) se refere a se a análise pode realmente ser usada para tomar decisões.  
2. Reconhecer que as características da base de dados influenciam todos os resultados: Reconheça que as características da sua base de dados (quantidade de dados, ausência de valores, etc.) afetam diretamente os resultados da mineração. Um pré-processamento inadequado pode invalidar toda a sua análise.  
3. Necessidade de conhecer os dados: Antes de começar a mineração, é fundamental fazer uma análise preliminar para entender os dados. Use técnicas de estatística descritiva (como a média e análise de componentes principais) para ter uma visão geral e identificar possíveis problemas.  
4. Buscar pela parcimônia: Ao escolher entre diferentes modelos, prefira a solução mais simples e menos complexa, desde que ela tenha um bom desempenho. Um modelo mais simples é geralmente mais fácil de entender, implementar e manter.  
5. Verificar os erros: Analise o desempenho dos seus algoritmos para entender os erros. Use métricas de avaliação específicas para cada tipo de tarefa (agrupamento, predição, etc.) para identificar por que o algoritmo pode estar errando e use essa informação para melhorar o processo.  
6. Validar seus resultados: Não confie apenas em um único resultado. Valide suas análises usando diferentes técnicas, comparando os resultados ou, idealmente, consultando um especialista na área. Isso confirma se os resultados fazem sentido e são de alta qualidade.
