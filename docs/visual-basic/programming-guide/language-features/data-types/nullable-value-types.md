---
title: Tipos que admiten valores null (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Nullable
helpviewer_keywords:
- nullable types [Visual Basic]
- '? [Visual Basic]'
- types [Visual Basic], nullable
- nullable types [Visual Basic]
- data types [Visual Basic], nullable
ms.assetid: 9ac3b602-6f96-4e6d-96f7-cd4e81c468a6
ms.openlocfilehash: 437107bb522e1635dffa4a2de88c5d10d6707592
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58825149"
---
# <a name="nullable-value-types-visual-basic"></a>Tipos que admiten valores null (Visual Basic)
A veces se trabaja con un tipo de valor que no tiene un valor definido en determinadas circunstancias. Por ejemplo, podría tener un campo en una base de datos distinguir entre tener un valor asignado que es significativo y no tener un valor asignado. Tipos de valor pueden ampliarse para aprovechar sus valores normales o un valor null. Se llama a este tipo de extensión un *tipo que acepta valores NULL*.  
  
 Cada tipo que acepta valores NULL se construye a partir del genérico <xref:System.Nullable%601> estructura. Considere la posibilidad de una base de datos que realiza el seguimiento de las actividades relacionadas con el trabajo. En el ejemplo siguiente se crea un que acepta valores NULL `Boolean` escriba y declara una variable de ese tipo. Puede escribir la declaración de tres maneras:  
  
 [!code-vb[VbVbalrNullableValue#1](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#1)]  
  
 La variable `ridesBusToWork` puede contener un valor de `True`, un valor de `False`, o ningún valor en absoluto. Su valor predeterminado inicial no es ningún valor en absoluto, lo que en este caso podría significar que la información no se ha obtenido para esa persona. En cambio, `False` puede significar que se ha obtenido la información y la persona que no utiliza el autobús funcione.  
  
 Puede declarar variables y propiedades con tipos que aceptan valores NULL y puede declarar una matriz con elementos de un tipo que acepta valores NULL. Puede declarar procedimientos con tipos que aceptan valores NULL como parámetros y devolver un tipo que acepta valores NULL de un `Function` procedimiento.  
  
 No se puede construir un tipo que acepta valores NULL en un tipo de referencia como una matriz, un `String`, o una clase. El tipo subyacente debe ser un tipo de valor. Para obtener más información, consulta [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).  
  
## <a name="using-a-nullable-type-variable"></a>Uso de una Variable de tipo que acepta valores null  
 Los miembros más importantes de un tipo que acepta valores NULL son su <xref:System.Nullable%601.HasValue%2A> y <xref:System.Nullable%601.Value%2A> propiedades. Para una variable de un tipo que acepta valores NULL, <xref:System.Nullable%601.HasValue%2A> indica si la variable contiene un valor definido. Si <xref:System.Nullable%601.HasValue%2A> es `True`, puede leer el valor de <xref:System.Nullable%601.Value%2A>. Tenga en cuenta que ambos <xref:System.Nullable%601.HasValue%2A> y <xref:System.Nullable%601.Value%2A> son `ReadOnly` propiedades.  
  
### <a name="default-values"></a>Valores predeterminados  
 Cuando se declara una variable con un tipo que acepta valores NULL, su <xref:System.Nullable%601.HasValue%2A> propiedad tiene un valor predeterminado de `False`. Esto significa que, de forma predeterminada, la variable no tiene ningún valor definido, en lugar del valor predeterminado de su tipo de valor subyacente. En el ejemplo siguiente, la variable `numberOfChildren` inicialmente no tiene ningún valor definido, aunque el valor predeterminado de la `Integer` tipo es 0.  
  
 [!code-vb[VbVbalrNullableValue#2](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#2)]  
  
 Un valor null es útil para indicar un valor indefinido o desconocido. Si `numberOfChildren` se ha declarado como `Integer`, no habría ningún valor que podría indicar que la información no está disponible actualmente.  
  
### <a name="storing-values"></a>Almacenamiento de valores  
 Almacenar un valor en una variable o propiedad de un tipo que acepta valores NULL de la manera habitual. En el ejemplo siguiente se asigna un valor a la variable `numberOfChildren` declarado en el ejemplo anterior.  
  
 [!code-vb[VbVbalrNullableValue#3](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#3)]  
  
 Si una variable o propiedad de un tipo que acepta valores NULL contiene un valor definido, puede provocar que vuelva a su estado inicial de no tener un valor asignado. Para ello, Establece la variable o propiedad a `Nothing`, como se muestra en el ejemplo siguiente.  
  
 [!code-vb[VbVbalrNullableValue#4](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#4)]  
  
> [!NOTE]
>  Aunque puede asignar `Nothing` a una variable de un tipo que acepta valores NULL, no se puede probar para `Nothing` mediante el uso del signo igual. Comparación que utiliza el signo igual, `someVar = Nothing`, siempre se evalúa como `Nothing`. Puede probar la variable <xref:System.Nullable%601.HasValue%2A> propiedad `False`, o probar mediante el `Is` o `IsNot` operador.  
  
### <a name="retrieving-values"></a>Recuperación de valores  
 Para recuperar el valor de una variable de un tipo que acepta valores NULL, debe probar su <xref:System.Nullable%601.HasValue%2A> propiedad para confirmar que tiene un valor. Si se intenta leer el valor cuando <xref:System.Nullable%601.HasValue%2A> es `False`, Visual Basic produce una <xref:System.InvalidOperationException> excepción. El ejemplo siguiente muestra la manera recomendada para leer la variable `numberOfChildren` de los ejemplos anteriores.  
  
 [!code-vb[VbVbalrNullableValue#5](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#5)]  
  
## <a name="comparing-nullable-types"></a>Comparación de tipos que aceptan valores null  
 Cuando acepta valores NULL `Boolean` variables se usan en expresiones booleanas, el resultado puede ser `True`, `False`, o `Nothing`. El siguiente es la tabla de verdad para `And` y `Or`. Dado que `b1` y `b2` ahora tiene tres valores posibles, hay nueve combinaciones para evaluar.  
  
|b1|b2|B1 y b2|B1 o b2|  
|--------|--------|---------------|--------------|  
|`Nothing`|`Nothing`|`Nothing`|`Nothing`|  
|`Nothing`|`True`|`Nothing`|`True`|  
|`Nothing`|`False`|`False`|`Nothing`|  
|`True`|`Nothing`|`Nothing`|`True`|  
|`True`|`True`|`True`|`True`|  
|`True`|`False`|`False`|`True`|  
|`False`|`Nothing`|`False`|`Nothing`|  
|`False`|`True`|`False`|`True`|  
|`False`|`False`|`False`|`False`|  
  
 Cuando el valor de una variable o expresión booleana es `Nothing`, ninguna de ellas es `true` ni `false`. Considere el ejemplo siguiente.  
  
 [!code-vb[VbVbalrNullableValue#6](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#6)]  
  
 En este ejemplo, `b1 And b2` se evalúa como `Nothing`. Como resultado, el `Else` cláusula se ejecuta en cada `If` instrucción y el resultado es como sigue:  
  
 `Expression is not true`  
  
 `Expression is not false`  
  
> [!NOTE]
>  `AndAlso` y `OrElse`, que usan cortocircuitar la evaluación, debe evaluar los operandos segundo cuando se evalúa como el primer `Nothing`.  
  
## <a name="propagation"></a>Propagación  
 Si uno o ambos operandos de una aritmética, comparación, MAYÚS o de operación de tipo acepta valores NULL, el resultado de la operación también es que acepta valores NULL. Si ambos operandos tienen valores que no son `Nothing`, la operación se realiza en los valores subyacentes de los operandos, como si no fuera un tipo que acepta valores NULL. En el ejemplo siguiente, las variables `compare1` y `sum1` tipos se declaran implícitamente. Si sitúa el puntero del mouse sobre ellos, verá que el compilador infiere los tipos que aceptan valores NULL para ambas.  
  
 [!code-vb[VbVbalrNullableValue#7](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#7)]  
  
 Si uno o ambos operandos tienen un valor de `Nothing`, el resultado será `Nothing`.  
  
 [!code-vb[VbVbalrNullableValue#8](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#8)]  
  
## <a name="using-nullable-types-with-data"></a>Utilizar tipos que aceptan valores NULL con datos  
 Una base de datos es uno de los lugares más importantes para utilizar tipos que aceptan valores NULL. Actualmente, no todos los objetos de base de datos admiten tipos que aceptan valores NULL, pero hace de los adaptadores de tabla generado por el diseñador. Consulte "Compatibilidad de TableAdapter para tipos que aceptan valores null" en [información general sobre TableAdapter](/visualstudio/data-tools/tableadapter-overview).
  
## <a name="see-also"></a>Vea también

- <xref:System.InvalidOperationException>
- <xref:System.Nullable%601.HasValue%2A>
- [Utilizar tipos que aceptan valores NULL](../../../../csharp/programming-guide/nullable-types/using-nullable-types.md)
- [Tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [Solución de problemas de tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Introducción a TableAdapter](/visualstudio/data-tools/tableadapter-overview)
- [If (operador)](../../../../visual-basic/language-reference/operators/if-operator.md)
- [Inferencia de tipo de variable local](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Is (operador)](../../../../visual-basic/language-reference/operators/is-operator.md)
- [IsNot (operador)](../../../../visual-basic/language-reference/operators/isnot-operator.md)
