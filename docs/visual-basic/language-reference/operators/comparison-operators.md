---
title: Operadores de comparación
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
- comparison operators [Visual Basic], Visual Basic
ms.assetid: d6cb12a8-e52e-46a7-8aaf-f804d634a825
ms.openlocfilehash: fcbb9052a79fa4b20b5a0f8fdc15de73d55a4281
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873449"
---
# <a name="comparison-operators-visual-basic"></a>Operadores de comparación (Visual Basic)

A continuación se muestran los operadores de comparación definidos en Visual Basic.

 `<` Operator

 `<=` Operator

 `>` Operator

 `>=` Operator

 `=` Operator

 `<>` Operator

 [Operador Is](is-operator.md)

 [Operador IsNot](isnot-operator.md)

 [Like (Operador)](like-operator.md)

 Estos operadores comparan dos expresiones para determinar si son iguales o no, y si no, cómo se diferencian. `Is`, `IsNot` y `Like` se describen en detalle en páginas de ayuda independientes. Los operadores de comparación relacional se describen en detalle en esta página.

## <a name="syntax"></a>Sintaxis
  
```vb
result = expression1 comparisonoperator expression2  
result = object1 [Is | IsNot] object2  
result = string Like pattern  
```  
  
## <a name="parts"></a>Partes

 `result`  
 Obligatorio. `Boolean`Valor que representa el resultado de la comparación.

 `expression1`, `expression2`  
 Obligatorio. Cualquier expresión.

 `comparisonoperator`  
 Obligatorio. Cualquier operador de comparación relacional.

 `object1`, `object2`  
 Obligatorio. Cualquier nombre de objeto de referencia.

 `string`  
 Obligatorio. Cualquier expresión `String` .

 `pattern`  
 Obligatorio. Cualquier `String` expresión o intervalo de caracteres.

## <a name="remarks"></a>Comentarios

 La tabla siguiente contiene una lista de los operadores de comparación relacionales y las condiciones que determinan si `result` es `True` o `False` .

|Operator|`True` si|`False` si|
|--------------|---------------|----------------|
|`<` (Menor que)|`expression1` < `expression2`|`expression1` >= `expression2`|
|`<=` (Menor o igual que)|`expression1` <= `expression2`|`expression1` > `expression2`|
|`>` (Mayor que)|`expression1` > `expression2`|`expression1` <= `expression2`|
|`>=` (Mayor o igual que)|`expression1` >= `expression2`|`expression1` < `expression2`|
|`=` (Igual a)|`expression1` = `expression2`|`expression1` <> `expression2`|
|`<>` (No es igual a)|`expression1` <> `expression2`|`expression1` = `expression2`|

> [!NOTE]
> El [operador =](assignment-operator.md) también se usa como operador de asignación.

 El `Is` operador, el `IsNot` operador y el `Like` operador tienen funcionalidades de comparación específicas que difieren de los operadores de la tabla anterior.

## <a name="comparing-numbers"></a>Comparar números

 Al comparar una expresión de tipo `Single` con una de tipo `Double` , la `Single` expresión se convierte en `Double` . Este comportamiento es opuesto al comportamiento que se encuentra en Visual Basic 6.

 Del mismo modo, al comparar una expresión de tipo `Decimal` con una expresión de tipo `Single` o `Double` , la `Decimal` expresión se convierte en `Single` o `Double` . En el caso de `Decimal` las expresiones, se puede perder cualquier valor fraccionario inferior a 1E-28. Esta pérdida de valor fraccionario puede hacer que dos valores se comparen como iguales cuando no lo son. Por este motivo, debe tener cuidado al usar la igualdad ( `=` ) para comparar dos variables de punto flotante. Es más seguro probar si el valor absoluto de la diferencia entre los dos números es menor que una pequeña tolerancia aceptable.

### <a name="floating-point-imprecision"></a>Imprecisión de punto flotante

 Al trabajar con números de punto flotante, tenga en cuenta que no siempre tienen una representación precisa en la memoria. Esto podría dar lugar a resultados inesperados de ciertas operaciones, como la comparación de valores y el [operador mod](mod-operator.md). Para obtener más información, vea [solución de problemas de tipos de datos](../../programming-guide/language-features/data-types/troubleshooting-data-types.md).

