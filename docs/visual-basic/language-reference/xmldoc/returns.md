---
title: <returns> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- returns XML tag
- <returns> XML tag
ms.assetid: a03a6469-d907-425d-882f-083187950e7e
ms.openlocfilehash: 5a0ff0da7cf26a1cea75a5b2e4678593d9b72f54
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940795"
---
# <a name="returns-visual-basic"></a>\<Devuelve > (Visual Basic)
Especifica el valor devuelto de la propiedad o función.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<returns>description</returns>  
```  
  
## <a name="parameters"></a>Parámetros  
 `description`  
 Descripción del valor devuelto.  
  
## <a name="remarks"></a>Comentarios  
 Use la `<returns>` etiqueta en el comentario de una declaración de método describir el valor devuelto.  
  
 Compile con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación a un archivo.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo se usa el `<returns>` etiqueta para explicar qué es el `DoesRecordExist` función devuelve.  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>Vea también

- [Etiquetas XML para comentarios](../../../visual-basic/language-reference/xmldoc/index.md)
