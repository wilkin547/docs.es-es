---
title: Operadores de comparación en Visual Basic
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
ms.openlocfilehash: d08974a929a723d4037300f9d72ae03c072d47fa
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58826163"
---
# <a name="comparison-operators-in-visual-basic"></a>Operadores de comparación en Visual Basic
Operadores de comparación comparan dos expresiones y devuelven un `Boolean` valor que representa la relación de los valores. Existen operadores para comparar valores numéricos, operadores para comparar cadenas y operadores para comparar objetos. Los tres tipos de operadores se describen a continuación.  
  
## <a name="comparing-numeric-values"></a>Comparar valores numéricos  
 Visual Basic compara valores numéricos con seis operadores de comparación numérica. Cada operador toma como operandos dos expresiones que se evalúan como valores numéricos. En la tabla siguiente se enumera los operadores y se muestra ejemplos de cada uno.  
  
|Operador|Condición de prueba|Ejemplos|  
|--------------|----------------------|--------------|  
|`=` (Igualdad)|¿Es el valor de la primera expresión igual al valor del segundo?|`23`   `=`   `33    ' False`<br /><br /> `23`   `=`   `23    ' True`<br /><br /> `23`   `=`   `12    ' False`|  
|`<>` (Desigualdad)|¿No es igual al valor de la segunda el valor de la primera expresión?|`23`   `<>`   `33    ' True`<br /><br /> `23`   `<>`   `23    ' False`<br /><br /> `23`   `<>`   `12    ' True`|  
|`<` (Menor que)|¿Es el valor de la primera expresión menor que el valor del segundo?|`23`   `<`   `33    ' True`<br /><br /> `23`   `<`   `23    ' False`<br /><br /> `23`   `<`   `12    ' False`|  
|`>` (Mayor que)|¿El valor de la primera expresión es mayor que el valor del segundo?|`23`   `>`   `33    ' False`<br /><br /> `23`   `>`   `23    ' False`<br /><br /> `23`   `>`   `12    ' True`|  
|`<=` (Menor o igual que)|¿Es el valor de la primera expresión menor o igual que el valor del segundo?|`23`   `<=`   `33    ' True`<br /><br /> `23`   `<=`   `23    ' True`<br /><br /> `23`   `<=`   `12    ' False`|  
|`>=` (Mayor o igual que)|¿Es el valor de la primera expresión mayor o igual que el valor del segundo?|`23`   `>=`   `33    ' False`<br /><br /> `23`   `>=`   `23    ' True`<br /><br /> `23`   `>=`   `12    ' True`|  
  
## <a name="comparing-strings"></a>Comparar cadenas  
 Visual Basic compara cadenas mediante la [Like (operador)](../../../../visual-basic/language-reference/operators/like-operator.md) , así como los operadores de comparación numérica. El `Like` operador permite especificar un patrón. La cadena, a continuación, se compara con el patrón, y si coincide, el resultado es `True`. De lo contrario, el resultado es `False`. Los operadores numéricos permiten comparar `String` valores según su criterio de ordenación, como se muestra en el ejemplo siguiente.  
  
 `"73" < "9"`  
  
 `' The result of the preceding comparison is True.`  
  
 El resultado en el ejemplo anterior es `True` porque el primer carácter de la primera cadena que se ordena delante del primer carácter en la segunda cadena. Si los primeros caracteres sean iguales, la comparación podría seguir al carácter siguiente en las dos cadenas y así sucesivamente. También puede comprobar la igualdad de cadenas con el operador de igualdad, como se muestra en el ejemplo siguiente.  
  
 `"734" = "734"`  
  
 `' The result of the preceding comparison is True.`  
  
 Si una cadena es un prefijo de otra, como "aa" y "aaa", la cadena más larga se considera que es mayor que la cadena más corta. Esto se ilustra en el siguiente ejemplo:  
  
 `"aaa" > "aa"`  
  
 `' The result of the preceding comparison is True.`  
  
 El criterio de ordenación se basa en una comparación binaria o una comparación textual según la configuración de `Option Compare`. Para obtener más información, consulte [instrucción Option Compare](../../../../visual-basic/language-reference/statements/option-compare-statement.md).  
  
## <a name="comparing-objects"></a>Comparar objetos  
 Visual Basic compara dos variables de referencia de objeto con el [operador Is](../../../../visual-basic/language-reference/operators/is-operator.md) y [IsNot (operador)](../../../../visual-basic/language-reference/operators/isnot-operator.md). Puede usar cualquiera de estos operadores para determinar si dos variables de referencia que hacen referencia a la misma instancia de objeto. Esto se ilustra en el siguiente ejemplo:  
  
 [!code-vb[VbVbalrOperators#65](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#65)]  
  
 En el ejemplo anterior, `x Is y` se evalúa como `True`, ya que ambas variables hacen referencia a la misma instancia. Compare este resultado con el siguiente ejemplo.  
  
 [!code-vb[VbVbalrOperators#66](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#66)]  
  
 En el ejemplo anterior, `x Is y` se evalúa como `False`, porque aunque las variables hacen referencia a objetos del mismo tipo, hacen referencia a distintas instancias de ese tipo.  
  
 Cuando desea probar dos objetos no está señalando a la misma instancia, el `IsNot` operador le permite evitar una combinación gramaticalmente torpe de `Not` y `Is`. Esto se ilustra en el siguiente ejemplo:  
  
 [!code-vb[VbVbalrOperators#67](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#67)]  
  
 En el ejemplo anterior, `If a IsNot b` es equivalente a `If Not a Is b`.  
  
### <a name="comparing-object-type"></a>Comparación de tipo de objeto  
 Puede probar si un objeto es de un tipo determinado con el `TypeOf`... `Is` expresión. La sintaxis es la siguiente:  
  
 `TypeOf <objectexpression> Is <typename>`  
  
 Cuando `typename` especifica un tipo de interfaz, el `TypeOf`... `Is` expresión devuelve `True` si el objeto implementa el tipo de interfaz. Cuando `typename` es un tipo de clase, la expresión devuelve `True` si el objeto es una instancia de la clase especificada o de una clase que derive de la clase especificada. Esto se ilustra en el siguiente ejemplo:  
  
 [!code-vb[VbVbalrOperators#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#68)]  
  
 En el ejemplo anterior, el `TypeOf x Is Control` expresión se evalúa como `True` porque el tipo de `x` es `Button`, que hereda de `Control`.  
  
 Para obtener más información, consulte [operador TypeOf](../../../../visual-basic/language-reference/operators/typeof-operator.md).  
  
## <a name="see-also"></a>Vea también

- [Comparaciones de valores](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)
- [Operadores de comparación](../../../../visual-basic/language-reference/operators/comparison-operators.md)
- [Operadores](../../../../visual-basic/language-reference/operators/index.md)
- [Operadores aritméticos en Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [Operadores de concatenación en Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
- [Operadores lógicos y bit a bit en Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
