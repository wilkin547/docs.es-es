---
title: "&lt;typeparamref&gt; (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
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
  - "typeparamref"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<typeparamref> (etiqueta XML) [C#]"
  - "typeparamref (etiqueta XML) [C#]"
ms.assetid: 6d8ffc58-12c5-4688-8db6-833a7ded5886
caps.latest.revision: 15
caps.handback.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# &lt;typeparamref&gt; (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

## Sintaxis  
  
```  
<typeparamref name="name"/>  
```  
  
#### Parámetros  
 `name`  
 Nombre del parámetro de tipo.  Ponga el nombre entre comillas dobles \(" "\).  
  
## Comentarios  
 Para obtener más información sobre los parámetros de tipo en tipos y métodos genéricos, vea [Genéricos](../../../csharp/programming-guide/generics/index.md).  
  
 Utilice esta etiqueta para permitir a los consumidores del archivo de documentación dar formato a la palabra de una manera distinta, por ejemplo en cursiva.  
  
 Compile con el parámetro [\/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación y generar un archivo con ellos.  
  
## Ejemplo  
 [!code-cs[csProgGuideDocComments#13](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/typeparamref_1.cs)]  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Etiquetas recomendadas para los comentarios de documentación](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)