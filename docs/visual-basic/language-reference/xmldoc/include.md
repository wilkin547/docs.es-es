---
title: '&lt;incluir&gt; (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- include XML tag
- <include> XML tag
ms.assetid: ba8e9173-82cd-460b-8938-a075a2dfb36d
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 22eebaa8da8ef082e132cfdf8cb68498bfe16d73
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="ltincludegt-visual-basic"></a>&lt;incluir&gt; (Visual Basic)
Hace referencia a otro archivo que describe los tipos y miembros en el código fuente.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<include file="filename" path="tagpath[@name='id']" />  
```  
  
#### <a name="parameters"></a>Parámetros  
 `filename`  
 Obligatorio. El nombre del archivo que contiene la documentación. El nombre de archivo se puede calificar con una ruta de acceso. Incluya `filename` comillas dobles ("").  
  
 `tagpath`  
 Obligatorio. La ruta de acceso de las etiquetas de `filename` que conduce a la etiqueta `name`. Escriba la ruta de acceso entre comillas dobles ("").  
  
 `name`  
 Obligatorio. El especificador de nombre en la etiqueta que precede a los comentarios. `Name`tendrá un `id`.  
  
 `id`  
 Obligatorio. El identificador de la etiqueta que precede a los comentarios. Incluya el identificador entre comillas simples (' ').  
  
## <a name="remarks"></a>Comentarios  
 Use la `<include>` etiqueta para hacer referencia a comentarios colocados en otro archivo que describen los tipos y miembros en el código fuente. Esto es una alternativa a colocar los comentarios de documentación directamente en el archivo de código fuente.  
  
 La `<include>` etiqueta utilizará la recomendación de la versión 1.0 de W3C XML Path Language (XPath). Para obtener más información para formas de personalizar su `<include>` utilizar está disponible en http://www.w3.org/TR/xpath.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo se utiliza la `<include>` etiqueta que se va a importar los comentarios de documentación de miembro desde un archivo denominado `commentFile.xml`.  
  
 [!code-vb[VbVbcnXmlDocComments#4](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/include_1.vb)]  
  
 El formato de la `commentFile.xml` es como sigue.  
  
```xml  
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
  
## <a name="see-also"></a>Vea también  
 [Etiquetas XML para comentarios](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