## <a name="comparing-strings"></a>Comparar cadenas

 Cuando se comparan cadenas, las expresiones de cadena se evalúan en función de su criterio de ordenación alfabético, que depende de la `Option Compare` configuración.

 `Option Compare Binary` basa las comparaciones de cadenas en un criterio de ordenación derivado de las representaciones binarias internas de los caracteres. La página de códigos determina el criterio de ordenación. En el ejemplo siguiente se muestra un criterio de ordenación binario típico.

 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`

 `Option Compare Text` basa las comparaciones de cadenas en un criterio de ordenación textual que no distingue entre mayúsculas y minúsculas, determinado por la configuración regional de la aplicación. Al establecer `Option Compare Text` y ordenar los caracteres en el ejemplo anterior, se aplica el siguiente criterio de ordenación de texto:

 `(A=a) < (À= à) < (B=b) < (E=e) < (Ê= ê) < (Ø = ø) < (Z=z)`

### <a name="locale-dependence"></a>Dependencia de la configuración regional

 Al establecer `Option Compare Text` , el resultado de una comparación de cadenas puede depender de la configuración regional en la que se ejecuta la aplicación. Dos caracteres podrían compararse como iguales en una configuración regional, pero no en otra. Si utiliza una comparación de cadenas para tomar decisiones importantes, por ejemplo, si desea aceptar un intento de inicio de sesión, debe alertar a la confidencialidad de la configuración regional. Considere la posibilidad de establecer `Option Compare Binary` o llamar a <xref:Microsoft.VisualBasic.Strings.StrComp%2A> , que tiene en cuenta la configuración regional.

## <a name="typeless-programming-with-relational-comparison-operators"></a>Programación sin tipos con operadores de comparación relacionales

 No se permite el uso de operadores de comparación relacionales con `Object` expresiones en `Option Strict On` . Cuando `Option Strict` es `Off` , y `expression1` o `expression2` es una `Object` expresión, los tipos en tiempo de ejecución determinan cómo se comparan. En la tabla siguiente se muestra cómo se comparan las expresiones y el resultado de la comparación, dependiendo del tipo en tiempo de ejecución de los operandos.

|Si los operandos son|La comparación es|
|---------------------|-------------------|
|Ambos `String`|Ordenar la comparación en función de las características de ordenación de cadenas.|
|Ambos numéricos|Objetos convertidos en `Double` , comparación numérica.|
|Un valor numérico y uno `String`|`String`Se convierte en `Double` y se realiza una comparación numérica. Si `String` no se puede convertir en `Double` , <xref:System.InvalidCastException> se produce una excepción.|
|Uno o ambos son tipos de referencia distintos de `String`|Se inicia una <xref:System.InvalidCastException>.|

 Las comparaciones numéricas se tratan `Nothing` como 0. Las comparaciones `Nothing` de cadenas tratan como `""` (una cadena vacía).

## <a name="overloading"></a>Sobrecarga

 Operadores de comparación relacionales ( `<` . `<=`, `>` , `>=` , `=` , `<>` ) se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura. Si el código usa cualquiera de estos operadores en una clase o estructura de este tipo, asegúrese de que comprende el comportamiento redefinido. Para obtener más información, consulta [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).

 Observe que el [operador =](assignment-operator.md) solo se puede sobrecargar como operador de comparación relacional, no como operador de asignación.

## <a name="example"></a>Ejemplo

 En el ejemplo siguiente se muestran varios usos de operadores de comparación relacionales, que se usan para comparar expresiones. Los operadores de comparación relacional devuelven un `Boolean` resultado que indica si la expresión indicada se evalúa como `True` . Cuando se aplican `>` los `<` operadores y a las cadenas, la comparación se realiza utilizando el criterio de ordenación alfabético normal de las cadenas. Este orden puede depender de la configuración regional. La ordenación distingue entre mayúsculas y minúsculas o no depende del valor [Option Compare](../statements/option-compare-statement.md) .

 [!code-vb[VbVbalrOperators#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#1)]

 En el ejemplo anterior, la primera comparación devuelve `False` y las comparaciones restantes devuelven `True` .

## <a name="see-also"></a>Consulte también

- <xref:System.InvalidCastException>
- [= (Operador)](assignment-operator.md)
- [Prioridad de operador en Visual Basic](operator-precedence.md)
- [Lista de operadores según funcionalidad](operators-listed-by-functionality.md)
- [Solución de problemas de los tipos de datos](../../programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Comparison Operators in Visual Basic](../../programming-guide/language-features/operators-and-expressions/comparison-operators.md)
