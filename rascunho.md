---
title: "Descomplicando o R Markdown:"
subtitle: Componentes básicos
author: "Natália Souza"
date: "26 de Setembro de 2020"
output:
  html_document:
    number_sections: yes #numera os capítulos
    toc: yes #gera o indice lateral
    toc_depth: 6 # Até quantos titulos vai abrir, h1, h2, h3, h4, etc.
    toc_float:   
      collapsed: yes #starta colapsado o sumário lateral
    code_folding: hide #abre opçaõ de ocultar todos os códigos e apertar o botão, opção show
    fig_caption: yes #legenda nas figuras
    fig_height: 6 #padroniza a altura das figuras em polegadas
    fig_width: 7 #padroniza a largura das figuras em polegadas, podera altarar posteriormente.
    highlight: tango #Opções de personalização de apresentação do chunk (tango, pygments, kate, monochrome, espresso, zenburn, haddock, breezedark, e textmate)
    theme: journal #Só funciona para html, altera o layout de apresentação, opções: (cerulean, journal, flatly, darkly, readable, spacelab, united, cosmo, lumen, paper, sandstone, simplex e yeti.)
    df_print: paged #forma de exibição das tabelas, opções: kable, tibble e  paged
bibliography: Ref.bib #Este é o nome do arquivo.
link-citations: yes #ao clicar em uma sitação vai levar para a referência.
#o esquema de referência abaixo não funciona em PDF, utilize o sistema acima com .bib
references:
- id: fenner2012a #nome da referência
  title: One-click science marketing
  author:
  - family: Fenner
    given: Martin
  container-title: Nature Materials
  volume: 11
  URL: 'http://dx.doi.org/10.1038/nmat3283'
  DOI: 10.1038/nmat3283
  issue: 4
  publisher: Nature Publishing Group
  page: 261-263
  type: article-journal
  issued:
    year: 2012
    month: 3
nocite: "@*" #como chamar o nome da referência
---

>  <p style='text-align: justify;'> Como vimos, podemos utilizar o R Markdown de diversas maneiras. No contexto de um documento/relatório, iremos detalhar três componentes: Os metadados, os códigos e o texto. </p>

# Metadados {.tabset .tabset-fade .tabset-pills}

Definem a estrutura do documento. Iniciam e terminam com três travessões. *Variam de acordo com o tipo de saída*. Exemplos:

- **Índice**
Parâmetro: toc; Binário; O padrão é falso.

- **Profundidade do índice** - ~~Parâmetro~~: toc_depth; Varia de 1 a 6; O padrão é 3.

- **Numerar as seções - ** Parâmetro: number_sections; Binário; O padrão é falso. 

- **Temas** Parâmetro: **theme**. 

  - Opções: Cerulean, _journal_, flatly, darkly, readable, spacelab, united, cosmo, lumen, paper, sandstone, simplex e yeti.

- **Estilo dos chunks - ** Parâmetro: highlight.

  - Opções: Tango, pygments, kate, monochrome, espresso, zenburn, haddock, breezedark, e textmate.

- **Incluir o código, mas deixá-lo oculto - ** Parâmetro: code_folding; o padrão é show.

  - Opções: hide e show.


# Código 

## Detalhando as funções do chunk

- Observe as opções de click da engrenagem.
```{r conta, fig.height=8, fig.width=7, message=TRUE, warning=TRUE, include=FALSE, paged.print=TRUE}
Soma <-  4+9; Soma

```

- No chunk acima foi ocultado tanto código quanto saída. Apesar disso, o código (Soma <-  4+9) foi compilado, portanto o objeto "Soma" foi criado. Logo, podemos chamá-lo: Soma = `r Soma`.

- Inserindo uma condição para compilar um chunk e apresentar o código.

>   Parâmetro para compilar o chunk: **eval**; Binário.
>   Parâmetro para apresentar o código: **echo**; Binário.


```{r include=FALSE}
correlacao <- cor(iris$Sepal.Length, iris$Sepal.Width)
flag <- correlacao > 0; correlacao
```
