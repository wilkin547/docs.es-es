---
title: Tipos de valores que aceptan valores NULL
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
ms.openlocfilehash: beed8262c50dc68330b8f03aa3d864ed2f8df0d5
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249687"
---
# <a name="nullable-value-types-visual-basic"></a>Tipos que admiten valores null (Visual Basic)

A veces se trabaja con un tipo de valor que no tiene un valor definido en determinadas circunstancias. Por ejemplo, un campo de una base de datos podría tener que distinguir entre tener un valor asignado que sea significativo y no tener un valor asignado. Los tipos de valor se pueden extender para tomar sus valores normales o un valor nulo. Dicha extensión se denomina tipo que *acepta valores NULL*.

Cada tipo de valor que acepta <xref:System.Nullable%601> valores NULL se construye a partir de la estructura genérica. Considere una base de datos que realiza un seguimiento de las actividades relacionadas con el trabajo. En el ejemplo siguiente `Boolean` se construye un tipo que acepta valores NULL y se declara una variable de ese tipo. Puede escribir la declaración de tres maneras:

[!code-vb[VbVbalrNullableValue#1](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#1)]

La `ridesBusToWork` variable puede contener `True`un valor `False`de , un valor de , o ningún valor en absoluto. Su valor predeterminado inicial no es ningún valor en absoluto, lo que en este caso podría significar que la información aún no se ha obtenido para esta persona. Por el `False` contrario, podría significar que la información se ha obtenido y la persona no viaja en el autobús al trabajo.

Puede declarar variables y propiedades con tipos de valor que aceptan valores NULL y puede declarar una matriz con elementos de un tipo de valor que acepta valores NULL. Puede declarar procedimientos con tipos de valor que aceptan valores NULL `Function` como parámetros y puede devolver un tipo de valor que acepta valores NULL de un procedimiento.

No se puede construir un tipo que acepta valores `String`NULL en un tipo de referencia como una matriz, una o una clase. El tipo subyacente debe ser un tipo de valor. Para obtener más información, vea [Tipos de valor y tipos](value-types-and-reference-types.md)de referencia .

## <a name="using-a-nullable-type-variable"></a>Uso de una variable de tipo que acepta valores NULL

Los miembros más importantes de un <xref:System.Nullable%601.HasValue%2A> <xref:System.Nullable%601.Value%2A> tipo de valor que acepta valores NULL son sus propiedades. Para una variable de un <xref:System.Nullable%601.HasValue%2A> tipo de valor que acepta valores NULL, le indica si la variable contiene un valor definido. Si <xref:System.Nullable%601.HasValue%2A> `True`es , puede leer <xref:System.Nullable%601.Value%2A>el valor de . Tenga en <xref:System.Nullable%601.HasValue%2A> <xref:System.Nullable%601.Value%2A> cuenta `ReadOnly` que ambas y son propiedades.

### <a name="default-values"></a>Valores predeterminados

Cuando se declara una variable con un <xref:System.Nullable%601.HasValue%2A> tipo de valor `False`que acepta valores NULL, su propiedad tiene un valor predeterminado de . Esto significa que, de forma predeterminada, la variable no tiene ningún valor definido, en lugar del valor predeterminado de su tipo de valor subyacente. En el ejemplo siguiente, la variable `numberOfChildren` inicialmente no tiene ningún `Integer` valor definido, aunque el valor predeterminado del tipo es 0.

[!code-vb[VbVbalrNullableValue#2](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#2)]

Un valor nulo es útil para indicar un valor indefinido o desconocido. Si `numberOfChildren` se hubiera `Integer`declarado como , no habría ningún valor que pudiera indicar que la información no está disponible actualmente.

### <a name="storing-values"></a>Almacenar valores

Almacenar un valor en una variable o propiedad de un tipo de valor que acepta valores NULL de la manera típica. En el ejemplo siguiente se `numberOfChildren` asigna un valor a la variable declarada en el ejemplo anterior.

[!code-vb[VbVbalrNullableValue#3](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#3)]

Si una variable o propiedad de un tipo de valor que acepta valores NULL contiene un valor definido, puede hacer que vuelva a su estado inicial de no tener un valor asignado. Para ello, establezca la variable `Nothing`o propiedad en , como se muestra en el ejemplo siguiente.

[!code-vb[VbVbalrNullableValue#4](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#4)]

> [!NOTE]
> Aunque puede `Nothing` asignar a una variable de un tipo de `Nothing` valor que acepta valores NULL, no puede probarlo mediante el signo igual. La comparación que `someVar = Nothing`utiliza el signo `Nothing`igual, , siempre se evalúa como . Puede probar la propiedad <xref:System.Nullable%601.HasValue%2A> de `False`la variable para `Is` `IsNot` , o probar mediante el operador or.

### <a name="retrieving-values"></a>Recuperación de valores

Para recuperar el valor de una variable de un tipo <xref:System.Nullable%601.HasValue%2A> de valor que acepta valores NULL, primero debe probar su propiedad para confirmar que tiene un valor. Si intenta leer el <xref:System.Nullable%601.HasValue%2A> valor `False`cuando es , <xref:System.InvalidOperationException> Visual Basic produce una excepción. En el ejemplo siguiente se muestra `numberOfChildren` la forma recomendada de leer la variable de los ejemplos anteriores.

[!code-vb[VbVbalrNullableValue#5](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#5)]

## <a name="comparing-nullable-types"></a>Comparación de tipos que aceptan valores NULL

Cuando se `Boolean` utilizan variables que aceptan valores `True`NULL `False`en `Nothing`expresiones booleanas, el resultado puede ser , , o . La siguiente es la `And` `Or`tabla de la verdad para y . Dado `b1` `b2` que y ahora tienen tres valores posibles, hay nueve combinaciones para evaluar.

|b1|B2|b1 Y b2|b1 O b2|
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

Cuando el valor de una `Nothing`variable o `true` expresión `false`booleana es , no es ni . Considere el ejemplo siguiente.

[!code-vb[VbVbalrNullableValue#6](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#6)]

En este `b1 And b2` ejemplo, `Nothing`se evalúa como . Como resultado, `Else` la cláusula se `If` ejecuta en cada instrucción y la salida es la siguiente:

`Expression is not true`

`Expression is not false`

> [!NOTE]
> `AndAlso`y `OrElse`, que utilizan la evaluación de cortocircuito, deben evaluar `Nothing`sus segundos operandos cuando el primero se evalúa como .

## <a name="propagation"></a>Propagación

Si uno o ambos de los operandos de una operación aritmética, de comparación, de desplazamiento o de tipo es un tipo de valor que acepta valores NULL, el resultado de la operación también es un tipo de valor que acepta valores NULL. Si ambos operandos tienen `Nothing`valores que no lo son, la operación se realiza en los valores subyacentes de los operandos, como si ninguno de los dos fuera un tipo de valor que acepta valores NULL. En el ejemplo siguiente, las variables `compare1` y `sum1` se escriben implícitamente. Si descansa el puntero del mouse sobre ellos, verá que el compilador deduce tipos de valor que aceptan valores NULL para ambos.

[!code-vb[VbVbalrNullableValue#7](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#7)]

Si uno o ambos operandos `Nothing`tienen un `Nothing`valor de , el resultado será .

[!code-vb[VbVbalrNullableValue#8](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#8)]

## <a name="using-nullable-types-with-data"></a>Uso de tipos que aceptan valores NULL con datos

Una base de datos es uno de los lugares más importantes para usar tipos de valor que aceptan valores NULL. No todos los objetos de base de datos admiten actualmente tipos de valor que aceptan valores NULL, pero sí los adaptadores de tabla generados por el diseñador. Consulte [Compatibilidad con TableAdapter para tipos que aceptan valores NULL](/visualstudio/data-tools/fill-datasets-by-using-tableadapters#tableadapter-support-for-nullable-types).

## <a name="see-also"></a>Vea también

- <xref:System.InvalidOperationException>
- <xref:System.Nullable%601.HasValue%2A>
- [Tipos de datos](index.md)
- [Tipos de valor y tipos de referencia](value-types-and-reference-types.md)
- [Solución de problemas de los tipos de datos](troubleshooting-data-types.md)
- [Rellenar conjuntos de datos mediante TableAdapters](/visualstudio/data-tools/fill-datasets-by-using-tableadapters)
- [Operador If](../../../language-reference/operators/if-operator.md)
- [Inferencia de tipo de variable local](../variables/local-type-inference.md)
- [Operador Is](../../../language-reference/operators/is-operator.md)
- [Operador IsNot](../../../language-reference/operators/isnot-operator.md)
- [Tipos de valor que aceptan valores NULL (C-)](../../../../csharp/language-reference/builtin-types/nullable-value-types.md)
