---
title: Tipos de métodos de manipulación de cadenas en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], manipulating [Visual Basic]
- string manipulation
ms.assetid: 905055cd-7f50-48fb-9eed-b0995af1dc1f
ms.openlocfilehash: a75984d0eb64ef8c18def3ae59d5e1f4b6d20ce2
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56980352"
---
# <a name="types-of-string-manipulation-methods-in-visual-basic"></a>Tipos de métodos de manipulación de cadenas en Visual Basic
Hay varias maneras de analizar y manipular las cadenas. Algunos de los métodos son una parte del lenguaje Visual Basic y otros son inherentes a la `String` clase.  
  
## <a name="visual-basic-language-and-the-net-framework"></a>Lenguaje Visual Basic y .NET Framework  
 Métodos de Visual Basic se usan como funciones inherentes del lenguaje. Se puede usar sin calificación en el código. El ejemplo siguiente muestra un uso típico de un comando de manipulación de cadenas de Visual Basic:  
  
 [!code-vb[VbVbalrStrings#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#44)]  
  
 En este ejemplo, el `Mid` función realiza una operación directa en `aString` y asigna el valor a `bString`.  
  
 Para obtener una lista de métodos de manipulación de cadenas de Visual Basic, vea [resumen de manipulación de cadenas](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md).  
  
### <a name="shared-methods-and-instance-methods"></a>Métodos compartidos y métodos de instancia  
 También puede manipular cadenas con los métodos de la `String` clase. Hay dos tipos de métodos de `String`: *compartido* métodos y *instancia* métodos.  
  
#### <a name="shared-methods"></a>Métodos compartidos  
 Un método compartido es un método que se deriva el `String` propia clase y no requiere una instancia de esa clase para que funcionen. Estos métodos se pueden calificar con el nombre de la clase (`String`) en lugar de con una instancia de la `String` clase. Por ejemplo:  
  
 [!code-vb[VbVbalrStrings#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#45)]  
  
 En el ejemplo anterior, el <xref:System.String.Copy%2A?displayProperty=nameWithType> método es un método estático, que actúa sobre una expresión dada y asigna el valor resultante a `bString`.  
  
#### <a name="instance-methods"></a>Métodos de instancia  
 Métodos de instancia, por el contrario, se derivan de una instancia determinada de `String` y deben estar calificados con el nombre de instancia. Por ejemplo:  
  
 [!code-vb[VbVbalrStrings#46](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#46)]  
  
 En este ejemplo, el <xref:System.String.Substring%2A?displayProperty=nameWithType> método es un método de la instancia de `String` (es decir, `aString`). Realiza una operación en `aString` y asigna ese valor a `bString`.  
  
 Para obtener más información, consulte la documentación para el <xref:System.String> clase.  
  
## <a name="see-also"></a>Vea también
- [Introducción a las cadenas en Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
