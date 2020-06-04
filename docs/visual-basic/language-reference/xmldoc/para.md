---
title: <para>
ms.date: 07/20/2015
helpviewer_keywords:
- <para> XML tag
- para XML tag
ms.assetid: a3a18b6c-6416-4358-94ec-37b22675fd37
ms.openlocfilehash: 0e2051d1b00b881c06082b3af483890d8595899f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400078"
---
# <a name="para-visual-basic"></a>\<para> (Visual Basic)
Especifica que el contenido está formateado como un párrafo.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<para>content</para>  
```  
  
## <a name="parameters"></a>Parámetros  
 `content`  
 El texto del párrafo.  
  
## <a name="remarks"></a>Comentarios  
 La `<para>` etiqueta se usa dentro de una etiqueta, como [\<summary>](summary.md) , [\<remarks>](remarks.md) o [\<returns>](returns.md) , y permite agregar la estructura al texto.  
  
 Compile con [-doc](../../reference/command-line-compiler/doc.md) para procesar los comentarios de documentación de un archivo.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se usa la `<para>` etiqueta para dividir la sección Comentarios del `UpdateRecord` método en dos párrafos.  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>Vea también

- [Etiquetas de comentario XML](index.md)
