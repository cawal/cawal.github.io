---
title: Guia para prover aplicações
---

## Geral

- Crie um repositório GIT para o código;
	- Adicione arquivos `.gitignore` e retire do repositório todos os arquivos derivados automaticamente, arquivos binários e configurações locais;
	- Providencie um sistema de integração contínua para o repositório;
	- Proteja o *branch* main, de modo que não seja possível comitar direto a ele. Só permita que sejam realizadas pull requests e que todos os testes precisem ser executados antes do merge;  

- Defina um README contendo:
	- Objetivo da aplicação
	- Ambiente de execução almejado;
	- Passos para a compilação e uso;

- Use um sistema de build automático e gerenciamento de dependências;
	- Deve ser possível buscar todas as dependencias e compilar o código por meio de uma única linha de comando; 

- Defina testes automatizados;

- Providencie um sistema de integração contínua para o repositório;


## Ferramentas de linhas de comando:

- Use uma biblioteca de *parsing* da linha de comando:
	- Disponibilize uma mensagem de ajuda automatizada;
	- Garanta que haja identificadores com nomes adequados para todos os parâmetros;
	- Disponibilize valores padrão para todos os valores opcionais;

- Defina o empacotamento  
