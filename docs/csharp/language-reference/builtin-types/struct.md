---
title: 'Tipos de estructura: Referencia de C#'
ms.date: 02/24/2020
f1_keywords:
- struct_CSharpKeyword
helpviewer_keywords:
- struct keyword [C#]
- struct type [C#]
- structure type [C#]
ms.assetid: ff3dd9b7-dc93-4720-8855-ef5558f65c7c
ms.openlocfilehash: b85d0df086f3ca65ed995594dd374286e1c3ba5c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "78847734"
---
# <a name="structure-types-c-reference"></a>Tipos de estructura (Referencia de C#)

Un *tipo de estructura* (o *tipo struct*) es un [tipo de valor](value-types.md) que puede encapsular datos y funcionalidad relacionada. Para definir un tipo de estructura se usa la palabra clave `struct`:

[!code-csharp[struct example](snippets/StructType.cs#StructExample)]

Los tipos de estructura tienen *semántica de valores*. Es decir, una variable de un tipo de estructura contiene una instancia del tipo. De forma predeterminada, los valores de variable se copian al asignar, pasar un argumento a un método o devolver el resultado de un método. En el caso de una variable de tipo de estructura, se copia una instancia del tipo. Para más información, vea [Tipos de valor](value-types.md).

Normalmente, los tipos de estructura se usan para diseñar tipos de pequeño tamaño centrados en datos que proporcionan poco o ningún comportamiento. Por ejemplo, en .NET se usan los tipos de estructura para representar un número ([entero](integral-numeric-types.md) y [real](floating-point-numeric-types.md)), un [valor booleano](bool.md), un [caracter Unicode](char.md), una [instancia de tiempo](xref:System.DateTime). Si le interesa el comportamiento de un tipo, considere la posibilidad de definir una [clase](../keywords/class.md). Los tipos de clase tienen *semántica de referencias*. Es decir, una variable de un tipo de clase contiene una referencia a una instancia del tipo, no la propia instancia.

## <a name="limitations-with-the-design-of-a-structure-type"></a>Limitaciones del diseño de un tipo de estructura

Al diseñar un tipo de estructura, tiene las mismas funciones que con un tipo de [clase](../keywords/class.md), con las siguientes excepciones:

- No se puede declarar un constructor sin parámetros. Cada tipo de estructura ya proporciona un constructor sin parámetros implícito que genera el [valor predeterminado](default-values.md) del tipo.

- No se puede inicializar una propiedad o un campo de instancia en su declaración. Pero se puede inicializar un campo [static](../keywords/static.md) o [const](../keywords/const.md), o una propiedad estática en su declaración.

- Un constructor de un tipo de estructura debe inicializar todos los campos de instancia del tipo.

- Un tipo de estructura no puede heredar de otro tipo de clase o estructura, y no puede ser la base de una clase. Pero un tipo de estructura puede implementar [interfaces](../keywords/interface.md).

- No se puede declarar un [finalizador](../../programming-guide/classes-and-structs/destructors.md) dentro de un tipo de estructura.

## <a name="instantiation-of-a-structure-type"></a>Creación de instancias de un tipo de estructura

En C#, debe inicializar una variable declarada antes de poder usarla. Como una variable de tipo de estructura no puede ser `null` (a menos que sea una variable de un [tipo de valor que admite un valor NULL](nullable-value-types.md)), tendrá que crear instancias de una instancia del tipo correspondiente. Existen varias formas de hacerlo.

Normalmente, para crear una instancia de un tipo de estructura, se llama a un constructor adecuado con el operador [`new`](../operators/new-operator.md). Todos los tipos de estructura tienen al menos un constructor. Se trata de un constructor sin parámetros implícito, que genera el [valor predeterminado](default-values.md) del tipo. También puede usar el operador o literal [default](../operators/default.md) para generar el valor predeterminado de un tipo.

Si se puede acceder a todos los campos de instancia de un tipo de estructura, también puede crear una instancia de él sin el operador `new`. En ese caso, debe inicializar todos los campos de instancia antes del primer uso de la instancia. En el siguiente ejemplo se muestra cómo hacerlo:

[!code-csharp[without new](snippets/StructType.cs#WithoutNew)]

En el caso de los [tipos de valor integrados](value-types.md#built-in-value-types), use los literales correspondientes para especificar un valor del tipo.

## <a name="passing-structure-type-variables-by-reference"></a>Pasar variables de tipo de estructura por referencia

Cuando se pasa una variable de tipo de estructura a un método como argumento o se devuelve un valor de tipo de estructura a partir de un método, se copia toda la instancia de un tipo de estructura. Esto puede afectar al rendimiento del código en escenarios de alto rendimiento que impliquen tipos de estructura grandes. Puede evitar la copia de valores si pasa una variable de tipo de estructura por referencia. Use los modificadores de parámetro de método [`ref`](../keywords/ref.md#passing-an-argument-by-reference), [`out`](../keywords/out-parameter-modifier.md) o [`in`](../keywords/in-parameter-modifier.md) para indicar que un argumento se debe pasar por referencia. Use [valores devueltos de tipo ref](../../programming-guide/classes-and-structs/ref-returns.md) para devolver el resultado de un método por referencia. Para más información, consulte [Escritura de código C# seguro y eficaz](../../write-safe-efficient-code.md).

## <a name="conversions"></a>Conversiones

Para cualquier tipo de estructura, existen conversiones [boxing y unboxing](../../programming-guide/types/boxing-and-unboxing.md) a y desde los tipos <xref:System.ValueType?displayProperty=nameWithType> y <xref:System.Object?displayProperty=nameWithType>. También existen conversiones boxing y unboxing entre un tipo de estructura y cualquier interfaz que implemente.

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para más información, vea la sección [Estructuras](~/_csharplang/spec/structs.md) de la [especificación del lenguaje C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Instrucciones de diseño: elección entre clase y estructura](../../../standard/design-guidelines/choosing-between-class-and-struct.md)
- [Instrucciones de diseño: diseño de estructuras](../../../standard/design-guidelines/struct.md)
- [Clases y estructuras](../../programming-guide/classes-and-structs/index.md)
