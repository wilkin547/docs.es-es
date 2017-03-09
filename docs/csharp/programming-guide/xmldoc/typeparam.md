---
title: "&lt;typeparam&gt; (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "typeparam"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<typeparam> (etiqueta XML) [C#]"
  - "typeparam (etiqueta XML) [C#]"
ms.assetid: 9b99d400-e911-4e55-99c6-64367c96aa4f
caps.latest.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# &lt;typeparam&gt; (Gu&#237;a de programaci&#243;n de C#)
## Sintaxis  
  
```  
<typeparam name="name">description</typeparam>  
```  
  
#### Parámetros  
 `name`  
 Nombre del parámetro de tipo.  Ponga el nombre entre comillas dobles \(" "\).  
  
 `description`  
 Descripción del parámetro de tipo.  
  
## Comentarios  
 La etiqueta `<typeparam>` se debería utilizar en el comentario de una declaración de tipo o método genérico para describir un parámetro de tipo.  Agregue una etiqueta para cada parámetro de tipo del tipo o método genérico.  
  
 Para obtener más información, vea [Genéricos](../../../csharp/programming-guide/generics/index.md).  
  
 El texto de la etiqueta `<typeparam>` se mostrará en IntelliSense, el informe web de comentario de código de [Object Browser Window](http://msdn.microsoft.com/es-es/3c7f1673-1f0d-41b1-94ca-a3dcfcb82cda).  
  
 Compile con el parámetro [\/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación y generar un archivo con ellos.  
  
## Ejemplo  
 [!code-cs[csProgGuideDocComments#13](../../../csharp/programming-guide/xmldoc/codesnippet/csharp/typeparam_1.cs)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Etiquetas recomendadas para los comentarios de documentación](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)