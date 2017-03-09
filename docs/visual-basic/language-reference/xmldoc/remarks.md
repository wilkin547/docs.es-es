---
title: "&lt;remarks&gt; (Visual Basic) | Microsoft Docs"
ms.custom: ""
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
  - "<remarks> (etiqueta XML)"
  - "remarks (etiqueta XML)"
ms.assetid: c6241773-a7ed-41c9-9a8b-9722a0c606a9
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# &lt;remarks&gt; (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Especifica una sección de comentarios para el miembro.  
  
## Sintaxis  
  
```  
<remarks>description</remarks>  
```  
  
#### Parámetros  
 `description`  
 Descripción del miembro.  
  
## Comentarios  
 Utilice la etiqueta `<remarks>` para agregar información sobre un tipo, complementando la información especificada con [\<summary\>](../../../visual-basic/language-reference/xmldoc/summary.md).  
  
 Esta información aparece en el explorador de objetos.  Para obtener información sobre el explorador de objetos, vea [Ver la estructura del código](/visual-studio/ide/viewing-the-structure-of-code).  
  
 Compile con [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación en un archivo.  
  
## Ejemplo  
 Este ejemplo utiliza la etiqueta `<remarks>` para explicar qué hace el método `UpdateRecord`.  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/visualbasic/remarks_1.vb)]  
  
## Vea también  
 [Etiquetas XML para comentarios](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)