---
title: Agrupar resultados por claves contiguas
description: "Cómo agrupar resultados por claves contiguas."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: cbda9c08-151b-4c9e-82f7-c3d7f3dac66b
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ddd028a3aad5186ef6773b32e9f9e8e1cbff95fc
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="group-results-by-contiguous-keys"></a><span data-ttu-id="c7593-104">Agrupar resultados por claves contiguas</span><span class="sxs-lookup"><span data-stu-id="c7593-104">Group results by contiguous keys</span></span>

<span data-ttu-id="c7593-105">En el ejemplo siguiente se muestra cómo agrupar elementos en fragmentos que representan subsecuencias de claves contiguas.</span><span class="sxs-lookup"><span data-stu-id="c7593-105">The following example shows how to group elements into chunks that represent subsequences of contiguous keys.</span></span> <span data-ttu-id="c7593-106">Por ejemplo, suponga que tiene la siguiente secuencia de pares clave-valor:</span><span class="sxs-lookup"><span data-stu-id="c7593-106">For example, assume that you are given the following sequence of key-value pairs:</span></span>  
  
|<span data-ttu-id="c7593-107">Clave</span><span class="sxs-lookup"><span data-stu-id="c7593-107">Key</span></span>|<span data-ttu-id="c7593-108">Valor</span><span class="sxs-lookup"><span data-stu-id="c7593-108">Value</span></span>|  
|---------|-----------|  
|<span data-ttu-id="c7593-109">A</span><span class="sxs-lookup"><span data-stu-id="c7593-109">A</span></span>|<span data-ttu-id="c7593-110">We</span><span class="sxs-lookup"><span data-stu-id="c7593-110">We</span></span>|  
|<span data-ttu-id="c7593-111">A</span><span class="sxs-lookup"><span data-stu-id="c7593-111">A</span></span>|<span data-ttu-id="c7593-112">think</span><span class="sxs-lookup"><span data-stu-id="c7593-112">think</span></span>|  
|<span data-ttu-id="c7593-113">A</span><span class="sxs-lookup"><span data-stu-id="c7593-113">A</span></span>|<span data-ttu-id="c7593-114">that</span><span class="sxs-lookup"><span data-stu-id="c7593-114">that</span></span>|  
|<span data-ttu-id="c7593-115">B</span><span class="sxs-lookup"><span data-stu-id="c7593-115">B</span></span>|<span data-ttu-id="c7593-116">Linq</span><span class="sxs-lookup"><span data-stu-id="c7593-116">Linq</span></span>|  
|<span data-ttu-id="c7593-117">C</span><span class="sxs-lookup"><span data-stu-id="c7593-117">C</span></span>|<span data-ttu-id="c7593-118">is</span><span class="sxs-lookup"><span data-stu-id="c7593-118">is</span></span>|  
|<span data-ttu-id="c7593-119">A</span><span class="sxs-lookup"><span data-stu-id="c7593-119">A</span></span>|<span data-ttu-id="c7593-120">really</span><span class="sxs-lookup"><span data-stu-id="c7593-120">really</span></span>|  
|<span data-ttu-id="c7593-121">B</span><span class="sxs-lookup"><span data-stu-id="c7593-121">B</span></span>|<span data-ttu-id="c7593-122">cool</span><span class="sxs-lookup"><span data-stu-id="c7593-122">cool</span></span>|  
|<span data-ttu-id="c7593-123">B</span><span class="sxs-lookup"><span data-stu-id="c7593-123">B</span></span>|<span data-ttu-id="c7593-124">!</span><span class="sxs-lookup"><span data-stu-id="c7593-124">!</span></span>|  
  
 <span data-ttu-id="c7593-125">Los siguientes grupos se crearán en este orden:</span><span class="sxs-lookup"><span data-stu-id="c7593-125">The following groups will be created in this order:</span></span>  
  
1.  <span data-ttu-id="c7593-126">We, think, that</span><span class="sxs-lookup"><span data-stu-id="c7593-126">We, think, that</span></span>  
  
