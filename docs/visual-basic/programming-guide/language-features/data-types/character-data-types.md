---
title: Tipos de datos (Visual Basic) de caracteres | Documentos de Microsoft
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
- data types [Visual Basic], character
- String data type, character data types
- character data types [Visual Basic]
- Char data type, character data types
- data types [Visual Basic], choosing
ms.assetid: 902479ef-1679-47fc-9911-0c1c5008226c
caps.latest.revision: 23
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
ms.openlocfilehash: 7ce600fe188c94593e4c07e37883ca11f90d9ae5
ms.lasthandoff: 03/13/2017

---
# <a name="character-data-types-visual-basic"></a>Tipos de datos de caracteres (Visual Basic)
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]proporciona *tipos de datos de caracteres* para tratar con caracteres que se pueden mostrar e imprimir. Aunque ambos tipos utilizan caracteres Unicode, `Char` contiene un único carácter, mientras que `String` contiene un número indefinido de caracteres.  
  
 Para una tabla que muestra una comparación en paralelo de la [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] tipos de datos, vea [tipos de datos](../../../../visual-basic/language-reference/data-types/data-type-summary.md).  
  
## <a name="char-type"></a>Char (tipo)  
 El `Char` tipo de datos es un único carácter Unicode de dos bytes (16 bits). Si una variable siempre almacena exactamente un carácter, declárela como `Char`. Por ejemplo:  
  
 [!code-vb[1 VbVbalrCharTypes](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/character-data-types_1.vb)]  
  
 Cada valor posible de un `Char` o `String` variable es un *punto de código*, o código de carácter en el juego de caracteres Unicode. Los caracteres Unicode incluyen el juego de caracteres ASCII básico, diversas otras letras del alfabeto, acentos, símbolos de moneda, fracciones, signos diacríticos y símbolos matemáticos y técnicos.  
  
> [!NOTE]
>  Juego de caracteres Unicode reserva los puntos de código D800 u+DFFF (55296 a 55551 decimales) para *pares suplentes*, que requiere dos valores de 16 bits para representar un punto de código único. Un `Char` variable no puede contener un par suplente y un `String` utiliza dos posiciones para contener un par.  
  
 Para obtener más información, consulte [tipo de datos Char](../../../../visual-basic/language-reference/data-types/char-data-type.md).  
  
## <a name="string-type"></a>Tipo de cadena  
 El `String` tipo de datos es una secuencia de cero o más caracteres Unicode de dos bytes (16 bits). Si una variable puede contener un número indefinido de caracteres, se declara como `String`. Por ejemplo:  
  
 [!code-vb[VbVbalrCharTypes&#2;](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/character-data-types_2.vb)]  
  
 Para obtener más información, consulte [tipo de datos String](../../../../visual-basic/language-reference/data-types/string-data-type.md).  
  
## <a name="see-also"></a>Vea también  
 [Tipos de datos elementales](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)   
 [Tipos de datos compuestos](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)   
 [Tipos genéricos en Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [Tipos de valor y tipos de referencia](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)   
 [Conversiones de tipos en Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Solucionar problemas de tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [Caracteres de tipo](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
