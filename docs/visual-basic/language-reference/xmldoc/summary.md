---
title: "&lt;summary&gt; (Visual Basic) | Microsoft Docs"
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
  - "<summary> (etiqueta XML)"
  - "summary (etiqueta XML)"
ms.assetid: 861c847d-dd94-478a-aa23-bf4899cdc848
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# &lt;summary&gt; (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Especifica el resumen del miembro.  
  
## Sintaxis  
  
```  
<summary>description</summary>  
```  
  
#### Parámetros  
 `description`  
 Resumen del objeto.  
  
## Comentarios  
 Utilice la etiqueta `<summary>` para describir un tipo o un miembro de tipo.  Utilice [\<remarks\>](../../../visual-basic/language-reference/xmldoc/remarks.md) para suministrar información adicional a una descripción de tipo.  
  
 El texto de la etiqueta `<summary>` es la única fuente de información sobre el tipo en IntelliSense, y se muestra en el explorador de objetos.  Para obtener información sobre el explorador de objetos, vea [Ver la estructura del código](/visual-studio/ide/viewing-the-structure-of-code).  
  
 Compile con [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación en un archivo.  
  
## Ejemplo  
 Este ejemplo utiliza la etiqueta `<summary>` para describir el método `ResetCounter` y la propiedad `Counter`.  
  
 [!code-vb[VbVbcnXmlDocComments#1](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/summary_1.vb)]  
  
## Vea también  
 [Etiquetas XML para comentarios](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)