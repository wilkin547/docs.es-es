---
title: "&lt;c&gt; (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "<c> (etiqueta XML)"
  - "c (etiqueta XML)"
ms.assetid: 36ad5d1b-11f7-4012-8932-41962ac327d1
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;c&gt; (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Indica que el texto dentro de una descripción es código.  
  
## Sintaxis  
  
```  
<c>text</c>  
```  
  
#### Parámetros  
  
|||  
|-|-|  
|Parámetro|Descripción|  
|`text`|Texto que se desea marcar como código.|  
  
## Comentarios  
 La etiqueta `<c>` proporciona un modo de indicar que el texto de una descripción se debe marcar como código.  Utilice [\<code\>](../../../visual-basic/language-reference/xmldoc/code.md) para marcar varias líneas como código.  
  
 Compile con [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación en un archivo.  
  
## Ejemplo  
 Este ejemplo utiliza la etiqueta `<c>` en la sección de resumen para indicar que `Counter` es código.  
  
 [!code-vb[VbVbcnXmlDocComments#1](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/c_1.vb)]  
  
## Vea también  
 [Etiquetas XML para comentarios](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)