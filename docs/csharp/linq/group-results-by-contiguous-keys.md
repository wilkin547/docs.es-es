---
title: Agrupar resultados por claves contiguas
description: Cómo agrupar resultados por claves contiguas.
ms.date: 12/1/2016
ms.assetid: cbda9c08-151b-4c9e-82f7-c3d7f3dac66b
ms.openlocfilehash: a8d6ac133932a12154d5b23454065144c7652067
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33281442"
---
# <a name="group-results-by-contiguous-keys"></a><span data-ttu-id="8e285-103">Agrupar resultados por claves contiguas</span><span class="sxs-lookup"><span data-stu-id="8e285-103">Group results by contiguous keys</span></span>

<span data-ttu-id="8e285-104">En el ejemplo siguiente se muestra cómo agrupar elementos en fragmentos que representan subsecuencias de claves contiguas.</span><span class="sxs-lookup"><span data-stu-id="8e285-104">The following example shows how to group elements into chunks that represent subsequences of contiguous keys.</span></span> <span data-ttu-id="8e285-105">Por ejemplo, suponga que tiene la siguiente secuencia de pares clave-valor:</span><span class="sxs-lookup"><span data-stu-id="8e285-105">For example, assume that you are given the following sequence of key-value pairs:</span></span>  
  
|<span data-ttu-id="8e285-106">Key</span><span class="sxs-lookup"><span data-stu-id="8e285-106">Key</span></span>|<span data-ttu-id="8e285-107">Valor</span><span class="sxs-lookup"><span data-stu-id="8e285-107">Value</span></span>|  
|---------|-----------|  
|<span data-ttu-id="8e285-108">A</span><span class="sxs-lookup"><span data-stu-id="8e285-108">A</span></span>|<span data-ttu-id="8e285-109">We</span><span class="sxs-lookup"><span data-stu-id="8e285-109">We</span></span>|  
|<span data-ttu-id="8e285-110">A</span><span class="sxs-lookup"><span data-stu-id="8e285-110">A</span></span>|<span data-ttu-id="8e285-111">think</span><span class="sxs-lookup"><span data-stu-id="8e285-111">think</span></span>|  
|<span data-ttu-id="8e285-112">A</span><span class="sxs-lookup"><span data-stu-id="8e285-112">A</span></span>|<span data-ttu-id="8e285-113">that</span><span class="sxs-lookup"><span data-stu-id="8e285-113">that</span></span>|  
|<span data-ttu-id="8e285-114">B</span><span class="sxs-lookup"><span data-stu-id="8e285-114">B</span></span>|<span data-ttu-id="8e285-115">Linq</span><span class="sxs-lookup"><span data-stu-id="8e285-115">Linq</span></span>|  
|<span data-ttu-id="8e285-116">C</span><span class="sxs-lookup"><span data-stu-id="8e285-116">C</span></span>|<span data-ttu-id="8e285-117">is</span><span class="sxs-lookup"><span data-stu-id="8e285-117">is</span></span>|  
|<span data-ttu-id="8e285-118">A</span><span class="sxs-lookup"><span data-stu-id="8e285-118">A</span></span>|<span data-ttu-id="8e285-119">really</span><span class="sxs-lookup"><span data-stu-id="8e285-119">really</span></span>|  
|<span data-ttu-id="8e285-120">B</span><span class="sxs-lookup"><span data-stu-id="8e285-120">B</span></span>|<span data-ttu-id="8e285-121">cool</span><span class="sxs-lookup"><span data-stu-id="8e285-121">cool</span></span>|  
|<span data-ttu-id="8e285-122">B</span><span class="sxs-lookup"><span data-stu-id="8e285-122">B</span></span>|<span data-ttu-id="8e285-123">!</span><span class="sxs-lookup"><span data-stu-id="8e285-123">!</span></span>|  
  
 <span data-ttu-id="8e285-124">Los siguientes grupos se crearán en este orden:</span><span class="sxs-lookup"><span data-stu-id="8e285-124">The following groups will be created in this order:</span></span>  
  
