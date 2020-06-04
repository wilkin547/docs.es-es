---
title: Tipos de datos de caracteres
ms.date: 07/20/2015
helpviewer_keywords:
- data types [Visual Basic], character
- String data type [Visual Basic], character data types
- character data types [Visual Basic]
- Char data type [Visual Basic], character data types
- data types [Visual Basic], choosing
ms.assetid: 902479ef-1679-47fc-9911-0c1c5008226c
ms.openlocfilehash: 33dd4c62776ae8c5ec0ce0a6d0858a7ed0d047fb
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401997"
---
# <a name="character-data-types-visual-basic"></a>Tipos de datos de caracteres (Visual Basic)
Visual Basic proporciona *tipos de datos de caracteres* para tratar con caracteres imprimibles y que se pueda mostrar. Aunque ambos tratan con caracteres Unicode, `Char` contiene un solo carácter, mientras que `String` contiene un número indefinido de caracteres.  
  
 Para obtener una tabla en la que se muestra una comparación en paralelo de los tipos de datos Visual Basic, vea [tipos de datos](../../../language-reference/data-types/index.md).  
  
## <a name="char-type"></a>Char (tipo)  
 El `Char` tipo de datos es un único carácter Unicode de dos bytes (16 bits). Si una variable siempre almacena exactamente un carácter, declárelo como `Char` . Por ejemplo:  
  
 [!code-vb[VbVbalrCharTypes#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrchartypes/vb/module1.vb#1)]
  
 Cada valor posible de una `Char` `String` variable o es un *punto de código*, o código de carácter, en el juego de caracteres Unicode. Los caracteres Unicode incluyen el juego de caracteres ASCII básico, otras letras, acentos, símbolos de moneda, fracciones, diacríticos y símbolos matemáticos y técnicos.  
  
> [!NOTE]
> El juego de caracteres Unicode reserva los puntos de código D800 a DFFF (de 55296 a 55551 decimal) para los *pares suplentes*, que requieren valores de 2 16 bits para representar un solo punto de código. Una `Char` variable no puede contener un par suplente y `String` usa dos posiciones para contener este tipo de par.  
  
 Para obtener más información, vea [Char (tipo de datos](../../../language-reference/data-types/char-data-type.md)).  
  
## <a name="string-type"></a>Tipo de cadena  
 El `String` tipo de datos es una secuencia de cero o más caracteres Unicode de dos bytes (16 bits). Si una variable puede contener un número indefinido de caracteres, declárelo como `String` . Por ejemplo:  
  
 [!code-vb[VbVbalrCharTypes#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrchartypes/vb/module1.vb#2)]
  
 Para obtener más información, vea [String (tipo de datos](../../../language-reference/data-types/string-data-type.md)).  
  
## <a name="see-also"></a>Consulte también

- [Tipos de datos básicos](elementary-data-types.md)
- [Tipos de datos compuestos](composite-data-types.md)
- [Tipos genéricos en Visual Basic](generic-types.md)
- [Tipos de valor y tipos de referencia](value-types-and-reference-types.md)
- [Conversiones de tipos en Visual Basic](type-conversions.md)
- [Solución de problemas de los tipos de datos](troubleshooting-data-types.md)
- [Caracteres de tipo](type-characters.md)
