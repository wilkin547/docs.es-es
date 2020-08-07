---
title: 'Genéricos y matrices: Guía de programación de C#'
description: Aprenda sobre genéricos y matrices en la programación de C#. Vea ejemplos de código y examine los recursos adicionales disponibles.
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], arrays
- arrays [C#], generics
ms.assetid: 7d956536-3851-41b5-94ad-3e7c0a5fe485
ms.openlocfilehash: f3d9e9e0c84d954278780e7598545f80aea0e58c
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "87299050"
---
# <a name="generics-and-arrays-c-programming-guide"></a><span data-ttu-id="f2d16-104">Genéricos y matrices (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="f2d16-104">Generics and Arrays (C# Programming Guide)</span></span>
<span data-ttu-id="f2d16-105">En C# 2.0 y versiones posteriores, las matrices unidimensionales que tienen un límite inferior de cero implementan <xref:System.Collections.Generic.IList%601> automáticamente.</span><span class="sxs-lookup"><span data-stu-id="f2d16-105">In C# 2.0 and later, single-dimensional arrays that have a lower bound of zero automatically implement <xref:System.Collections.Generic.IList%601>.</span></span> <span data-ttu-id="f2d16-106">Esto le permite crear métodos genéricos que pueden usar el mismo código para recorrer en iteración matrices y otros tipos de colección.</span><span class="sxs-lookup"><span data-stu-id="f2d16-106">This enables you to create generic methods that can use the same code to iterate through arrays and other collection types.</span></span> <span data-ttu-id="f2d16-107">Esta técnica es útil principalmente para leer datos en colecciones.</span><span class="sxs-lookup"><span data-stu-id="f2d16-107">This technique is primarily useful for reading data in collections.</span></span> <span data-ttu-id="f2d16-108">La interfaz <xref:System.Collections.Generic.IList%601> no puede usarse para agregar o quitar elementos de una matriz.</span><span class="sxs-lookup"><span data-stu-id="f2d16-108">The <xref:System.Collections.Generic.IList%601> interface cannot be used to add or remove elements from an array.</span></span> <span data-ttu-id="f2d16-109">Se generará una excepción si intenta llamar a un método <xref:System.Collections.Generic.IList%601> como <xref:System.Collections.Generic.IList%601.RemoveAt%2A> en una matriz en este contexto.</span><span class="sxs-lookup"><span data-stu-id="f2d16-109">An exception will be thrown if you try to call an <xref:System.Collections.Generic.IList%601> method such as <xref:System.Collections.Generic.IList%601.RemoveAt%2A> on an array in this context.</span></span>  
  
 <span data-ttu-id="f2d16-110">En el siguiente ejemplo de código se muestra cómo un método genérico único que toma un parámetro de entrada <xref:System.Collections.Generic.IList%601> puede recorrer en iteración una lista y una matriz, en este caso una matriz de enteros.</span><span class="sxs-lookup"><span data-stu-id="f2d16-110">The following code example demonstrates how a single generic method that takes an <xref:System.Collections.Generic.IList%601> input parameter can iterate through both a list and an array, in this case an array of integers.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#35](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#35)]  
  
## <a name="see-also"></a><span data-ttu-id="f2d16-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f2d16-111">See also</span></span>

- <xref:System.Collections.Generic>
- [<span data-ttu-id="f2d16-112">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="f2d16-112">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="f2d16-113">Genéricos</span><span class="sxs-lookup"><span data-stu-id="f2d16-113">Generics</span></span>](./index.md)
- [<span data-ttu-id="f2d16-114">Matrices</span><span class="sxs-lookup"><span data-stu-id="f2d16-114">Arrays</span></span>](../arrays/index.md)
- [<span data-ttu-id="f2d16-115">Genéricos</span><span class="sxs-lookup"><span data-stu-id="f2d16-115">Generics</span></span>](../../../standard/generics/index.md)
