---
title: Memoria e intervalos
ms.date: 10/03/2018
helpviewer_keywords:
- Memory<T>
- Span<T>
- buffers"
- pipeline processing
ms.openlocfilehash: 4b0464cc81cf0908a907f8305ea4e35b716c18fb
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830667"
---
# <a name="memory--and-span-related-types"></a><span data-ttu-id="a8b2b-102">Tipos relacionados con el intervalo y la memoria</span><span class="sxs-lookup"><span data-stu-id="a8b2b-102">Memory- and span-related types</span></span>

<span data-ttu-id="a8b2b-103">A partir de .NET Core 2.1, .NET incluye una serie de tipos interrelacionados que representan una región contigua de memoria arbitraria fuertemente tipada.</span><span class="sxs-lookup"><span data-stu-id="a8b2b-103">Starting with .NET Core 2.1, .NET includes a number of interrelated types that represent a contiguous, strongly typed region of arbitrary memory.</span></span> <span data-ttu-id="a8b2b-104">Se incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="a8b2b-104">These include:</span></span>

- <span data-ttu-id="a8b2b-105"><xref:System.Span%601?displayProperty=nameWithType>, un tipo que se usa para acceder a una región de memoria contigua.</span><span class="sxs-lookup"><span data-stu-id="a8b2b-105"><xref:System.Span%601?displayProperty=nameWithType>, a type that is used to access a contiguous region of memory.</span></span> <span data-ttu-id="a8b2b-106">Se puede respaldar una instancia de <xref:System.Span%601> mediante cualquier matriz de tipo `T`, un elemento <xref:System.String>, a búfer asignado con [stackalloc](../../csharp/language-reference/operators/stackalloc.md) o un puntero a memoria sin administrar.</span><span class="sxs-lookup"><span data-stu-id="a8b2b-106">A <xref:System.Span%601> instance can be backed by an array of type `T`, a <xref:System.String>, a buffer allocated with [stackalloc](../../csharp/language-reference/operators/stackalloc.md), or a pointer to unmanaged memory.</span></span> <span data-ttu-id="a8b2b-107">Como debe asignarse en la pila, tiene una serie de restricciones.</span><span class="sxs-lookup"><span data-stu-id="a8b2b-107">Because it has to be allocated on the stack, it has a number of restrictions.</span></span> <span data-ttu-id="a8b2b-108">Por ejemplo, un campo de una clase no puede ser de tipo <xref:System.Span%601>, ni se puede usar un intervalo en operaciones asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="a8b2b-108">For example, a field in a class cannot be of type <xref:System.Span%601>, nor can span be used in asynchronous operations.</span></span>

- <span data-ttu-id="a8b2b-109"><xref:System.ReadOnlySpan%601?displayProperty=nameWithType>, una versión inmutable de la estructura <xref:System.Span%601>.</span><span class="sxs-lookup"><span data-stu-id="a8b2b-109"><xref:System.ReadOnlySpan%601?displayProperty=nameWithType>, an immutable version of the <xref:System.Span%601> structure.</span></span>

- <span data-ttu-id="a8b2b-110"><xref:System.Memory%601?displayProperty=nameWithType>, una región contigua de memoria que se asigna en el montón administrado en lugar de en la pila.</span><span class="sxs-lookup"><span data-stu-id="a8b2b-110"><xref:System.Memory%601?displayProperty=nameWithType>, a contiguous region of memory that is allocated on the managed heap rather than the stack.</span></span> <span data-ttu-id="a8b2b-111">Se puede respaldar una instancia de <xref:System.Memory%601> mediante cualquier matriz de tipo `T` o un elemento <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="a8b2b-111">A <xref:System.Memory%601> instance can be backed by an array of type `T` or a <xref:System.String>.</span></span> <span data-ttu-id="a8b2b-112">Dado que puede almacenarse en el montón administrado, <xref:System.Memory%601> no tiene ninguna de las limitaciones de <xref:System.Span%601>.</span><span class="sxs-lookup"><span data-stu-id="a8b2b-112">Because it can be stored on the managed heap, <xref:System.Memory%601> has none of the limitations of <xref:System.Span%601>.</span></span>

- <span data-ttu-id="a8b2b-113"><xref:System.ReadOnlyMemory%601?displayProperty=nameWithType>, una versión inmutable de la estructura <xref:System.Memory%601>.</span><span class="sxs-lookup"><span data-stu-id="a8b2b-113"><xref:System.ReadOnlyMemory%601?displayProperty=nameWithType>, an immutable version of the <xref:System.Memory%601> structure.</span></span>

