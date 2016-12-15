---
title: "&lt;exception&gt; (Visual Basic) | Microsoft Docs"
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
  - "<exception> (etiqueta XML)"
  - "exception (etiqueta XML)"
ms.assetid: c0517549-171e-4dae-ab88-a9c1700b6eee
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;exception&gt; (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Especifica las excepciones que se pueden producir.  
  
## Sintaxis  
  
```  
<exception cref="member">description</exception>  
```  
  
#### Parámetros  
 `member`  
 Referencia a una excepción disponible desde el entorno de compilación actual.  El compilador comprueba que la excepción proporcionada existe y traduce `member` al nombre de elemento canónico en el resultado XML.  `member` debe aparecer entre comillas dobles \(""\).  
  
 `description`  
 Descripción.  
  
## Comentarios  
 Utilice la etiqueta `<exception>` para especificar las excepciones que se pueden producir.  Esta etiqueta se aplica a una definición de método.  
  
 Compile con [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación en un archivo.  
  
## Ejemplo  
 Este ejemplo utiliza la etiqueta `<exception>` para describir una excepción que puede producir la función `IntDivide`.  
  
 [!code-vb[VbVbcnXmlDocComments#3](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/exception_1.vb)]  
  
## Vea también  
 [Etiquetas XML para comentarios](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)