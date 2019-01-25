---
title: Procedimiento Coincide con una cadena con un patrón (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- comparison operators [Visual Basic], comparing strings
- pattern matching
- strings [Visual Basic], comparing
- string comparison [Visual Basic], operators
- Visual Basic code, operators
- pattern matching [Visual Basic], string comparison
- string comparison [Visual Basic]
- Like operator [Visual Basic], pattern matching
- pattern matching, empty strings
- operators [Visual Basic], comparison
ms.assetid: 19a83804-b5af-4739-928b-ac93e64e457f
ms.openlocfilehash: a4d5f12c5cf1ba89f7b505fb44c3f8fb19cb09d4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54669164"
---
# <a name="how-to-match-a-string-against-a-pattern-visual-basic"></a>Procedimiento Coincide con una cadena con un patrón (Visual Basic)
Si desea averiguar si una expresión de la [tipo de datos String](../../../../visual-basic/language-reference/data-types/string-data-type.md) satisface un patrón, puede usar el [Like (operador)](../../../../visual-basic/language-reference/operators/like-operator.md).  
  
 `Like` toma dos operandos. El operando izquierdo es una expresión de cadena y el operando derecho es una cadena que contiene el patrón que se usará para la coincidencia. `Like` Devuelve un `Boolean` valor que indica si la expresión de cadena ajusta al modelo.  
  
 Puede hacer coincidir cada carácter de la expresión de cadena con un carácter concreto, un carácter comodín, una lista de caracteres o un intervalo de caracteres. Las posiciones de las especificaciones de la cadena patrón corresponden a las posiciones de los caracteres que debe coincidir con la expresión de cadena.  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-specific-character"></a>Para hacer coincidir un carácter en la expresión de cadena con un carácter específico  
  
-   Coloque el carácter concreto en la cadena de patrón directamente. Algunos caracteres especiales deben escribirse entre corchetes (`[ ]`). Para obtener más información, consulte [Like (operador)](../../../../visual-basic/language-reference/operators/like-operator.md).  
  
     El siguiente ejemplo se comprueba si `myString` consta exactamente de carácter único `H`.  
  
     [!code-vb[VbVbalrOperators#70](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-match-a-string-against-a-pattern_1.vb)]  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-wildcard-character"></a>Para hacer coincidir un carácter en la expresión de cadena con un carácter comodín  
  
-   Ponga un signo de interrogación (`?`) en la cadena de patrón. Cualquier carácter válido en esta posición realiza una coincidencia correcta.  
  
     El siguiente ejemplo se comprueba si `myString` se compone del carácter único `W` seguido de exactamente dos caracteres de los valores.  
  
     [!code-vb[VbVbalrOperators#71](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-match-a-string-against-a-pattern_2.vb)]  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters"></a>Para hacer coincidir un carácter en la expresión de cadena con una lista de caracteres  
  
-   Coloque corchetes (`[ ]`) en la cadena de patrón y dentro de los corchetes que ponga la lista de caracteres. No separe los caracteres con comas o cualquier otro separador. Cualquier carácter individual en la lista hace que sea una coincidencia correcta.  
  
     El siguiente ejemplo se comprueba si `myString` consta de cualquier carácter válido seguido exactamente uno de los caracteres `A`, `C`, o `E`.  
  
     [!code-vb[VbVbalrOperators#72](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-match-a-string-against-a-pattern_3.vb)]  
  
     Tenga en cuenta que esta coincidencia distingue mayúsculas de minúsculas.  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-range-of-characters"></a>Para hacer coincidir un carácter en la expresión de cadena con un intervalo de caracteres  
  
-   Coloque corchetes (`[ ]`) en la cadena de patrón y dentro de los corchetes que colocar los caracteres mínimo y máximo del intervalo, separados por un guión (`–`). Cualquier carácter individual dentro del intervalo, realiza una coincidencia correcta.  
  
     El siguiente ejemplo se comprueba si `myString` consta de los caracteres `num` seguido exactamente uno de los caracteres `i`, `j`, `k`, `l`, `m`, o `n`.  
  
     [!code-vb[VbVbalrOperators#73](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-match-a-string-against-a-pattern_4.vb)]  
  
     Tenga en cuenta que esta coincidencia distingue mayúsculas de minúsculas.  
  
## <a name="matching-empty-strings"></a>Coincidencia de cadenas vacías  
 `Like` trata la secuencia `[]` como una cadena de longitud cero (`""`). Puede usar `[]` para comprobar si toda la expresión está vacía, pero no puede usar para probar si una posición concreta en la expresión de cadena está vacía. Si una posición vacía es una de las opciones necesita va a comprobar, puede usar `Like` más de una vez.  
  
#### <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters-or-no-character"></a>Para hacer coincidir un carácter en la expresión de cadena con una lista de caracteres o ningún carácter  
  
1.  Llame a la `Like` operador dos veces en la misma expresión de cadena y conecte las dos llamadas con cualquiera el [operador o](../../../../visual-basic/language-reference/operators/or-operator.md) o [OrElse (operador)](../../../../visual-basic/language-reference/operators/orelse-operator.md).  
  
2.  En la cadena de patrón para la primera `Like` cláusula, incluir la lista de caracteres entre corchetes (`[ ]`).  
  
3.  En la cadena de patrón para el segundo `Like` cláusula, no coloque cualquier carácter en la posición en cuestión.  
  
     El ejemplo siguiente comprueba el número de teléfono de siete dígitos `phoneNum` exactamente tres dígitos numéricos, seguida por un espacio, un guión (`–`), un período (`.`), o ningún carácter en absoluto, seguidos exactamente cuatro dígitos numéricos.  
  
     [!code-vb[VbVbalrOperators#74](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-match-a-string-against-a-pattern_5.vb)]  
  
## <a name="see-also"></a>Vea también
- [Operadores de comparación](../../../../visual-basic/language-reference/operators/comparison-operators.md)
- [Operadores y expresiones](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [Like (operador)](../../../../visual-basic/language-reference/operators/like-operator.md)
- [String (tipo de datos)](../../../../visual-basic/language-reference/data-types/string-data-type.md)
