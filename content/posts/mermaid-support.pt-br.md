---
authors:
- Lone Coder
categories:
- sintaxe
- demonstração do tema
date: "2023-07-08"
description: The post demonstrates Mermaid JS support
series:
- Demonstração do Tema
tags:
- hugo
- markdown
- css
- html
title: Mermaid JS support
---

Se quiser usar o [Mermaid-JS](https://mermaid-js.github.io/mermaid/#/) em sua página.
Use o [shortcode](https://gohugo.io/content-management/shortcodes/#readout) `mermaid` em seus conteúdos Markdown.

{{<mermaid>}}
flowchart LR

    A --> B

    B --> C

    C --> D

    D --> B

{{</mermaid>}}

{{<mermaid>}}
sequenceDiagram
participant Alice
participant Bob
Alice->>Bob: Hi Bob
Bob->>Alice: Hi Alice
{{</mermaid>}}

Entro mais exemplos na página do [Mermaid-JS](https://mermaid-js.github.io/mermaid/#/).
