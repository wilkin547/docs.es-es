---
title: "&lt;example&gt; (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "<example>"
  - "example"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<example> (etiqueta XML) [C#]"
  - "example (etiqueta XML) [C#]"
ms.assetid: 32d6e73b-2554-4abb-83ee-a1e321334fd2
caps.latest.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 13
---
# &lt;example&gt; (Gu&#237;a de programaci&#243;n de C#)
## Sintaxis  
  
```  
<example>description</example>  
```  
  
#### Parámetros  
 `description`  
 Descripción del ejemplo de código.  
  
## Comentarios  
 La etiqueta \<example\> permite especificar un ejemplo de cómo utilizar un método u otro miembro de una biblioteca.  Generalmente, esto supone utilizar la etiqueta [\<code\>](../../../csharp/programming-guide/xmldoc/code.md).  
  
 Compile con el parámetro [\/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación y generar un archivo con ellos.  
  
## Ejemplo  
 [!code-cs[csProgGuideDocComments#3](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/example_1.cs)]  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Etiquetas recomendadas para los comentarios de documentación](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)