---
layout: post
title:  "Incorporando o Kotlin Playground em um blog Jekyll"
date:   2019-09-17 12:00:00 -0300
categories: kotlin
---

Tenho usado muito Kotlin em meus projetos Java e vi que é possível adicionar um mini-editor como o presente no Kotlin Playground em uma página pessoal, permitindo a inclusão de código editável e que pode ser executado remotamente pelo Kotlin Playground. 
Esse post é um teste para essa inclusão aqui no blog:

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



