---
title: "&lt;seealso&gt; (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "cref"
  - "<seealso>"
  - "seealso"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<seealso> (etiqueta XML) [C#]"
  - "cref [C#]"
  - "cref [C#], véase también"
  - "referencias cruzadas [C#], etiquetas"
  - "seealso (etiqueta XML) [C#]"
ms.assetid: 8e157f3f-f220-4fcf-9010-88905b080b18
caps.latest.revision: 11
caps.handback.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# &lt;seealso&gt; (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

## Sintaxis  
  
```  
<seealso cref="member"/>  
```  
  
#### Parámetros  
 cref \= "`member`"  
 Referencia a un miembro o campo al cual se puede llamar desde el entorno de compilación actual.  El compilador comprueba si el elemento de código dado existe y pasa `member` al nombre de elemento en el resultado XML.`member` debe aparecer entre comillas dobles \(" "\).  
  
 Para obtener información sobre cómo crear una referencia de tipo cref a un tipo genérico, vea [\<see\>](../../../csharp/programming-guide/xmldoc/see.md).  
  
## Comentarios  
 La etiqueta \<seealso\> permite especificar el texto que se desea que aparezca en una sección Vea también.  Utilice [\<see\>](../../../csharp/programming-guide/xmldoc/see.md) para especificar un vínculo desde dentro del texto.  
  
 Compile con el parámetro [\/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación y generar un archivo con ellos.  
  
## Ejemplo  
 Vea [\<summary\>](../../../csharp/programming-guide/xmldoc/summary.md) para obtener un ejemplo del uso de \<seealso\>.  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Etiquetas recomendadas para los comentarios de documentación](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)