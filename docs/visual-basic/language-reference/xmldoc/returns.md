---
title: '&lt;Devuelve&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- returns XML tag
- <returns> XML tag
ms.assetid: a03a6469-d907-425d-882f-083187950e7e
ms.openlocfilehash: 47debcef2c6ce56fda4c4a0818c8e813b41ebad1
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/25/2018
ms.locfileid: "42925023"
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
 [Etiquetas XML para comentarios](../../../visual-basic/language-reference/xmldoc/index.md)
