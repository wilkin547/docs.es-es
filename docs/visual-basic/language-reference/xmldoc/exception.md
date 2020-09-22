---
title: <exception>
ms.date: 07/20/2015
helpviewer_keywords:
- <exception> XML tag
- exception XML tag
ms.assetid: c0517549-171e-4dae-ab88-a9c1700b6eee
ms.openlocfilehash: e3f386d2a1e15ea3e1519d6e1e5e31c34c73fb99
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90872905"
---
# <a name="exception-visual-basic"></a>\<exception> (Visual Basic)

Especifica qué excepciones se pueden iniciar.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<exception cref="member">description</exception>  
```  
  
## <a name="parameters"></a>Parámetros  

 `member`  
 Una referencia a una excepción que está disponible desde el entorno de compilación actual. El compilador comprueba si la excepción dada existe y traduce `member` al nombre de elemento canónico en la salida XML. `member` debe aparecer entre comillas dobles (" ").  
  
 `description`  
 Una descripción.  
  
## <a name="remarks"></a>Comentarios  

 Use la `<exception>` etiqueta para especificar qué excepciones se pueden iniciar. Esta etiqueta se aplica a una definición de método.  
  
 Compile con [-doc](../../reference/command-line-compiler/doc.md) para procesar los comentarios de documentación de un archivo.  
  
## <a name="example"></a>Ejemplo  

 En este ejemplo se usa la `<exception>` etiqueta para describir una excepción que la `IntDivide` función puede iniciar.  
  
 [!code-vb[VbVbcnXmlDocComments#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#3)]  
  
## <a name="see-also"></a>Consulte también

- [Etiquetas de comentario XML](index.md)
