---
title: "&lt;para&gt; (Visual Basic) | Microsoft Docs"
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
  - "<para> (etiqueta XML)"
  - "para (etiqueta XML)"
ms.assetid: a3a18b6c-6416-4358-94ec-37b22675fd37
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;para&gt; (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Especifica que el contenido tiene el formato de un párrafo.  
  
## Sintaxis  
  
```  
<para>content</para>  
```  
  
#### Parámetros  
 `content`  
 Texto del párrafo.  
  
## Comentarios  
 La etiqueta `<para>` se utiliza en una etiqueta, como [\<summary\>](../../../visual-basic/language-reference/xmldoc/summary.md), [\<remarks\>](../../../visual-basic/language-reference/xmldoc/remarks.md) o [\<returns\>](../../../visual-basic/language-reference/xmldoc/returns.md), y permite agregar estructura al texto.  
  
 Compile con [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación en un archivo.  
  
## Ejemplo  
 Este ejemplo utiliza la etiqueta `<para>` para dividir la sección de comentarios del método `UpdateRecord` en dos párrafos.  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/para_1.vb)]  
  
## Vea también  
 [Etiquetas XML para comentarios](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)