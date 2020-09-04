---
description: Obtenga información sobre el tipo de estructura en C#.
title: 'Tipos de estructura: Referencia de C#'
ms.date: 04/21/2020
f1_keywords:
- struct_CSharpKeyword
helpviewer_keywords:
- struct keyword [C#]
- struct type [C#]
- structure type [C#]
ms.assetid: ff3dd9b7-dc93-4720-8855-ef5558f65c7c
ms.openlocfilehash: 7f3940ce487b9e382150234f317cf1dba34bb060
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89132734"
---
# <a name="structure-types-c-reference"></a>Tipos de estructura (Referencia de C#)

Un *tipo de estructura* (o *tipo struct*) es un [tipo de valor](value-types.md) que puede encapsular datos y funcionalidad relacionada. Para definir un tipo de estructura se usa la palabra clave `struct`:

[!code-csharp[struct example](snippets/StructType.cs#StructExample)]

Los tipos de estructura tienen *semántica de valores*. Es decir, una variable de un tipo de estructura contiene una instancia del tipo. De forma predeterminada, los valores de variable se copian al asignar, pasar un argumento a un método o devolver el resultado de un método. En el caso de una variable de tipo de estructura, se copia una instancia del tipo. Para más información, vea [Tipos de valor](value-types.md).

Normalmente, los tipos de estructura se usan para diseñar tipos de pequeño tamaño centrados en datos que proporcionan poco o ningún comportamiento. Por ejemplo, en .NET se usan los tipos de estructura para representar un número ([entero](integral-numeric-types.md) y [real](floating-point-numeric-types.md)), un [valor booleano](bool.md), un [caracter Unicode](char.md), una [instancia de tiempo](xref:System.DateTime). Si le interesa el comportamiento de un tipo, considere la posibilidad de definir una [clase](../keywords/class.md). Los tipos de clase tienen *semántica de referencias*. Es decir, una variable de un tipo de clase contiene una referencia a una instancia del tipo, no la propia instancia.

Dado que los tipos de estructura tienen semántica del valor, le recomendamos que defina tipos de estructura *inmutables*.

## <a name="readonly-struct"></a>Estructura `readonly`

A partir de C# 7.2, usa el modificador `readonly` para declarar que un tipo de estructura es inmutable:

[!code-csharp[readonly struct](snippets/StructType.cs#ReadonlyStruct)]

Todos los miembros de datos de una estructura `readonly` debe ser de solo lectura tal como se indica a continuación:

- Cualquier declaración de campo debe tener el [modificador `readonly`](../keywords/readonly.md)
- Cualquier propiedad, incluidas las implementadas automáticamente, deben ser de solo lectura

Esto garantiza que ningún miembro de una estructura `readonly` modifique el estado de la misma. En C# 8.0 y en versiones posteriores, eso significa que otros miembros de instancia, excepto los constructores, son implícitamente [`readonly`](#readonly-instance-members).

> [!NOTE]
> En una estructura `readonly`, un miembro de datos de un tipo de referencia mutable puede seguir mutando su propio estado. Por ejemplo, no puede reemplazar una instancia de <xref:System.Collections.Generic.List%601>, pero puede agregarle nuevos elementos.

## <a name="readonly-instance-members"></a>Miembros de instancia de `readonly`

A partir de C# 8.0, también puede usar el modificador `readonly` para declarar que un miembro de instancia no modifica el estado de una estructura. Si no puede declarar el tipo de estructura completa como `readonly`, use el modificador `readonly` para marcar los miembros de instancia que no modifican el estado de la estructura.

Dentro de un miembro de instancia `readonly`, no se puede realizar la asignación a campos de instancia de la estructura. Pero un miembro `readonly` puede llamar a un miembro que no sea `readonly`. En ese caso, el compilador crea una copia de la instancia de la estructura y llama al miembro que no es `readonly` en esa copia. Como resultado, la instancia de la estructura original no se modifica.

Normalmente, se aplica el modificador `readonly` a los siguientes tipos de miembros de instancia:

- Métodos:

  [!code-csharp[readonly method](snippets/StructType.cs#ReadonlyMethod)]

  También puede aplicar el modificador `readonly` a los métodos que invalidan los métodos declarados en <xref:System.Object?displayProperty=nameWithType>:

  [!code-csharp[readonly override](snippets/StructType.cs#ReadonlyOverride)]

- Propiedades e indizadores:

  [!code-csharp[readonly property get](snippets/StructType.cs#ReadonlyProperty)]

  Si tiene que aplicar el modificador `readonly` a los dos descriptores de acceso de una propiedad o un indizador, aplíquelo en la declaración de la propiedad o el indizador.

  > [!NOTE]
  > El compilador declara un descriptor de acceso `get` de una [propiedad implementada automáticamente](../../programming-guide/classes-and-structs/auto-implemented-properties.md) como `readonly`, con independencia de la presencia del modificador `readonly` en la declaración de una propiedad.

No se puede aplicar el modificador `readonly` a los miembros estáticos de un tipo de estructura.

Es posible que el compilador use el modificador `readonly` para optimizaciones de rendimiento. Para más información, consulte [Escritura de código C# seguro y eficaz](../../write-safe-efficient-code.md).

## <a name="limitations-with-the-design-of-a-structure-type"></a>Limitaciones del diseño de un tipo de estructura

Al diseñar un tipo de estructura, tiene las mismas funciones que con un tipo de [clase](../keywords/class.md), con las siguientes excepciones:

- No se puede declarar un constructor sin parámetros. Cada tipo de estructura ya proporciona un constructor sin parámetros implícito que genera el [valor predeterminado](default-values.md) del tipo.

- No se puede inicializar una propiedad o un campo de instancia en su declaración. Pero se puede inicializar un campo [static](../keywords/static.md) o [const](../keywords/const.md), o una propiedad estática en su declaración.

- Un constructor de un tipo de estructura debe inicializar todos los campos de instancia del tipo.

- Un tipo de estructura no puede heredar de otro tipo de estructura o clase ni puede ser la base de una clase. Pero un tipo de estructura puede implementar [interfaces](../keywords/interface.md).

- No se puede declarar un [finalizador](../../programming-guide/classes-and-structs/destructors.md) dentro de un tipo de estructura.

## <a name="instantiation-of-a-structure-type"></a>Creación de instancias de un tipo de estructura

En C#, debe inicializar una variable declarada antes de poder usarla. Como una variable de tipo de estructura no puede ser `null` (a menos que sea una variable de un [tipo de valor que admite valores NULL](nullable-value-types.md)), tendrá que crear instancias de una instancia del tipo correspondiente. Existen varias formas de hacerlo.

Normalmente, para crear una instancia de un tipo de estructura, se llama a un constructor adecuado con el operador [`new`](../operators/new-operator.md). Todos los tipos de estructura tienen al menos un constructor. Se trata de un constructor sin parámetros implícito, que genera el [valor predeterminado](default-values.md) del tipo. También puede usar una [expresión de valor predeterminado](../operators/default.md) para generar el valor predeterminado de un tipo.

Si se puede acceder a todos los campos de instancia de un tipo de estructura, también puede crear una instancia de él sin el operador `new`. En ese caso, debe inicializar todos los campos de instancia antes del primer uso de la instancia. En el siguiente ejemplo se muestra cómo hacerlo:

[!code-csharp[without new](snippets/StructType.cs#WithoutNew)]

En el caso de los [tipos de valor integrados](value-types.md#built-in-value-types), use los literales correspondientes para especificar un valor del tipo.

## <a name="passing-structure-type-variables-by-reference"></a>Pasar variables de tipo de estructura por referencia

Cuando se pasa una variable de tipo de estructura a un método como argumento o se devuelve un valor de tipo de estructura a partir de un método, se copia toda la instancia de un tipo de estructura. Esto puede afectar al rendimiento del código en escenarios de alto rendimiento que impliquen tipos de estructura grandes. Puede evitar la copia de valores si pasa una variable de tipo de estructura por referencia. Use los modificadores de parámetro de método [`ref`](../keywords/ref.md#passing-an-argument-by-reference), [`out`](../keywords/out-parameter-modifier.md) o [`in`](../keywords/in-parameter-modifier.md) para indicar que un argumento se debe pasar por referencia. Use [valores devueltos de tipo ref](../../programming-guide/classes-and-structs/ref-returns.md) para devolver el resultado de un método por referencia. Para más información, consulte [Escritura de código C# seguro y eficaz](../../write-safe-efficient-code.md).

## <a name="ref-struct"></a>Estructura `ref`

A partir de C# 7.2, puede usar el modificador `ref` en la declaración de un tipo de estructura. Las instancias de un tipo de estructura `ref` se asignan en la pila y no pueden escapar al montón administrado. Para asegurarse de eso, el compilador limita el uso de tipos de estructura `ref` de la manera siguiente:

- Una estructura `ref` no puede ser el tipo de elemento de una matriz.
- Una estructura `ref` no puede ser un tipo declarado de un campo de una clase o una estructura que no sea `ref`.
- Una estructura `ref` no puede implementar interfaces.
- En una estructura `ref` no se puede aplicar una conversión boxing a <xref:System.ValueType?displayProperty=nameWithType> ni <xref:System.Object?displayProperty=nameWithType>.
- Una estructura `ref` no puede ser un argumento de tipo.
- Una `ref` variable de estructura no se puede capturar mediante una [expresión lambda](../operators/lambda-expressions.md) o una [función local](../../programming-guide/classes-and-structs/local-functions.md).
- Una variable de estructura `ref` no se puede usar en un método [`async`](../keywords/async.md). Aunque se pueden usar variables de estructura `ref` en métodos sincrónicos, como, por ejemplo, en los que devuelven <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601>.
- Una variable de estructura `ref` no se puede usar en [iteradores](../../iterators.md).

Normalmente, se define un tipo de estructura `ref` cuando se necesita un tipo que también incluye miembros de datos de tipos de estructura `ref`:

[!code-csharp[ref struct](snippets/StructType.cs#RefStruct)]

Para declarar una estructura `ref` como [`readonly`](#readonly-struct), combine los modificadores `readonly` y `ref` en la declaración de tipos (el modificador `readonly` debe ir delante del modificador `ref`):

[!code-csharp[readonly ref struct](snippets/StructType.cs#ReadonlyRef)]

En .NET, <xref:System.Span%601?displayProperty=nameWithType> y <xref:System.ReadOnlySpan%601?displayProperty=nameWithType> son ejemplos de una estructura `ref`.

## <a name="conversions"></a>Conversiones

Para cualquier tipo de estructura (excepto los tipos de [estructura `ref`](#ref-struct)), existen conversiones [boxing y unboxing](../../programming-guide/types/boxing-and-unboxing.md) a y desde los tipos <xref:System.ValueType?displayProperty=nameWithType> y <xref:System.Object?displayProperty=nameWithType>. También existen conversiones boxing y unboxing entre un tipo de estructura y cualquier interfaz que implemente.

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para más información, vea la sección [Estructuras](~/_csharplang/spec/structs.md) de la [especificación del lenguaje C#](~/_csharplang/spec/introduction.md).

Para obtener más información sobre de las características presentadas en C# 7.2 y versiones posteriores, vea las siguientes notas de propuesta de características:

- [Estructuras readonly](~/_csharplang/proposals/csharp-7.2/readonly-ref.md#readonly-structs)
- [Miembros de instancia readonly](~/_csharplang/proposals/csharp-8.0/readonly-instance-members.md)
- [Seguridad de tiempo de compilación para tipos similares a ref](~/_csharplang/proposals/csharp-7.2/span-safety.md)

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Instrucciones de diseño: elección entre clase y estructura](../../../standard/design-guidelines/choosing-between-class-and-struct.md)
- [Instrucciones de diseño: diseño de estructuras](../../../standard/design-guidelines/struct.md)
- [Clases y estructuras](../../programming-guide/classes-and-structs/index.md)
