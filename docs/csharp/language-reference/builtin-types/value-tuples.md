---
title: Tipos de tupla - Referencia de C#
description: 'Obtenga información sobre las tuplas de C#: estructuras de datos ligeras que puede usar para agrupar elementos de datos relacionados de forma flexible'
ms.date: 07/09/2020
helpviewer_keywords:
- value tuples [C#]
ms.openlocfilehash: d996c7afecba1b58bfd8337fa444fd71790dd482
ms.sourcegitcommit: 870bc4b4087510f6fba3c7b1c0d391f02bcc1f3e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/23/2020
ms.locfileid: "92471777"
---
# <a name="tuple-types-c-reference"></a>Tipos de tupla (referencia de C#)

Disponible en C# 7.0 y versiones posteriores, la característica *tuplas* proporciona una sintaxis concisa para agrupar varios elementos de datos en una estructura de datos ligera. En el siguiente ejemplo se muestra cómo se puede declarar una variable de tupla, inicializarla y acceder a sus miembros de datos:

[!code-csharp-interactive[tuple intro](snippets/shared/ValueTuples.cs#Introduction)]

Como se muestra en el ejemplo anterior, para definir un tipo de tupla, se especifican los tipos de todos sus miembros de datos y, opcionalmente, los [nombres de campos](#tuple-field-names). No se pueden definir métodos en un tipo de tupla, pero se pueden usar los métodos proporcionados por .NET, como se muestra en el siguiente ejemplo:

[!code-csharp-interactive[tuple methods](snippets/shared/ValueTuples.cs#MethodOnTuples)]

A partir de C# 7.3, los tipos de tupla admiten [operadores de igualdad](../operators/equality-operators.md) `==` y `!=`. Para obtener más información, consulte la sección [Igualdad de tupla](#tuple-equality).

Los tipos de tupla son [tipos de valores](value-types.md); los elementos de tupla son campos públicos. Esto hace que las tuplas sean tipos de valor *mutables* .

> [!NOTE]
> La característica de las tuplas requiere el tipo <xref:System.ValueTuple?displayProperty=nameWithType> y los tipos genéricos relacionados (por ejemplo, <xref:System.ValueTuple%602?displayProperty=nameWithType>), que están disponibles en .NET Core y .NET Framework 4.7 y versiones posteriores. Para usar tuplas en un proyecto que tenga como destino .NET Framework 4.6.2 o versiones anteriores, agregue el paquete NuGet [`System.ValueTuple`](https://www.nuget.org/packages/System.ValueTuple/) al proyecto.

Puede definir tuplas con un gran número arbitrario de elementos:

[!code-csharp-interactive[large tuple](snippets/shared/ValueTuples.cs#LargeTuple)]

## <a name="use-cases-of-tuples"></a>Casos de uso de tuplas

Uno de los casos de uso más comunes de tuplas es como un tipo devuelto del método. Es decir, en lugar de definir [`out`los parámetros del método](../keywords/out-parameter-modifier.md), puede agrupar los resultados del método en un tipo devuelto de tupla, como se muestra en el ejemplo siguiente:

[!code-csharp-interactive[multiple method outputs](snippets/shared/ValueTuples.cs#MultipleReturns)]

Como se muestra en el ejemplo anterior, puede trabajar directamente con la instancia de la tupla devuelta o [deconstruirla](#tuple-assignment-and-deconstruction) en variables independientes.

También puede utilizar tipos de tupla en lugar de [tipos anónimos](../../programming-guide/classes-and-structs/anonymous-types.md); por ejemplo, en las consultas LINQ. Para obtener más información, vea [Elección entre tipos de tupla y anónimos](../../../standard/base-types/choosing-between-anonymous-and-tuple.md).

Normalmente, se usan tuplas para agrupar elementos de datos relacionados de forma flexible. Esto suele ser útil en métodos de utilidad privados e internos. En el caso de la API pública, considere la posibilidad de definir un tipo de [clase](../keywords/class.md) o de [estructura](struct.md).

## <a name="tuple-field-names"></a>Nombres de campo de tupla

Puede especificar explícitamente los nombres de campo de tupla en una expresión de inicialización de tuplas o en la definición de un tipo de tupla, como se muestra en el siguiente ejemplo:

[!code-csharp-interactive[explicit field names](snippets/shared/ValueTuples.cs#ExplicitFieldNames)]

A partir de C# 7.1, si no se especifica ningún nombre de campo, se puede deducir del nombre de la variable correspondiente en una expresión de inicialización de tupla, como se muestra en el siguiente ejemplo:

[!code-csharp-interactive[inferred field names](snippets/shared/ValueTuples.cs#InferFieldNames)]

Esto se conoce como "inicializadores de proyección de tupla". El nombre de una variable no se proyecta en un nombre de campo de tupla en los siguientes casos:

- El nombre del candidato es un nombre de miembro de un tipo de tupla, por ejemplo, `Item3`, `ToString` o `Rest`.
- El nombre del candidato es un duplicado de otro nombre de campo de tupla, ya sea explícita o implícita.

En estos casos, se especifica el nombre de un campo o se accede a un campo por su nombre predeterminado.

Los nombres predeterminados de los campos de tupla son `Item1`, `Item2`, `Item3`, etc. Siempre puede usar el nombre predeterminado de un campo, incluso cuando se especifica un nombre de campo de forma explícita o inferida, como se muestra en el siguiente ejemplo:

[!code-csharp-interactive[default field names](snippets/shared/ValueTuples.cs#DefaultFieldNames)]

En la [asignación de tuplas](#tuple-assignment-and-deconstruction) y las [comparaciones de igualdad de tuplas](#tuple-equality) no se tienen en cuenta los nombres de campo.

En el tiempo de compilación, el compilador sustituye los nombres de campo no predeterminados por los nombres predeterminados correspondientes. Como resultado, los nombres de campo especificados o inferidos no están disponibles en el tiempo de ejecución.

## <a name="tuple-assignment-and-deconstruction"></a>Asignación y deconstrucción de tuplas

C# admite la asignación entre tipos de tupla que satisfacen estas dos condiciones:

- ambos tipos de tupla tienen el mismo número de elementos;
- para cada posición de tupla, el tipo de elemento de tupla de la derecha es el mismo que el tipo de elemento de tupla de la izquierda correspondiente, o bien puede convertirse a este.

Los valores de elementos de tupla se asignan siguiendo el orden de los elementos de tupla. Los nombres de los campos de tupla se omiten y no se asignan, como se muestra en el siguiente ejemplo:

[!code-csharp-interactive[tuple assignment](snippets/shared/ValueTuples.cs#Assignment)]

También puede usar el operador de asignación `=` para *deconstruir* una instancia de tupla en variables independientes. Para ello, siga uno de estos métodos:

- Declarar explícitamente el tipo de cada variable entre paréntesis:

  [!code-csharp-interactive[specify types of variables](snippets/shared/ValueTuples.cs#DeconstructExplicit)]

- Usar la palabra clave `var` fuera de los paréntesis para declarar las variables con tipo implícito y permitir que el compilador deduzca sus tipos:

  [!code-csharp-interactive[implicitly typed variables](snippets/shared/ValueTuples.cs#DeconstructVar)]

- Usar variables existentes:

  [!code-csharp-interactive[existing variables](snippets/shared/ValueTuples.cs#DeconstructExisting)]

Para obtener más información sobre la deconstrucción de tuplas y otros tipos, consulte [Deconstrucción de tuplas y otros tipos](../../deconstruct.md).

## <a name="tuple-equality"></a>Igualdad de tupla

Comenzando con C# 7.3, los tipos de tupla admiten los operadores `==` y `!=`. Estos operadores comparan los miembros del operando izquierdo con los miembros correspondientes del operando derecho, siguiendo el orden de los elementos de la tupla.

[!code-csharp-interactive[tuple equality](snippets/shared/ValueTuples.cs#TupleEquality)]

Como se muestra en el ejemplo anterior, las operaciones `==` y `!=` no tienen en cuenta los nombres de campo de tupla.

Dos tuplas son comparables cuando se cumplen estas dos condiciones:

- Ambas tuplas tienen el mismo número de elementos. Por ejemplo, `t1 != t2` no se compila si `t1` y `t2` tienen números diferentes de elementos.
- Para cada posición de tupla, los elementos correspondientes de los operandos de la tupla de la izquierda y de la derecha son comparables con los operadores `==` y `!=`. Por ejemplo, `(1, (2, 3)) == ((1, 2), 3)` no se compila porque `1` no es comparable con `(1, 2)`.

Los operadores `==` y `!=` comparan las tuplas en modo de cortocircuito. Es decir, una operación se detiene en cuanto da con un par de elementos que no son iguales o alcanza los extremos de las tuplas. Sin embargo, antes de cualquier comparación, se evalúan *todos* los elementos de tupla, como se muestra en el siguiente ejemplo:

[!code-csharp-interactive[tuple element evaluation](snippets/shared/ValueTuples.cs#TupleEvaluationForEquality)]

## <a name="tuples-as-out-parameters"></a>Tuplas como parámetros de salida

Normalmente, se refactoriza un método que tiene parámetros de [`out`](../keywords/out-parameter-modifier.md) en un método que devuelve una tupla. Sin embargo, hay casos en los que un parámetro de `out` puede ser de un tipo de tupla. En el siguiente ejemplo básico se indica cómo trabajar con tuplas como parámetros de `out`:

[!code-csharp-interactive[tuple as out parameter](snippets/shared/ValueTuples.cs#TupleAsOutParameter)]

## <a name="tuples-vs-systemtuple"></a>Tuplas frente a `System.Tuple`

Las tuplas de C#, que están respaldadas por tipos de <xref:System.ValueTuple?displayProperty=nameWithType>, son diferentes de las tuplas representadas por tipos de <xref:System.Tuple?displayProperty=nameWithType>. Las diferencias principales son las siguientes:

- Los tipos de `ValueTuple` son [tipos de valores](value-types.md). Los tipos de `Tuple` son [tipos de referencia](../keywords/reference-types.md).
- Los tipos de `ValueTuple` son mutables. Los tipos de `Tuple` son inmutables.
- Los miembros de datos de tipos de `ValueTuple` son campos. Los miembros de datos de tipos de `Tuple` son propiedades.

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para obtener más información, consulte las siguientes notas de propuestas de características:

- [Deducción de nombres de tupla (también conocidos como "inicializadores de proyección de tupla")](~/_csharplang/proposals/csharp-7.1/infer-tuple-names.md)
- [Compatibilidad con `==` y `!=` en tipos de tupla](~/_csharplang/proposals/csharp-7.3/tuple-equality.md)

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Tipos de valor](value-types.md)
- [Elección entre tipos de tupla y anónimos](../../../standard/base-types/choosing-between-anonymous-and-tuple.md)
- <xref:System.ValueTuple?displayProperty=nameWithType>
