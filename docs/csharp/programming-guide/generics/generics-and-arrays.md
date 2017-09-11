---
title: "Genéricos y matrices (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- generics [C#], arrays
- arrays [C#], generics
ms.assetid: 7d956536-3851-41b5-94ad-3e7c0a5fe485
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 46cea2733504e56aec5e65a4c9a8b655bc9431cf
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="generics-and-arrays-c-programming-guide"></a><span data-ttu-id="eee06-102">Genéricos y matrices (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="eee06-102">Generics and Arrays (C# Programming Guide)</span></span>
<span data-ttu-id="eee06-103">En C# 2.0 y versiones posteriores, las matrices unidimensionales que tienen un límite inferior de cero implementan <xref:System.Collections.Generic.IList%601> automáticamente.</span><span class="sxs-lookup"><span data-stu-id="eee06-103">In C# 2.0 and later, single-dimensional arrays that have a lower bound of zero automatically implement <xref:System.Collections.Generic.IList%601>.</span></span> <span data-ttu-id="eee06-104">Esto le permite crear métodos genéricos que pueden usar el mismo código para recorrer en iteración matrices y otros tipos de colección.</span><span class="sxs-lookup"><span data-stu-id="eee06-104">This enables you to create generic methods that can use the same code to iterate through arrays and other collection types.</span></span> <span data-ttu-id="eee06-105">Esta técnica es útil principalmente para leer datos en colecciones.</span><span class="sxs-lookup"><span data-stu-id="eee06-105">This technique is primarily useful for reading data in collections.</span></span> <span data-ttu-id="eee06-106">La interfaz <xref:System.Collections.Generic.IList%601> no puede usarse para agregar o quitar elementos de una matriz.</span><span class="sxs-lookup"><span data-stu-id="eee06-106">The <xref:System.Collections.Generic.IList%601> interface cannot be used to add or remove elements from an array.</span></span> <span data-ttu-id="eee06-107">Se generará una excepción si intenta llamar a un método <xref:System.Collections.Generic.IList%601> como <xref:System.Collections.Generic.IList%601.RemoveAt%2A> en una matriz en este contexto.</span><span class="sxs-lookup"><span data-stu-id="eee06-107">An exception will be thrown if you try to call an <xref:System.Collections.Generic.IList%601> method such as <xref:System.Collections.Generic.IList%601.RemoveAt%2A> on an array in this context.</span></span>  
  
 <span data-ttu-id="eee06-108">En el siguiente ejemplo de código se muestra cómo un método genérico único que toma un parámetro de entrada <xref:System.Collections.Generic.IList%601> puede recorrer en iteración una lista y una matriz, en este caso una matriz de enteros.</span><span class="sxs-lookup"><span data-stu-id="eee06-108">The following code example demonstrates how a single generic method that takes an <xref:System.Collections.Generic.IList%601> input parameter can iterate through both a list and an array, in this case an array of integers.</span></span>  
  
 <span data-ttu-id="eee06-109">[!code-cs[csProgGuideGenerics#35](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-arrays_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="eee06-109">[!code-cs[csProgGuideGenerics#35](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-arrays_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eee06-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="eee06-110">See Also</span></span>  
 <span data-ttu-id="eee06-111"><xref:System.Collections.Generic></span><span class="sxs-lookup"><span data-stu-id="eee06-111"><xref:System.Collections.Generic></span></span>   
 <span data-ttu-id="eee06-112">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="eee06-112">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="eee06-113">[Genéricos](../../../csharp/programming-guide/generics/index.md) </span><span class="sxs-lookup"><span data-stu-id="eee06-113">[Generics](../../../csharp/programming-guide/generics/index.md) </span></span>  
 <span data-ttu-id="eee06-114">[Arrays](../../../csharp/programming-guide/arrays/index.md)  (Matrices)</span><span class="sxs-lookup"><span data-stu-id="eee06-114">[Arrays](../../../csharp/programming-guide/arrays/index.md) </span></span>  
 [<span data-ttu-id="eee06-115">Genéricos</span><span class="sxs-lookup"><span data-stu-id="eee06-115">Generics</span></span>](~/docs/standard/generics/index.md)

