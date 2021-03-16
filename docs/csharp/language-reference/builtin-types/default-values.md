---
title: 'Valores predeterminados de los tipos de C#: referencia de C#'
description: Aprenda los valores predeterminados de C#, como bool, char, int, float, double y más.
ms.date: 12/18/2019
helpviewer_keywords:
- default [C#]
- parameterless constructor [C#]
ms.openlocfilehash: 72d6249ed56ae6ae34a6f51102e1e7bbd3f64ab7
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102104120"
---
# <a name="default-values-of-c-types-c-reference"></a>Valores predeterminados de los tipos de C# (referencia de C#)

En la tabla siguiente se muestran los valores predeterminados de los tipos de C#:

|Tipo|Valor predeterminado|
|---------|------------------|
|Cualquier [tipo de referencia](../keywords/reference-types.md)|`null`|
|Cualquier [tipo numérico entero integrado](integral-numeric-types.md)|0 (cero)|
|Cualquier [tipo numérico de punto flotante integrado](floating-point-numeric-types.md)|0 (cero)|
|[bool](bool.md)|`false`|
|[char](char.md)|`'\0'` (U+0000)|
|[enum](enum.md)|Valor generado por la expresión `(E)0`, donde `E` es el identificador de enumeración.|
|[struct](struct.md)|El valor generado al establecer todos los campos de tipo de valor en sus valores predeterminados y todos los campos de tipo de referencia en `null`.|
|Cualquier [tipo de valor que acepta valores NULL](nullable-value-types.md)|Instancia para la que la propiedad <xref:System.Nullable%601.HasValue%2A> es `false` y la propiedad <xref:System.Nullable%601.Value%2A> no está definida. Este valor predeterminado también se conoce con el valor *null* de un tipo de valor que acepta valores NULL.|

Use el operador [`default`](../operators/default.md#default-operator) para producir el valor predeterminado de un tipo, como se muestra en el ejemplo siguiente:

```csharp
int a = default(int);
```

A partir de C# 7.1, se puede usar el [literal `default`](../operators/default.md#default-literal) para inicializar una variable con el valor predeterminado de su tipo:

```csharp
int a = default;
```

Para un tipo de valor, el constructor implícito sin parámetros también genera el valor predeterminado del tipo, como se muestra en el ejemplo siguiente:

```csharp-interactive
var n = new System.Numerics.Complex();
Console.WriteLine(n);  // output: (0, 0)
```

En tiempo de ejecución, si la instancia de <xref:System.Type?displayProperty=nameWithType> representa un tipo de valor, puede usar el método <xref:System.Activator.CreateInstance(System.Type)?displayProperty=nameWithType> para invocar el constructor sin parámetros y obtener el valor predeterminado del tipo.

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para más información, vea las secciones siguientes de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md):

- [Valores predeterminados](~/_csharplang/spec/variables.md#default-values)
- [Constructores predeterminados](~/_csharplang/spec/types.md#default-constructors)

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Constructores](../../programming-guide/classes-and-structs/constructors.md)
