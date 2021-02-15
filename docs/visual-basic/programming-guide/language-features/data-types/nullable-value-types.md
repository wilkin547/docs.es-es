---
description: 'Más información sobre: tipos de valor que aceptan valores NULL (Visual Basic)'
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
ms.openlocfilehash: acc91d98a3ed288a9bf0bcf6abbd3d8a516bd699
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100483890"
---
# <a name="nullable-value-types-visual-basic"></a>Tipos que admiten valores null (Visual Basic)

A veces se trabaja con un tipo de valor que no tiene un valor definido en determinadas circunstancias. Por ejemplo, un campo de una base de datos podría tener que distinguir entre tener un valor asignado que sea significativo y que no tenga un valor asignado. Los tipos de valor se pueden extender para tomar sus valores normales o un valor null. Dicha extensión se denomina un *tipo que acepta valores NULL*.

Cada tipo de valor que acepta valores NULL se construye a partir de la <xref:System.Nullable%601> estructura genérica. Considere una base de datos que realice un seguimiento de las actividades relacionadas con el trabajo. En el ejemplo siguiente se crea un tipo que acepta valores NULL `Boolean` y se declara una variable de ese tipo. Puede escribir la declaración de tres maneras:

[!code-vb[VbVbalrNullableValue#1](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#1)]

La variable `ridesBusToWork` puede contener un valor de `True` , un valor de `False` o ningún valor. Su valor predeterminado inicial es ningún valor, que en este caso podría significar que la información no se ha obtenido todavía para esta persona. Por el contrario, `False` podría significar que se ha obtenido la información y que la persona no pasa el bus para que funcione.

Puede declarar variables y propiedades con tipos de valor que aceptan valores NULL y puede declarar una matriz con elementos de un tipo de valor que acepta valores NULL. Puede declarar procedimientos con tipos de valor que aceptan valores NULL como parámetros, y puede devolver un tipo de valor que acepta valores NULL de un `Function` procedimiento.

No se puede crear un tipo que acepta valores NULL en un tipo de referencia, como una matriz, una `String` o una clase. El tipo subyacente debe ser un tipo de valor. Para obtener más información, vea [tipos de valor y tipos de referencia](value-types-and-reference-types.md).

## <a name="using-a-nullable-type-variable"></a>Usar una variable de tipo que acepta valores NULL

Los miembros más importantes de un tipo de valor que acepta valores NULL son sus <xref:System.Nullable%601.HasValue%2A> <xref:System.Nullable%601.Value%2A> propiedades y. En el caso de una variable de un tipo de valor que acepta valores NULL, <xref:System.Nullable%601.HasValue%2A> indica si la variable contiene un valor definido. Si <xref:System.Nullable%601.HasValue%2A> es `True` , puede leer el valor de <xref:System.Nullable%601.Value%2A> . Tenga en cuenta que <xref:System.Nullable%601.HasValue%2A> y <xref:System.Nullable%601.Value%2A> son `ReadOnly` propiedades.

### <a name="default-values"></a>Valores predeterminados

Cuando se declara una variable con un tipo de valor que acepta valores NULL, su <xref:System.Nullable%601.HasValue%2A> propiedad tiene un valor predeterminado de `False` . Esto significa que, de forma predeterminada, la variable no tiene ningún valor definido, en lugar del valor predeterminado de su tipo de valor subyacente. En el ejemplo siguiente, la variable `numberOfChildren` inicialmente no tiene ningún valor definido, aunque el valor predeterminado del `Integer` tipo sea 0.

[!code-vb[VbVbalrNullableValue#2](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#2)]

Un valor NULL es útil para indicar un valor no definido o desconocido. Si se `numberOfChildren` hubiera declarado como `Integer` , no habría ningún valor que pudiera indicar que la información no está disponible actualmente.

### <a name="storing-values"></a>Almacenar valores

Puede almacenar un valor en una variable o propiedad de un tipo de valor que acepta valores NULL de la manera habitual. En el ejemplo siguiente se asigna un valor a la variable `numberOfChildren` declarada en el ejemplo anterior.

[!code-vb[VbVbalrNullableValue#3](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#3)]

Si una variable o propiedad de un tipo de valor que acepta valores NULL contiene un valor definido, puede hacer que revierta a su estado inicial de no tener asignado un valor. Para ello, establezca la variable o la propiedad en `Nothing` , como se muestra en el ejemplo siguiente.

[!code-vb[VbVbalrNullableValue#4](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#4)]

> [!NOTE]
> Aunque puede asignar `Nothing` a una variable de un tipo de valor que acepta valores NULL, no puede probarla con `Nothing` el signo igual. La comparación que usa el signo igual, `someVar = Nothing` , siempre se evalúa como `Nothing` . Puede probar la propiedad de la variable <xref:System.Nullable%601.HasValue%2A> para `False` o probar mediante el `Is` `IsNot` operador OR.

### <a name="retrieving-values"></a>Recuperación de valores

Para recuperar el valor de una variable de un tipo de valor que acepta valores NULL, primero debe probar su <xref:System.Nullable%601.HasValue%2A> propiedad para confirmar que tiene un valor. Si intenta leer el valor cuando <xref:System.Nullable%601.HasValue%2A> es `False` , Visual Basic produce una <xref:System.InvalidOperationException> excepción. En el ejemplo siguiente se muestra la forma recomendada de leer la variable `numberOfChildren` de los ejemplos anteriores.

[!code-vb[VbVbalrNullableValue#5](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#5)]

## <a name="comparing-nullable-types"></a>Comparar tipos que aceptan valores NULL

Cuando `Boolean` se usan variables que aceptan valores NULL en Expresiones booleanas, el resultado puede ser `True` , `False` o `Nothing` . A continuación se encuentra la tabla de verdad para `And` y `Or` . Dado que `b1` y `b2` ahora tienen tres valores posibles, hay nueve combinaciones que evaluar.

|B1|B2|B1 y B2|B1 o B2|
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

Cuando el valor de una expresión o variable booleana es `Nothing` , no es `true` ni `false` . Considere el ejemplo siguiente.

[!code-vb[VbVbalrNullableValue#6](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#6)]

En este ejemplo, `b1 And b2` se evalúa como `Nothing` . Como resultado, la `Else` cláusula se ejecuta en cada `If` instrucción y el resultado es el siguiente:

`Expression is not true`

`Expression is not false`

> [!NOTE]
> `AndAlso` y `OrElse` , que usan la evaluación de cortocircuito, deben evaluar sus segundos operandos cuando el primero se evalúa como `Nothing` .

## <a name="propagation"></a>Propagación

Si uno o los dos operandos de una operación aritmética, de comparación, de desplazamiento o de tipo es un tipo de valor que acepta valores NULL, el resultado de la operación es también un tipo de valor que acepta valores NULL. Si ambos operandos tienen valores que no son `Nothing` , la operación se realiza en los valores subyacentes de los operandos, como si ninguno fuese un tipo de valor que acepta valores NULL. En el ejemplo siguiente, las variables `compare1` y `sum1` se escriben implícitamente. Si coloca el puntero del mouse sobre ellos, verá que el compilador deduce los tipos de valor que aceptan valores NULL para ambos.

[!code-vb[VbVbalrNullableValue#7](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#7)]

Si uno o ambos operandos tienen un valor de `Nothing` , el resultado será `Nothing` .

[!code-vb[VbVbalrNullableValue#8](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#8)]

## <a name="using-nullable-types-with-data"></a>Usar tipos que aceptan valores NULL con datos

Una base de datos es uno de los lugares más importantes para usar tipos de valor que aceptan valores NULL. No todos los objetos de base de datos admiten actualmente tipos de valor que aceptan valores NULL, pero sí los adaptadores de tabla generados por el diseñador. Vea [compatibilidad de TableAdapter con tipos que aceptan valores NULL](/visualstudio/data-tools/fill-datasets-by-using-tableadapters#tableadapter-support-for-nullable-types).

## <a name="see-also"></a>Consulte también

- <xref:System.InvalidOperationException>
- <xref:System.Nullable%601.HasValue%2A>
- [Tipo de datos](index.md)
- [Tipos de valor y tipos de referencia](value-types-and-reference-types.md)
- [Solución de problemas de los tipos de datos](troubleshooting-data-types.md)
- [Rellenar conjuntos de datos mediante TableAdapters](/visualstudio/data-tools/fill-datasets-by-using-tableadapters)
- [Operador If](../../../language-reference/operators/if-operator.md)
- [Inferencia de tipo de variable local](../variables/local-type-inference.md)
- [Operador Is](../../../language-reference/operators/is-operator.md)
- [Operador IsNot](../../../language-reference/operators/isnot-operator.md)
- [Tipos de valor que aceptan valores NULL (C#)](../../../../csharp/language-reference/builtin-types/nullable-value-types.md)