1.  <span data-ttu-id="8e285-125">We, think, that</span><span class="sxs-lookup"><span data-stu-id="8e285-125">We, think, that</span></span>  
  
2.  <span data-ttu-id="8e285-126">Linq</span><span class="sxs-lookup"><span data-stu-id="8e285-126">Linq</span></span>  
  
3.  <span data-ttu-id="8e285-127">is</span><span class="sxs-lookup"><span data-stu-id="8e285-127">is</span></span>  
  
4.  <span data-ttu-id="8e285-128">really</span><span class="sxs-lookup"><span data-stu-id="8e285-128">really</span></span>  
  
5.  <span data-ttu-id="8e285-129">cool, !</span><span class="sxs-lookup"><span data-stu-id="8e285-129">cool, !</span></span>  
  
 <span data-ttu-id="8e285-130">La solución se implementa como un método de extensión seguro para subprocesos que devuelve sus resultados mediante transmisión por secuencias.</span><span class="sxs-lookup"><span data-stu-id="8e285-130">The solution is implemented as an extension method that is thread-safe and that returns its results in a streaming manner.</span></span> <span data-ttu-id="8e285-131">Es decir, genera sus grupos a medida que se desplaza por la secuencia de origen.</span><span class="sxs-lookup"><span data-stu-id="8e285-131">In other words, it produces its groups as it moves through the source sequence.</span></span> <span data-ttu-id="8e285-132">A diferencia de los operadores `group` u `orderby`, puede comenzar a devolver grupos al llamador antes de que se haya leído toda la secuencia.</span><span class="sxs-lookup"><span data-stu-id="8e285-132">Unlike the `group` or `orderby` operators, it can begin returning groups to the caller before all of the sequence has been read.</span></span>  
  
 <span data-ttu-id="8e285-133">La seguridad de subprocesos se logra realizando una copia de cada grupo o fragmento a medida que se recorre en iteración la secuencia de origen, tal y como se explica en los comentarios del código fuente.</span><span class="sxs-lookup"><span data-stu-id="8e285-133">Thread-safety is accomplished by making a copy of each group or chunk as the source sequence is iterated, as explained in the source code comments.</span></span> <span data-ttu-id="8e285-134">Si la secuencia de origen tiene una secuencia grande de elementos contiguos, Common Language Runtime puede producir una excepción <xref:System.OutOfMemoryException>.</span><span class="sxs-lookup"><span data-stu-id="8e285-134">If the source sequence has a large sequence of contiguous items, the common language runtime may throw an <xref:System.OutOfMemoryException>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e285-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8e285-135">Example</span></span>  
 <span data-ttu-id="8e285-136">En el siguiente ejemplo se muestran el método de extensión y el código de cliente que lo usa.</span><span class="sxs-lookup"><span data-stu-id="8e285-136">The following example shows both the extension method and the client code that uses it.</span></span>  
  
 [!code-csharp[cscsrefContiguousGroups#1](../../../samples/snippets/csharp/concepts/linq/how-to-group-results-by-contiguous-keys_1.cs)]  
  
 <span data-ttu-id="8e285-137">Para usar el método de extensión en el proyecto, copie la clase estática `MyExtensions` en un archivo de código fuente nuevo o ya existente y, si es necesario, agregue una directiva `using` para el espacio de nombres donde se encuentra.</span><span class="sxs-lookup"><span data-stu-id="8e285-137">To use the extension method in your project, copy the `MyExtensions` static class to a new or existing source code file and if it is required, add a `using` directive for the namespace where it is located.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e285-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="8e285-138">See also</span></span>  
 [<span data-ttu-id="8e285-139">Expresiones de consulta LINQ</span><span class="sxs-lookup"><span data-stu-id="8e285-139">LINQ Query Expressions</span></span>](index.md)  
 
