---
aliases:
- migrate-from-jekyl
authors:
- Programador Solitário
categories:
- sintaxe
- demonstração do tema
date: "2023-07-09"
description: Sample article showcasing shortcodes for HTML/CSS only tabs
series:
- Demonstração do Tema
tags:
- hugo
- markdown
- css
- html
- shortcodes
title: HTML and CSS only tabs
---

## Shortcodes

O seguinte conteúdo:

```markdown
{{</* tabgroup */>}}
{{</* tab name="Hello" */>}}
Hello World!
{{</* /tab */>}}

{{</* tab name="Goodbye" */>}}
Goodbye Everybody!
{{</* /tab */>}}
{{</* /tabgroup */>}}
```

Irá gerar:

{{< tabgroup >}}
{{< tab name="Hello" >}}
Hello World!
{{< /tab >}}

{{< tab name="Goodbye" >}}
Goodbye Everybody!
{{< /tab >}}
{{< /tabgroup >}}

## Alinhamento à direita

Você também pode alinhas as tabs à direita:

```markdown
{{</* tabgroup align="right" */>}}
{{</* tab name="Hello" */>}}
Hello World!
{{</* /tab */>}}

{{</* tab name="Goodbye" */>}}
Goodbye Everybody!
{{</* /tab */>}}
{{</* /tabgroup */>}}
```

Obtendo o seguinte resultado:

{{< tabgroup align="right" >}}
{{< tab name="Hello" >}}
Hello World!
{{< /tab >}}

{{< tab name="Goodbye" >}}
Goodbye Everybody!
{{< /tab >}}
{{< /tabgroup >}}

## Conteúdo Markdown

Qualquer conteúdo Markdown válido pode ser usado dentro das tabs:

````markdown
{{</* tabgroup align="right" style="code" */>}}
{{</* tab name="Ruby" */>}}

```ruby
puts 'Hello'
```

{{</* /tab */>}}
{{</* tab name="Python" */>}}

```python
print('Hello')
```

{{</* /tab */>}}
{{</* tab name="JavaScript" */>}}

```js
console.log("Hello");
```

{{</* /tab */>}}
{{</* /tabgroup */>}}
````

Assim você obterá o seguinte resultado:

{{< tabgroup align="right" style="code" >}}
{{< tab name="Ruby" >}}

```ruby
puts 'Hello'
```

{{< /tab >}}
{{< tab name="Python" >}}

```python
print('Hello')
```

{{< /tab >}}
{{< tab name="JavaScript" >}}

```js
console.log("Hello");
```

{{< /tab >}}
{{< /tabgroup >}}

Nesse exemplo, `style="code"` faz com que o resultado seja mais agradável quando conteúdo é puramente blocos de código.
