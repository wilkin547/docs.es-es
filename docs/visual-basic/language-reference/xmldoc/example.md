---
title: "&lt;example&gt; (Visual Basic) | Microsoft Docs"
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
  - "<example> (etiqueta XML)"
  - "example (etiqueta XML)"
ms.assetid: 90eeda1c-3fc4-427c-879c-5046d265a97c
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;example&gt; (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Especifica un ejemplo para el miembro.  
  
## Sintaxis  
  
```  
<example>description</example>  
```  
  
#### Parámetros  
 `description`  
 Descripción del ejemplo de código.  
  
## Comentarios  
 La etiqueta `<example>` permite especificar un ejemplo de cómo utilizar un método u otro miembro de una biblioteca.  Generalmente, esto supone utilizar la etiqueta [\<code\>](../../../visual-basic/language-reference/xmldoc/code.md).  
  
 Compile con [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación en un archivo.  
  
## Ejemplo  
 Este ejemplo utiliza la etiqueta `<example>` para incluir un ejemplo de utilización del campo `ID`.  
  
 [!code-vb[VbVbcnXmlDocComments#2](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/example_1.vb)]  
  
## Vea también  
 [Etiquetas XML para comentarios](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)