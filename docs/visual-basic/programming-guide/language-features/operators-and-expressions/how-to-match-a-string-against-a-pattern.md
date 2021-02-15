---
description: 'Más información sobre: Cómo: buscar coincidencias de una cadena con un patrón (Visual Basic)'
title: Procedimiento para comprobar si una cadena coincide con un patrón
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
ms.openlocfilehash: f3e3426f85d420726571f03c88546d181cdccf97
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100461949"
---
# <a name="how-to-match-a-string-against-a-pattern-visual-basic"></a>Cómo: Comprobar si una cadena coincide con un modelo (Visual Basic)

Si desea averiguar si una expresión del tipo de datos de [cadena](../../../language-reference/data-types/string-data-type.md) satisface un modelo, puede usar el [operador like](../../../language-reference/operators/like-operator.md).

`Like` toma dos operandos. El operando izquierdo es una expresión de cadena y el operando derecho es una cadena que contiene el patrón que se va a usar para la búsqueda de coincidencias. `Like` Devuelve un `Boolean` valor que indica si la expresión de cadena satisface el modelo.

Puede hacer coincidir cada carácter de la expresión de cadena con un carácter específico, un carácter comodín, una lista de caracteres o un intervalo de caracteres. Las posiciones de las especificaciones en la cadena de patrón corresponden a las posiciones de los caracteres que se van a buscar en la expresión de cadena.

## <a name="to-match-a-character-in-the-string-expression-against-a-specific-character"></a>Para hacer coincidir un carácter de la expresión de cadena con un carácter concreto

Coloque el carácter específico directamente en la cadena de patrón. Algunos caracteres especiales deben ir entre corchetes ( `[ ]` ). Para obtener más información, vea [operador like](../../../language-reference/operators/like-operator.md).

En el ejemplo siguiente se comprueba si `myString` consta exactamente del carácter único `H` .

[!code-vb[VbVbalrOperators#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#70)]

## <a name="to-match-a-character-in-the-string-expression-against-a-wildcard-character"></a>Para hacer coincidir un carácter de la expresión de cadena con un carácter comodín

Coloque un signo de interrogación ( `?` ) en la cadena de patrón. Cualquier carácter válido en esta posición realiza una coincidencia correcta.

En el ejemplo siguiente se comprueba si `myString` consta del carácter individual `W` seguido de exactamente dos caracteres de cualquier valor.

[!code-vb[VbVbalrOperators#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#71)]

## <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters"></a>Para hacer coincidir un carácter de la expresión de cadena con una lista de caracteres

Escriba corchetes ( `[ ]` ) en la cadena de patrón y, dentro de los corchetes, coloque la lista de caracteres. No separe los caracteres con comas ni con ningún otro separador. Cualquier carácter individual de la lista realiza una coincidencia correcta.

En el ejemplo siguiente se comprueba si `myString` consta de cualquier carácter válido seguido de exactamente uno de los caracteres `A` , `C` o `E` .

[!code-vb[VbVbalrOperators#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#72)]

Tenga en cuenta que esta coincidencia distingue entre mayúsculas y minúsculas.

## <a name="to-match-a-character-in-the-string-expression-against-a-range-of-characters"></a>Para hacer coincidir un carácter de la expresión de cadena con un intervalo de caracteres

Escriba corchetes ( `[ ]` ) en la cadena de patrón y, dentro de los corchetes, coloque los caracteres más bajos y más altos en el intervalo, separados por un guión ( `–` ). Cualquier carácter individual del intervalo realiza una coincidencia correcta.

En el ejemplo siguiente se comprueba si `myString` consta de los caracteres `num` seguidos de exactamente uno de los caracteres `i` , `j` ,, `k` `l` , `m` o `n` .

[!code-vb[VbVbalrOperators#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#73)]

Tenga en cuenta que esta coincidencia distingue entre mayúsculas y minúsculas.

## <a name="matching-empty-strings"></a>Coincidencia de cadenas vacías

`Like` trata la secuencia `[]` como una cadena de longitud cero ( `""` ). Puede usar `[]` para comprobar si la expresión de cadena completa está vacía, pero no puede utilizarla para probar si una posición determinada en la expresión de cadena está vacía. Si una posición vacía es una de las opciones que necesita probar, puede usar `Like` más de una vez.

### <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters-or-no-character"></a>Para hacer coincidir un carácter de la expresión de cadena con una lista de caracteres o sin carácter

1. Llame al `Like` operador dos veces en la misma expresión de cadena y conecte las dos llamadas con el [operador o](../../../language-reference/operators/or-operator.md) o con el [operador OrElse](../../../language-reference/operators/orelse-operator.md).

2. En la cadena de patrón de la primera `Like` cláusula, incluya la lista de caracteres entre corchetes ( `[ ]` ).

3. En la cadena de patrón de la segunda `Like` cláusula, no coloque ningún carácter en la posición en cuestión.

    En el ejemplo siguiente se prueba el número de teléfono `phoneNum` de siete dígitos para exactamente tres dígitos, seguidos de un espacio, un guión ( `–` ), un punto ( `.` ) o ningún carácter, seguido de exactamente cuatro dígitos numéricos.

    [!code-vb[VbVbalrOperators#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#74)]

## <a name="see-also"></a>Consulte también

- [Operadores de comparación](../../../language-reference/operators/comparison-operators.md)
- [Operadores y expresiones](index.md)
- [Like (Operador)](../../../language-reference/operators/like-operator.md)
- [String (Tipo de datos)](../../../language-reference/data-types/string-data-type.md)
