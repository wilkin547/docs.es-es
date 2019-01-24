---
title: '&lt;comentarios&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- <remarks> XML tag
- remarks XML tag
ms.assetid: c6241773-a7ed-41c9-9a8b-9722a0c606a9
ms.openlocfilehash: 137e2fcd36d5d7618e0193461ebf7ca70b24d19f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54737655"
---
# <a name="ltremarksgt-visual-basic"></a>&lt;comentarios&gt; (Visual Basic)
Especifica una sección de comentarios del miembro.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<remarks>description</remarks>  
```  
  
#### <a name="parameters"></a>Parámetros  
 `description`  
 Descripción del miembro.  
  
## <a name="remarks"></a>Comentarios  
 Use la `<remarks>` etiqueta para agregar información sobre un tipo, complementar la información especificada con [ \<resumen >](../../../visual-basic/language-reference/xmldoc/summary.md).  
  
 Esta información aparece en el Examinador de objetos. Para obtener información sobre el Examinador de objetos, vea [ver la estructura del código](/visualstudio/ide/viewing-the-structure-of-code).  
  
 Compile con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación a un archivo.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo se usa el `<remarks>` etiqueta para explicar qué es el `UpdateRecord` método.  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/remarks_1.vb)]  
  
## <a name="see-also"></a>Vea también
- [Etiquetas XML para comentarios](../../../visual-basic/language-reference/xmldoc/index.md)
