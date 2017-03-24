---
title: "&lt;c&gt; (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "c"
  - "<c>"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<c> (etiqueta XML) [C#]"
  - "c (etiqueta XML) [C#]"
  - "código, marcar texto como [C#]"
  - "texto, marcar como código [C#]"
ms.assetid: aad5b16e-a29e-445e-bd0d-eea0b138d7b2
caps.latest.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 12
---
# &lt;c&gt; (Gu&#237;a de programaci&#243;n de C#)
## Sintaxis  
  
```  
<c>text</c>  
```  
  
#### Parámetros  
 `text`  
 Texto que se desea marcar como código.  
  
## Comentarios  
 La etiqueta \<c\> proporciona un modo de indicar que el texto de una descripción se debería marcar como código.  Utilice [\<code\>](../../../csharp/programming-guide/xmldoc/code.md) para marcar varias líneas como código.  
  
 Compile con el parámetro [\/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación y generar un archivo con ellos.  
  
## Ejemplo  
 [!code-cs[csProgGuideDocComments#2](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/code-inline_1.cs)]  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Etiquetas recomendadas para los comentarios de documentación](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)