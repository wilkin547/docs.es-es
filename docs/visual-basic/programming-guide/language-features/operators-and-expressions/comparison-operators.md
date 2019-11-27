---
title: Operadores de comparación
ms.date: 07/20/2015
helpviewer_keywords:
- comparison operators [Visual Basic], comparing strings
- comparison operators [Visual Basic], comparing objects
- strings [Visual Basic], comparing
- comparison operators [Visual Basic]
- string comparison [Visual Basic], operators
- objects [Visual Basic], comparing
- numbers [Visual Basic], comparing
- Visual Basic code, operators
- string comparison [Visual Basic]
- numeric values [Visual Basic], comparing
- comparison operators [Visual Basic], comparing numeric values
- operators [Visual Basic], comparison
ms.assetid: 0b570339-5407-474f-8421-e183a8b303ee
ms.openlocfilehash: e1feb08539e47ec6fda64aa1a1f8ec2cc19f7b62
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346064"
---
# <a name="comparison-operators-in-visual-basic"></a>Operadores de comparación en Visual Basic
Los operadores de comparación comparan dos expresiones y devuelven un valor `Boolean` que representa la relación de sus valores. Existen operadores para comparar valores numéricos, operadores para comparar cadenas y operadores para comparar objetos. Los tres tipos de operadores se describen aquí.  
  
## <a name="comparing-numeric-values"></a>Comparar valores numéricos  
 Visual Basic compara los valores numéricos utilizando seis operadores de comparación numéricos. Cada operador toma como operandos dos expresiones que se evalúan como valores numéricos. En la tabla siguiente se enumeran los operadores y se muestran ejemplos de cada uno.  
  
|Operador|Condición probada|Ejemplos|  
|--------------|----------------------|--------------|  
|`=` (igualdad)|¿El valor de la primera expresión es igual al valor de la segunda?|`23`   `=`   `33    ' False`<br /><br /> `23`   `=`   `23    ' True`<br /><br /> `23`   `=`   `12    ' False`|  
|`<>` (desigualdad)|¿El valor de la primera expresión es distinto del valor del segundo?|`23`   `<>`   `33    ' True`<br /><br /> `23`   `<>`   `23    ' False`<br /><br /> `23`   `<>`   `12    ' True`|  
|`<` (menor que)|¿El valor de la primera expresión es menor que el valor de la segunda?|`23`   `<`   `33    ' True`<br /><br /> `23`   `<`   `23    ' False`<br /><br /> `23`   `<`   `12    ' False`|  
|`>` (mayor que)|¿El valor de la primera expresión es mayor que el valor de la segunda?|`23`   `>`   `33    ' False`<br /><br /> `23`   `>`   `23    ' False`<br /><br /> `23`   `>`   `12    ' True`|  
|`<=` (menor o igual que)|¿El valor de la primera expresión es menor o igual que el valor de la segunda?|`23`   `<=`   `33    ' True`<br /><br /> `23`   `<=`   `23    ' True`<br /><br /> `23`   `<=`   `12    ' False`|  
|`>=` (mayor o igual que)|¿El valor de la primera expresión es mayor o igual que el valor de la segunda?|`23`   `>=`   `33    ' False`<br /><br /> `23`   `>=`   `23    ' True`<br /><br /> `23`   `>=`   `12    ' True`|  
  
## <a name="comparing-strings"></a>Comparar cadenas  
 Visual Basic compara cadenas mediante el [operador like](../../../../visual-basic/language-reference/operators/like-operator.md) y los operadores de comparación numéricos. El operador `Like` permite especificar un patrón. A continuación, la cadena se compara con el patrón y, si coincide, el resultado es `True`. De lo contrario, el resultado es `False`. Los operadores numéricos permiten comparar `String` valores según su criterio de ordenación, como se muestra en el ejemplo siguiente.  
  
 `"73" < "9"`  
  
 `' The result of the preceding comparison is True.`  
  
 El resultado del ejemplo anterior es `True` porque el primer carácter de la primera cadena se ordena antes que el primer carácter de la segunda cadena. Si los primeros caracteres fueran iguales, la comparación continuaría con el siguiente carácter de ambas cadenas, y así sucesivamente. También puede probar la igualdad de cadenas mediante el operador de igualdad, como se muestra en el ejemplo siguiente.  
  
 `"734" = "734"`  
  
 `' The result of the preceding comparison is True.`  
  
 Si una cadena es un prefijo de otro, como "AA" y "AAA", se considera que la cadena más larga es mayor que la cadena más corta. En el ejemplo siguiente se ilustra esto.  
  
 `"aaa" > "aa"`  
  
 `' The result of the preceding comparison is True.`  
  
 El criterio de ordenación se basa en una comparación binaria o en una comparación textual, dependiendo del valor de `Option Compare`. Para obtener más información [, vea Option Compare Statement](../../../../visual-basic/language-reference/statements/option-compare-statement.md).  
  
## <a name="comparing-objects"></a>Comparar objetos  
 Visual Basic compara dos variables de referencia de objeto con el [operador is](../../../../visual-basic/language-reference/operators/is-operator.md) y el [Operador IsNot](../../../../visual-basic/language-reference/operators/isnot-operator.md). Puede utilizar cualquiera de estos operadores para determinar si dos variables de referencia hacen referencia a la misma instancia de objeto. En el ejemplo siguiente se ilustra esto.  
  
 [!code-vb[VbVbalrOperators#65](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#65)]  
  
 En el ejemplo anterior, `x Is y` se evalúa como `True`, porque ambas variables hacen referencia a la misma instancia. Compare este resultado con el ejemplo siguiente.  
  
 [!code-vb[VbVbalrOperators#66](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#66)]  
  
 En el ejemplo anterior, `x Is y` se evalúa como `False`, porque aunque las variables hacen referencia a objetos del mismo tipo, hacen referencia a instancias diferentes de ese tipo.  
  
 Si desea probar dos objetos que no señalan a la misma instancia, el operador `IsNot` le permite evitar una combinación gramaticalmente torpe de `Not` y `Is`. En el ejemplo siguiente se ilustra esto.  
  
 [!code-vb[VbVbalrOperators#67](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#67)]  
  
 En el ejemplo anterior, `If a IsNot b` es equivalente a `If Not a Is b`.  
  
### <a name="comparing-object-type"></a>Comparar el tipo de objeto  
 Puede comprobar si un objeto es de un tipo determinado con la expresión `TypeOf`...`Is`. La sintaxis es la siguiente:  
  
 `TypeOf <objectexpression> Is <typename>`  
  
 Cuando `typename` especifica un tipo de interfaz, la expresión `TypeOf`...`Is` devuelve `True` si el objeto implementa el tipo de interfaz. Cuando `typename` es un tipo de clase, la expresión devuelve `True` si el objeto es una instancia de la clase especificada o de una clase que se deriva de la clase especificada. En el ejemplo siguiente se ilustra esto.  
  
 [!code-vb[VbVbalrOperators#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#68)]  
  
 En el ejemplo anterior, la expresión `TypeOf x Is Control` se evalúa como `True` porque el tipo de `x` es `Button`, que hereda de `Control`.  
  
 Para obtener más información, vea [operador typeof](../../../../visual-basic/language-reference/operators/typeof-operator.md).  
  
## <a name="see-also"></a>Vea también

- [Comparaciones de valores](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)
- [Operadores de comparación](../../../../visual-basic/language-reference/operators/comparison-operators.md)
- [Operadores](../../../../visual-basic/language-reference/operators/index.md)
- [Operadores aritméticos en Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [Operadores de concatenación en Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
- [Operadores lógicos y bit a bit en Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
