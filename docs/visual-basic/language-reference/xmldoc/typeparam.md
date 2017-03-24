---
title: "&lt;typeparam&gt; (Visual Basic) | Microsoft Docs"
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
  - "<typeparam> (etiqueta XML)"
  - "typeparam (etiqueta XML)"
ms.assetid: 1bb5ba78-f060-478c-905c-77a2e43639af
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# &lt;typeparam&gt; (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Define un nombre y descripción de parámetro de tipo.  
  
## Sintaxis  
  
```  
<typeparam name="name">description</typeparam>  
```  
  
#### Parámetros  
 `name`  
 Nombre del parámetro de tipo.  Ponga el nombre entre comillas dobles \(" "\).  
  
 `description`  
 Una descripción del parámetro de tipo.  
  
## Comentarios  
 Utilice la etiqueta `<typeparam>` en el comentario para que una declaración de tipo genérico o de miembro genérico describa uno de los parámetros de tipo.  
  
 Compile con [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación en un archivo.  
  
## Ejemplo  
 Este ejemplo utiliza la etiqueta `<typeparam>` para describir el parámetro `id`.  
  
 [!code-vb[VbVbcnXmlDocComments#8](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/typeparam_1.vb)]  
  
## Vea también  
 [Etiquetas XML para comentarios](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)