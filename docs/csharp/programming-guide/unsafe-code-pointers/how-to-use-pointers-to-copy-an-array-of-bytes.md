---
title: 'Procedimiento Utilizar punteros para copiar una matriz de bytes: Guía de programación de C#'
description: Aprenda a usar punteros para copiar una matriz de bytes Vea un ejemplo de código y examine los recursos adicionales disponibles.
ms.date: 04/20/2018
helpviewer_keywords:
- byte arrays [C#]
- arrays [C#], byte
- pointers [C#], to copy bytes
ms.openlocfilehash: f0122d29729ac8ad634f39f0643902e9bb78a8a5
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "103478602"
---
# <a name="how-to-use-pointers-to-copy-an-array-of-bytes-c-programming-guide"></a><span data-ttu-id="3f28e-104">Procedimiento Utilizar punteros para copiar una matriz de bytes (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="3f28e-104">How to use pointers to copy an array of bytes (C# Programming Guide)</span></span>

<span data-ttu-id="3f28e-105">En el ejemplo siguiente se usan punteros para copiar bytes de una matriz a otra.</span><span class="sxs-lookup"><span data-stu-id="3f28e-105">The following example uses pointers to copy bytes from one array to another.</span></span>

<span data-ttu-id="3f28e-106">En este ejemplo se usa la palabra clave [unsafe](../../language-reference/keywords/unsafe.md), que permite el uso de punteros en el método `Copy`.</span><span class="sxs-lookup"><span data-stu-id="3f28e-106">This example uses the [unsafe](../../language-reference/keywords/unsafe.md) keyword, which enables you to use pointers in the `Copy` method.</span></span> <span data-ttu-id="3f28e-107">La instrucción [fixed](../../language-reference/keywords/fixed-statement.md) se usa para declarar punteros a las matrices de origen y destino.</span><span class="sxs-lookup"><span data-stu-id="3f28e-107">The [fixed](../../language-reference/keywords/fixed-statement.md) statement is used to declare pointers to the source and destination arrays.</span></span> <span data-ttu-id="3f28e-108">La instrucción `fixed`*ancla* la ubicación de las matrices de origen y destino en memoria, para que no puedan ser desplazadas por la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="3f28e-108">The `fixed` statement *pins* the location of the source and destination arrays in memory so that they will not be moved by garbage collection.</span></span> <span data-ttu-id="3f28e-109">Estos bloques de memoria para las matrices se desanclan cuando finaliza el bloque `fixed`.</span><span class="sxs-lookup"><span data-stu-id="3f28e-109">The memory blocks for the arrays are unpinned when the `fixed` block is completed.</span></span> <span data-ttu-id="3f28e-110">Como el método `Copy` de este ejemplo usa la palabra clave `unsafe`, se debe compilar con la opción del compilador [**AllowUnsafeBlocks**](../../language-reference/compiler-options/language.md#allowunsafeblocks).</span><span class="sxs-lookup"><span data-stu-id="3f28e-110">Because the `Copy` method in this example uses the `unsafe` keyword, it must be compiled with the [**AllowUnsafeBlocks**](../../language-reference/compiler-options/language.md#allowunsafeblocks) compiler option.</span></span>

<span data-ttu-id="3f28e-111">Este ejemplo accede a los elementos de ambas matrices con índices en lugar de con un segundo puntero no administrado.</span><span class="sxs-lookup"><span data-stu-id="3f28e-111">This example accesses the elements of both arrays using indices rather than a second unmanaged pointer.</span></span> <span data-ttu-id="3f28e-112">La declaración de los punteros `pSource` y `pTarget` ancla las matrices.</span><span class="sxs-lookup"><span data-stu-id="3f28e-112">The declaration of the `pSource` and `pTarget` pointers pins the arrays.</span></span> <span data-ttu-id="3f28e-113">Esta característica está disponible a partir de C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="3f28e-113">This feature is available starting with C# 7.3.</span></span>

## <a name="example"></a><span data-ttu-id="3f28e-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3f28e-114">Example</span></span>

[!code-csharp[Struct with embedded inline array](snippets/FixedKeywordExamples.cs#8)]

## <a name="see-also"></a><span data-ttu-id="3f28e-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="3f28e-115">See also</span></span>

- [<span data-ttu-id="3f28e-116">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="3f28e-116">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="3f28e-117">Código no seguro y punteros</span><span class="sxs-lookup"><span data-stu-id="3f28e-117">Unsafe Code and Pointers</span></span>](index.md)
- [<span data-ttu-id="3f28e-118">**AllowUnsafeBlocks** (opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="3f28e-118">**AllowUnsafeBlocks** (C# Compiler Options)</span></span>](../../language-reference/compiler-options/language.md#allowunsafeblocks)
- [<span data-ttu-id="3f28e-119">Recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="3f28e-119">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
