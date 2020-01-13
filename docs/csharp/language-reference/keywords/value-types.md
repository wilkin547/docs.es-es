---
title: Tipos de valor - Referencia de C#
ms.date: 11/26/2018
f1_keywords:
- cs.valuetypes
helpviewer_keywords:
- value types [C#]
- types [C#], value types
- C# language, value types
ms.assetid: 471eb994-2958-49d5-a6be-19b4313f80a3
ms.openlocfilehash: 0ab9b6e089f5add9963ffae73e196643ad999763
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712915"
---
# <a name="value-types-c-reference"></a>Tipos de valor (Referencia de C#)

Existen dos clases de tipos de valor:

- [Structs](struct.md)

- [Enumeraciones](../builtin-types/enum.md)

## <a name="main-features-of-value-types"></a>Características principales de los tipos de valor

Una variable de un tipo de valor contiene un valor del tipo. Por ejemplo, una variable del tipo `int` podría contener el valor `42`. Esto difiere de una variable de un tipo de referencia, que contiene una referencia a una instancia del tipo y que también se conoce como un objeto. Al asignar un nuevo valor a una variable de un tipo de valor, se copia ese valor. Al asignar un nuevo valor a una variable de un tipo de referencia, se copia la referencia, no el propio objeto.

Todos los tipos de valor se derivan implícitamente de <xref:System.ValueType?displayProperty=nameWithType>.

A diferencia de los tipos de referencia, no puede derivar un tipo nuevo de un tipo de valor. En cambio, como los tipos de referencia, los structs pueden implementar interfaces.

Las variables de tipo de valor no pueden ser `null` de forma predeterminada. Sin embargo, las variables de los [tipos de valor que admiten un valor NULL](../builtin-types/nullable-value-types.md) correspondientes pueden ser `null`.

Cada tipo de valor tiene un constructor sin parámetros implícito que inicializa el valor predeterminado de ese tipo. Para información sobre los valores predeterminados de los tipos de valor, vea [Tabla de valores predeterminados](default-values-table.md).

## <a name="simple-types"></a>Tipos simples

Los *tipos simples* son un conjunto de tipos struct predefinidos proporcionados por C# y comprenden los siguientes tipos:

- [Tipos enteros](../builtin-types/integral-numeric-types.md): tipos numéricos enteros y tipo [char](../builtin-types/char.md)
- [Tipos de punto flotante](../builtin-types/floating-point-numeric-types.md)
- [bool](../builtin-types/bool.md)

Los tipos simples se identifican mediante palabras clave, pero estas palabras clave son simplemente los alias para tipos struct predefinidos en el espacio de nombres <xref:System>. Por ejemplo, [int](../builtin-types/integral-numeric-types.md) es un alias de <xref:System.Int32?displayProperty=nameWithType>. Para una lista completa de alias, vea [Tabla de tipos integrados](built-in-types-table.md).

Los tipos simples se diferencian de otros tipos struct en que permiten determinadas operaciones adicionales:

- Los tipos simples pueden inicializarse mediante el uso de literales. Por ejemplo, `'A'` es un literal del tipo `char` y `2001` es un literal del tipo `int`.

- Puede declarar constantes de los tipos simples con la palabra clave [const](const.md). No es posible tener constantes de otros tipos struct.

- Las expresiones constantes, cuyos operandos son todas constantes de tipo simple, se evalúan en tiempo de compilación.

Para más información, vea la sección [Tipos simples](~/_csharplang/spec/types.md#simple-types) de la [Especificación del lenguaje C#](/dotnet/csharp/language-reference/language-specification/introduction).

## <a name="initializing-value-types"></a>Inicialización de tipos de valor

Las variables locales en C# deben inicializarse antes de usarse. Por ejemplo, puede declarar una variable local sin inicialización como en el ejemplo siguiente:

```csharp
int myInt;
```

No puede usarla antes de inicializarla. Puede inicializarla con la siguiente instrucción:

```csharp
myInt = new int();  // Invoke parameterless constructor for int type.
```

Esta instrucción es equivalente a la instrucción siguiente:

```csharp
myInt = 0;         // Assign an initial value, 0 in this example.
```

Por supuesto, puede tener la declaración y la inicialización en la misma instrucción como en los ejemplos siguientes:

```csharp
int myInt = new int();
```

-O bien-

```csharp
int myInt = 0;
```

Con el operador [new](../operators/new-operator.md) se llama al constructor sin parámetros del tipo específico y se asigna el valor predeterminado a la variable. En el ejemplo anterior, el constructor sin parámetros ha asignado el valor `0` a `myInt`. Para más información sobre los valores que se han asignado llamando a los constructores sin parámetros, consulte [Tabla de valores predeterminados](default-values-table.md).

Con tipos definidos por el usuario, use [new](../operators/new-operator.md) para invocar al constructor sin parámetros. Por ejemplo, la siguiente instrucción invoca al constructor sin parámetros del struct `Point`:

```csharp
var p = new Point(); // Invoke parameterless constructor for the struct.
```

Después de esta llamada, el struct se considera asignado definitivamente; es decir, todos sus miembros se inicializan a sus valores predeterminados.

Para obtener más información acerca del operador `new`, vea [new](../operators/new-operator.md).

Para información sobre cómo aplicar formato al resultado de los tipos numéricos, vea [Tabla de formatos de presentación para valores numéricos](formatting-numeric-results-table.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Palabras clave de C#](index.md)
- [Tipos de referencia](reference-types.md)
- [Tipos de valores que aceptan valores NULL](../builtin-types/nullable-value-types.md)
