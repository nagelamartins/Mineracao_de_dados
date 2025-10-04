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
* Dados Semi-estruturados: possuem alguma organização, mas não uma estrutura rígida. Um bom exemplo são arquivos XML ou JSON.
* Dados Não Estruturados: não possuem uma estrutura específica, como textos, áudios e vídeos.
<img width="786" height="390" alt="Tipos de Dados" src="https://github.com/user-attachments/assets/b303549e-d707-4ffe-b684-6ee493312366" />

*Fonte: Gerado com Napkin.AI a partir dos slides e anotações da aula.*

Com o avanço da tecnologia, a capacidade de coletar e armazenar dados superou nossa capacidade de analisá-los, resultando em um problema de superabundância de dados.
Como apontado por Castro e Ferrari (2016, p. 4), "[...] frequentemente os dados não podem ser analisados manualmente em virtude de fatores como grande quantidade de registros, elevado número
de atributos, valores ausentes, presença de dados qualitativos e não quantitativos, entre outros."  

Nesse contexto, surge o KDD (*Knowledge Discovery in Databases*), um processo usado para transformar grandes volumes de dados em conhecimento. 
Esse processo é composto por etapas que podem ser revisitadas e modificadas.  
<img width="1093" height="528" alt="Etapas de KDD" src="https://github.com/user-attachments/assets/e114bf87-e5d2-4015-9acb-6b08c6d2765f" />
*Fonte: Gerado com Napkin.AI a partir dos slides e anotações da aula.*  

A **Mineração de Dados** é, portanto, uma das etapas do processo KDD. Seu objetivo é aplicar algoritmos para extrair conhecimento de dados que já foram pré-processados. 
Fazendo um paralelo com a mineração tradicional:  
* A mina é o **banco de dados**.
* A substância a ser extraída são os **dados**.
* Os **algoritmos** são as ferramentas para fazer essa extração.
* O mineral é a **informação**.
* O resultado de todo o processo é o **conhecimento**.  