2.  <span data-ttu-id="c7593-127">Linq</span><span class="sxs-lookup"><span data-stu-id="c7593-127">Linq</span></span>  
  
3.  <span data-ttu-id="c7593-128">is</span><span class="sxs-lookup"><span data-stu-id="c7593-128">is</span></span>  
  
4.  <span data-ttu-id="c7593-129">really</span><span class="sxs-lookup"><span data-stu-id="c7593-129">really</span></span>  
  
5.  <span data-ttu-id="c7593-130">cool, !</span><span class="sxs-lookup"><span data-stu-id="c7593-130">cool, !</span></span>  
  
 <span data-ttu-id="c7593-131">La solución se implementa como un método de extensión seguro para subprocesos que devuelve sus resultados mediante transmisión por secuencias.</span><span class="sxs-lookup"><span data-stu-id="c7593-131">The solution is implemented as an extension method that is thread-safe and that returns its results in a streaming manner.</span></span> <span data-ttu-id="c7593-132">Es decir, genera sus grupos a medida que se desplaza por la secuencia de origen.</span><span class="sxs-lookup"><span data-stu-id="c7593-132">In other words, it produces its groups as it moves through the source sequence.</span></span> <span data-ttu-id="c7593-133">A diferencia de los operadores `group` u `orderby`, puede comenzar a devolver grupos al llamador antes de que se haya leído toda la secuencia.</span><span class="sxs-lookup"><span data-stu-id="c7593-133">Unlike the `group` or `orderby` operators, it can begin returning groups to the caller before all of the sequence has been read.</span></span>  
  
 <span data-ttu-id="c7593-134">La seguridad de subprocesos se logra realizando una copia de cada grupo o fragmento a medida que se recorre en iteración la secuencia de origen, tal y como se explica en los comentarios del código fuente.</span><span class="sxs-lookup"><span data-stu-id="c7593-134">Thread-safety is accomplished by making a copy of each group or chunk as the source sequence is iterated, as explained in the source code comments.</span></span> <span data-ttu-id="c7593-135">Si la secuencia de origen tiene una secuencia grande de elementos contiguos, Common Language Runtime puede producir una excepción <xref:System.OutOfMemoryException>.</span><span class="sxs-lookup"><span data-stu-id="c7593-135">If the source sequence has a large sequence of contiguous items, the common language runtime may throw an <xref:System.OutOfMemoryException>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7593-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c7593-136">Example</span></span>  
 <span data-ttu-id="c7593-137">En el siguiente ejemplo se muestran el método de extensión y el código de cliente que lo usa.</span><span class="sxs-lookup"><span data-stu-id="c7593-137">The following example shows both the extension method and the client code that uses it.</span></span>  
  
 <span data-ttu-id="c7593-138">[!code-cs[cscsrefContiguousGroups#1](../../../samples/snippets/csharp/concepts/linq/how-to-group-results-by-contiguous-keys_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="c7593-138">[!code-cs[cscsrefContiguousGroups#1](../../../samples/snippets/csharp/concepts/linq/how-to-group-results-by-contiguous-keys_1.cs)]</span></span>  
  
 <span data-ttu-id="c7593-139">Para usar el método de extensión en el proyecto, copie la clase estática `MyExtensions` en un archivo de código fuente nuevo o ya existente y, si es necesario, agregue una directiva `using` para el espacio de nombres donde se encuentra.</span><span class="sxs-lookup"><span data-stu-id="c7593-139">To use the extension method in your project, copy the `MyExtensions` static class to a new or existing source code file and if it is required, add a `using` directive for the namespace where it is located.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7593-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="c7593-140">See also</span></span>  
 [<span data-ttu-id="c7593-141">Expresiones de consulta LINQ</span><span class="sxs-lookup"><span data-stu-id="c7593-141">LINQ Query Expressions</span></span>](index.md)   
 

