---
title: 'Operador sizeof: Referencia de C#'
ms.date: 07/25/2019
f1_keywords:
- sizeof_CSharpKeyword
- sizeof
helpviewer_keywords:
- sizeof keyword [C#]
ms.assetid: c548592c-677c-4f40-a4ce-e613f7529141
ms.openlocfilehash: a9e80ecb3288479a2ca81b43c9d088809ed5f2f0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "78847292"
---
# <a name="sizeof-operator-c-reference"></a>Operador sizeof (referencia de C#)

El operador `sizeof` devuelve el número de bytes ocupados por una variable de un tipo determinado. El argumento del operador `sizeof` debe ser el nombre de un [tipo administrado](../builtin-types/unmanaged-types.md) o un parámetro de tipo que está [restringido](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint) para ser un tipo no administrado.

El operador `sizeof` requiere un contexto de [unsafe](../keywords/unsafe.md). Sin embargo, las expresiones presentadas en la tabla siguiente se evalúan en tiempo de compilación según los valores de constantes correspondientes y no necesitan un contexto de unsafe:

|Expresión|Valor constante|
|---------|---------------|
|`sizeof(sbyte)`|1|
|`sizeof(byte)`|1|
|`sizeof(short)`|2|
|`sizeof(ushort)`|2|
|`sizeof(int)`|4|
|`sizeof(uint)`|4|
|`sizeof(long)`|8|
|`sizeof(ulong)`|8|
|`sizeof(char)`|2|
|`sizeof(float)`|4|
|`sizeof(double)`|8|
|`sizeof(decimal)`|16|
|`sizeof(bool)`|1|

Tampoco es necesario usar un contexto de unsafe cuando el operando del operador `sizeof` es el nombre de un tipo [enum](../builtin-types/enum.md).

En el siguiente ejemplo se muestra el uso del operador `sizeof`:

[!code-csharp[sizeof examples](snippets/SizeOfOperator.cs)]

El operador `sizeof` devuelve un número de bytes que asignará Common Language Runtime en la memoria administrada. Para los tipos [struct](../builtin-types/struct.md), el valor incluye el relleno, tal y como se muestra en el ejemplo anterior. El resultado del operador `sizeof` puede ser distinto del resultado del método <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType>, que devuelve el tamaño de un tipo en la memoria *no administrada*.

## <a name="c-language-specification"></a>especificación del lenguaje C#

Para obtener más información, vea la sección [Operador sizeof](~/_csharplang/spec/unsafe-code.md#the-sizeof-operator) de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Operadores de C#](index.md)
- [Operadores relacionados con el puntero](pointer-related-operators.md)
- [Tipos de puntero](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [Tipos relacionados con el intervalo y la memoria](../../../standard/memory-and-spans/index.md)
- [Elementos genéricos en .NET](../../../standard/generics/index.md)
