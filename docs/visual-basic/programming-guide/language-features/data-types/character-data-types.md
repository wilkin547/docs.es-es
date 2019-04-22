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
ms.openlocfilehash: 14085172a8f9f9d60af0495a36dd4ba7592213fa
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58840983"
---
# <a name="character-data-types-visual-basic"></a>Tipos de datos de caracteres (Visual Basic)
Visual Basic ofrece *tipos de datos de caracteres* para tratar con caracteres que se puede mostrar e imprimir. Aunque ambas tienen que ver con los caracteres Unicode, `Char` contiene un único carácter, mientras que `String` contiene un número indefinido de caracteres.  
  
 Para una tabla que muestra una comparación en paralelo de los tipos de datos de Visual Basic, vea [tipos de datos](../../../../visual-basic/language-reference/data-types/index.md).  
  
## <a name="char-type"></a>Tipo char  
 El `Char` tipo de datos es un único carácter Unicode de dos bytes (16 bits). Si una variable siempre almacena exactamente un carácter, declárelo como `Char`. Por ejemplo:  
  
 [!code-vb[VbVbalrCharTypes#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrchartypes/vb/module1.vb#1)]
  
 Cada valor posible en un `Char` o `String` variable es un *punto de código*, o el código en el juego de caracteres Unicode. Los caracteres Unicode incluyen el juego de caracteres ASCII básico, diversas otras letras del alfabeto, acentos, símbolos de moneda, fracciones, los signos diacríticos y símbolos técnicos y matemáticos.  
  
> [!NOTE]
>  Juego de caracteres Unicode recursos en reserva en los puntos de código D800 a DFFF (55296 a 55551 decimales) para *pares suplentes*, que requiere dos valores de 16 bits para representar un único punto de código. Un `Char` variable no puede contener un par suplente y un `String` utiliza dos posiciones que contiene un par de este tipo.  
  
 Para obtener más información, consulte [tipo de datos Char](../../../../visual-basic/language-reference/data-types/char-data-type.md).  
  
## <a name="string-type"></a>Tipo de cadena  
 El `String` tipo de datos es una secuencia de cero o más caracteres Unicode de dos bytes (16 bits). Si una variable puede contener un número indefinido de caracteres, declárelo como `String`. Por ejemplo:  
  
 [!code-vb[VbVbalrCharTypes#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrchartypes/vb/module1.vb#2)]
  
 Para obtener más información, consulte [tipo de datos String](../../../../visual-basic/language-reference/data-types/string-data-type.md).  
  
## <a name="see-also"></a>Vea también

- [Tipos de datos básicos](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [Tipos de datos compuestos](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [Generic Types in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [Conversiones de tipos en Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [Solución de problemas de tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Caracteres de tipo](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
