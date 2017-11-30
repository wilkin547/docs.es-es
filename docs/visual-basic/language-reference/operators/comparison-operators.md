---
title: "Operadores de comparación (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.<>
- vb.>=
- vb.<=
- vb.>
- vb.<
helpviewer_keywords:
- greater than or equal to operator [Visual Basic]
- '>= operator [Visual Basic]'
- = operator [Visual Basic]
- < operator [Visual Basic]
- less than operator [Visual Basic]
- relational operators [Visual Basic], syntax
- Like operator [Visual Basic]
- <> operator [Visual Basic]
- '> operator [Visual Basic]'
- equal operator [Visual Basic]
- less than or equal to operator [Visual Basic]
- symbols, operators
- greater than operator [Visual Basic]
- comparing values [Visual Basic]
- operators [Visual Basic], relational
- string comparison [Visual Basic]
- not equal to comparison operator [Visual Basic]
- <= operator [Visual Basic]
- operators [Visual Basic], comparison
- Is operator [Visual Basic]
- comparison operators [Visual Basic], Visual Basicl
ms.assetid: d6cb12a8-e52e-46a7-8aaf-f804d634a825
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: aa450f7978f46196663c7534b31597b04d80482a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="comparison-operators-visual-basic"></a>Operadores de comparación (Visual Basic)
Éstos son los operadores de comparación definidos en Visual Basic.  
  
 `<`operador  
  
 `<=`operador  
  
 `>`operador  
  
 `>=`operador  
  
 `=`operador  
  
 `<>`operador  
  
 [Is (operador)](../../../visual-basic/language-reference/operators/is-operator.md)  
  
 [IsNot (operador)](../../../visual-basic/language-reference/operators/isnot-operator.md)  
  
 [Like (operador)](../../../visual-basic/language-reference/operators/like-operator.md)  
  
 Estos operadores comparan dos expresiones para determinar si no son iguales y, si no es así, cómo se diferencian. `Is`, `IsNot`, y `Like` se describen en detalle en las páginas de Ayuda independientes. Los operadores de comparación relacionales se explican detalladamente en esta página.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
      result = expression1 comparisonoperator expression2  
