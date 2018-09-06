---
title: '&lt;c&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- c XML tag
- <c> XML tag
ms.assetid: 36ad5d1b-11f7-4012-8932-41962ac327d1
ms.openlocfilehash: 06c6899895f278fdf652725a05ecc7229805f4d4
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43854735"
---
# <a name="ltcgt-visual-basic"></a>&lt;c&gt; (Visual Basic)
Indica que el texto dentro de una descripción es código.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<c>text</c>  
```  
  
#### <a name="parameters"></a>Parámetros  
  
|Parámetro|Descripción|  
|---|---|  
|`text`|El texto que le gustaría indicar como código.|  
  
## <a name="remarks"></a>Comentarios  
 El `<c>` etiqueta ofrece una manera de indicar que el texto dentro de una descripción debe marcarse como código. Use [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) para indicar varias líneas como código.  
  
 Compile con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación a un archivo.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo se usa el `<c>` etiqueta en la sección de resumen para indicar que `Counter` es el código.  
  
 [!code-vb[VbVbcnXmlDocComments#1](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/c_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Etiquetas XML para comentarios](../../../visual-basic/language-reference/xmldoc/index.md)
