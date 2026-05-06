# Atribuição de autor no código

Algumas linguagens proveem maneiras de identificar o autor de um dado arquivo. Por exemplo, Java provê a tag `@author` para ser utilizada nos comentários de um arquivo Java. A informação marcada com `@author` é apresentada, posteriormente, no Javadoc daquele arquivo.

Embora essa tag seja uma maneira fácil de atribuição de responsabilidade, em um código sempre em evolução ela fica rapidamente desatualizada e/ou incongruente: se Ana escreveu a primeira versão de uma classe, quantas mudanças naquela classe precisam ser feitas por João para que a classe não seja mais responsabilidade de Ana? Além disso, se essa classe/documentação é parte de uma API que será usado por terceiros, estes deveriam questionar a organização/laboratório sobre o funcionamento dessa unidade de códigou ou deveriam contatar diretamente aquele desenvolvedor(a) em particular? 

Muito provavelmente, é preferível que a organização seja a intermediária dessa conversa: Cada desenvolvedor não é responsável por uma única classes/arquivo, Geralmente, desenvolvedores possuem outras atribuições/tarefas que já estão trabalhando, e parar o fluxo de trabalho de um desenvolvedor tem um custo para a organização. Adicionalmente, desenvolvedores passam por uma organização durante um dado período de tempo. Porém, o código que produzem pode ser mantido ativo  por muito mais tempo. Nesta situação, não faz sentido manter referências ao autor de um dado artefato se este autor já não possui nenhum vínculo de responsabilidade com a organização em que o código está ativo.

## Discussões interessantes sobre o tema

- https://issues.apache.org/jira/browse/TAVERNA-897

- https://mail-archives.apache.org/mod_mbox/www-community/200306.mbox/%3C20030609234538.GA22335@lyra.org%3E

- https://github.com/apache/zeppelin/pull/571
