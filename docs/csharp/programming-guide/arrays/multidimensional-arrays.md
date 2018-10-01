---
title: Matrices multidimensionales (Guía de programación de C#)
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], multidimensional
- multidimensional arrays [C#]
ms.assetid: 020ce02e-7dff-4273-8e53-bf0b33747232
ms.openlocfilehash: a1d7a0a014c330682316e869f6727082fa3b31ef
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2018
ms.locfileid: "47421484"
---
# <a name="multidimensional-arrays-c-programming-guide"></a><span data-ttu-id="2a731-102">Matrices multidimensionales (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="2a731-102">Multidimensional Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="2a731-103">Las matrices pueden tener varias dimensiones.</span><span class="sxs-lookup"><span data-stu-id="2a731-103">Arrays can have more than one dimension.</span></span> <span data-ttu-id="2a731-104">Por ejemplo, la siguiente declaración crea una matriz bidimensional de cuatro filas y dos columnas.</span><span class="sxs-lookup"><span data-stu-id="2a731-104">For example, the following declaration creates a two-dimensional array of four rows and two columns.</span></span>  
  
 [!code-csharp[csProgGuideArrays#11](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_1.cs)]  
  
 <span data-ttu-id="2a731-105">La siguiente declaración crea una matriz de tres dimensiones, 4, 2 y 3.</span><span class="sxs-lookup"><span data-stu-id="2a731-105">The following declaration creates an array of three dimensions, 4, 2, and 3.</span></span>  
  
 [!code-csharp[csProgGuideArrays#12](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_2.cs)]  
  
## <a name="array-initialization"></a><span data-ttu-id="2a731-106">Inicialización de matriz</span><span class="sxs-lookup"><span data-stu-id="2a731-106">Array Initialization</span></span>

 <span data-ttu-id="2a731-107">La matriz se puede inicializar en la declaración como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="2a731-107">You can initialize the array upon declaration, as is shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideArrays#13](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_3.cs)]  
  
 <span data-ttu-id="2a731-108">También se puede inicializar la matriz sin especificar el intervalo.</span><span class="sxs-lookup"><span data-stu-id="2a731-108">You also can initialize the array without specifying the rank.</span></span>  
  
 [!code-csharp[csProgGuideArrays#14](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_4.cs)]  
  
 <span data-ttu-id="2a731-109">Si opta por declarar una variable de matriz sin inicializarla, deberá usar el operador `new` para asignar una matriz a la variable.</span><span class="sxs-lookup"><span data-stu-id="2a731-109">If you choose to declare an array variable without initialization, you must use the `new` operator to assign an array to the variable.</span></span> <span data-ttu-id="2a731-110">El uso de `new` se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="2a731-110">The use of `new` is shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideArrays#15](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_5.cs)]  
  
 <span data-ttu-id="2a731-111">En el ejemplo siguiente se asigna un valor a un elemento de matriz determinado.</span><span class="sxs-lookup"><span data-stu-id="2a731-111">The following example assigns a value to a particular array element.</span></span>  
  
 [!code-csharp[csProgGuideArrays#16](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_6.cs)]  
  
 <span data-ttu-id="2a731-112">De igual forma, en el ejemplo siguiente se obtiene el valor de un elemento de matriz determinado y se asigna a la variable `elementValue`.</span><span class="sxs-lookup"><span data-stu-id="2a731-112">Similarly, the following example gets the value of a particular array element and assigns it to variable `elementValue`.</span></span>  
  
 [!code-csharp[csProgGuideArrays#42](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_7.cs)]  
  
 <span data-ttu-id="2a731-113">El ejemplo de código siguiente inicializa los elementos de matriz con valores predeterminados (salvo las matrices escalonadas).</span><span class="sxs-lookup"><span data-stu-id="2a731-113">The following code example initializes the array elements to default values (except for jagged arrays).</span></span>  
  
 [!code-csharp[csProgGuideArrays#17](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_8.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="2a731-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="2a731-114">See Also</span></span>

- [<span data-ttu-id="2a731-115">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="2a731-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="2a731-116">Matrices</span><span class="sxs-lookup"><span data-stu-id="2a731-116">Arrays</span></span>](../../../csharp/programming-guide/arrays/index.md)  
- [<span data-ttu-id="2a731-117">Matrices unidimensionales</span><span class="sxs-lookup"><span data-stu-id="2a731-117">Single-Dimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)  
- [<span data-ttu-id="2a731-118">Matrices escalonadas</span><span class="sxs-lookup"><span data-stu-id="2a731-118">Jagged Arrays</span></span>](../../../csharp/programming-guide/arrays/jagged-arrays.md)
