---
title: <returns>
ms.date: 07/20/2015
helpviewer_keywords:
- returns XML tag
- <returns> XML tag
ms.assetid: a03a6469-d907-425d-882f-083187950e7e
ms.openlocfilehash: 62f70ae7f40fa3cde9492563b7bd14dfa5940a5f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352241"
---
# <a name="returns-visual-basic"></a>\<returns> (Visual Basic)
Specifies the return value of the property or function.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<returns>description</returns>  
```  
  
## <a name="parameters"></a>Parámetros  
 `description`  
 Descripción del valor devuelto.  
  
## <a name="remarks"></a>Comentarios  
 Use the `<returns>` tag in the comment for a method declaration to describe the return value.  
  
 Compile con [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación de un archivo.  
  
## <a name="example"></a>Ejemplo  
 This example uses the `<returns>` tag to explain what the `DoesRecordExist` function returns.  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>Vea también

- [Etiquetas XML para comentarios](../../../visual-basic/language-reference/xmldoc/index.md)
