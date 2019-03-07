---
title: <example> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- example XML tag
- <example> XML tag
ms.assetid: 90eeda1c-3fc4-427c-879c-5046d265a97c
ms.openlocfilehash: 8d1c2a958fa148238eaeedb9c2af3df2cb86d33d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57502610"
---
# <a name="example-visual-basic"></a>\<ejemplo > (Visual Basic)
Especifica un ejemplo para el miembro.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<example>description</example>  
```  
  
## <a name="parameters"></a>Parámetros  
 `description`  
 Una descripción del ejemplo de código.  
  
## <a name="remarks"></a>Comentarios  
 El `<example>` etiqueta le permite especificar un ejemplo de cómo usar un método u otro miembro de biblioteca. Esto normalmente implica el uso de la etiqueta [\<code>](../../../visual-basic/language-reference/xmldoc/code.md).  
  
 Compile con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación a un archivo.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo se usa el `<example>` etiqueta para incluir un ejemplo para usar el `ID` campo.  
  
 [!code-vb[VbVbcnXmlDocComments#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#2)]  
  
## <a name="see-also"></a>Vea también
- [Etiquetas XML para comentarios](../../../visual-basic/language-reference/xmldoc/index.md)
