---
title: '&lt;Devuelve&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- returns XML tag
- <returns> XML tag
ms.assetid: a03a6469-d907-425d-882f-083187950e7e
ms.openlocfilehash: 4dcf8e9aee6edecbda2874a6e07fbe6e3772b18b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54580530"
---
# <a name="ltreturnsgt-visual-basic"></a>&lt;Devuelve&gt; (Visual Basic)
Especifica el valor devuelto de la propiedad o función.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<returns>description</returns>  
```  
  
#### <a name="parameters"></a>Parámetros  
 `description`  
 Descripción del valor devuelto.  
  
## <a name="remarks"></a>Comentarios  
 Use la `<returns>` etiqueta en el comentario de una declaración de método describir el valor devuelto.  
  
 Compile con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación a un archivo.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo se usa el `<returns>` etiqueta para explicar qué es el `DoesRecordExist` función devuelve.  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/returns_1.vb)]  
  
## <a name="see-also"></a>Vea también
- [Etiquetas XML para comentarios](../../../visual-basic/language-reference/xmldoc/index.md)
