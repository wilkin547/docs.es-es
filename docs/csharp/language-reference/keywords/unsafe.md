---
title: unsafe (palabra clave) - Referencia de C#
ms.date: 07/20/2015
f1_keywords:
- unsafe_CSharpKeyword
- unsafe
helpviewer_keywords:
- unsafe keyword [C#]
ms.assetid: 7e818009-1c6e-4b9e-b769-3728a01586a0
ms.openlocfilehash: ef98809eae0329c028dfb318c4a437aae4736db1
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712993"
---
# <a name="unsafe-c-reference"></a><span data-ttu-id="1790a-102">unsafe (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="1790a-102">unsafe (C# Reference)</span></span>

<span data-ttu-id="1790a-103">La palabra clave `unsafe` denota un contexto no seguro, que es necesario para realizar cualquier operación que implique punteros.</span><span class="sxs-lookup"><span data-stu-id="1790a-103">The `unsafe` keyword denotes an unsafe context, which is required for any operation involving pointers.</span></span> <span data-ttu-id="1790a-104">Para obtener más información, vea [Unsafe Code and Pointers](../../programming-guide/unsafe-code-pointers/index.md) (Código no seguro y punteros [Guía de programación de C#]).</span><span class="sxs-lookup"><span data-stu-id="1790a-104">For more information, see [Unsafe Code and Pointers](../../programming-guide/unsafe-code-pointers/index.md).</span></span>

<span data-ttu-id="1790a-105">Puede usar el codificador `unsafe` en la declaración de un tipo o miembro.</span><span class="sxs-lookup"><span data-stu-id="1790a-105">You can use the `unsafe` modifier in the declaration of a type or a member.</span></span> <span data-ttu-id="1790a-106">Por consiguiente, toda la extensión textual del tipo o miembro se considera un contexto no seguro.</span><span class="sxs-lookup"><span data-stu-id="1790a-106">The entire textual extent of the type or member is therefore considered an unsafe context.</span></span> <span data-ttu-id="1790a-107">Por ejemplo, el siguiente método se declara con el modificador `unsafe`:</span><span class="sxs-lookup"><span data-stu-id="1790a-107">For example, the following is a method declared with the `unsafe` modifier:</span></span>

```csharp
unsafe static void FastCopy(byte[] src, byte[] dst, int count)
{
    // Unsafe context: can use pointers here.
}
```

<span data-ttu-id="1790a-108">El ámbito del contexto no seguro se extiende desde la lista de parámetros hasta el final del método, por lo que también pueden usarse punteros en la lista de parámetros:</span><span class="sxs-lookup"><span data-stu-id="1790a-108">The scope of the unsafe context extends from the parameter list to the end of the method, so pointers can also be used in the parameter list:</span></span>

```csharp
unsafe static void FastCopy ( byte* ps, byte* pd, int count ) {...}
```

<span data-ttu-id="1790a-109">También puede usarse un bloque no seguro para habilitar el uso de código no seguro en el bloque.</span><span class="sxs-lookup"><span data-stu-id="1790a-109">You can also use an unsafe block to enable the use of an unsafe code inside this block.</span></span> <span data-ttu-id="1790a-110">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="1790a-110">For example:</span></span>

```csharp
unsafe
{
    // Unsafe context: can use pointers here.
}
```

<span data-ttu-id="1790a-111">Para compilar código no seguro, debe especificar la opción del compilador [`-unsafe`](../compiler-options/unsafe-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="1790a-111">To compile unsafe code, you must specify the [`-unsafe`](../compiler-options/unsafe-compiler-option.md) compiler option.</span></span> <span data-ttu-id="1790a-112">Common Language Runtime no puede comprobar el código no seguro.</span><span class="sxs-lookup"><span data-stu-id="1790a-112">Unsafe code is not verifiable by the common language runtime.</span></span>

## <a name="example"></a><span data-ttu-id="1790a-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1790a-113">Example</span></span>

[!code-csharp[csrefKeywordsModifiers#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#22)]

## <a name="c-language-specification"></a><span data-ttu-id="1790a-114">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="1790a-114">C# language specification</span></span>

<span data-ttu-id="1790a-115">Para más información, vea la sección sobre [código no seguro](~/_csharplang/spec/unsafe-code.md) de la [Especificación del lenguaje C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="1790a-115">For more information, see [Unsafe code](~/_csharplang/spec/unsafe-code.md) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="1790a-116">La especificación del lenguaje es la fuente definitiva de la sintaxis y el uso de C#.</span><span class="sxs-lookup"><span data-stu-id="1790a-116">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="1790a-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="1790a-117">See also</span></span>

- [<span data-ttu-id="1790a-118">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="1790a-118">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="1790a-119">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="1790a-119">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="1790a-120">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="1790a-120">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="1790a-121">fixed (instrucción)</span><span class="sxs-lookup"><span data-stu-id="1790a-121">fixed Statement</span></span>](fixed-statement.md)
- [<span data-ttu-id="1790a-122">Código no seguro y punteros</span><span class="sxs-lookup"><span data-stu-id="1790a-122">Unsafe Code and Pointers</span></span>](../../programming-guide/unsafe-code-pointers/index.md)
- [<span data-ttu-id="1790a-123">Búferes de tamaño fijo</span><span class="sxs-lookup"><span data-stu-id="1790a-123">Fixed Size Buffers</span></span>](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md)
