---
title: "&lt;param&gt; (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "param"
  - "<param>"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<param>(etiqueta XML) [C#]"
  - "param (etiqueta XML) [C#]"
ms.assetid: 46d329b1-5b84-4537-9e17-73ca97313e4e
caps.latest.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 15
---
# &lt;param&gt; (Gu&#237;a de programaci&#243;n de C#)
## Sintaxis  
  
```  
<param name="name">description</param>  
```  
  
#### Parámetros  
 `name`  
 Nombre de un parámetro de método.  Ponga el nombre entre comillas dobles \(" "\).  
  
 `description`  
 Descripción del parámetro.  
  
## Comentarios  
 La etiqueta \<param\> se debe utilizar en el comentario de una declaración de método para describir uno de los parámetros del método.  Para documentar varios parámetros, use varias etiquetas \<param\>.  
  
 El texto para la etiqueta \<param\> se mostrará en IntelliSense, el Explorador de objetos y en el Informe Web de comentario de código.  
  
 Compile con el parámetro [\/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación y generar un archivo con ellos.  
  
## Ejemplo  
 [!code-cs[csProgGuideDocComments#1](../../../csharp/programming-guide/xmldoc/codesnippet/csharp/param_1.cs)]  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Etiquetas recomendadas para los comentarios de documentación](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)