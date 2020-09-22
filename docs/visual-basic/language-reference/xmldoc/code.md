---
title: <code>
ms.date: 07/20/2015
helpviewer_keywords:
- code XML tag
- <code> XML tag
ms.assetid: 925e5342-be05-45f2-bf66-7398bbd6710e
ms.openlocfilehash: d058663213cf02f2142bff740aeec1b60791362c
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873028"
---
# <a name="code-visual-basic"></a>\<code> (Visual Basic)

Indica que el texto es varias líneas de código.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<code>content</code>  
```  
  
## <a name="parameters"></a>Parámetros  

 `content`  
 Texto que se va a marcar como código.  
  
## <a name="remarks"></a>Comentarios  

 Use la `<code>` etiqueta para indicar varias líneas como código. Use [\<c>](c.md) para indicar que el texto dentro de una descripción debe marcarse como código.  
  
 Compile con [-doc](../../reference/command-line-compiler/doc.md) para procesar los comentarios de documentación de un archivo.  
  
## <a name="example"></a>Ejemplo  

 En este ejemplo se usa la \<code> etiqueta para incluir código de ejemplo para usar el `ID` campo.  
  
 [!code-vb[VbVbcnXmlDocComments#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#2)]  
  
## <a name="see-also"></a>Consulte también

- [Etiquetas de comentario XML](index.md)
