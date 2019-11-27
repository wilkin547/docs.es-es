---
title: <example>
ms.date: 07/20/2015
helpviewer_keywords:
- example XML tag
- <example> XML tag
ms.assetid: 90eeda1c-3fc4-427c-879c-5046d265a97c
ms.openlocfilehash: 8f36ac1337dd0d1400180fbd3deae2bb24ad9c58
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348478"
---
# <a name="example-visual-basic"></a>> de ejemplo \<(Visual Basic)
Especifica un ejemplo para el miembro.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<example>description</example>  
```  
  
## <a name="parameters"></a>Parámetros  
 `description`  
 Una descripción del ejemplo de código.  
  
## <a name="remarks"></a>Comentarios  
 La etiqueta `<example>` permite especificar un ejemplo de cómo usar un método u otro miembro de la biblioteca. Esto normalmente implica el uso de la etiqueta [\<code>](../../../visual-basic/language-reference/xmldoc/code.md).  
  
 Compile con [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación de un archivo.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se usa la etiqueta `<example>` para incluir un ejemplo de uso del campo `ID`.  
  
 [!code-vb[VbVbcnXmlDocComments#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#2)]  
  
## <a name="see-also"></a>Vea también

- [Etiquetas XML para comentarios](../../../visual-basic/language-reference/xmldoc/index.md)
