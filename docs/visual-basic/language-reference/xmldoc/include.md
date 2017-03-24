---
title: "&lt;include&gt; (Visual Basic) | Microsoft Docs"
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
  - "<include> (etiqueta XML)"
  - "include (etiqueta XML)"
ms.assetid: ba8e9173-82cd-460b-8938-a075a2dfb36d
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# &lt;include&gt; (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Hace referencia a otro archivo que describe los tipos y miembros de su código fuente.  
  
## Sintaxis  
  
```  
<include file="filename" path="tagpath[@name='id']" />  
```  
  
#### Parámetros  
 `filename`  
 Obligatorio.  Nombre del archivo que contiene la documentación.  El nombre de archivo se puede completar con una ruta de acceso.  Agregue `filename` entre comillas \(" "\).  
  
 `tagpath`  
 Obligatorio.  Ruta de acceso de las etiquetas de `filename` que conduce a la etiqueta `name`.  Agregue la ruta entre comillas \(" "\).  
  
 `name`  
 Obligatorio.  Especificador de nombres de la etiqueta que precede a los comentarios.  `Name` tendrá un `id`.  
  
 `id`  
 Obligatorio.  Identificador para la etiqueta que precede a los comentarios.  Agregue el identificador entre comillas simples \(' '\).  
  
## Comentarios  
 Utilice la etiqueta `<include>` para hacer referencia a comentarios colocados en otro archivo que describen los tipos y miembros del código fuente.  Ésta es una alternativa al método habitual de colocar los comentarios de la documentación directamente en el archivo de código fuente.  
  
 La etiqueta `<include>` utiliza la recomendación W3C XML Path Language \(XPath\) Versión 1.0.  Para obtener más información sobre formas de personalizar el uso de `<include>`, puede ver http:\/\/www.w3.org\/TR\/xpath.  
  
## Ejemplo  
 Este ejemplo utiliza la etiqueta `<include>` para importar comentarios de documentación del miembro de un archivo denominado `commentFile.xml`.  
  
 [!code-vb[VbVbcnXmlDocComments#4](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/include_1.vb)]  
  
 El formato de `commentFile.xml` es el siguiente.  
  
```  
<Docs>  
<Members name="Open">  
<summary>Opens a file.</summary>  
<param name="filename">File name to open.</param>  
</Members>  
<Members name="Close">  
<summary>Closes a file.</summary>  
<param name="filename">File name to close.</param>  
</Members>  
</Docs>  
```  
  
## Vea también  
 [Etiquetas XML para comentarios](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)