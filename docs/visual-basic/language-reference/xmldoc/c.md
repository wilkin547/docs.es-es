---
title: <c>
ms.date: 07/20/2015
helpviewer_keywords:
- c XML tag
- <c> XML tag
ms.assetid: 36ad5d1b-11f7-4012-8932-41962ac327d1
ms.openlocfilehash: c8ba03d9cc01c4751d15c01530c6cbf7d499dc3b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400168"
---
# <a name="c-visual-basic"></a>\<c> (Visual Basic)
Indica que el texto de una descripción es código.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<c>text</c>  
```  
  
## <a name="parameters"></a>Parámetros  
  
|Parámetro|Descripción|  
|---|---|  
|`text`|El texto que le gustaría indicar como código.|  
  
## <a name="remarks"></a>Observaciones  
 La `<c>` etiqueta proporciona una manera de indicar que el texto dentro de una descripción debe marcarse como código. [\<code>](code.md)Se usa para indicar varias líneas como código.  
  
 Compile with [-doc](../../reference/command-line-compiler/doc.md) para procesar los comentarios de documentación en un archivo.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se usa la `<c>` etiqueta en la sección de resumen para indicar que `Counter` es código.  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a>Consulte también

- [Etiquetas de comentario XML](index.md)
