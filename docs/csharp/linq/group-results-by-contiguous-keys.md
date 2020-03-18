---
title: Agrupar resultados por claves contiguas (LINQ en C#)
description: Cómo agrupar resultados por claves con LINQ en C#.
ms.date: 08/14/2018
ms.assetid: cbda9c08-151b-4c9e-82f7-c3d7f3dac66b
ms.openlocfilehash: b5753c85bb07be4fc84b78a299eece961969ff9d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "61659909"
---
# <a name="group-results-by-contiguous-keys"></a><span data-ttu-id="a3c40-103">Agrupar resultados por claves contiguas</span><span class="sxs-lookup"><span data-stu-id="a3c40-103">Group results by contiguous keys</span></span>

<span data-ttu-id="a3c40-104">En el ejemplo siguiente se muestra cómo agrupar elementos en fragmentos que representan subsecuencias de claves contiguas.</span><span class="sxs-lookup"><span data-stu-id="a3c40-104">The following example shows how to group elements into chunks that represent subsequences of contiguous keys.</span></span> <span data-ttu-id="a3c40-105">Por ejemplo, suponga que tiene la siguiente secuencia de pares clave-valor:</span><span class="sxs-lookup"><span data-stu-id="a3c40-105">For example, assume that you are given the following sequence of key-value pairs:</span></span>

|<span data-ttu-id="a3c40-106">Clave</span><span class="sxs-lookup"><span data-stu-id="a3c40-106">Key</span></span>|<span data-ttu-id="a3c40-107">Valor</span><span class="sxs-lookup"><span data-stu-id="a3c40-107">Value</span></span>|
|---------|-----------|
|<span data-ttu-id="a3c40-108">A</span><span class="sxs-lookup"><span data-stu-id="a3c40-108">A</span></span>|<span data-ttu-id="a3c40-109">We</span><span class="sxs-lookup"><span data-stu-id="a3c40-109">We</span></span>|
|<span data-ttu-id="a3c40-110">A</span><span class="sxs-lookup"><span data-stu-id="a3c40-110">A</span></span>|<span data-ttu-id="a3c40-111">think</span><span class="sxs-lookup"><span data-stu-id="a3c40-111">think</span></span>|
|<span data-ttu-id="a3c40-112">A</span><span class="sxs-lookup"><span data-stu-id="a3c40-112">A</span></span>|<span data-ttu-id="a3c40-113">that</span><span class="sxs-lookup"><span data-stu-id="a3c40-113">that</span></span>|
|<span data-ttu-id="a3c40-114">B</span><span class="sxs-lookup"><span data-stu-id="a3c40-114">B</span></span>|<span data-ttu-id="a3c40-115">Linq</span><span class="sxs-lookup"><span data-stu-id="a3c40-115">Linq</span></span>|
|<span data-ttu-id="a3c40-116">C</span><span class="sxs-lookup"><span data-stu-id="a3c40-116">C</span></span>|<span data-ttu-id="a3c40-117">is</span><span class="sxs-lookup"><span data-stu-id="a3c40-117">is</span></span>|
|<span data-ttu-id="a3c40-118">A</span><span class="sxs-lookup"><span data-stu-id="a3c40-118">A</span></span>|<span data-ttu-id="a3c40-119">really</span><span class="sxs-lookup"><span data-stu-id="a3c40-119">really</span></span>|
|<span data-ttu-id="a3c40-120">B</span><span class="sxs-lookup"><span data-stu-id="a3c40-120">B</span></span>|<span data-ttu-id="a3c40-121">cool</span><span class="sxs-lookup"><span data-stu-id="a3c40-121">cool</span></span>|
|<span data-ttu-id="a3c40-122">B</span><span class="sxs-lookup"><span data-stu-id="a3c40-122">B</span></span>|<span data-ttu-id="a3c40-123">!</span><span class="sxs-lookup"><span data-stu-id="a3c40-123">!</span></span>|

<span data-ttu-id="a3c40-124">Los siguientes grupos se crearán en este orden:</span><span class="sxs-lookup"><span data-stu-id="a3c40-124">The following groups will be created in this order:</span></span>

1. <span data-ttu-id="a3c40-125">We, think, that</span><span class="sxs-lookup"><span data-stu-id="a3c40-125">We, think, that</span></span>

2. <span data-ttu-id="a3c40-126">Linq</span><span class="sxs-lookup"><span data-stu-id="a3c40-126">Linq</span></span>

3. <span data-ttu-id="a3c40-127">is</span><span class="sxs-lookup"><span data-stu-id="a3c40-127">is</span></span>

4. <span data-ttu-id="a3c40-128">really</span><span class="sxs-lookup"><span data-stu-id="a3c40-128">really</span></span>

5. <span data-ttu-id="a3c40-129">cool, !</span><span class="sxs-lookup"><span data-stu-id="a3c40-129">cool, !</span></span>

<span data-ttu-id="a3c40-130">La solución se implementa como un método de extensión seguro para subprocesos que devuelve sus resultados mediante transmisión por secuencias.</span><span class="sxs-lookup"><span data-stu-id="a3c40-130">The solution is implemented as an extension method that is thread-safe and that returns its results in a streaming manner.</span></span> <span data-ttu-id="a3c40-131">Es decir, genera sus grupos a medida que se desplaza por la secuencia de origen.</span><span class="sxs-lookup"><span data-stu-id="a3c40-131">In other words, it produces its groups as it moves through the source sequence.</span></span> <span data-ttu-id="a3c40-132">A diferencia de los operadores `group` u `orderby`, puede comenzar a devolver grupos al llamador antes de que se haya leído toda la secuencia.</span><span class="sxs-lookup"><span data-stu-id="a3c40-132">Unlike the `group` or `orderby` operators, it can begin returning groups to the caller before all of the sequence has been read.</span></span>

<span data-ttu-id="a3c40-133">La seguridad de subprocesos se logra realizando una copia de cada grupo o fragmento a medida que se recorre en iteración la secuencia de origen, tal y como se explica en los comentarios del código fuente.</span><span class="sxs-lookup"><span data-stu-id="a3c40-133">Thread-safety is accomplished by making a copy of each group or chunk as the source sequence is iterated, as explained in the source code comments.</span></span> <span data-ttu-id="a3c40-134">Si la secuencia de origen tiene una secuencia grande de elementos contiguos, Common Language Runtime puede producir una excepción <xref:System.OutOfMemoryException>.</span><span class="sxs-lookup"><span data-stu-id="a3c40-134">If the source sequence has a large sequence of contiguous items, the common language runtime may throw an <xref:System.OutOfMemoryException>.</span></span>

## <a name="example"></a><span data-ttu-id="a3c40-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a3c40-135">Example</span></span>

<span data-ttu-id="a3c40-136">En el ejemplo siguiente se muestran el método de extensión y el código de cliente que lo usa:</span><span class="sxs-lookup"><span data-stu-id="a3c40-136">The following example shows both the extension method and the client code that uses it:</span></span>

[!code-csharp[cscsrefContiguousGroups#1](~/samples/snippets/csharp/concepts/linq/how-to-group-results-by-contiguous-keys_1.cs)]

<span data-ttu-id="a3c40-137">Para usar el método de extensión en el proyecto, copie la clase estática `MyExtensions` en un archivo de código fuente nuevo o ya existente y, si es necesario, agregue una directiva `using` para el espacio de nombres donde se encuentra.</span><span class="sxs-lookup"><span data-stu-id="a3c40-137">To use the extension method in your project, copy the `MyExtensions` static class to a new or existing source code file and if it is required, add a `using` directive for the namespace where it is located.</span></span>

## <a name="see-also"></a><span data-ttu-id="a3c40-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="a3c40-138">See also</span></span>

- [<span data-ttu-id="a3c40-139">Language-Integrated Query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="a3c40-139">Language Integrated Query (LINQ)</span></span>](index.md)
