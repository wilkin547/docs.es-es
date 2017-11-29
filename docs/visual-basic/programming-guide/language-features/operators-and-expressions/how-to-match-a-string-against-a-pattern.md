---
title: "Cómo: Comprobar si una cadena coincide con un modelo (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 83433bdb41df0ce40d0979f3f44603f10ba1c7d5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-match-a-string-against-a-pattern-visual-basic"></a>Cómo: Comprobar si una cadena coincide con un modelo (Visual Basic)
Si desea averiguar si una expresión de la [tipo de datos String](../../../../visual-basic/language-reference/data-types/string-data-type.md) satisface un patrón, puede usar el [operador Like](../../../../visual-basic/language-reference/operators/like-operator.md).  
  
 `Like`se aplica a dos operandos. El operando izquierdo es una expresión de cadena y el operando derecho es una cadena que contiene el patrón que se usará para la coincidencia. `Like`Devuelve un `Boolean` valor que indica si la expresión de cadena ajusta al modelo.  
  
 Puede hacer coincidir cada carácter de la expresión de cadena con un carácter concreto, un carácter comodín, una lista de caracteres o un intervalo de caracteres. Las posiciones de las especificaciones de la cadena patrón corresponden a las posiciones de los caracteres que se debe coincidir en la expresión de cadena.  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-specific-character"></a>Para hacer coincidir un carácter en la expresión de cadena con un carácter específico  
  
-   Coloque el carácter concreto en la cadena de patrón directamente. Algunos caracteres especiales deben incluirse entre corchetes (`[ ]`). Para obtener más información, consulte [operador Like](../../../../visual-basic/language-reference/operators/like-operator.md).  
  
     El ejemplo siguiente se comprueba si `myString` exactamente está formada por el carácter único `H`.  
  
     [!code-vb[VbVbalrOperators#70](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-match-a-string-against-a-pattern_1.vb)]  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-wildcard-character"></a>Para hacer coincidir un carácter en la expresión de cadena con un carácter comodín  
  
-   Coloque un signo de interrogación (`?`) en la cadena de patrón. Cualquier carácter válido en esta posición Obtiene una coincidencia correcta.  
  
     El ejemplo siguiente se comprueba si `myString` está formada por el carácter único `W` seguido exactamente dos caracteres de los valores.  
  
     [!code-vb[VbVbalrOperators#71](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-match-a-string-against-a-pattern_2.vb)]  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters"></a>Para hacer coincidir un carácter en la expresión de cadena con una lista de caracteres  
  
-   Coloque corchetes (`[ ]`) en la cadena del modelo y, dentro de los corchetes que coloque la lista de caracteres. No separe los caracteres con comas o cualquier otro tipo de separador. Cualquier carácter individual en la lista, realiza una coincidencia correcta.  
  
     El ejemplo siguiente se comprueba si `myString` está formada por cualquier carácter válido seguido por exactamente uno de los caracteres `A`, `C`, o `E`.  
  
     [!code-vb[VbVbalrOperators#72](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-match-a-string-against-a-pattern_3.vb)]  
  
     Tenga en cuenta que esta coincidencia distingue entre mayúsculas y minúsculas.  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-range-of-characters"></a>Para hacer coincidir un carácter en la expresión de cadena con un intervalo de caracteres  
  
-   Coloque corchetes (`[ ]`) en la cadena de patrón y dentro de los corchetes que colocar los caracteres mínimo y máximo del intervalo, separados por un guión (`–`). Cualquier carácter individual dentro del intervalo, realiza una coincidencia correcta.  
  
     El ejemplo siguiente se comprueba si `myString` consta de los caracteres `num` seguido exactamente uno de los caracteres `i`, `j`, `k`, `l`, `m`, o `n`.  
  
     [!code-vb[VbVbalrOperators#73](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-match-a-string-against-a-pattern_4.vb)]  
  
     Tenga en cuenta que esta coincidencia distingue entre mayúsculas y minúsculas.  
  
## <a name="matching-empty-strings"></a>Coincidencia de cadenas vacías  
 `Like`trata la secuencia `[]` como una cadena de longitud cero (`""`). Puede usar `[]` para comprobar si la expresión de cadena completa está vacía, pero no puede utilizarlo para probar si una posición concreta en la expresión de cadena está vacía. Si una posición vacía es una de las opciones deberá comprobar, puede usar `Like` más de una vez.  
  
#### <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters-or-no-character"></a>Para hacer coincidir un carácter en la expresión de cadena con una lista de caracteres o ningún carácter  
  
1.  Llame a la `Like` operador dos veces en la misma expresión de cadena y conecte las dos llamadas con cualquiera el [operador o](../../../../visual-basic/language-reference/operators/or-operator.md) o [OrElse (operador)](../../../../visual-basic/language-reference/operators/orelse-operator.md).  
  
2.  En la cadena de patrón para la primera `Like` cláusula, incluyen la lista de caracteres entre corchetes (`[ ]`).  
  
3.  En la cadena de patrón para el segundo `Like` cláusula, no coloque ningún carácter en la posición en cuestión.  
  
     En el ejemplo siguiente se comprueba el número de teléfono de siete dígitos `phoneNum` exactamente tres dígitos numéricos, seguido por un espacio, un guión (`–`), un período (`.`), o ningún carácter, seguidos por exactamente cuatro dígitos numéricos.  
  
     [!code-vb[VbVbalrOperators#74](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-match-a-string-against-a-pattern_5.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Operadores de comparación](../../../../visual-basic/language-reference/operators/comparison-operators.md)  
 [Operadores y expresiones](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [Like (operador)](../../../../visual-basic/language-reference/operators/like-operator.md)  
 [String (tipo de datos)](../../../../visual-basic/language-reference/data-types/string-data-type.md)
