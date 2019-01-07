---
title: 'void: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- void_CSharpKeyword
- void
helpviewer_keywords:
- void keyword [C#]
ms.assetid: 0d2d8a95-fe20-4fbd-bf5d-c1e54bce71d4
ms.openlocfilehash: ce52e4d19335db0e21637b87bbd1589c86c06ae1
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2018
ms.locfileid: "53613133"
---
# <a name="void-c-reference"></a>void (Referencia de C#)

Cuando se usa como tipo de valor devuelto para un método, `void` especifica que el método no devuelve un valor.

`void` no se permite en la lista de parámetros de un método. Un método que no usa parámetros y que no devuelve ningún valor se declara del siguiente modo:

```csharp
public void SampleMethod()
{
    // Body of the method.
}
```

`void` también se usa en un contexto no seguro para declarar un puntero a un tipo desconocido. Para obtener más información, vea [Tipos de puntero](../../programming-guide/unsafe-code-pointers/pointer-types.md).

`void` es un alias del tipo <xref:System.Void?displayProperty=nameWithType> de .NET Framework.

## <a name="c-language-specification"></a>Especificación del lenguaje C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Palabras clave de C#](index.md)
- [Tipos de referencia](reference-types.md)
- [Tipos de valor](value-types.md)
- [Métodos](../../programming-guide/classes-and-structs/methods.md)
- [Código no seguro y punteros](../../programming-guide/unsafe-code-pointers/index.md)