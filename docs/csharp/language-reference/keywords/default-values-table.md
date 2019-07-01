---
title: 'Tabla de valores predeterminados: Referencia de C#'
ms.custom: seodec18
description: Obtenga información sobre los valores predeterminados de los tipos de valor de C#.
ms.date: 08/23/2018
helpviewer_keywords:
- constructors [C#], return values
- keywords [C#], new
- parameterless constructor [C#]
- defaults [C#]
- value types [C#], initializing
- variables [C#], value types
- constructors [C#], parameterless constructor
- types [C#], parameterless constructor return values
ms.openlocfilehash: dfab5107d4a0ad14c3ffbfc6a5f3c4317b44d17c
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/28/2019
ms.locfileid: "67424229"
---
# <a name="default-values-table-c-reference"></a>Tabla de valores predeterminados (Referencia de C#)

En la tabla siguiente se muestran los valores predeterminados de los [tipos de valor](value-types.md).

|Tipo de valor|Valor predeterminado|
|----------------|-------------------|
|[bool](bool.md)|`false`|
|[byte](../builtin-types/integral-numeric-types.md)|0|
|[char](char.md)|'\0'|
|[decimal](decimal.md)|0M|
|[double](double.md)|0.0D|
|[enum](enum.md)|Valor generado por la expresión `(E)0`, donde `E` es el identificador de enumeración.|
|[float](float.md)|0.0F|
|[int](../builtin-types/integral-numeric-types.md)|0|
|[long](../builtin-types/integral-numeric-types.md)|0L|
|[sbyte](../builtin-types/integral-numeric-types.md)|0|
|[short](../builtin-types/integral-numeric-types.md)|0|
|[struct](struct.md)|El valor generado al establecer todos los campos de tipo de valor en sus valores predeterminados y todos los campos de tipo de referencia en `null`.|
|[uint](../builtin-types/integral-numeric-types.md)|0|
|[ulong](../builtin-types/integral-numeric-types.md)|0|
|[ushort](../builtin-types/integral-numeric-types.md)|0|

## <a name="remarks"></a>Comentarios

En C# no se pueden usar variables sin inicializar. Una variable se puede inicializar con el valor predeterminado de su tipo. También se puede usar el valor predeterminado de un tipo para especificar el valor predeterminado del [argumento opcional](../../programming-guide/classes-and-structs/named-and-optional-arguments.md#optional-arguments) de un método.

Use la [expresión de valor predeterminado](../../programming-guide/statements-expressions-operators/default-value-expressions.md) para generar el valor predeterminado de un tipo, como se muestra en el ejemplo siguiente:

```csharp
int a = default(int);
```

A partir de C# 7.1, se puede usar el [literal `default`](../../programming-guide/statements-expressions-operators/default-value-expressions.md#default-literal-and-type-inference) para inicializar una variable con el valor predeterminado de su tipo:

```csharp
int a = default;
```

También se puede usar el constructor sin parámetros o el constructor sin parámetros implícito para generar el valor predeterminado de un tipo de valor, como se muestra en el ejemplo siguiente. Para obtener más información sobre los constructores, vea el artículo [Constructores](../../programming-guide/classes-and-structs/constructors.md).

```csharp
int a = new int();
```

El valor predeterminado de cualquier [tipo de referencia](reference-types.md) es `null`. El valor predeterminado de un [tipo que acepta valores NULL](../../programming-guide/nullable-types/index.md) es una instancia para la que la propiedad <xref:System.Nullable%601.HasValue%2A> es `false` y la propiedad <xref:System.Nullable%601.Value%2A> no está definida.

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Palabras clave de C#](index.md)
- [Tipos de valor](value-types.md)
- [Tabla de tipos de valor](value-types-table.md)
- [Tabla de tipos integrados](built-in-types-table.md)
