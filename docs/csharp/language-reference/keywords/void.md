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
# <a name="void-c-reference"></a><span data-ttu-id="3989e-102">void (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="3989e-102">void (C# Reference)</span></span>

<span data-ttu-id="3989e-103">Cuando se usa como tipo de valor devuelto para un método, `void` especifica que el método no devuelve un valor.</span><span class="sxs-lookup"><span data-stu-id="3989e-103">When used as the return type for a method, `void` specifies that the method doesn't return a value.</span></span>

<span data-ttu-id="3989e-104">`void` no se permite en la lista de parámetros de un método.</span><span class="sxs-lookup"><span data-stu-id="3989e-104">`void` isn't allowed in the parameter list of a method.</span></span> <span data-ttu-id="3989e-105">Un método que no usa parámetros y que no devuelve ningún valor se declara del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="3989e-105">A method that takes no parameters and returns no value is declared as follows:</span></span>

```csharp
public void SampleMethod()
{
    // Body of the method.
}
```

<span data-ttu-id="3989e-106">`void` también se usa en un contexto no seguro para declarar un puntero a un tipo desconocido.</span><span class="sxs-lookup"><span data-stu-id="3989e-106">`void` is also used in an unsafe context to declare a pointer to an unknown type.</span></span> <span data-ttu-id="3989e-107">Para obtener más información, vea [Tipos de puntero](../../programming-guide/unsafe-code-pointers/pointer-types.md).</span><span class="sxs-lookup"><span data-stu-id="3989e-107">For more information, see [Pointer types](../../programming-guide/unsafe-code-pointers/pointer-types.md).</span></span>

<span data-ttu-id="3989e-108">`void` es un alias del tipo <xref:System.Void?displayProperty=nameWithType> de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3989e-108">`void` is an alias for the .NET Framework <xref:System.Void?displayProperty=nameWithType> type.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="3989e-109">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="3989e-109">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="3989e-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="3989e-110">See also</span></span>

- [<span data-ttu-id="3989e-111">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="3989e-111">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="3989e-112">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="3989e-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="3989e-113">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="3989e-113">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="3989e-114">Tipos de referencia</span><span class="sxs-lookup"><span data-stu-id="3989e-114">Reference Types</span></span>](reference-types.md)
- [<span data-ttu-id="3989e-115">Tipos de valor</span><span class="sxs-lookup"><span data-stu-id="3989e-115">Value Types</span></span>](value-types.md)
- [<span data-ttu-id="3989e-116">Métodos</span><span class="sxs-lookup"><span data-stu-id="3989e-116">Methods</span></span>](../../programming-guide/classes-and-structs/methods.md)
- [<span data-ttu-id="3989e-117">Código no seguro y punteros</span><span class="sxs-lookup"><span data-stu-id="3989e-117">Unsafe Code and Pointers</span></span>](../../programming-guide/unsafe-code-pointers/index.md)