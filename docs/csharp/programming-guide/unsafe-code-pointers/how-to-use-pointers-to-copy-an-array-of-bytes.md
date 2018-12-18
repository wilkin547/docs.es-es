---
title: 'Procedimiento Utilizar punteros para copiar una matriz de bytes: Guía de programación de C#'
ms.custom: seodec18
ms.date: 04/20/2018
helpviewer_keywords:
- byte arrays [C#]
- arrays [C#], byte
- pointers [C#], to copy bytes
ms.openlocfilehash: 49151c6d2a573a24e63f733a5279faeee40de1b7
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53241131"
---
# <a name="how-to-use-pointers-to-copy-an-array-of-bytes--c-programming-guide"></a><span data-ttu-id="7cbb6-102">Procedimiento Utilizar punteros para copiar una matriz de bytes (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="7cbb6-102">How to: Use Pointers to Copy an Array of Bytes  (C# Programming Guide)</span></span>

<span data-ttu-id="7cbb6-103">En el ejemplo siguiente se usan punteros para copiar bytes de una matriz a otra.</span><span class="sxs-lookup"><span data-stu-id="7cbb6-103">The following example uses pointers to copy bytes from one array to another.</span></span>

<span data-ttu-id="7cbb6-104">En este ejemplo se usa la palabra clave [unsafe](../../language-reference/keywords/unsafe.md), que permite el uso de punteros en el método `Copy`.</span><span class="sxs-lookup"><span data-stu-id="7cbb6-104">This example uses the [unsafe](../../language-reference/keywords/unsafe.md) keyword, which enables you to use pointers in the `Copy` method.</span></span> <span data-ttu-id="7cbb6-105">La instrucción [fixed](../../language-reference/keywords/fixed-statement.md) se usa para declarar punteros a las matrices de origen y destino.</span><span class="sxs-lookup"><span data-stu-id="7cbb6-105">The [fixed](../../language-reference/keywords/fixed-statement.md) statement is used to declare pointers to the source and destination arrays.</span></span> <span data-ttu-id="7cbb6-106">La instrucción `fixed` *ancla* la ubicación de las matrices de origen y destino en memoria, para que no puedan ser desplazadas por la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="7cbb6-106">The `fixed` statement *pins* the location of the source and destination arrays in memory so that they will not be moved by garbage collection.</span></span> <span data-ttu-id="7cbb6-107">Estos bloques de memoria para las matrices se desanclan cuando finaliza el bloque `fixed`.</span><span class="sxs-lookup"><span data-stu-id="7cbb6-107">The memory blocks for the arrays are unpinned when the `fixed` block is completed.</span></span> <span data-ttu-id="7cbb6-108">Dado que el método `Copy` de este ejemplo usa la palabra clave `unsafe`, se debe compilar con la opción del compilador [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="7cbb6-108">Because the `Copy` method in this example uses the `unsafe` keyword, it must be compiled with the [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md) compiler option.</span></span>

<span data-ttu-id="7cbb6-109">Este ejemplo accede a los elementos de ambas matrices con índices en lugar de con un segundo puntero no administrado.</span><span class="sxs-lookup"><span data-stu-id="7cbb6-109">This example accesses the elements of both arrays using indices rather than a second unmanaged pointer.</span></span> <span data-ttu-id="7cbb6-110">La declaración de los punteros `pSource` y `pTarget` ancla las matrices.</span><span class="sxs-lookup"><span data-stu-id="7cbb6-110">The declaration of the `pSource` and `pTarget` pointers pins the arrays.</span></span> <span data-ttu-id="7cbb6-111">Esta característica está disponible a partir de C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="7cbb6-111">This feature is available starting with C# 7.3.</span></span>

## <a name="example"></a><span data-ttu-id="7cbb6-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7cbb6-112">Example</span></span>

[!code-csharp[Struct with embedded inline array](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#8)]

## <a name="see-also"></a><span data-ttu-id="7cbb6-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="7cbb6-113">See Also</span></span>

- [<span data-ttu-id="7cbb6-114">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="7cbb6-114">C# Programming Guide</span></span>](../index.md)  
- [<span data-ttu-id="7cbb6-115">Código no seguro y punteros</span><span class="sxs-lookup"><span data-stu-id="7cbb6-115">Unsafe Code and Pointers</span></span>](index.md)  
- [<span data-ttu-id="7cbb6-116">-unsafe (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="7cbb6-116">-unsafe (C# Compiler Options)</span></span>](../../language-reference/compiler-options/unsafe-compiler-option.md)  
- [<span data-ttu-id="7cbb6-117">Recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="7cbb6-117">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)  
