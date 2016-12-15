---
title: "&lt;paramref&gt; (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
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
  - "paramref"
  - "<paramref>"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<paramref> (etiqueta XML) [C#]"
  - "paramref (etiqueta XML) [C#]"
ms.assetid: 756c24c1-f591-40e8-a838-559761539b0b
caps.latest.revision: 12
caps.handback.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# &lt;paramref&gt; (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

## Sintaxis  
  
```  
<paramref name="name"/>  
```  
  
#### Parámetros  
 `name`  
 Nombre del parámetro al que hay que hacer referencia.  Ponga el nombre entre comillas dobles \(" "\).  
  
## Comentarios  
 La etiqueta \<paramref\> proporciona una forma de indicar que una palabra en los comentarios del código, por ejemplo en un bloque \<summary\> o \<remarks\>, hace referencia a un parámetro.  El archivo XML se puede procesar para dar formato a esta palabra de alguna manera distinta, como con una fuente en negrita o en cursiva.  
  
 Compile con el parámetro [\/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación y generar un archivo con ellos.  
  
## Ejemplo  
 [!code-cs[csProgGuideDocComments#7](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/paramref_1.cs)]  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Etiquetas recomendadas para los comentarios de documentación](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)