---
layout: post
title: File over app
date: 2026-05-06 00:00:00 -0300
source: https://stephango.com/file-over-app
published: true
description: If you want to create digital artifacts that last, they must be files you can control, in formats that are easy to retrieve and read. Use tools that give you...
banner: https://images.unsplash.com/photo-1569235186275-626cb53b83ce?crop=entropy&cs=tinysrgb&fit=max&fm=jpg&ixid=M3wzNjAwOTd8MHwxfHNlYXJjaHwxfHxmaWxlfGVufDB8MHx8fDE3Njk1NTI5MjV8MA&ixlib=rb-4.1.0&q=80&w=1080
---

*File over app* é um crivo para a decisão de ferramentas e fluxos de trabalho digitais que visa criar e utilizar artefatos digitais que durem e sejam utilizados por muitos anos (ou mesmo indefinitivamente), de maneira independente do *software* disponível. Esse crivo foi definido por Steph Ango em 2023 em [um post de seu blog](https://stephango.com/file-over-app).

O crivo *File over app* restringe a decisão de ferramentas e fluxo obrigando que todos os artefatos digitais criados ou usados:

- **Existam como arquivos que você controla:** Decida sempre por arquivos locais ou facilmente baixáveis/exportáveis;
- **E que o formato utilizado para esses arquivos sejam facilmente recuperados e utilizados:** Decida sempre em favor de formatos abertos, de preferência baseados em texto e facilmente manipulados por qualquer editor de texto.

A idéia principal que sustenta essa idéia é a observação empírica que *softwares* são efêmeros e facilmente um editor ou programa que seja usado hoje para manipular um formato de arquivo proprietário pode estar inacessível e sem suporte no futuro. Se, sem acesso ao *software* original perde-se acesso também aos dados, os dados tornam-se tão efêmeros quanto o *software* que foi utilizado para criá-los. Também conclui-se que a propriedade dos dados não é realmente do criador do artefato, pois eles ficam limitados a serem utilizados apenas de certas maneiras, como o criador da ferramenta permitiu ser feito.

Empiricamente, a efemeridade do *software* me parece ainda mais forte no mundo pós SaaS. Muitos *softwares* que eu usava para criar anotações e diagramas durante o meu mestrado, há uns 7 anos atrás, já não tenho acesso nos dias atuais, seja por terem perdido suporte do desenvolvedor como um todo ou ao formato de arquivo que eu utilizava, ou seja ganhando *paywalls* que, para mim, não valham o custo. Mesmo diagramas que fiz há poucos anos atrás eu perdi acesso quando a empresa que eu estava parou de pagar a plataforma que utilizávamos. Contraste isso com documentos existentes no "mundo real": um livro de 1000 anos pode ser lido por qualquer um que seja capaz de ver e conheça a língua em que ele foi escrito.

## Sinergias com IA

Abordagens *File over App*, principalmente aquelas que usam formatos de arquivos textuais, se tornam ainda mais interessantes quando colocamos agentes de IAs/LLMs nos fluxos de trabalho do dia-a-dia, pois abrem mais possibilidades para a transformação e o uso facilitado dos dados armazenados nesses arquivos. As LLM atuais apresentam razoável capacidade em "compreender" e manipular os dados presentes nesses arquivos, tanto esses dados representados de maneira não-estruturada quando para dados representados de maneira estruturada, mantendo a fidedignidade da informação.

Em meus usos diários, agentes de IA se mostraram sendo ferramentas muito úteis para fazer extrações de dados e transformações *ad hoc* de arquivos entre formatos de representação textuais que estejam relativamente bem descritos ou com exemplos. LLMs são, também, muito úteis para estudar e dialogar com as informações presentes em vários arquivos textuais ao mesmo tempo. Porém, deve-se ter em mente que toda transformação ou extração de dados por LLM ainda podem sofrer de "alucinações" ou falhas, e o resultado deve ser sempre verificado.

## Como decisão empresarial e no desenvolvimento de software

Como tudo que cai em uma decisão empresarial, há sempre uma consideração de custo, de eficiência e de oportunidade: vai ser muito difícil, ou mesmo contra-producente, tentar implementar *File over app* em todos os pontos do trabalho.

Porém, na área de desenvolvimentos nós estamos razoavelmente bem posicionados para decidir por abordagens independentes de *software*, pois já temos muitos formatos de arquivos com suporte extenso para os mais diferentes usos. Algumas sugestões de usos e formatos de arquivos:

- Documentação/anotações: armazenadas em Markdown. Lidos com qualquer editor de texto e com renderização suportada por muitos editores/IDEs e repositórios de código.
- Diagramas de diversos tipos: criadas com mermaid ou plantuml, dentro de arquivos markdown ou em arquivos próprios. São renderizados em muitos editores/repositórios quando inseridos nos arquivos markdown. Podem ser transformados em imagens para visualização facilitada (SVG de preferência) usando CLIs.
- Requisições HTTP para teste: Arquivos [HTTP/Rest](https://learn.microsoft.com/en-us/aspnet/core/test/http-files?view=aspnetcore-8.0) e usados com suportes variados.
- Tabelas/planilhas: CSV/TSV para artefatos que possam ser usados de diferentes formas. OpenDocument para planilhas gerais (mas, em geral, a facilidade de compartilhamento com o resto do time de um Google Spreadsheets vai acabar vencendo nesse caso).
- Valores quaisquer, tais como logs, configuração, etc...: YAML, JSON, XML, ENV Files...

Quando arquivos puramente locais e compartilhados via repositórios de código não trazem uma boa usabilidade, dê preferência a soluções mais gerais e facilmente exportáveis que soluções muito dedicadas. Por exemplo, documentos de reuniões 1-a-1 são melhor aproveitados quando compartilhados por líder e liderado. Nesse sentido, muitas plataformas de gestão de pessoas vão prover soluções para criar esses documentos. Porém, minha experiência é que frequentemente o RH vai mudar de plataforma e poucas dão opções para exportar os registros de maneira facilmente reutilizável (se é que dão acesso a qualquer exportação). Nesse sentido, manter um documento no Google Drive ou Confluence privado e compartilhado é uma solução muito mais à prova de futuro, pois essas plataformas permitem exportação fácil para formatos de documentos com suporte externo como DOC ou ODC.

Naturalmente, no dia-a-dia de uma equipe de software nem tudo precisa ser *File over app* e armazenamento local: há muitas situações que a solução dedicada e sem interoperabilidade é suficiente, pois sincronização facilitada é mais importante ou os dados são importantes em um período definido de tempo. Por exemplo, não faz sentido implementar uma solução *File over App* para gestão de tarefas e sincronização se temos um Jira ou outra plataforma disponível: as facilidades que essas plataformas trazem para o dia-a-dia são muito mais importantes que a gestão local de todas as informações. Porém, mesmo assim, é preciso pensar em implementar práticas que possam manter o conhecimento produzido disponível e re-utilizável por um longo tempo.
