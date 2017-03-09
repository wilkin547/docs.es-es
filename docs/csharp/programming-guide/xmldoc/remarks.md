---
title: "&lt;remarks&gt; (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "remarks"
  - "<remarks>"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<remarks> (etiqueta XML) [C#]"
  - "remarks (etiqueta XML) [C#]"
ms.assetid: f8641391-31f3-4735-af7a-c502a5b6a251
caps.latest.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 13
---
# &lt;remarks&gt; (Gu&#237;a de programaci&#243;n de C#)
## Sintaxis  
  
```  
<remarks>description</remarks>  
```  
  
#### Parámetros  
 `Description`  
 Descripción del miembro.  
  
## Comentarios  
 La etiqueta \<remarks\> se utiliza para agregar información sobre un tipo, de modo que completa la información especificada con [\<summary\>](../../../csharp/programming-guide/xmldoc/summary.md).  Esta información se muestra en el [Object Browser Window](http://msdn.microsoft.com/es-es/3c7f1673-1f0d-41b1-94ca-a3dcfcb82cda).  
  
 Compile con el parámetro [\/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación y generar un archivo con ellos.  
  
## Ejemplo  
 [!code-cs[csProgGuideDocComments#9](../../../csharp/programming-guide/xmldoc/codesnippet/csharp/remarks_1.cs)]  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Etiquetas recomendadas para los comentarios de documentación](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)