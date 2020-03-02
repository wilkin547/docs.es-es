---
title: Tipos no administrados - Referencia de C#
ms.date: 09/06/2019
helpviewer_keywords:
- unmanaged type [C#]
ms.openlocfilehash: 042cf382879cc4010a388fb75f41099b4342c9d9
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2020
ms.locfileid: "77626950"
---
# <a name="unmanaged-types-c-reference"></a>Tipos no administrados (referencia de C#)

Un tipo es un **tipo no administrado** si es cualquiera de los siguientes tipos:

- `sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float`, `double`, `decimal` o `bool`
- Cualquier tipo [enum](enum.md).
- Cualquier tipo [pointer](../../programming-guide/unsafe-code-pointers/pointer-types.md).
- Cualquier tipo de [struct](struct.md) definido por el usuario que solo contenga campos de tipos no administrados, en C# 7.3 y versiones anteriores, no es un tipo construido (un tipo que incluya al menos un argumento de tipo)

A partir de C# 7.3, puede usar [`unmanaged`constraint](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint) para especificar que un parámetro de tipo es un tipo no administrado que no acepta valores NULL y que no es de puntero.

A partir C# 8.0, un tipo de struct *construido* que solo contenga campos de tipos no administrados también es no administrado, como se muestra en el ejemplo siguiente:

[!code-csharp[unmanaged constructed types](~/samples/csharp/language-reference/builtin-types/UnmanagedTypes.cs#ProgramExample)]

Un struct genérico puede ser el origen de los tipos no administrados y de los tipos construidos no administrados. En el ejemplo anterior se define un struct `Coords<T>` genérico y se presentan los ejemplos de tipos construidos no administrados. El ejemplo de un tipo no administrado es `Coords<object>`. No está administrado porque tiene los campos del tipo `object`, que es no administrado. Si desea que *todos* los tipos construidos sean tipos no administrados, use la restricción `unmanaged` en la definición de un struct genérico:

[!code-csharp[unmanaged constraint in type definition](~/samples/csharp/language-reference/builtin-types/UnmanagedTypes.cs#AlwaysUnmanaged)]

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para obtener más información, vea la sección [Tipos de puntero](~/_csharplang/spec/unsafe-code.md#pointer-types) de [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Tipos de puntero](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [Tipos relacionados con el intervalo y la memoria](../../../standard/memory-and-spans/index.md)
- [sizeof (operador)](../operators/sizeof.md)
- [stackalloc (operador)](../operators/stackalloc.md)
