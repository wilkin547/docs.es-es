---
title: <para>
ms.date: 07/20/2015
helpviewer_keywords:
- <para> XML tag
- para XML tag
ms.assetid: a3a18b6c-6416-4358-94ec-37b22675fd37
ms.openlocfilehash: 0846efbaf2afacd3d0783a2d2d8e4dae3fc8b715
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90872701"
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

 La etiqueta `<para>` se usa dentro de otra etiqueta, como [\<summary>](summary.md), [\<remarks>](remarks.md) o [\<returns>](returns.md), y permite dar una estructura al texto.  
  
 Compile con [-doc](../../reference/command-line-compiler/doc.md) para procesar los comentarios de documentación de un archivo.  
  
## <a name="example"></a>Ejemplo  

 En este ejemplo se usa la `<para>` etiqueta para dividir la sección Comentarios del `UpdateRecord` método en dos párrafos.  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>Consulte también

- [Etiquetas de comentario XML](index.md)
