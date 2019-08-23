---
title: Tipos de datos de caracteres (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- data types [Visual Basic], character
- String data type [Visual Basic], character data types
- character data types [Visual Basic]
- Char data type [Visual Basic], character data types
- data types [Visual Basic], choosing
ms.assetid: 902479ef-1679-47fc-9911-0c1c5008226c
ms.openlocfilehash: d29e8771d61c04cf35aa71b5ba7fbba0d308c730
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965676"
---
# <a name="character-data-types-visual-basic"></a>Tipos de datos de caracteres (Visual Basic)
Visual Basic proporciona *tipos de datos de caracteres* para tratar con caracteres imprimibles y que se pueda mostrar. Aunque ambos tratan con caracteres Unicode, contiene `Char` un solo carácter, mientras `String` que contiene un número indefinido de caracteres.  
  
 Para obtener una tabla en la que se muestra una comparación en paralelo de los tipos de datos Visual Basic, vea [tipos de datos](../../../../visual-basic/language-reference/data-types/index.md).  
  
## <a name="char-type"></a>Char (tipo)  
 El `Char` tipo de datos es un único carácter Unicode de dos bytes (16 bits). Si una variable siempre almacena exactamente un carácter, declárelo como `Char`. Por ejemplo:  
  
 [!code-vb[VbVbalrCharTypes#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrchartypes/vb/module1.vb#1)]
  
 Cada valor posible de una `Char` variable `String` o es un *punto de código*, o código de carácter, en el juego de caracteres Unicode. Los caracteres Unicode incluyen el juego de caracteres ASCII básico, otras letras, acentos, símbolos de moneda, fracciones, diacríticos y símbolos matemáticos y técnicos.  
  
> [!NOTE]
> El juego de caracteres Unicode reserva los puntos de código D800 a DFFF (de 55296 a 55551 decimal) para los *pares suplentes*, que requieren valores de 2 16 bits para representar un solo punto de código. Una `Char` variable no puede contener un par suplente `String` y usa dos posiciones para contener este tipo de par.  
  
 Para obtener más información, vea [Char (tipo de datos](../../../../visual-basic/language-reference/data-types/char-data-type.md)).  
  
## <a name="string-type"></a>Tipo de cadena  
 El `String` tipo de datos es una secuencia de cero o más caracteres Unicode de dos bytes (16 bits). Si una variable puede contener un número indefinido de caracteres, declárelo como `String`. Por ejemplo:  
  
 [!code-vb[VbVbalrCharTypes#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrchartypes/vb/module1.vb#2)]
  
 Para obtener más información, vea [String (tipo de datos](../../../../visual-basic/language-reference/data-types/string-data-type.md)).  
  
## <a name="see-also"></a>Vea también

- [Tipos de datos básicos](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [Tipos de datos compuestos](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [Generic Types in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [Conversiones de tipos en Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [Solución de problemas de tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Caracteres de tipo](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
