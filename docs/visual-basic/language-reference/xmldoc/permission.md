---
title: "&lt;permission&gt; (Visual Basic) | Microsoft Docs"
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
  - "<permission> (etiqueta XML)"
  - "permission (etiqueta XML)"
ms.assetid: 0edf0500-5cd7-49c0-9255-64c48f972b77
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;permission&gt; (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Especifica un permiso necesario para el miembro.  
  
## Sintaxis  
  
```  
<permission cref="member">description</permission>  
```  
  
#### Parámetros  
 `member`  
 Referencia a un miembro o campo al cual se puede llamar desde el entorno de compilación actual.  El compilador comprueba si el elemento de código dado existe y traduce `member` al nombre de elemento canónico en el resultado XML.  Agregue `member` entre comillas \(" "\).  
  
 `description`  
 Descripción del acceso al miembro.  
  
## Comentarios  
 Utilice la etiqueta `<permission>` para documentar el acceso de un miembro.  Utilice la clase <xref:System.Security.PermissionSet> para especificar el acceso a un miembro.  
  
 Compile con [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación en un archivo.  
  
## Ejemplo  
 Este ejemplo utiliza la etiqueta `<permission>` para describir que el método `ReadFile` requiere <xref:System.Security.Permissions.FileIOPermission>.  
  
 [!code-vb[VbVbcnXmlDocComments#7](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/permission_1.vb)]  
  
## Vea también  
 [Etiquetas XML para comentarios](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)