---
title: <exception>
ms.date: 07/20/2015
helpviewer_keywords:
- <exception> XML tag
- exception XML tag
ms.assetid: c0517549-171e-4dae-ab88-a9c1700b6eee
ms.openlocfilehash: e1e7f2d0fb06599f83ba224ed52a10429d9b11fe
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346960"
---
# <a name="exception-visual-basic"></a>\<> de excepciones (Visual Basic)
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
 Use la etiqueta `<exception>` para especificar qué excepciones se pueden iniciar. Esta etiqueta se aplica a una definición de método.  
  
 Compile con [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación de un archivo.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se usa la etiqueta `<exception>` para describir una excepción que la función `IntDivide` puede iniciar.  
  
 [!code-vb[VbVbcnXmlDocComments#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#3)]  
  
## <a name="see-also"></a>Vea también

- [Etiquetas XML para comentarios](../../../visual-basic/language-reference/xmldoc/index.md)
