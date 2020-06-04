---
title: <include>
ms.date: 07/20/2015
helpviewer_keywords:
- include XML tag
- <include> XML tag
ms.assetid: ba8e9173-82cd-460b-8938-a075a2dfb36d
ms.openlocfilehash: 78a10624107cea349b01f484c641190a945dbd7e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400116"
---
# <a name="include-visual-basic"></a>\<include> (Visual Basic)
Hace referencia a otro archivo que describe los tipos y miembros en el código fuente.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<include file="filename" path="tagpath[@name='id']" />  
```  
  
## <a name="parameters"></a>Parámetros  
 `filename`  
 Necesario. El nombre del archivo que contiene la documentación. El nombre de archivo se puede calificar con una ruta de acceso. Escribir `filename` entre comillas dobles ("").  
  
 `tagpath`  
 Necesario. La ruta de acceso de las etiquetas de `filename` que conduce a la etiqueta `name`. Escriba la ruta de acceso entre comillas dobles ("").  
  
 `name`  
 Necesario. Especificador de nombre en la etiqueta que precede a los comentarios. `Name`tendrá una `id` .  
  
 `id`  
 Necesario. El identificador de la etiqueta que precede a los comentarios. Incluya el identificador entre comillas simples (' ').  
  
## <a name="remarks"></a>Observaciones  
 Use la `<include>` etiqueta para hacer referencia a los comentarios de otro archivo que describen los tipos y miembros en el código fuente. Esto es una alternativa a colocar los comentarios de documentación directamente en el archivo de código fuente.  
  
 La `<include>` etiqueta usa la recomendación W3C XML Path Language (XPath) versión 1,0. Para obtener más información acerca de cómo personalizar el `<include>` uso, vea <https://www.w3.org/TR/xpath> .  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se usa la `<include>` etiqueta para importar los comentarios de documentación de los miembros de un archivo denominado `commentFile.xml` .  
  
 [!code-vb[VbVbcnXmlDocComments#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#4)]  
  
 El formato de `commentFile.xml` es el siguiente.  
  
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
  
## <a name="see-also"></a>Consulte también

- [Etiquetas de comentario XML](index.md)
