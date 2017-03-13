---
title: "&lt;param&gt; (Visual Basic) | Microsoft Docs"
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
  - "<param> (etiqueta XML)"
  - "param (etiqueta XML)"
ms.assetid: 4e32e86f-f6f3-4301-b7fc-2f321fb54368
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# &lt;param&gt; (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Define un nombre y descripción de parámetro.  
  
## Sintaxis  
  
```  
<param name="name">description</param>  
```  
  
#### Parámetros  
 `name`  
 Nombre de un parámetro de método.  Ponga el nombre entre comillas dobles \(" "\).  
  
 `description`  
 Descripción del parámetro.  
  
## Comentarios  
 La etiqueta `<param>` se debe utilizar en el comentario de una declaración de método para describir uno de los parámetros del método.  
  
 El texto de la etiqueta `<param>` aparecerá en las siguientes ubicaciones:  
  
-   Información de parámetros de IntelliSense.  Para obtener más información, vea [Utilizar IntelliSense](/visual-studio/ide/using-intellisense).  
  
-   Examinador de objetos.  Para obtener más información, vea [Ver la estructura del código](/visual-studio/ide/viewing-the-structure-of-code).  
  
 Compile con [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación en un archivo.  
  
## Ejemplo  
 En este ejemplo se utiliza la etiqueta `<param>` para describir el parámetro `id`.  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/param_1.vb)]  
  
## Vea también  
 [Etiquetas XML para comentarios](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)