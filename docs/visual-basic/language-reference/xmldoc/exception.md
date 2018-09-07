---
title: '&lt;excepción&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- <exception> XML tag
- exception XML tag
ms.assetid: c0517549-171e-4dae-ab88-a9c1700b6eee
ms.openlocfilehash: 047805ad91d87550da80448fd10883ae58647bd6
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44081293"
---
# <a name="ltexceptiongt-visual-basic"></a>&lt;excepción&gt; (Visual Basic)
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
 [Etiquetas XML para comentarios](../../../visual-basic/language-reference/xmldoc/index.md)
