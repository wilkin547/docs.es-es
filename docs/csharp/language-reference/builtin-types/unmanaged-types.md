---
title: Tipos no administrados - Referencia de C#
ms.date: 07/23/2019
helpviewer_keywords:
- unmanaged type [C#]
ms.openlocfilehash: 2b675be5dbc61006725549f4b69284326650401d
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/26/2019
ms.locfileid: "68512075"
---
# <a name="unmanaged-types-c-reference"></a>Tipos no administrados (referencia de C#)

Un **tipo no administrado** es todo aquel que no es un tipo de referencia ni un tipo construido (un tipo que incluye al menos un argumento de tipo) y que no contiene ningún campo de tipo de referencia ni de tipo construido en ningún nivel del anidamiento. En otras palabras, un tipo no administrado es uno de los siguientes:

- `sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float`, `double`, `decimal` o `bool`
- Cualquier tipo [enum](../keywords/enum.md).
- Cualquier tipo [pointer](../../programming-guide/unsafe-code-pointers/pointer-types.md).
- Cualquier tipo [struct](../keywords/struct.md) definido por el usuario que no sea un tipo construido y que contenga campos solo de tipos no administrados.

A partir de C# 7.3, puede usar [`unmanaged`constraint](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint) para especificar que un parámetro de tipo es un tipo no administrado que no es de puntero.

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para obtener más información, vea la sección [Tipos de puntero](~/_csharplang/spec/unsafe-code.md#pointer-types) de [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Tipos de puntero](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [Tipos relacionados con el intervalo y la memoria](../../../standard/memory-and-spans/index.md)
- [sizeof (operador)](../operators/sizeof.md)
- [stackalloc (operador)](../operators/stackalloc.md)
