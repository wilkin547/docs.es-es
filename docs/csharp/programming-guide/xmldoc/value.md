---
title: "&lt;value&gt; (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "<value>"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<value> (etiqueta XML) [C#]"
  - "value (etiqueta XML) [C#]"
ms.assetid: 08dbadaf-9ab6-43d9-9493-98e43bed199a
caps.latest.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 12
---
# &lt;value&gt; (Gu&#237;a de programaci&#243;n de C#)
## Sintaxis  
  
```  
<value>property-description</value>  
```  
  
#### Parámetros  
 `property-description`  
 Descripción de la propiedad.  
  
## Comentarios  
 La etiqueta \<value\> permite describir el valor que representa una propiedad.  Tenga en cuenta que al agregar una propiedad a través de un asistente para código en el entorno de desarrollo de Visual Studio .NET, se agregará una etiqueta [\<summary\>](../../../csharp/programming-guide/xmldoc/summary.md) para la nueva propiedad.  A continuación, se debe agregar manualmente una etiqueta \<value\> que describa el valor que representa la propiedad.  
  
 Compile con el parámetro [\/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación y generar un archivo con ellos.  
  
## Ejemplo  
 [!code-cs[csProgGuideDocComments#14](../../../csharp/programming-guide/xmldoc/codesnippet/csharp/value_1.cs)]  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Etiquetas recomendadas para los comentarios de documentación](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)