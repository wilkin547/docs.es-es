---
title: '&lt;c&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- c XML tag
- <c> XML tag
ms.assetid: 36ad5d1b-11f7-4012-8932-41962ac327d1
ms.openlocfilehash: 556c00fa761a1bce5e922a304706c78893550901
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33599611"
---
# <a name="ltcgt-visual-basic"></a>&lt;c&gt; (Visual Basic)
Indica que el texto de una descripción es código.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<c>text</c>  
```  
  
#### <a name="parameters"></a>Parámetros  
  
|Parámetro|Descripción|  
|---|---|  
|`text`|El texto que le gustaría indicar como código.|  
  
## <a name="remarks"></a>Comentarios  
 La `<c>` etiqueta ofrece una manera de indicar que el texto dentro de una descripción se debe marcar como código. Use [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) para indicar varias líneas como código.  
  
 Compile con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación a un archivo.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo se utiliza la `<c>` etiqueta en la sección de resumen para indicar que `Counter` es el código.  
  
 [!code-vb[VbVbcnXmlDocComments#1](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/c_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Etiquetas XML para comentarios](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
