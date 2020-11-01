---
layout: post
title:  "Notas sobre DDD do jeito certo - Atacando a complexidade"  
date:   2020-10-31 23:59:00 -0300
categories: DDD
---

Na empresa em que trabalho, propus que pegássemos algum conteúdo sobre desenvolvimento de *software* e realizássemos reuniões periódicas para discutir esse conteúdo, buscando trazer sempre coisas novas para a empresa e evoluir continuamente a maturidade do time.
Nessas reuniões, atualmente estamos discutindo a *playlist* [DDD do jeito certo](https://www.youtube.com/watch?v=2X9Q97u4tUg&list=PLkpjQs-GfEMN8CHp7tIQqg6JFowrIX9ve), criada pelo [Elemar Jr.](https://twitter.com/elemarjr) no canal de Youtube da [EximiaCo](https://www.youtube.com/c/EximiaCo).
Uma vez que costumo fazer anotações para essas reuniões, achei que pode ser interessante registrar essas anotações aqui no blog.

Este artigo apresenta minhas anotações para a nossa reunião sobre o primeiro vídeo dessa playlist, 
[Atacando a complexidade | DDD do jeito certo | Parte 01](https://youtu.be/2X9Q97u4tUg)

## Visão geral

*Domain Driven Design* é uma abordagem de desenvolvimento de *software* que prega que as estruturas e a linguagem utilizada no código do *software* produzido deve refletir claramente as entidades, processos e regras do domínio de aplicação desse *software*.
Dessa maneira, visa-se controlar a complexidade do *software* implementado, facilitar a comunicação sobre o *software* e reduzir disparidades entre as regras do domínio de aplicação e a implementação dessas regras no software.


## Atacando a complexidade

Elemar Jr. define a complexidade de um software como um somatório de três diferentes complexidades: 

$$
C_{Soft} = 
    C_{Dom}
    + C_{SolTecn}
    + C_{Leg}
$$

Onde:
- $C_{Soft}$: Complexidade do software
- $C_{Dom}$: Complexidade do domínio da solução.
- $C_{SolTecn}$: Complexidade da solução técnica (linguagens e *frameworks* utilizados)
- $C_{Leg}$: Complexidade do código legado (dívidas técnicas)

A complexidade do domínio é referente à complexidade da implementação das regras e entidades de interesse ao problema que buscamos resolver.
Por sua vez, complexidade da solução técnica representa a complexidade adicionada durante a escolha de linguagens e *frameworks* utilizados para implementar o *software* e atingir os objetivos de negócio.
Finalmente, a complexidade do código legado é aquela que se aplica em um código já existente, com o qual é necessário interagir (ou manter) para atingir aos objetivos da aplicação.

As diferentes complexidades de um *software* podem ser divididas em complexidades *acidentais* e complexidades *essenciais*:
A complexidade da solução técnica e a complexidade de legado são consideradas complexidades acidentais, uma vez que a escolha de diferentes frameworks, linguagens ou padrões, bem como a refatoração/implementação/remoção do código, pode modificar essa complexidade.
Por sua vez, a complexidade do domínio é considerada essencial, pois o domínio está na essência da aplicação:  é aquilo que é importante para o problema que queremos resolver.

É na complexidade essencial, i.e. a complexidade do domínio, que está o valor de um *software*.
Complexidades acidentais não provêem valor aos usuários da aplicação. 
Ao cliente, pouco importa a escolha tecnológica realizada desde que a aplicação resolva corretamente o problema para o qual foi criada.

O objetivo do Domain Driven Design seria, então, lidar com a complexidade essencial da implementação das entidades e regras do domínio de aplicação.
(Porém o desenvolvedor deve estar ciente que complexidades acidentais elevam o custo de desenvolvimento e manutenção do *software* e, portanto, essas complexidades devem ser controladas também.)



## Reduzindo o gap semântico  

É necessário estar sempre em contato com os especialistas do domínio para que o *software* seja corretamente modelado e atenda às necessidades a que se propõe.
Porém, diferenças de linguajar entre especialistas de domínio e desenvolvedores dificultam essas interações:

Desenvolvedores(as) e pessoal de TI possuem mais competência para tratar da complexidade da solução técnica e da complexidade do código legado.
Estes(as) profissionais estão mais familiarizados com as entidades e o vocabulário do *espaço da solução*, frequentemente utilizando termos desse espaço em suas falas e textos.

Por outro lado, especialistas e usuários do domínio possuem maior familiaridade com as entidades e processos desse domínio.
Esses especialistas utilizam termos de uma linguagem adequada ao *espaço do problema* em si.
Essa linguagem baseia-se em uma conceitualização (implícita) que reflete as regras que ordenam o domínio de aplicação do *software*.

Assim, em uma conversa entre desenvolvedores e especialistas de domínio (durante o levantamento de requisitos, por exemplo), é natural que haja um desacoplamento conceitual entre o que é falado por um e o que é entendido por outro.
Termos utilizados pelo especialista de domínio podem não serem conhecidos pelo desenvolvedor ou, de maneira mais grave, podem ser utilizados de maneira sutilmente diferente entre os dois (*gap* semântico).

O desacoplamento conceitual durante a comunicação entre os especialistas do domínio e os desenvolvedores leva a dúvidas e ambiguidades que, sem escrutínio adequado, irão persistir após o levantamento de requisitos do *software* e serem materializadas em sua implementação.
Como efeito, o *software* irá representar uma conceitualização equivocada do domínio, de modo que o *software* poderá permitir a representação de conceitos que não existem no domínio, a má representação de  um conceito importante ao domínio e/ou a execuções de operações impróprias sobre os conceitos representados.


Sem conhecer ou se ater a aspectos técnicos e de implementação, os conceitos utilizados pelos especialistas do domínio estão mais próximos da complexidade essencial da aplicação e, portanto, do valor que ela pode prover.
Porém, está nas mãos dos desenvolvedores a implementação do *software*.
Como desenvolvedores, devemos deixar de lado a linguagem técnica e buscar falar com os especialistas nos termos do domínio do problema, trazendo esses conceitos do domínio e representando-os no modelo conceitual de nosso software. 




## Minhas considerações

Lembrando do artigo do Guarino[1] sobre ontologias formais e a sua discussão entre domínio/universo de discurso, linguagem de modelagem, conceitualização e modelo de domínio, penso que eu dividiria a complexidade do domínio em duas complexidades relacionadas:
a complexidade do domínio em si e a complexidade da implementação do domínio.

Eu vejo a complexidade do domínio como uma complexidade proporcional ao tamanho do conjunto de entidades e regras existentes nesse domínio.
A complexidade do domínio dá ao *software* uma linha base que representa a complexidade mínima necessária para atender ao problema em questão, uma vez que entidades e regras do domínio precisarão estar de alguma forma representadas no código do *software* para que possamos resolver esse problema.
Ou seja, dados dois *softwares* criados para solucionar diferentes problemas, aquele *software* cujo domínio de aplicação apresentar menos conceitos de interesse ou regras de negócio será, inicialmente, também o de menor complexidade. 

Na minha visão, a *complexidade da implementação do domínio* é proporcional à complexidade do domínio, porém também é afetada por decisões da solução técnica:
dado um mesmo domínio de aplicação e duas linguagens de programação, aquela linguagem de programação que representar mais claramente e inequivocamente o domínio apresentará uma menor complexidade final do software.

Ainda que DDD seja uma abordagem de desenvolvimento primariamente aplicada ao desenvolvimento orientado a objetos, diferentes linguagens orientadas a objetos provêem diferentes construtos e restrições que podem ser mais ou menos expressivos para essa abordagem de desenvolvimento.
Por exemplo, Kotlin possui o conceito de `data classes` que expressa mais claramente o conceito de objetos de valor do DDD que a implementação de uma classe com as mesmas restrições em Java pré-14.
Isso não deve ser considerado quando o desenvolvedor trabalha no *software*?

Talvez essa divisão seja desnecessária e isso represente realmente a complexidade da solução técnica.
Nesse caso, talvez a complexidade da solução técnica poderia ter incluído um fator extra, proporcional à complexidade do domínio.
Algo como:

$$
C_{Soft} = 
    C_{Dom}
    + (C_{SolTecnBase} + (C_{SolTecn}(C_{Dom})) 
    + C_{Leg}
$$

Eu precisaria pensar melhor na pertinência dessa divisão entre complexidade de domínio e complexidade da implementação do domínio.

 

--- 
[1] GUARINO, N. Formal Ontology and Information Systems. Proceedings of Formal Ontology and Information Systems (FOIS). Anais...1998
