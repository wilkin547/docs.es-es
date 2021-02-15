---
description: 'Más información sobre: tipos de métodos de manipulación de cadenas en Visual Basic'
title: Tipos de métodos de manipulación de cadenas
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], manipulating [Visual Basic]
- string manipulation
ms.assetid: 905055cd-7f50-48fb-9eed-b0995af1dc1f
ms.openlocfilehash: 02b127d5cd023a8bd73a3042a8bcec340ce63ed8
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100429759"
---
# <a name="types-of-string-manipulation-methods-in-visual-basic"></a>Tipos de métodos de manipulación de cadenas en Visual Basic

Hay varias maneras de analizar y manipular las cadenas. Algunos de los métodos forman parte del lenguaje Visual Basic y otros son inherentes a la `String` clase.  
  
## <a name="visual-basic-language-and-the-net-framework"></a>Visual Basic idioma y el .NET Framework  

 Visual Basic métodos se usan como funciones inherentes del lenguaje. Se pueden usar sin calificación en el código. En el ejemplo siguiente se muestra el uso típico de un comando de manipulación de cadenas Visual Basic:  
  
 [!code-vb[VbVbalrStrings#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#44)]  
  
 En este ejemplo, la `Mid` función realiza una operación directa en `aString` y asigna el valor a `bString` .  
  
 Para obtener una lista de los métodos de manipulación de cadenas de Visual Basic, vea Resumen de la [manipulación de cadenas](../../../language-reference/keywords/string-manipulation-summary.md).  
  
### <a name="shared-methods-and-instance-methods"></a>Métodos compartidos y métodos de instancia  

 También puede manipular cadenas con los métodos de la `String` clase. Hay dos tipos de métodos en `String` : métodos *compartidos* y métodos de *instancia* .  
  
#### <a name="shared-methods"></a>Métodos compartidos  

 Un método compartido es un método que se deriva de la `String` propia clase y no requiere que una instancia de esa clase funcione. Estos métodos se pueden calificar con el nombre de la clase ( `String` ) en lugar de con una instancia de la `String` clase. Por ejemplo:  
  
 [!code-vb[VbVbalrStrings#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#45)]  
  
 En el ejemplo anterior, el <xref:System.String.Copy%2A?displayProperty=nameWithType> método es un método estático, que actúa sobre una expresión que se proporciona y asigna el valor resultante a `bString` .  
  
#### <a name="instance-methods"></a>Métodos de instancia  

 Por el contrario, los métodos de instancia proceden de una instancia determinada de `String` y se deben calificar con el nombre de instancia. Por ejemplo:  
  
 [!code-vb[VbVbalrStrings#46](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#46)]  
  
 En este ejemplo, el <xref:System.String.Substring%2A?displayProperty=nameWithType> método es un método de la instancia de `String` (es decir, `aString` ). Realiza una operación en `aString` y asigna ese valor a `bString` .  
  
 Para obtener más información, vea la documentación de la <xref:System.String> clase.  
  
## <a name="see-also"></a>Consulte también

- [Introducción a las cadenas en Visual Basic](introduction-to-strings.md)
