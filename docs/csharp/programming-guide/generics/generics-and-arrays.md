---
title: "Genéricos y matrices (Guía de programación de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- generics [C#], arrays
- arrays [C#], generics
ms.assetid: 7d956536-3851-41b5-94ad-3e7c0a5fe485
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 94b144075fac44ff749474a5bfa8e81aaadc0a0c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="generics-and-arrays-c-programming-guide"></a><span data-ttu-id="03fd9-102">Genéricos y matrices (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="03fd9-102">Generics and Arrays (C# Programming Guide)</span></span>
<span data-ttu-id="03fd9-103">En C# 2.0 y versiones posteriores, las matrices unidimensionales que tienen un límite inferior de cero implementan <xref:System.Collections.Generic.IList%601> automáticamente.</span><span class="sxs-lookup"><span data-stu-id="03fd9-103">In C# 2.0 and later, single-dimensional arrays that have a lower bound of zero automatically implement <xref:System.Collections.Generic.IList%601>.</span></span> <span data-ttu-id="03fd9-104">Esto le permite crear métodos genéricos que pueden usar el mismo código para recorrer en iteración matrices y otros tipos de colección.</span><span class="sxs-lookup"><span data-stu-id="03fd9-104">This enables you to create generic methods that can use the same code to iterate through arrays and other collection types.</span></span> <span data-ttu-id="03fd9-105">Esta técnica es útil principalmente para leer datos en colecciones.</span><span class="sxs-lookup"><span data-stu-id="03fd9-105">This technique is primarily useful for reading data in collections.</span></span> <span data-ttu-id="03fd9-106">La interfaz <xref:System.Collections.Generic.IList%601> no puede usarse para agregar o quitar elementos de una matriz.</span><span class="sxs-lookup"><span data-stu-id="03fd9-106">The <xref:System.Collections.Generic.IList%601> interface cannot be used to add or remove elements from an array.</span></span> <span data-ttu-id="03fd9-107">Se generará una excepción si intenta llamar a un método <xref:System.Collections.Generic.IList%601> como <xref:System.Collections.Generic.IList%601.RemoveAt%2A> en una matriz en este contexto.</span><span class="sxs-lookup"><span data-stu-id="03fd9-107">An exception will be thrown if you try to call an <xref:System.Collections.Generic.IList%601> method such as <xref:System.Collections.Generic.IList%601.RemoveAt%2A> on an array in this context.</span></span>  
  
 <span data-ttu-id="03fd9-108">En el siguiente ejemplo de código se muestra cómo un método genérico único que toma un parámetro de entrada <xref:System.Collections.Generic.IList%601> puede recorrer en iteración una lista y una matriz, en este caso una matriz de enteros.</span><span class="sxs-lookup"><span data-stu-id="03fd9-108">The following code example demonstrates how a single generic method that takes an <xref:System.Collections.Generic.IList%601> input parameter can iterate through both a list and an array, in this case an array of integers.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#35](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-arrays_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="03fd9-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="03fd9-109">See Also</span></span>  
 <xref:System.Collections.Generic>  
 [<span data-ttu-id="03fd9-110">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="03fd9-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="03fd9-111">Genéricos</span><span class="sxs-lookup"><span data-stu-id="03fd9-111">Generics</span></span>](../../../csharp/programming-guide/generics/index.md)  
 [<span data-ttu-id="03fd9-112">Matrices</span><span class="sxs-lookup"><span data-stu-id="03fd9-112">Arrays</span></span>](../../../csharp/programming-guide/arrays/index.md)  
 [<span data-ttu-id="03fd9-113">Genéricos</span><span class="sxs-lookup"><span data-stu-id="03fd9-113">Generics</span></span>](~/docs/standard/generics/index.md)
