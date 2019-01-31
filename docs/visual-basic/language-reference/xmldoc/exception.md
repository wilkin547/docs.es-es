---
title: <exception> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <exception> XML tag
- exception XML tag
ms.assetid: c0517549-171e-4dae-ab88-a9c1700b6eee
ms.openlocfilehash: b2475bd5eaeadc12e4c8c9b0fb77a2fa5cb88911
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55283947"
---
# <a name="exception-visual-basic"></a>\<excepción > (Visual Basic)
Especifica qué excepciones se pueden producir.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<exception cref="member">description</exception>  
```  
  
#### <a name="parameters"></a>Parámetros  
 `member`  
 Una referencia a una excepción que está disponible desde el entorno de compilación actual. El compilador comprueba si la excepción dada existe y traduce `member` al nombre de elemento canónico en la salida XML. `member` debe aparecer entre comillas dobles (" ").  
  
 `description`  
 Una descripción.  
  
## <a name="remarks"></a>Comentarios  
 Use la `<exception>` etiqueta para especificar qué excepciones se pueden producir. Esta etiqueta se aplica a una definición de método.  
  
 Compile con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación a un archivo.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo se usa el `<exception>` etiquetas para describir una excepción que el `IntDivide` función puede producir.  
  
 [!code-vb[VbVbcnXmlDocComments#3](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/exception_1.vb)]  
  
## <a name="see-also"></a>Vea también
- [Etiquetas XML para comentarios](../../../visual-basic/language-reference/xmldoc/index.md)
