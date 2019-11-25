---
title: <code>
ms.date: 07/20/2015
helpviewer_keywords:
- code XML tag
- <code> XML tag
ms.assetid: 925e5342-be05-45f2-bf66-7398bbd6710e
ms.openlocfilehash: 1cbac2162bd39cdc8af9a55dfd6e2f90bc40b08a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354320"
---
# <a name="code-visual-basic"></a>\<code> (Visual Basic)
Indicates that the text is multiple lines of code.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<code>content</code>  
```  
  
## <a name="parameters"></a>Parámetros  
 `content`  
 The text to mark as code.  
  
## <a name="remarks"></a>Comentarios  
 Use the `<code>` tag to indicate multiple lines as code. Use [\<c>](../../../visual-basic/language-reference/xmldoc/c.md) para indicar que el texto dentro de una descripción debe marcarse como código.  
  
 Compile con [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación de un archivo.  
  
## <a name="example"></a>Ejemplo  
 This example uses the \<code> tag to include example code for using the `ID` field.  
  
 [!code-vb[VbVbcnXmlDocComments#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#2)]  
  
## <a name="see-also"></a>Vea también

- [Etiquetas XML para comentarios](../../../visual-basic/language-reference/xmldoc/index.md)
