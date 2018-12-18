---
title: 'Tabla de valores predeterminados: Referencia de C#'
ms.custom: seodec18
description: Obtenga información sobre los valores predeterminados de los tipos de valor de C#.
ms.date: 08/23/2018
helpviewer_keywords:
- constructors [C#], return values
- keywords [C#], new
- default constructor [C#]
- defaults [C#]
- value types [C#], initializing
- variables [C#], value types
- constructors [C#], default constructor
- types [C#], default constructor return values
ms.openlocfilehash: 19e9e4f94ab573f2313c185a08192d89103b98fd
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53237043"
---
# <a name="default-values-table-c-reference"></a>Tabla de valores predeterminados (Referencia de C#)

En la tabla siguiente se muestran los valores predeterminados de los [tipos de valor](value-types.md).

|Tipo de valor|Valor predeterminado|
|----------------|-------------------|
|[bool](bool.md)|`false`|
|[byte](byte.md)|0|
|[char](char.md)|'\0'|
|[decimal](decimal.md)|0M|
|[double](double.md)|0.0D|
|[enum](enum.md)|Valor generado por la expresión `(E)0`, donde `E` es el identificador de enumeración.|
|[float](float.md)|0.0F|
|[int](int.md)|0|
|[long](long.md)|0L|
|[sbyte](sbyte.md)|0|
|[short](short.md)|0|
|[struct](struct.md)|El valor generado al establecer todos los campos de tipo de valor en sus valores predeterminados y todos los campos de tipo de referencia en `null`.|
|[uint](uint.md)|0|
|[ulong](ulong.md)|0|
|[ushort](ushort.md)|0|

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

También se puede usar el constructor predeterminado o el constructor predeterminado implícito para generar el valor predeterminado de un tipo de valor, como se muestra en el ejemplo siguiente. Para obtener más información sobre los constructores, vea el artículo [Constructores](../../programming-guide/classes-and-structs/constructors.md).

```csharp
int a = new int();
```

El valor predeterminado de cualquier [tipo de referencia](reference-types.md) es `null`. El valor predeterminado de un [tipo que acepta valores NULL](../../programming-guide/nullable-types/index.md) es una instancia para la que la propiedad <xref:System.Nullable%601.HasValue%2A> es `false` y la propiedad <xref:System.Nullable%601.Value%2A> no está definida.

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Palabras clave de C#](index.md)
- [Tablas de referencia para tipos](reference-tables-for-types.md)
- [Tipos de valor](value-types.md)
- [Tabla de tipos de valor](value-types-table.md)
- [Tabla de tipos integrados](built-in-types-table.md)
