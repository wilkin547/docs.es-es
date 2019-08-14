---
title: 'Tabla de valores predeterminados: referencia de C#'
ms.custom: seodec18
description: Obtenga información sobre los valores predeterminados de los tipos de C#.
ms.date: 07/29/2019
helpviewer_keywords:
- default [C#]
- parameterless constructor [C#]
ms.openlocfilehash: 23fba8269670156000cb68b3aa07ae7c770eada1
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627740"
---
# <a name="default-values-table-c-reference"></a>Tabla de valores predeterminados (referencia de C#)

En la tabla siguiente se muestran los valores predeterminados de los tipos de C#:

|Tipo|Valor predeterminado|
|---------|------------------|
|Cualquier tipo de referencia|`null`|
|Cualquier [tipo numérico entero integrado](../builtin-types/integral-numeric-types.md)|0 (cero)|
|Cualquier [tipo numérico de punto flotante integrado](../builtin-types/floating-point-numeric-types.md)|0 (cero)|
|[bool](bool.md)|`false`|
|[char](char.md)|`'\0'` (U+0000)|
|[enum](enum.md)|Valor generado por la expresión `(E)0`, donde `E` es el identificador de enumeración.|
|[struct](struct.md)|El valor generado al establecer todos los campos de tipo de valor en sus valores predeterminados y todos los campos de tipo de referencia en `null`.|
|Cualquier [tipo de valor que acepta valores NULL](../../programming-guide/nullable-types/index.md)|Instancia para la que la propiedad <xref:System.Nullable%601.HasValue%2A> es `false` y la propiedad <xref:System.Nullable%601.Value%2A> no está definida. Este valor predeterminado también se conoce con el valor *null* del tipo de valor que acepta valores NULL.|

Use la [expresión de valor predeterminado](../../programming-guide/statements-expressions-operators/default-value-expressions.md) para generar el valor predeterminado de un tipo, como se muestra en el ejemplo siguiente:

```csharp
int a = default(int);
```

A partir de C# 7.1, se puede usar el [literal `default`](../../programming-guide/statements-expressions-operators/default-value-expressions.md#default-literal-and-type-inference) para inicializar una variable con el valor predeterminado de su tipo:

```csharp
int a = default;
```

Para un tipo de valor, el constructor implícito sin parámetros también genera el valor predeterminado del tipo, como se muestra en el ejemplo siguiente:

```csharp-interactive
var n = new System.Numerics.Complex();
Console.WriteLine(n);  // output: (0, 0)
```

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para más información, vea las secciones siguientes de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md):

- [Valores predeterminados](~/_csharplang/spec/variables.md#default-values)
- [Constructores predeterminados](~/_csharplang/spec/types.md#default-constructors)

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Palabras clave de C#](index.md)
- [Tabla de tipos integrados](built-in-types-table.md)
- [Constructores](../../programming-guide/classes-and-structs/constructors.md)
