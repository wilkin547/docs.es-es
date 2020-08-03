---
title: 'Matrices multidimensionales: Guía de programación de C#'
description: Las matrices de C# pueden tener más de una dimensión. En la declaración de este ejemplo se crea una matriz bidimensional de cuatro filas y dos columnas.
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], multidimensional
- multidimensional arrays [C#]
ms.assetid: 020ce02e-7dff-4273-8e53-bf0b33747232
ms.openlocfilehash: a2f204c0866672b317569fbc620aa8af60829ffd
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475013"
---
# <a name="multidimensional-arrays-c-programming-guide"></a><span data-ttu-id="7d779-104">Matrices multidimensionales (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="7d779-104">Multidimensional Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="7d779-105">Las matrices pueden tener varias dimensiones.</span><span class="sxs-lookup"><span data-stu-id="7d779-105">Arrays can have more than one dimension.</span></span> <span data-ttu-id="7d779-106">Por ejemplo, la siguiente declaración crea una matriz bidimensional de cuatro filas y dos columnas.</span><span class="sxs-lookup"><span data-stu-id="7d779-106">For example, the following declaration creates a two-dimensional array of four rows and two columns.</span></span>  
  
 [!code-csharp[csProgGuideArrays#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#11)]  
  
 <span data-ttu-id="7d779-107">La siguiente declaración crea una matriz de tres dimensiones, 4, 2 y 3.</span><span class="sxs-lookup"><span data-stu-id="7d779-107">The following declaration creates an array of three dimensions, 4, 2, and 3.</span></span>  
  
 [!code-csharp[csProgGuideArrays#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#12)]  
  
## <a name="array-initialization"></a><span data-ttu-id="7d779-108">Inicialización de matriz</span><span class="sxs-lookup"><span data-stu-id="7d779-108">Array Initialization</span></span>

 <span data-ttu-id="7d779-109">La matriz se puede inicializar en la declaración como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="7d779-109">You can initialize the array upon declaration, as is shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideArrays#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#13)]  
  
 <span data-ttu-id="7d779-110">También se puede inicializar la matriz sin especificar el rango.</span><span class="sxs-lookup"><span data-stu-id="7d779-110">You can also initialize the array without specifying the rank.</span></span>  
  
 [!code-csharp[csProgGuideArrays#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#14)]  
  
 <span data-ttu-id="7d779-111">Si opta por declarar una variable de matriz sin inicializarla, deberá usar el operador `new` para asignar una matriz a la variable.</span><span class="sxs-lookup"><span data-stu-id="7d779-111">If you choose to declare an array variable without initialization, you must use the `new` operator to assign an array to the variable.</span></span> <span data-ttu-id="7d779-112">El uso de `new` se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="7d779-112">The use of `new` is shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideArrays#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#15)]  
  
 <span data-ttu-id="7d779-113">En el ejemplo siguiente se asigna un valor a un elemento de matriz determinado.</span><span class="sxs-lookup"><span data-stu-id="7d779-113">The following example assigns a value to a particular array element.</span></span>  
  
 [!code-csharp[csProgGuideArrays#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#16)]  
  
 <span data-ttu-id="7d779-114">De igual forma, en el ejemplo siguiente se obtiene el valor de un elemento de matriz determinado y se asigna a la variable `elementValue`.</span><span class="sxs-lookup"><span data-stu-id="7d779-114">Similarly, the following example gets the value of a particular array element and assigns it to variable `elementValue`.</span></span>  
  
 [!code-csharp[csProgGuideArrays#42](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#42)]  
  
 <span data-ttu-id="7d779-115">El ejemplo de código siguiente inicializa los elementos de matriz con valores predeterminados (salvo las matrices escalonadas).</span><span class="sxs-lookup"><span data-stu-id="7d779-115">The following code example initializes the array elements to default values (except for jagged arrays).</span></span>  
  
 [!code-csharp[csProgGuideArrays#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#17)]  
  
## <a name="see-also"></a><span data-ttu-id="7d779-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="7d779-116">See also</span></span>

- [<span data-ttu-id="7d779-117">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="7d779-117">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="7d779-118">Matrices</span><span class="sxs-lookup"><span data-stu-id="7d779-118">Arrays</span></span>](./index.md)
- [<span data-ttu-id="7d779-119">Matrices unidimensionales</span><span class="sxs-lookup"><span data-stu-id="7d779-119">Single-Dimensional Arrays</span></span>](./single-dimensional-arrays.md)
- [<span data-ttu-id="7d779-120">Matrices escalonadas</span><span class="sxs-lookup"><span data-stu-id="7d779-120">Jagged Arrays</span></span>](./jagged-arrays.md)
