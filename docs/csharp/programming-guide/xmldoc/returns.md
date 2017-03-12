---
title: "&lt;returns&gt; (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "returns"
  - "<returns>"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<returns> (etiqueta XML) [C#]"
  - "returns (etiqueta XML) [C#]"
ms.assetid: bb2d9958-62fc-47c7-9511-6311171f119f
caps.latest.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 11
---
# &lt;returns&gt; (Gu&#237;a de programaci&#243;n de C#)
## Sintaxis  
  
```  
<returns>description</returns>  
```  
  
#### Parámetros  
 `description`  
 Descripción del valor devuelto.  
  
## Comentarios  
 La etiqueta \<returns\> se debe utilizar en el comentario de una declaración de método para describir el valor devuelto.  
  
 Compile con el parámetro [\/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación y generar un archivo con ellos.  
  
## Ejemplo  
 [!code-cs[csProgGuideDocComments#10](../../../csharp/programming-guide/xmldoc/codesnippet/csharp/returns_1.cs)]  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Etiquetas recomendadas para los comentarios de documentación](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)