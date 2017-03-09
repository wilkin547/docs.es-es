---
title: "&lt;see&gt; (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "<see>"
  - "see"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<see> (etiqueta XML) [C#]"
  - "cref [C#], <see> (etiqueta)"
  - "referencias cruzadas [C#]"
  - "see (etiqueta XML) [C#]"
ms.assetid: 0200de01-7e2f-45c4-9094-829d61236383
caps.latest.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# &lt;see&gt; (Gu&#237;a de programaci&#243;n de C#)
## Sintaxis  
  
```  
<see cref="member"/>  
```  
  
#### Parámetros  
 cref \= "`member`"  
 Referencia a un miembro o campo al cual se puede llamar desde el entorno de compilación actual.  El compilador comprueba si el elemento de código dado existe y pasa `member` al nombre de elemento en el resultado XML.Agregue *member* entre comillas dobles \(" "\).  
  
## Comentarios  
 La etiqueta \<see\> permite especificar un vínculo desde dentro del texto.  Use [\<seealso\>](../../../csharp/programming-guide/xmldoc/seealso.md) para indicar que el texto debe colocarse en una sección Vea también.  Use el atributo [cref](../../../csharp/programming-guide/xmldoc/cref-attribute.md) para crear hipervínculos internos a las páginas de documentación de los elementos de código.  
  
 Compile con el parámetro [\/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación y generar un archivo con ellos.  
  
 En el ejemplo siguiente se muestra una etiqueta \<see\> dentro de una sección de resumen.  
  
 [!code-cs[csProgGuideDocComments#12](../../../csharp/programming-guide/xmldoc/codesnippet/csharp/see_1.cs)]  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Etiquetas recomendadas para los comentarios de documentación](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)