- <span data-ttu-id="a8b2b-114"><xref:System.Buffers.MemoryPool%601?displayProperty=nameWithType>, que asigna bloques de memoria fuertemente tipados de un grupo de memoria a un propietario.</span><span class="sxs-lookup"><span data-stu-id="a8b2b-114"><xref:System.Buffers.MemoryPool%601?displayProperty=nameWithType>, which allocates strongly typed blocks of memory from a memory pool to an owner.</span></span> <span data-ttu-id="a8b2b-115">Se pueden alquilar instancias de <xref:System.Buffers.IMemoryOwner%601> del grupo mediante la llamada a <xref:System.Buffers.MemoryPool%601.Rent%2A?displayProperty=nameWithType> y liberarse de nuevo en el grupo mediante la llamada a <xref:System.Buffers.MemoryPool%601.Dispose?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a8b2b-115"><xref:System.Buffers.IMemoryOwner%601> instances can be rented from the pool by calling <xref:System.Buffers.MemoryPool%601.Rent%2A?displayProperty=nameWithType> and released back to the pool by calling <xref:System.Buffers.MemoryPool%601.Dispose?displayProperty=nameWithType>.</span></span>

- <span data-ttu-id="a8b2b-116"><xref:System.Buffers.IMemoryOwner%601?displayProperty=nameWithType>, que representa el propietario de un bloque de memoria y controla su administración de duración.</span><span class="sxs-lookup"><span data-stu-id="a8b2b-116"><xref:System.Buffers.IMemoryOwner%601?displayProperty=nameWithType>, which represents the owner of a block of memory and controls its lifetime management.</span></span>

- <span data-ttu-id="a8b2b-117"><xref:System.Buffers.MemoryManager%601>, una clase base abstracta que puede usarse para reemplazar la implementación de <xref:System.Memory%601> para que <xref:System.Memory%601> pueda respaldarse mediante tipos adicionales, como controladores seguros.</span><span class="sxs-lookup"><span data-stu-id="a8b2b-117"><xref:System.Buffers.MemoryManager%601>, an abstract base class that can be used to replace the implementation of <xref:System.Memory%601> so that <xref:System.Memory%601> can be backed by additional types, such as safe handles.</span></span> <span data-ttu-id="a8b2b-118"><xref:System.Buffers.MemoryManager%601> está pensado para escenarios avanzados.</span><span class="sxs-lookup"><span data-stu-id="a8b2b-118"><xref:System.Buffers.MemoryManager%601> is intended for advanced scenarios.</span></span>

- <span data-ttu-id="a8b2b-119"><xref:System.ArraySegment%601>, un contenedor para un determinado número de elementos de matriz, que comienza en un índice determinado.</span><span class="sxs-lookup"><span data-stu-id="a8b2b-119"><xref:System.ArraySegment%601>, a wrapper for a particular number of array elements starting at a particular index.</span></span>

- <span data-ttu-id="a8b2b-120"><xref:System.MemoryExtensions?displayProperty=nameWithType>, una colección de métodos de extensión para convertir cadenas, matrices y segmentos de matriz en bloques de <xref:System.Memory%601>.</span><span class="sxs-lookup"><span data-stu-id="a8b2b-120"><xref:System.MemoryExtensions?displayProperty=nameWithType>, a collection of extension methods for converting strings, arrays, and array segments to <xref:System.Memory%601> blocks.</span></span>

> [!NOTE]
> <span data-ttu-id="a8b2b-121">En plataformas anteriores, <xref:System.Span%601> y <xref:System.Memory%601> están disponibles en el [paquete NuGet System.Memory](https://www.nuget.org/packages/System.Memory/).</span><span class="sxs-lookup"><span data-stu-id="a8b2b-121">For earlier frameworks, <xref:System.Span%601> and <xref:System.Memory%601> are available in the [System.Memory NuGet package](https://www.nuget.org/packages/System.Memory/).</span></span>

<span data-ttu-id="a8b2b-122">Para obtener más información, vea el espacio de nombres <xref:System.Buffers?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a8b2b-122">For more information, see the <xref:System.Buffers?displayProperty=nameWithType> namespace.</span></span>

## <a name="working-with-memory-and-span"></a><span data-ttu-id="a8b2b-123">Uso de memoria e intervalo</span><span class="sxs-lookup"><span data-stu-id="a8b2b-123">Working with memory and span</span></span>

<span data-ttu-id="a8b2b-124">Dado que los tipos relacionados con el intervalo y la memoria se usan normalmente para almacenar datos en una canalización de procesamiento, es importante que los desarrolladores sigan un conjunto de procedimientos recomendados al usar <xref:System.Span%601>, <xref:System.Memory%601> y tipos relacionados.</span><span class="sxs-lookup"><span data-stu-id="a8b2b-124">Because the memory- and span-related types are typically used to store data in a processing pipeline, it is important that developers follow a set of best practices when using <xref:System.Span%601>, <xref:System.Memory%601>, and related types.</span></span> <span data-ttu-id="a8b2b-125">Estos procedimientos recomendados se documentan en las directrices de uso de [Memory\<T> y Span\<T>](memory-t-usage-guidelines.md).</span><span class="sxs-lookup"><span data-stu-id="a8b2b-125">These best practices are documented in [Memory\<T> and Span\<T> usage guidelines](memory-t-usage-guidelines.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a8b2b-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="a8b2b-126">See also</span></span>

- <xref:System.Memory%601?displayProperty=nameWithType>
- <xref:System.ReadOnlyMemory%601?displayProperty=nameWithType>
- <xref:System.Span%601?displayProperty=nameWithType>
- <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>
- <xref:System.Buffers?displayProperty=nameWithType>
