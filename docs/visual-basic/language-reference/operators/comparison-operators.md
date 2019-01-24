---
title: Operadores de comparación (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: bf7ff1870a523903babd7140e0d8271f9946064b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54628063"
---
# <a name="comparison-operators-visual-basic"></a>Operadores de comparación (Visual Basic)
Estos son los operadores de comparación definidos en Visual Basic.  
  
 `<` Operador  
  
 `<=` Operador  
  
 `>` Operador  
  
 `>=` Operador  
  
 `=` Operador  
  
 `<>` Operador  
  
 [Is (operador)](../../../visual-basic/language-reference/operators/is-operator.md)  
  
 [IsNot (operador)](../../../visual-basic/language-reference/operators/isnot-operator.md)  
  
 [Like (operador)](../../../visual-basic/language-reference/operators/like-operator.md)  
  
 Estos operadores comparan dos expresiones para determinar si son iguales y, si no, cómo se diferencian. `Is`, `IsNot`, y `Like` se tratan detalladamente en las páginas de Ayuda independientes. Los operadores de comparación relacional se tratan detalladamente en esta página.  
  
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
 Obligatorio. Los nombres de objeto de referencia.  
  
 `string`  
 Obligatorio. Cualquier expresión `String` .  
  
 `pattern`  
 Obligatorio. Cualquier `String` expresión o un intervalo de caracteres.  
  
## <a name="remarks"></a>Comentarios  
 En la tabla siguiente contiene una lista de los operadores de comparación relacional y las condiciones que determinan si `result` es `True` o `False`.  
  
|Operador|`True` si|`False` si|  
|--------------|---------------|----------------|  
|`<` (Menor que)|`expression1` < `expression2`|`expression1` >= `expression2`|  
|`<=` (Menor o igual que)|`expression1` <= `expression2`|`expression1` > `expression2`|  
|`>` (Mayor que)|`expression1` > `expression2`|`expression1` <= `expression2`|  
|`>=` (Mayor o igual que)|`expression1` >= `expression2`|`expression1` < `expression2`|  
|`=` (Igual a)|`expression1` = `expression2`|`expression1` <> `expression2`|  
|`<>` (No es igual a)|`expression1` <> `expression2`|`expression1` = `expression2`|  
  
> [!NOTE]
>  El [= (operador)](../../../visual-basic/language-reference/operators/assignment-operator.md) también se utiliza como un operador de asignación.  
  
 El `Is` operador, el `IsNot` operador y el `Like` operador tiene funcionalidades de comparación específica que difieren de los operadores en la tabla anterior.  
  
## <a name="comparing-numbers"></a>Comparación de números  
 Cuando se compara una expresión de tipo `Single` a uno de tipo `Double`, `Single` expresión se convierte en `Double`. Este comportamiento es opuesto del comportamiento encontrado en Visual Basic 6.  
  
 De forma similar, cuando se compara una expresión de tipo `Decimal` en una expresión de tipo `Single` o `Double`, `Decimal` expresión se convierte en `Single` o `Double`. Para `Decimal` expresiones, cualquier valor fraccionario menor que 1E-28 podría perderse. Dicha pérdida de valor fraccionario puede hacen que se consideran iguales cuando no estén dos valores. Por este motivo, debe tener cuidado al usar la igualdad (`=`) para comparar dos variables de punto flotante. Es más seguro comprobar si el valor absoluto de la diferencia entre los dos números es menor que el mínimo aceptable.  
  
### <a name="floating-point-imprecision"></a>Punto flotante imprecisión  
 Cuando se trabaja con números de punto flotante, tenga en cuenta que no siempre tienen una representación precisa en memoria. Esto podría provocar resultados inesperados en ciertas operaciones, como la comparación de valor y el [Mod (operador)](../../../visual-basic/language-reference/operators/mod-operator.md). Para obtener más información, consulte [solución de problemas de los tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).  
  
## <a name="comparing-strings"></a>Comparar cadenas  
 Cuando se comparan cadenas, las expresiones de cadena se evalúan según su criterio de ordenación alfabética, que depende el `Option Compare` configuración.  
  
 `Option Compare Binary` comparaciones en un criterio de ordenación que se deriva de las representaciones binarias internas de los caracteres de cadenas de bases de datos. El criterio de ordenación viene determinada por la página de códigos. El ejemplo siguiente muestra un criterio de ordenación binario típico.  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 `Option Compare Text` bases de datos de cadena comparaciones en un criterio de ordenación textual entre mayúsculas y minúsculas determinado por la configuración regional de la aplicación. Al establecer `Option Compare Text` y ordenar los caracteres en el ejemplo anterior, se aplica el criterio de ordenación de texto siguiente:  
  
 `(A=a) < (À= à) < (B=b) < (E=e) < (Ê= ê) < (Ø = ø) < (Z=z)`  
  
### <a name="locale-dependence"></a>Dependencia de la configuración regional  
 Al establecer `Option Compare Text`, el resultado de una comparación de cadenas puede depender de la configuración regional en que se ejecuta la aplicación. Pueden comparar dos caracteres como iguales en una configuración regional, pero no en otro. Si está utilizando una comparación de cadenas para tomar decisiones importantes, por ejemplo, si desea aceptar un intento de inicio de sesión, debe aparecer la alerta para la sensibilidad de la configuración regional. Considere la posibilidad de cualquier `Option Compare Binary` o que realiza la llamada la <xref:Microsoft.VisualBasic.Strings.StrComp%2A>, que tiene la configuración regional en la cuenta.  
  
## <a name="typeless-programming-with-relational-comparison-operators"></a>Programación sin tipos con operadores de comparación relacional  
 El uso de operadores de comparación relacional con `Object` expresiones no se permite en `Option Strict On`. Cuando `Option Strict` es `Off`y `expression1` o `expression2` es un `Object` expresión, los tipos de tiempo de ejecución determinan cómo se comparan. En la tabla siguiente se muestra cómo se comparan las expresiones y el resultado de la comparación, dependiendo del tipo en tiempo de ejecución de los operandos.  
  
|Si los operandos son|La comparación es|  
|---------------------|-------------------|  
|Ambos `String`|Ordenar en función de las características de ordenación de cadenas de comparación.|  
|Ambas numéricas|Convierten objetos en `Double`, comparación numérica.|  
|Uno numérico y otro `String`|El `String` se convierte en un `Double` y se realiza una comparación numérica. Si el `String` no se puede convertir a `Double`, un <xref:System.InvalidCastException> se produce.|  
|Uno o ambos son tipos de referencia distinto `String`|Se inicia una <xref:System.InvalidCastException>.|  
  
 Tratan las comparaciones numéricas `Nothing` como 0. Tratan las comparaciones de cadenas `Nothing` como `""` (una cadena vacía).  
  
## <a name="overloading"></a>Sobrecarga  
 Los operadores de comparación relacional (`<`. `<=``>`, `>=`, `=`, `<>`) puede ser *sobrecargado*, lo que significa que una clase o estructura puede redefinir su comportamiento cuando un operando tiene el tipo de esa clase o estructura. Si el código usa cualquiera de estos operadores en una clase o estructura de este tipo, asegúrese de que comprender el comportamiento redefinido. Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
 Tenga en cuenta que el [= (operador)](../../../visual-basic/language-reference/operators/assignment-operator.md) se puede sobrecargar únicamente como un operador de comparación relacional, no como un operador de asignación.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra varios usos de los operadores de comparación relacional, que se utilizan para comparar expresiones. Operadores de comparación relacional devuelven un `Boolean` resultado que representa si se evalúa como la expresión indicada `True`. Al aplicar el `>` y `<` operadores en cadenas, la comparación se realiza mediante el criterio de ordenación alfabético normal de las cadenas. Este orden puede depender de la configuración regional. Si el criterio de ordenación distingue mayúsculas de minúsculas o no depende de la [Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md) configuración.  
  
 [!code-vb[VbVbalrOperators#1](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_1.vb)]  
  
 En el ejemplo anterior, se devuelve la primera comparación `False` y las comparaciones restantes devuelven `True`.  
  
## <a name="see-also"></a>Vea también
- <xref:System.InvalidCastException>
- [Operador =](../../../visual-basic/language-reference/operators/assignment-operator.md)
- [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Solución de problemas de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Operadores de comparación en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
