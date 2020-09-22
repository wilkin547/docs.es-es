---
title: <example>
ms.date: 07/20/2015
helpviewer_keywords:
- example XML tag
- <example> XML tag
ms.assetid: 90eeda1c-3fc4-427c-879c-5046d265a97c
ms.openlocfilehash: 6e9f63e4d31df7790f51ae4d166b606f2c63f14b
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90872977"
---
# <a name="example-visual-basic"></a>\<example> (Visual Basic)

Especifica un ejemplo para el miembro.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<example>description</example>  
```  
  
## <a name="parameters"></a>Parámetros  

 `description`  
 Una descripción del ejemplo de código.  
  
## <a name="remarks"></a>Comentarios  

 La etiqueta `<example>` le permite especificar un ejemplo de cómo usar un método u otro miembro de biblioteca. Esto normalmente implica el uso de la etiqueta [\<code>](code.md).  
  
 Compile con [-doc](../../reference/command-line-compiler/doc.md) para procesar los comentarios de documentación de un archivo.  
  
## <a name="example"></a>Ejemplo  

 En este ejemplo se usa la `<example>` etiqueta para incluir un ejemplo de uso del `ID` campo.  
  
 [!code-vb[VbVbcnXmlDocComments#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#2)]  
  
## <a name="see-also"></a>Consulte también

- [Etiquetas de comentario XML](index.md)
