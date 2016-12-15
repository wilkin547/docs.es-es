---
title: "&lt;seealso&gt; (Visual Basic) | Microsoft Docs"
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
  - "<seealso> (etiqueta XML)"
  - "seealso (etiqueta XML)"
ms.assetid: 36050c95-1af2-4284-b9b6-1a70691ed978
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;seealso&gt; (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Especifica un vínculo que aparece en la sección Vea también.  
  
## Sintaxis  
  
```  
<seealso cref="member"/>  
```  
  
#### Parámetros  
 `member`  
 Referencia a un miembro o campo al cual se puede llamar desde el entorno de compilación actual.  El compilador comprueba si el elemento de código dado existe y pasa `member` al nombre de elemento en el resultado XML.  `member` debe aparecer entre comillas dobles \(""\).  
  
## Comentarios  
 Utilice la etiqueta `<seealso>` para especificar el texto que desea mostrar en una sección Vea también.  Utilice [\<see\>](../../../visual-basic/language-reference/xmldoc/see.md) para especificar un vínculo desde dentro del texto.  
  
 Compile con [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación en un archivo.  
  
## Ejemplo  
 Este ejemplo utiliza la etiqueta `<seealso>` en la sección de comentarios `DoesRecordExist` para hacer referencia al método `UpdateRecord`.  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/seealso_1.vb)]  
  
## Vea también  
 [Etiquetas XML para comentarios](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)