result = object1 [Is | IsNot] object2  
result = string Like pattern  
```  
  
## <a name="parts"></a>Elementos  
 `result`  
 Obligatorio. Un `Boolean` valor que representa el resultado de la comparación.  
  
 `expression`  
 Obligatorio. Cualquier expresión.  
  
 `comparisonoperator`  
 Obligatorio. Cualquier operador de comparación relacional.  
  
 `object1`, `object2`  
 Requerido. Los nombres de objeto de referencia.  
  
 `string`  
 Obligatorio. Cualquier expresión `String`.  
  
 `pattern`  
 Obligatorio. Cualquier `String` expresión o un intervalo de caracteres.  
  
## <a name="remarks"></a>Comentarios  
 En la tabla siguiente contiene una lista de los operadores de comparación relacionales y las condiciones que determinan si `result` es `True` o `False`.  
  
|Operador|`True`If|`False`If|  
|--------------|---------------|----------------|  
|`<`(Menor que)|`expression1` < `expression2`|`expression1` >= `expression2`|  
|`<=`(Menor o igual que)|`expression1` <= `expression2`|`expression1` > `expression2`|  
|`>`(Mayor que)|`expression1` > `expression2`|`expression1` <= `expression2`|  
|`>=`(Mayor o igual que)|`expression1` >= `expression2`|`expression1` < `expression2`|  
|`=`(Igual a)|`expression1` = `expression2`|`expression1` <> `expression2`|  
|`<>`(No es igual a)|`expression1` <> `expression2`|`expression1` = `expression2`|  
  
> [!NOTE]
>  El [= (operador)](../../../visual-basic/language-reference/operators/assignment-operator.md) también se utiliza como un operador de asignación.  
  
 El `Is` (operador), el `IsNot` (operador) y el `Like` operador tienen funcionalidades de comparación específicas que difieren de los operadores en la tabla anterior.  
  
## <a name="comparing-numbers"></a>Comparación de números  
 Cuando se compara una expresión de tipo `Single` en uno de tipo `Double`, `Single` expresión se convierte en `Double`. Este comportamiento es opuesto del comportamiento encontrado en Visual Basic 6.  
  
 De forma similar, cuando se compara una expresión de tipo `Decimal` en una expresión de tipo `Single` o `Double`, `Decimal` expresión se convierte a `Single` o `Double`. Para `Decimal` expresiones, cualquier valor fraccionario inferior a 1E-28 podría perderse. Dicha pérdida de valor fraccionario puede provocar dos valores que se consideran iguales cuando no lo están. Por este motivo, debe tener cuidado de cuando se usa la igualdad (`=`) para comparar dos variables de punto flotante. Es más seguro comprobar si el valor absoluto de la diferencia entre los dos números es menor que el mínimo aceptable.  
  
### <a name="floating-point-imprecision"></a>Punto flotante imprecisión  
 Cuando trabaje con números de punto flotante, tenga en cuenta que no siempre tienen una representación precisa en memoria. Esto podría provocar resultados inesperados en ciertas operaciones, como comparación de valores y la [Mod (operador)](../../../visual-basic/language-reference/operators/mod-operator.md). Para obtener más información, consulte [solución de problemas de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).  
  
## <a name="comparing-strings"></a>Comparar cadenas  
 Cuando se comparan cadenas, las expresiones de cadena se evalúan según su criterio de ordenación alfabética, que depende de la `Option Compare` configuración.  
  
 `Option Compare Binary`comparaciones en un criterio de ordenación que se deriva de las representaciones binarias internas de los caracteres de cadenas de bases de datos. El criterio de ordenación viene determinado por la página de código. En el ejemplo siguiente se muestra un criterio de ordenación binario típico.  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 `Option Compare Text`bases de datos de cadena comparaciones en un criterio de ordenación entre mayúsculas y minúsculas, textual determinado por la configuración regional de su aplicación. Al establecer `Option Compare Text` y ordenar los caracteres en el ejemplo anterior, se aplica el criterio de ordenación de texto siguiente:  
  
 `(A=a) < (À= à) < (B=b) < (E=e) < (Ê= ê) < (Ø = ø) < (Z=z)`  
  
### <a name="locale-dependence"></a>Dependen de la configuración regional  
 Al establecer `Option Compare Text`, el resultado de una comparación de cadenas puede depender de la configuración regional en que se ejecuta la aplicación. Dos caracteres podrían compararse como iguales en varias configuraciones regionales, pero no en otro. Si está usando una comparación de cadenas para tomar decisiones importantes, por ejemplo, si desea aceptar un intento de inicio de sesión, debe aparecer la alerta para la sensibilidad de la configuración regional. Tenga en cuenta cualquier configuración `Option Compare Binary` o que realiza la llamada la <xref:Microsoft.VisualBasic.Strings.StrComp%2A>, la configuración regional que tiene en cuenta.  
  
## <a name="typeless-programming-with-relational-comparison-operators"></a>Programación sin tipos con operadores de comparación relacionales  
 El uso de operadores de comparación relacionales con `Object` expresiones no se permite en `Option Strict On`. Cuando `Option Strict` es `Off`y `expression1` o `expression2` es un `Object` expresión, los tipos de tiempo de ejecución determinan cómo se comparan. En la tabla siguiente se muestra cómo se comparan las expresiones y el resultado de la comparación, dependiendo del tipo en tiempo de ejecución de los operandos.  
  
|Si los operandos son|La comparación es|  
|---------------------|-------------------|  
|Ambos`String`|Ordenar la comparación según las características de ordenación de las cadenas.|  
|Ambas numéricas|Los objetos se convierten a `Double`, comparación numérica.|  
|Uno numérico y otro`String`|El `String` se convierte en un `Double` y se realiza una comparación numérica. Si el `String` no se puede convertir a `Double`, un <xref:System.InvalidCastException> se produce.|  
|Uno o ambos son tipos de referencia distintos de`String`|Se inicia una <xref:System.InvalidCastException>.|  
  
 Las comparaciones numéricas tratan `Nothing` como 0. Las comparaciones de cadena tratan `Nothing` como `""` (una cadena vacía).  
  
## <a name="overloading"></a>Sobrecarga  
 Los operadores de comparación relacionales (`<`. `<=``>`, `>=`, `=`, `<>`) puede ser *sobrecargados*, lo que significa que una clase o estructura puede definir de nuevo su comportamiento cuando un operando tiene el tipo de esa clase o estructura. Si el código usa cualquiera de estos operadores en una clase o estructura de este tipo, asegúrese de que comprende el comportamiento redefinido. Para obtener más información, consulte [procedimientos de operadores](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
 Tenga en cuenta que la [= (operador)](../../../visual-basic/language-reference/operators/assignment-operator.md) se puede sobrecargar únicamente como un operador de comparación relacional, no como un operador de asignación.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra varios usos de los operadores de comparación relacionales, que se utilizan para comparar expresiones. Operadores de comparación relacionales devuelven un `Boolean` resultado que representa si o no se evalúa como la expresión indicada `True`. Al aplicar el `>` y `<` operadores para las cadenas, la comparación se realiza utilizando el orden alfabético normal de las cadenas. Este orden puede ser dependiente de la configuración regional. Si el criterio de ordenación distingue mayúsculas de minúsculas o no depende de la [Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md) configuración.  
  
 [!code-vb[VbVbalrOperators#1](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_1.vb)]  
  
 En el ejemplo anterior, se devuelve la primera comparación `False` y las comparaciones restantes devuelven `True`.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.InvalidCastException>  
 [Operador =](../../../visual-basic/language-reference/operators/assignment-operator.md)  
 [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Solución de problemas de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [Operadores de comparación en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
