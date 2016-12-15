---
title: "&lt;paramref&gt; (Visual Basic) | Microsoft Docs"
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
  - "<paramref> (etiqueta XML)"
  - "paramref (etiqueta XML)"
ms.assetid: 8979d53b-beb1-41b7-b41e-6bbea1c17a03
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;paramref&gt; (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Da formato a una palabra como un parámetro.  
  
## Sintaxis  
  
```  
<paramref name="name"/>  
```  
  
#### Parámetros  
 `name`  
 Nombre del parámetro al que hay que hacer referencia.  Ponga el nombre entre comillas dobles \(" "\).  
  
## Comentarios  
 La etiqueta `<paramref>` proporciona un modo de indicar que una palabra es un parámetro.  El archivo XML se puede procesar de manera que aplique formato a este parámetro de algún modo diferente.  
  
 Compile con [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación en un archivo.  
  
## Ejemplo  
 En este ejemplo se utiliza la etiqueta `<paramref>` para hacer referencia al parámetro `id`.  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/paramref_1.vb)]  
  
## Vea también  
 [Etiquetas XML para comentarios](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)