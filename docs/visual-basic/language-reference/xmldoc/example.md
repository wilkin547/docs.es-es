---
title: '&lt;ejemplo&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- example XML tag
- <example> XML tag
ms.assetid: 90eeda1c-3fc4-427c-879c-5046d265a97c
ms.openlocfilehash: cd5ec21001263d7484500ab7680e6e36270e8768
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54670522"
---
# <a name="ltexamplegt-visual-basic"></a>&lt;ejemplo&gt; (Visual Basic)
Especifica un ejemplo para el miembro.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<example>description</example>  
```  
  
#### <a name="parameters"></a>Parámetros  
 `description`  
 Una descripción del ejemplo de código.  
  
## <a name="remarks"></a>Comentarios  
 El `<example>` etiqueta le permite especificar un ejemplo de cómo usar un método u otro miembro de biblioteca. Esto normalmente implica el uso de la etiqueta [\<code>](../../../visual-basic/language-reference/xmldoc/code.md).  
  
 Compile con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación a un archivo.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo se usa el `<example>` etiqueta para incluir un ejemplo para usar el `ID` campo.  
  
 [!code-vb[VbVbcnXmlDocComments#2](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/example_1.vb)]  
  
## <a name="see-also"></a>Vea también
- [Etiquetas XML para comentarios](../../../visual-basic/language-reference/xmldoc/index.md)
