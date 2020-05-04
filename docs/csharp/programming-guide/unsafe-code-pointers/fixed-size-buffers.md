---
title: 'Búferes de tamaño fijo: Guía de programación de C#'
ms.date: 04/23/2020
helpviewer_keywords:
- fixed size buffers [C#]
- unsafe buffers [C#]
- unsafe code [C#], fixed size buffers
ms.openlocfilehash: 5920dd125ded34969d60feb299568b56402056ab
ms.sourcegitcommit: 839777281a281684a7e2906dccb3acd7f6a32023
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/24/2020
ms.locfileid: "82140551"
---
# <a name="fixed-size-buffers-c-programming-guide"></a>Búferes de tamaño fijo (Guía de programación de C#)

En C#, puede usar la instrucción [fixed](../../language-reference/keywords/fixed-statement.md) para crear un búfer con una matriz de tamaño fijo en una estructura de datos. Los búferes de tamaño fijo resultan útiles al escribir métodos que interoperan con orígenes de datos de otros lenguajes o plataformas. La matriz fija puede tomar cualquiera de los atributos o modificadores permitidos para los miembros de structs normales. La única restricción es que el tipo de matriz debe ser `bool`, `byte`, `char`, `short`, `int`, `long`, `sbyte`, `ushort`, `uint`, `ulong`, `float` o `double`.

```csharp
private fixed char name[30];
```

## <a name="remarks"></a>Comentarios

En el código seguro, un struct de C# que contiene una matriz no contiene los elementos de matriz. En su lugar, el struct contiene una referencia a los elementos. Puede insertar una matriz de tamaño fijo en un [struct](../../language-reference/builtin-types/struct.md) cuando se usa en un bloque de código [no seguro](../../language-reference/keywords/unsafe.md).

El tamaño del siguiente `struct` no depende del número de elementos en la matriz, ya que `pathName` es una referencia:

[!code-csharp[Struct with embedded array](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#6)]

Un `struct` puede contener una matriz insertada en el código no seguro. En el siguiente ejemplo, la matriz `fixedBuffer` tiene un tamaño fijo. Se usa una instrucción `fixed` para establecer un puntero al primer elemento. Se accede a los elementos de la matriz mediante este puntero. La instrucción `fixed` ancla el campo de instancia `fixedBuffer` a una ubicación concreta en la memoria.

[!code-csharp[Struct with embedded inline array](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#7)]

El tamaño de la matriz `char` de 128 elementos es 256 bytes. Los búferes [char](../../language-reference/builtin-types/char.md) de tamaño fijo siempre admiten dos bytes por carácter, independientemente de la codificación. Esto es verdadero, incluso cuando se calculan las referencias de los búferes de caracteres a los métodos API o structs con `CharSet = CharSet.Auto` o `CharSet = CharSet.Ansi`. Para obtener más información, vea <xref:System.Runtime.InteropServices.CharSet>.

En el ejemplo anterior se muestra cómo acceder a campos `fixed` sin anclar, lo que está disponible a partir de C# 7.3.

Otra matriz de tamaño fijo común es la matriz [bool](../../language-reference/builtin-types/bool.md). Los elementos de una matriz `bool` siempre tienen un byte de tamaño. Las matrices `bool` no son adecuadas para crear matrices de bits o búferes.

Los búferes de tamaño fijo se compilan con el atributo <xref:System.Runtime.CompilerServices.UnsafeValueTypeAttribute?displayProperty=nameWithType>, que indica a Common Language Runtime (CLR) que un tipo contiene una matriz no administrada que puede provocar un desbordamiento. Esto es similar a la memoria creada mediante [stackalloc](../../language-reference/operators/stackalloc.md), que habilita automáticamente las características de detección de saturación del búfer en CLR. En el ejemplo anterior se muestra cómo podría existir un búfer de tamaño fijo en un `unsafe struct`.

```csharp
internal unsafe struct Buffer
{
    public fixed char fixedBuffer[128];
}
```

El código de C# generado por el compilador para `Buffer` se atribuye de la siguiente forma:

```csharp
internal struct Buffer
{
    [StructLayout(LayoutKind.Sequential, Size = 256)]
    [CompilerGenerated]
    [UnsafeValueType]
    public struct <fixedBuffer>e__FixedBuffer
    {
        public char FixedElementField;
    }

    [FixedBuffer(typeof(char), 128)]
    public <fixedBuffer>e__FixedBuffer fixedBuffer;
}
```

Los búferes de tamaño fijo son diferentes de las matrices normales en los siguientes puntos:

- Solo se pueden usar en un contexto [no seguro](../../language-reference/keywords/unsafe.md).
- Solo pueden ser campos de instancia de structs.
- Siempre son vectores o matrices unidimensionales.
- La declaración debe incluir la longitud, como `fixed char id[8]`. No se puede usar `fixed char id[]`.

## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Código no seguro y punteros](index.md)
- [fixed (instrucción)](../../language-reference/keywords/fixed-statement.md)
- [Interoperabilidad](../interop/index.md)
