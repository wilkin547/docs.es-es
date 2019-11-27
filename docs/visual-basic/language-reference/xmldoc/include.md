---
title: <include>
ms.date: 07/20/2015
helpviewer_keywords:
- include XML tag
- <include> XML tag
ms.assetid: ba8e9173-82cd-460b-8938-a075a2dfb36d
ms.openlocfilehash: 2f2bebfd06d4614f05cb66834cc5bef40524ce3b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348456"
---
# <a name="include-visual-basic"></a>\<incluir > (Visual Basic)
Hace referencia a otro archivo que describe los tipos y miembros en el código fuente.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<include file="filename" path="tagpath[@name='id']" />  
```  
  
## <a name="parameters"></a>Parámetros  
 `filename`  
 Obligatorio. El nombre del archivo que contiene la documentación. El nombre de archivo se puede calificar con una ruta de acceso. Escriba `filename` entre comillas dobles ("").  
  
 `tagpath`  
 Obligatorio. La ruta de acceso de las etiquetas de `filename` que conduce a la etiqueta `name`. Escriba la ruta de acceso entre comillas dobles ("").  
  
 `name`  
 Obligatorio. Especificador de nombre en la etiqueta que precede a los comentarios. `Name` tendrá un `id`.  
  
 `id`  
 Obligatorio. El identificador de la etiqueta que precede a los comentarios. Incluya el identificador entre comillas simples (' ').  
  
## <a name="remarks"></a>Comentarios  
 Use la etiqueta `<include>` para hacer referencia a los comentarios de otro archivo que describen los tipos y miembros del código fuente. Esto es una alternativa a colocar los comentarios de documentación directamente en el archivo de código fuente.  
  
 La etiqueta `<include>` usa la recomendación W3C XML Path Language (XPath) versión 1,0. Para obtener más información acerca de cómo personalizar el uso de `<include>`, vea <https://www.w3.org/TR/xpath>.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se usa la etiqueta `<include>` para importar los comentarios de documentación de los miembros de un archivo denominado `commentFile.xml`.  
  
 [!code-vb[VbVbcnXmlDocComments#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#4)]  
  
 El formato del `commentFile.xml` es el siguiente.  
  
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

- [Etiquetas XML para comentarios](../../../visual-basic/language-reference/xmldoc/index.md)
