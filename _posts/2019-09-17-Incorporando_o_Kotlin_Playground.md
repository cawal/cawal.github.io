---
layout: post
title:  "Incorporando o Kotlin Playground em um blog Jekyll"
date:   2019-09-17 12:00:00 -0300
categories: kotlin
---

Tenho usado muito Kotlin em meus projetos Java: é uma linguagem muito agradável de utilizar, com boas abstrações e que interopera eficientemente com todo o conjunto de bibliotecas já existentes para Java. Passando pelo Kotlin Playground, vi que é possível adicionar um mini-bloco de código Kotlin uma página pessoal de maneira editável e executável (ótimo para representar pequenos exemplos).
Esse post é um teste para a adição que fiz dessa funcionalidade aqui no blog:

```kotlin
fun main() { 
	print("Hello, Kt!")
}
```

Para incluir o Kotlin Playground automaticamente nas caixas de código de seu site Jekyll, adicione à *tag* `<head>` de sua página (no meu caso, definido em `_includes/head.html`) a *tag* abaixo:
```html
  <script src="https://unpkg.com/kotlin-playground@1" data-selector=".language-kotlin"></script>
```
O *script* automaticamente reconhece caixas de código marcadas como `kotlin` por causa do atributo `data-selector=".language-kotlin"`.

Mais informações no [Blog da Jetbrains](https://blog.jetbrains.com/kotlin/2018/04/embedding-kotlin-playground/) e no [repositório no Github](https://github.com/JetBrains/kotlin-playground#installation).



