---
title: "&lt;code&gt; (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "<code> (etiqueta XML)"
  - "code (etiqueta XML)"
ms.assetid: 925e5342-be05-45f2-bf66-7398bbd6710e
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# &lt;code&gt; (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Indica que el texto consiste en varias líneas de código.  
  
## Sintaxis  
  
```  
<code>content</code>  
```  
  
#### Parámetros  
 `content`  
 El texto que se marca como código.  
  
## Comentarios  
 Utilice la etiqueta `<code>` para indicar varias líneas como código.  Utilice [\<c\>](../../../visual-basic/language-reference/xmldoc/c.md) para indicar que el texto de una descripción debe marcarse como código.  
  
 Compile con [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación en un archivo.  
  
## Ejemplo  
 En este ejemplo se utiliza la etiqueta \<code\> para incluir el código de ejemplo para utilizar el campo `ID`.  
  
 [!code-vb[VbVbcnXmlDocComments#2](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/code_1.vb)]  
  
## Vea también  
 [Etiquetas XML para comentarios](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)