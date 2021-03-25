---
description: unsafe (palabra clave) - Referencia de C#
title: unsafe (palabra clave) - Referencia de C#
ms.date: 07/20/2015
f1_keywords:
- unsafe_CSharpKeyword
- unsafe
helpviewer_keywords:
- unsafe keyword [C#]
ms.assetid: 7e818009-1c6e-4b9e-b769-3728a01586a0
ms.openlocfilehash: 5be895621966dd10b2b1b0f53ebf0f3c688f1ef0
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "103480658"
---
# <a name="unsafe-c-reference"></a><span data-ttu-id="eb23a-103">unsafe (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="eb23a-103">unsafe (C# Reference)</span></span>

<span data-ttu-id="eb23a-104">La palabra clave `unsafe` denota un contexto no seguro, que es necesario para realizar cualquier operación que implique punteros.</span><span class="sxs-lookup"><span data-stu-id="eb23a-104">The `unsafe` keyword denotes an unsafe context, which is required for any operation involving pointers.</span></span> <span data-ttu-id="eb23a-105">Para obtener más información, vea [Código no seguro y punteros (Guía de programación de C#)](../../programming-guide/unsafe-code-pointers/index.md).</span><span class="sxs-lookup"><span data-stu-id="eb23a-105">For more information, see [Unsafe Code and Pointers](../../programming-guide/unsafe-code-pointers/index.md).</span></span>

<span data-ttu-id="eb23a-106">Puede usar el codificador `unsafe` en la declaración de un tipo o miembro.</span><span class="sxs-lookup"><span data-stu-id="eb23a-106">You can use the `unsafe` modifier in the declaration of a type or a member.</span></span> <span data-ttu-id="eb23a-107">Por consiguiente, toda la extensión textual del tipo o miembro se considera un contexto no seguro.</span><span class="sxs-lookup"><span data-stu-id="eb23a-107">The entire textual extent of the type or member is therefore considered an unsafe context.</span></span> <span data-ttu-id="eb23a-108">Por ejemplo, el siguiente método se declara con el modificador `unsafe`:</span><span class="sxs-lookup"><span data-stu-id="eb23a-108">For example, the following is a method declared with the `unsafe` modifier:</span></span>

```csharp
unsafe static void FastCopy(byte[] src, byte[] dst, int count)
{
    // Unsafe context: can use pointers here.
}
```

<span data-ttu-id="eb23a-109">El ámbito del contexto no seguro se extiende desde la lista de parámetros hasta el final del método, por lo que también pueden usarse punteros en la lista de parámetros:</span><span class="sxs-lookup"><span data-stu-id="eb23a-109">The scope of the unsafe context extends from the parameter list to the end of the method, so pointers can also be used in the parameter list:</span></span>

```csharp
unsafe static void FastCopy ( byte* ps, byte* pd, int count ) {...}
```

<span data-ttu-id="eb23a-110">También puede usarse un bloque no seguro para habilitar el uso de código no seguro en el bloque.</span><span class="sxs-lookup"><span data-stu-id="eb23a-110">You can also use an unsafe block to enable the use of an unsafe code inside this block.</span></span> <span data-ttu-id="eb23a-111">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="eb23a-111">For example:</span></span>

```csharp
unsafe
{
    // Unsafe context: can use pointers here.
}
```

<span data-ttu-id="eb23a-112">Para compilar código no seguro, debe especificar la opción del compilador [**AllowUnsafeBlocks**](../compiler-options/language.md#allowunsafeblocks).</span><span class="sxs-lookup"><span data-stu-id="eb23a-112">To compile unsafe code, you must specify the [**AllowUnsafeBlocks**](../compiler-options/language.md#allowunsafeblocks) compiler option.</span></span> <span data-ttu-id="eb23a-113">Common Language Runtime no puede comprobar el código no seguro.</span><span class="sxs-lookup"><span data-stu-id="eb23a-113">Unsafe code is not verifiable by the common language runtime.</span></span>

## <a name="example"></a><span data-ttu-id="eb23a-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="eb23a-114">Example</span></span>

[!code-csharp[csrefKeywordsModifiers#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#22)]

## <a name="c-language-specification"></a><span data-ttu-id="eb23a-115">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="eb23a-115">C# language specification</span></span>

<span data-ttu-id="eb23a-116">Para más información, vea la sección sobre [código no seguro](~/_csharplang/spec/unsafe-code.md) de la [Especificación del lenguaje C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="eb23a-116">For more information, see [Unsafe code](~/_csharplang/spec/unsafe-code.md) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="eb23a-117">La especificación del lenguaje es la fuente definitiva de la sintaxis y el uso de C#.</span><span class="sxs-lookup"><span data-stu-id="eb23a-117">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="eb23a-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="eb23a-118">See also</span></span>

- [<span data-ttu-id="eb23a-119">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="eb23a-119">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="eb23a-120">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="eb23a-120">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="eb23a-121">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="eb23a-121">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="eb23a-122">fixed (instrucción)</span><span class="sxs-lookup"><span data-stu-id="eb23a-122">fixed Statement</span></span>](fixed-statement.md)
- [<span data-ttu-id="eb23a-123">Código no seguro y punteros</span><span class="sxs-lookup"><span data-stu-id="eb23a-123">Unsafe Code and Pointers</span></span>](../../programming-guide/unsafe-code-pointers/index.md)
- [<span data-ttu-id="eb23a-124">Búferes de tamaño fijo</span><span class="sxs-lookup"><span data-stu-id="eb23a-124">Fixed Size Buffers</span></span>](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md)
