---
title: <c>
ms.date: 07/20/2015
helpviewer_keywords:
- c XML tag
- <c> XML tag
ms.assetid: 36ad5d1b-11f7-4012-8932-41962ac327d1
ms.openlocfilehash: 857ea1ccca4d74daf65bba03845004561afefd55
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348508"
---
# <a name="c-visual-basic"></a>\<c > (Visual Basic)
Indica que el texto de una descripción es código.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<c>text</c>  
```  
  
## <a name="parameters"></a>Parámetros  
  
|Parámetro|Descripción|  
|---|---|  
|`text`|El texto que le gustaría indicar como código.|  
  
## <a name="remarks"></a>Comentarios  
 La etiqueta `<c>` proporciona una manera de indicar que el texto de una descripción debe marcarse como código. Use [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) para indicar varias líneas como código.  
  
 Compile con [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación de un archivo.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se usa la etiqueta `<c>` de la sección Summary para indicar que `Counter` es code.  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a>Vea también

- [Etiquetas XML para comentarios](../../../visual-basic/language-reference/xmldoc/index.md)
