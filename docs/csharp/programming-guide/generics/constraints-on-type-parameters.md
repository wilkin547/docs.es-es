---
title: 'Restricciones de tipos de parámetros: Guía de programación de C#'
ms.date: 04/12/2018
helpviewer_keywords:
- generics [C#], type constraints
- type constraints [C#]
- type parameters [C#], constraints
- unbound type parameter [C#]
ms.openlocfilehash: 76cd00b9c84f128d2a181115293df910d8deb6cb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79398410"
---
# <a name="constraints-on-type-parameters-c-programming-guide"></a>Restricciones de tipos de parámetros (Guía de programación de C#)

Las restricciones informan al compilador sobre las capacidades que debe tener un argumento de tipo. Sin restricciones, el argumento de tipo puede ser cualquier tipo. El compilador solo puede suponer los miembros de <xref:System.Object?displayProperty=nameWithType>, que es la clase base fundamental de los tipos .NET. Para más información, vea [Por qué usar restricciones](#why-use-constraints). Si el código de cliente intenta crear una instancia de su clase mediante un tipo que no se permite por una restricción, el resultado es un error en tiempo de compilación. Las restricciones se especifican con la palabra clave contextual `where`. En la tabla siguiente se muestran los siete tipos de restricciones:

|Restricción|Description|
|----------------|-----------------|
|`where T : struct`|El argumento de tipo debe ser un tipo que no acepta valores NULL. Para más información sobre los tipos de valor que admiten un valor NULL, consulte [Tipos de valor que admiten un valor NULL](../../language-reference/builtin-types/nullable-value-types.md). Todos los tipos de valor tienen un constructor sin parámetros accesible, por lo que la restricción `struct` implica la restricción `new()` y no se puede combinar con la restricción `new()`. Tampoco se puede combinar la restricción `struct` con la restricción `unmanaged`.|
|`where T : class`|El argumento de tipo debe ser un tipo de referencia. Esta restricción se aplica también a cualquier clase, interfaz, delegado o tipo de matriz.|
|`where T : notnull`|El argumento de tipo debe ser un tipo que no acepta valores NULL. El argumento puede ser un tipo de referencia que no acepta valores NULL en C# 8.0 o posterior, o un tipo de valor que no acepta valores NULL. Esta restricción se aplica también a cualquier clase, interfaz, delegado o tipo de matriz.|
|`where T : unmanaged`|El argumento de tipo debe ser un tipo [no administrado](../../language-reference/builtin-types/unmanaged-types.md) que no acepta valores NULL. La restricción `unmanaged` implica la restricción `struct` y no se puede combinar con las restricciones `struct` ni `new()`.|
|`where T : new()`|El argumento de tipo debe tener un constructor sin parámetros público. Cuando se usa conjuntamente con otras restricciones, la restricción `new()` debe especificarse en último lugar. La restricción `new()` no se puede combinar con las restricciones `struct` ni `unmanaged`.|
|`where T :` *\<nombre de clase base>*|El argumento de tipo debe ser o derivarse de la clase base especificada.|
|`where T :` *\<nombre de interfaz>*|El argumento de tipo debe ser o implementar la interfaz especificada. Pueden especificarse varias restricciones de interfaz. La interfaz de restricciones también puede ser genérica.|
|`where T : U`|El argumento de tipo proporcionado por T debe ser o derivarse del argumento proporcionado para U.|

## <a name="why-use-constraints"></a>Por qué usar restricciones

Al restringir el parámetro de tipo, aumenta el número de operaciones y llamadas al método permitidas a las que se admiten mediante el tipo de restricción y todos los tipos en su jerarquía de herencia. Cuando se diseñan clases o métodos genéricos, si se va a realizar una operación en los miembros genéricos más allá de una asignación simple o una llamada a un método que <xref:System.Object?displayProperty=nameWithType> no admita, será necesario aplicar restricciones al parámetro de tipo. Por ejemplo, la restricción de clase base indica al compilador que solo los objetos de este tipo o derivados de este tipo se usarán como argumentos de tipo. Una vez que el compilador tenga esta garantía, puede permitir que los métodos de ese tipo se llamen en la clase genérica. En el ejemplo de código siguiente se muestran las funciones que podemos agregar a la clase `GenericList<T>` (en [Introducción a los genéricos](../../../standard/generics/index.md)) mediante la aplicación de una restricción de clase base.

[!code-csharp[using the class and struct constraints](~/samples/snippets/csharp/keywords/GenericWhereConstraints.cs#9)]

La restricción permite que la clase genérica use la propiedad `Employee.Name`. La restricción especifica que está garantizado que todos los elementos de tipo `T` sean un objeto `Employee` u objeto que hereda de `Employee`.

Pueden aplicarse varias restricciones en el mismo parámetro de tipo, y las propias restricciones pueden ser tipos genéricos, de la manera siguiente:

[!code-csharp[using the class and struct constraints](~/samples/snippets/csharp/keywords/GenericWhereConstraints.cs#10)]

Al aplicar la restricción `where T : class`, evite los operadores `==` y `!=` en el parámetro de tipo porque estos operadores se probarán solo para la identidad de referencia, no para la igualdad de valor. Este comportamiento se produce incluso si estos operadores están sobrecargados en un tipo que se usa como un argumento. En el código siguiente se ilustra este punto; el resultado es False incluso cuando la clase <xref:System.String> sobrecarga al operador `==`.

[!code-csharp[using the class and struct constraints](~/samples/snippets/csharp/keywords/GenericWhereConstraints.cs#11)]

El compilador solo sabe que `T` es un tipo de referencia en tiempo de compilación y debe usar los operadores predeterminados que son válidos para todos los tipos de referencia. Si debe probar la igualdad de valor, la manera recomendada también es aplicar la restricción `where T : IEquatable<T>` o `where T : IComparable<T>` e implementar esa interfaz en cualquier clase que se usará para construir la clase genérica.

## <a name="constraining-multiple-parameters"></a>Restringir varios parámetros

Puede aplicar restricciones a varios parámetros, y varias restricciones a un solo parámetro, como se muestra en el siguiente ejemplo:

[!code-csharp[using the class and struct constraints](~/samples/snippets/csharp/keywords/GenericWhereConstraints.cs#12)]

## <a name="unbounded-type-parameters"></a>Parámetros de tipo sin enlazar

 Los parámetros de tipo que no tienen restricciones, como T en la clase pública `SampleClass<T>{}`, se denominan parámetros de tipo sin enlazar. Los parámetros de tipo sin enlazar tienen las reglas siguientes:

- Los operadores `!=` y `==` no pueden usarse porque no existe ninguna garantía de que el argumento de tipo concreto admita estos operadores.
- Pueden convertirse a y desde `System.Object` o convertirse explícitamente en cualquier tipo de interfaz.
- Puede compararlos con [NULL](../../language-reference/keywords/null.md). Si un parámetro sin enlazar se compara con `null`, la comparación siempre devolverá False si el argumento de tipo es un tipo de valor.

## <a name="type-parameters-as-constraints"></a>Parámetros de tipo como restricciones

El uso de un parámetro de tipo genérico como una restricción es útil cuando una función de miembro con su propio parámetro de tipo tiene que restringir ese parámetro al parámetro de tipo del tipo contenedor, como se muestra en el ejemplo siguiente:

[!code-csharp[using the class and struct constraints](~/samples/snippets/csharp/keywords/GenericWhereConstraints.cs#13)]

En el ejemplo anterior, `T` es una restricción de tipo en el contexto del método `Add`, y un parámetro de tipo sin enlazar en el contexto de la clase `List`.

Los parámetros de tipo también pueden usarse como restricciones en definiciones de clase genéricas. El parámetro de tipo debe declararse dentro de los corchetes angulares junto con los demás parámetros de tipo:

[!code-csharp[using the class and struct constraints](~/samples/snippets/csharp/keywords/GenericWhereConstraints.cs#14)]

La utilidad de los parámetros de tipo como restricciones con clases genéricas es limitada, ya que el compilador no puede dar por supuesto nada sobre el parámetro de tipo, excepto que deriva de `System.Object`. Use parámetros de tipo como restricciones en clases genéricas en escenarios en los que quiere aplicar una relación de herencia entre dos parámetros de tipo.

## <a name="notnull-constraint"></a>Restricción NotNull

A partir C# 8.0, puede usar la restricción `notnull` para especificar que el argumento de tipo debe ser un tipo de valor que no acepta valores NULL o un tipo de referencia que no acepta valores NULL. La restricción `notnull` solo se puede usar en un contexto `nullable enable`. El compilador genera una advertencia si se agrega una restricción `notnull` en un contexto donde se desconoce que se aceptan valores NULL.

A diferencia de otras restricciones, cuando un argumento de tipo infringe la restricción `notnull`, el compilador genera una advertencia cuando el código se compila en un contexto `nullable enable`. Si el código se compila en un contexto donde se desconoce que se aceptan valores NULL, el compilador no genera ninguna advertencia o error.

## <a name="unmanaged-constraint"></a>Restricción no administrada

A partir de C# 7.3, puede usar la restricción `unmanaged` para especificar que el parámetro de tipo debe ser un [tipo no administrado](../../language-reference/builtin-types/unmanaged-types.md) que no acepta valores NULL. La restricción `unmanaged` permite escribir rutinas reutilizables para trabajar con tipos que se pueden manipular como bloques de memoria, como se muestra en el ejemplo siguiente:

[!code-csharp[using the unmanaged constraint](~/samples/snippets/csharp/keywords/GenericWhereConstraints.cs#15)]

El método anterior debe compilarse en un contexto `unsafe`, ya que usa el operador `sizeof` en un tipo que se desconoce si es integrado. Sin la restricción `unmanaged`, el operador `sizeof` no está disponible.

La restricción `unmanaged` implica la restricción `struct` y no se puede combinar con ella. Dado que la restricción `struct` implica la restricción `new()`, la restricción `unmanaged` tampoco se puede combinar con la restricción `new()`.

## <a name="delegate-constraints"></a>Restricciones de delegado

También a partir de C# 7.3, puede usar <xref:System.Delegate?displayProperty=nameWithType> o <xref:System.MulticastDelegate?displayProperty=nameWithType> como una restricción de clase base. CLR siempre permitía esta restricción, pero el lenguaje C# no la permitía. La restricción `System.Delegate` permite escribir código que funciona con los delegados en un modo con seguridad de tipos. En el código siguiente se define un método de extensión que combina dos delegados siempre y cuando sean del mismo tipo:

[!code-csharp[using the delegate constraint](~/samples/snippets/csharp/keywords/GenericWhereConstraints.cs#16)]

Puede usar el método anterior para combinar delegados que sean del mismo tipo:

[!code-csharp[using the unmanaged constraint](~/samples/snippets/csharp/keywords/GenericWhereConstraints.cs#17)]

Si quita la marca de comentario de la última línea, no se compilará. Tanto `first` como `test` son tipos de delegado, pero son tipos de delegado distintos.

## <a name="enum-constraints"></a>Restricciones de enumeración

A partir de C# 7.3, también puede especificar el tipo <xref:System.Enum?displayProperty=nameWithType> como una restricción de clase base. CLR siempre permitía esta restricción, pero el lenguaje C# no la permitía. Los genéricos que usan `System.Enum` proporcionan programación con seguridad de tipos para almacenar en caché los resultados de usar los métodos estáticos en `System.Enum`. En el ejemplo siguiente se buscan todos los valores válidos para un tipo de enumeración y, después, se compila un diccionario que asigna esos valores a su representación de cadena.

[!code-csharp[using the enum constraint](~/samples/snippets/csharp/keywords/GenericWhereConstraints.cs#18)]

Los métodos empleados usan la reflexión, lo que tiene consecuencias en el rendimiento. Puede llamar a este método para compilar una recopilación que se almacene en caché y se vuelva a usar, en lugar de repetir las llamadas que requieren reflexión.

Podría usarla como se muestra en el ejemplo siguiente para crear una enumeración y compilar un diccionario con sus nombres y valores:

[!code-csharp[enum definition](~/samples/snippets/csharp/keywords/GenericWhereConstraints.cs#19)]

[!code-csharp[using the enum constrained method](~/samples/snippets/csharp/keywords/GenericWhereConstraints.cs#20)]

## <a name="see-also"></a>Vea también

- <xref:System.Collections.Generic>
- [Guía de programación de C#](../index.md)
- [Introducción a los genéricos](./index.md)
- [Clases genéricas](./generic-classes.md)
- [new (restricción)](../../language-reference/keywords/new-constraint.md)
