---
title: void (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- void_CSharpKeyword
- void
helpviewer_keywords:
- void keyword [C#]
ms.assetid: 0d2d8a95-fe20-4fbd-bf5d-c1e54bce71d4
ms.openlocfilehash: e66efc287fc3ed0fcc15963a827fccb788c38753
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33267293"
---
# <a name="void-c-reference"></a><span data-ttu-id="5f853-102">void (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="5f853-102">void (C# Reference)</span></span>
<span data-ttu-id="5f853-103">Cuando se usa como tipo de valor devuelto para un método, `void` especifica que el método no devuelve un valor.</span><span class="sxs-lookup"><span data-stu-id="5f853-103">When used as the return type for a method, `void` specifies that the method doesn't return a value.</span></span>

<span data-ttu-id="5f853-104">`void` no se permite en la lista de parámetros de un método.</span><span class="sxs-lookup"><span data-stu-id="5f853-104">`void` isn't allowed in the parameter list of a method.</span></span> <span data-ttu-id="5f853-105">Un método que no usa parámetros y que no devuelve ningún valor se declara del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="5f853-105">A method that takes no parameters and returns no value is declared as follows:</span></span>

```csharp
public void SampleMethod()
{
    // Body of the method.
}
```

<span data-ttu-id="5f853-106">`void` también se usa en un contexto no seguro para declarar un puntero a un tipo desconocido.</span><span class="sxs-lookup"><span data-stu-id="5f853-106">`void` is also used in an unsafe context to declare a pointer to an unknown type.</span></span> <span data-ttu-id="5f853-107">Para obtener más información, vea [Tipos de puntero](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md).</span><span class="sxs-lookup"><span data-stu-id="5f853-107">For more information, see [Pointer types](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md).</span></span>

<span data-ttu-id="5f853-108">`void` es un alias del tipo <xref:System.Void?displayProperty=nameWithType> de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5f853-108">`void` is an alias for the .NET Framework <xref:System.Void?displayProperty=nameWithType> type.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="5f853-109">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="5f853-109">C# Language Specification</span></span>
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="5f853-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="5f853-110">See also</span></span>
 [<span data-ttu-id="5f853-111">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="5f853-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="5f853-112">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="5f853-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="5f853-113">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="5f853-113">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="5f853-114">Tipos de referencia</span><span class="sxs-lookup"><span data-stu-id="5f853-114">Reference Types</span></span>](../../../csharp/language-reference/keywords/reference-types.md)  
 [<span data-ttu-id="5f853-115">Tipos de valor</span><span class="sxs-lookup"><span data-stu-id="5f853-115">Value Types</span></span>](../../../csharp/language-reference/keywords/value-types.md)  
 [<span data-ttu-id="5f853-116">Métodos</span><span class="sxs-lookup"><span data-stu-id="5f853-116">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)  
 [<span data-ttu-id="5f853-117">Código no seguro y punteros</span><span class="sxs-lookup"><span data-stu-id="5f853-117">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)
