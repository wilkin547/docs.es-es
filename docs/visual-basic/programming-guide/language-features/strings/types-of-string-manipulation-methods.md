---
title: "Tipos de métodos de manipulación de cadenas en Visual Basic | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- strings [Visual Basic], manipulating [Visual Basic]
- string manipulation
ms.assetid: 905055cd-7f50-48fb-9eed-b0995af1dc1f
caps.latest.revision: 12
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 349cfdb3e31225f6aeba90ac29aa1c66e37c7e11
ms.lasthandoff: 03/13/2017

---
# <a name="types-of-string-manipulation-methods-in-visual-basic"></a>Tipos de métodos de manipulación de cadenas en Visual Basic
Hay varias formas de analizar y manipular cadenas. Algunos de los métodos forman parte de la [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] lenguaje y otros son inherentes a la `String` clase.  
  
## <a name="visual-basic-language-and-the-net-framework"></a>Lenguaje Visual Basic y .NET Framework  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]métodos se utilizan como funciones inherentes del lenguaje. Se puede utilizar sin calificación en el código. En el ejemplo siguiente se muestra el uso típico de un [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] comando de manipulación de cadenas:  
  
 [!code-vb[VbVbalrStrings&#44;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_1.vb)]  
  
 En este ejemplo, el `Mid` función realiza una operación directa en `aString` y asigna el valor a `bString`.  
  
 Para obtener una lista de métodos de manipulación de cadenas de Visual Basic, consulte [resumen de manipulación de cadenas](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md).  
  
### <a name="shared-methods-and-instance-methods"></a>Métodos compartidos y métodos de instancia  
 También puede manipular cadenas con los métodos de la `String` clase. Hay dos tipos de métodos de `String`: *compartido* métodos y *instancia* métodos.  
  
#### <a name="shared-methods"></a>Métodos compartidos  
 Un método compartido es un método que se deriva el `String` propia clase y no requiere una instancia de dicha clase para funcionar. Estos métodos se pueden calificar con el nombre de la clase (`String`) en lugar de con una instancia de la `String` clase. Por ejemplo:  
  
 [!code-vb[VbVbalrStrings nº&45;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_2.vb)]  
  
 En el ejemplo anterior, el <xref:System.String.Copy%2A?displayProperty=fullName>método es un método estático, que actúa sobre una expresión dada y asigna el valor resultante a `bString`.</xref:System.String.Copy%2A?displayProperty=fullName>  
  
#### <a name="instance-methods"></a>Métodos de instancia  
 Métodos de instancia, por el contrario, se derivan de una instancia determinada de `String` y deben estar calificados con el nombre de instancia. Por ejemplo:  
  
 [!code-vb[VbVbalrStrings nº&46;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_3.vb)]  
  
 En este ejemplo, el <xref:System.String.Substring%2A?displayProperty=fullName>método es un método de la instancia de `String` (es decir, `aString`).</xref:System.String.Substring%2A?displayProperty=fullName> Realiza una operación en `aString` y asigna ese valor a `bString`.  
  
 Para obtener más información, consulte la documentación de la <xref:System.String>clase.</xref:System.String>  
  
## <a name="see-also"></a>Vea también  
 [Introducción a las cadenas en Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
