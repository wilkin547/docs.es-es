---
title: "&lt;exception&gt; (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "exception"
  - "<exception>"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<exception> (etiqueta XML) [C#]"
  - "exception (etiqueta XML) [C#]"
ms.assetid: dd73aac5-3c74-4fcf-9498-f11bff3a2f3c
caps.latest.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 16
---
# &lt;exception&gt; (Gu&#237;a de programaci&#243;n de C#)
## Sintaxis  
  
```  
<exception cref="member">description</exception>  
```  
  
#### Parámetros  
 cref \= "`member`"  
 Referencia a una excepción disponible desde el entorno de compilación actual.  El compilador comprueba que la excepción proporcionada existe y traduce `member` al nombre de elemento canónico en el resultado XML.  `member` debe aparecer entre comillas dobles \(""\).  
  
 Para obtener más información sobre cómo crear una referencia cref a un tipo genérico, vea [\<see\>](../../../csharp/programming-guide/xmldoc/see.md).  
  
 `description`  
 Descripción de la excepción.  
  
## Comentarios  
 La etiqueta \<exception\> permite especificar las excepciones que se pueden producir.  Esta etiqueta puede aplicarse a las definiciones de métodos, propiedades, eventos e indizadores.  
  
 Compile con el parámetro [\/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación y generar un archivo con ellos.  
  
 Para obtener más información acerca del control de excepciones, vea [Excepciones y control de excepciones](../../../csharp/programming-guide/exceptions/exceptions-and-exception-handling.md).  
  
## Ejemplo  
 [!code-cs[csProgGuideDocComments#4](../../../csharp/programming-guide/xmldoc/codesnippet/csharp/exception_1.cs)]  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Etiquetas recomendadas para los comentarios de documentación](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)