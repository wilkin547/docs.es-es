---
title: 'void: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- void_CSharpKeyword
- void
helpviewer_keywords:
- void keyword [C#]
ms.assetid: 0d2d8a95-fe20-4fbd-bf5d-c1e54bce71d4
ms.openlocfilehash: 0624b547ee2586334ac35d366ae3c8dfd14963ee
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742762"
---
# <a name="void-c-reference"></a><span data-ttu-id="5797c-102">void (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="5797c-102">void (C# Reference)</span></span>

<span data-ttu-id="5797c-103">Cuando se usa como tipo de valor devuelto para un método, `void` especifica que el método no devuelve un valor.</span><span class="sxs-lookup"><span data-stu-id="5797c-103">When used as the return type for a method, `void` specifies that the method doesn't return a value.</span></span>

<span data-ttu-id="5797c-104">`void` no se permite en la lista de parámetros de un método.</span><span class="sxs-lookup"><span data-stu-id="5797c-104">`void` isn't allowed in the parameter list of a method.</span></span> <span data-ttu-id="5797c-105">Un método que no usa parámetros y que no devuelve ningún valor se declara del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="5797c-105">A method that takes no parameters and returns no value is declared as follows:</span></span>

```csharp
public void SampleMethod()
{
    // Body of the method.
}
```

<span data-ttu-id="5797c-106">`void` también se usa en un contexto no seguro para declarar un puntero a un tipo desconocido.</span><span class="sxs-lookup"><span data-stu-id="5797c-106">`void` is also used in an unsafe context to declare a pointer to an unknown type.</span></span> <span data-ttu-id="5797c-107">Para obtener más información, vea [Tipos de puntero](../../programming-guide/unsafe-code-pointers/pointer-types.md).</span><span class="sxs-lookup"><span data-stu-id="5797c-107">For more information, see [Pointer types](../../programming-guide/unsafe-code-pointers/pointer-types.md).</span></span>

<span data-ttu-id="5797c-108">`void` es un alias del tipo <xref:System.Void?displayProperty=nameWithType> de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5797c-108">`void` is an alias for the .NET Framework <xref:System.Void?displayProperty=nameWithType> type.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="5797c-109">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="5797c-109">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="5797c-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="5797c-110">See also</span></span>

- [<span data-ttu-id="5797c-111">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="5797c-111">C# reference</span></span>](../index.md)
- [<span data-ttu-id="5797c-112">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="5797c-112">C# keywords</span></span>](index.md)
- [<span data-ttu-id="5797c-113">Tipos de referencia</span><span class="sxs-lookup"><span data-stu-id="5797c-113">Reference types</span></span>](reference-types.md)
- [<span data-ttu-id="5797c-114">Tipos de valor</span><span class="sxs-lookup"><span data-stu-id="5797c-114">Value types</span></span>](../builtin-types/value-types.md)
- [<span data-ttu-id="5797c-115">Métodos</span><span class="sxs-lookup"><span data-stu-id="5797c-115">Methods</span></span>](../../programming-guide/classes-and-structs/methods.md)
- [<span data-ttu-id="5797c-116">Código no seguro y punteros</span><span class="sxs-lookup"><span data-stu-id="5797c-116">Unsafe code and pointers</span></span>](../../programming-guide/unsafe-code-pointers/index.md)
