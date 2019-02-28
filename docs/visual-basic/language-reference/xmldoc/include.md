---
title: <include> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- include XML tag
- <include> XML tag
ms.assetid: ba8e9173-82cd-460b-8938-a075a2dfb36d
ms.openlocfilehash: bf7a434569bf82066c79962ae24741759b97e5ce
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56973696"
---
# <a name="include-visual-basic"></a>\<Incluir > (Visual Basic)
Hace referencia a otro archivo que se describe los tipos y miembros en el código fuente.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<include file="filename" path="tagpath[@name='id']" />  
```  
  
#### <a name="parameters"></a>Parámetros  
 `filename`  
 Obligatorio. El nombre del archivo que contiene la documentación. El nombre de archivo se puede calificar con una ruta de acceso. Incluya `filename` comillas dobles ("").  
  
 `tagpath`  
 Obligatorio. La ruta de acceso de las etiquetas de `filename` que conduce a la etiqueta `name`. Incluya la ruta de acceso entre comillas dobles ("").  
  
 `name`  
 Obligatorio. El especificador de nombre en la etiqueta que precede a los comentarios. `Name` tendrá un `id`.  
  
 `id`  
 Obligatorio. El identificador de la etiqueta que precede a los comentarios. Ponga el identificador entre comillas simples (' ').  
  
## <a name="remarks"></a>Comentarios  
 Use la `<include>` etiqueta para hacer referencia a los comentarios de otro archivo que describen los tipos y miembros en el código fuente. Esto es una alternativa a colocar los comentarios de documentación directamente en el archivo de código fuente.  
  
 El `<include>` etiqueta usa la recomendación versión 1.0 de W3C XML Path Language (XPath). Para obtener más información acerca de las formas de personalizar su `<include>` , consulte <https://www.w3.org/TR/xpath>.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo se usa el `<include>` etiqueta para importar los comentarios de documentación de miembro de un archivo denominado `commentFile.xml`.  
  
 [!code-vb[VbVbcnXmlDocComments#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#4)]  
  
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
- [Etiquetas XML para comentarios](../../../visual-basic/language-reference/xmldoc/index.md)
