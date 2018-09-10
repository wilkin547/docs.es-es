---
title: Pasar matrices como argumentos (Guía de programación de C#)
ms.date: 07/05/2018
helpviewer_keywords:
- arrays [C#], passing as arguments
ms.assetid: f3a0971e-c87c-4a1f-8262-bc0a3b712772
ms.openlocfilehash: b2e6c0134af3b5814e9c9321e1486820311aa5c6
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "44042431"
---
# <a name="passing-arrays-as-arguments-c-programming-guide"></a><span data-ttu-id="492d3-102">Pasar matrices como argumentos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="492d3-102">Passing arrays as arguments (C# Programming Guide)</span></span>

<span data-ttu-id="492d3-103">Las matrices se pueden pasar como argumentos a parámetros de método.</span><span class="sxs-lookup"><span data-stu-id="492d3-103">Arrays can be passed as arguments to method parameters.</span></span> <span data-ttu-id="492d3-104">Dado que las matrices son tipos de referencia, el método puede cambiar el valor de los elementos.</span><span class="sxs-lookup"><span data-stu-id="492d3-104">Because arrays are reference types, the method can change the value of the elements.</span></span>

## <a name="passing-single-dimensional-arrays-as-arguments"></a><span data-ttu-id="492d3-105">Pasar matrices unidimensionales como argumentos</span><span class="sxs-lookup"><span data-stu-id="492d3-105">Passing single-dimensional arrays as arguments</span></span>

<span data-ttu-id="492d3-106">Puede pasar una matriz unidimensional inicializada a un método.</span><span class="sxs-lookup"><span data-stu-id="492d3-106">You can pass an initialized single-dimensional array to a method.</span></span> <span data-ttu-id="492d3-107">Por ejemplo, la siguiente instrucción envía una matriz a un método de impresión.</span><span class="sxs-lookup"><span data-stu-id="492d3-107">For example, the following statement sends an array to a print method.</span></span>

[!code-csharp[csProgGuideArrays#34](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#34)]

<span data-ttu-id="492d3-108">En el siguiente código, se muestra una implementación parcial del método de impresión.</span><span class="sxs-lookup"><span data-stu-id="492d3-108">The following code shows a partial implementation of the print method.</span></span>

[!code-csharp[csProgGuideArrays#33](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#33)]

<span data-ttu-id="492d3-109">Puede inicializar y pasar una nueva matriz en un solo paso, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="492d3-109">You can initialize and pass a new array in one step, as is shown in the following example.</span></span>

[!code-csharp[CsProgGuideArrays#35](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#35)]

### <a name="example"></a><span data-ttu-id="492d3-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="492d3-110">Example</span></span>

<span data-ttu-id="492d3-111">En el ejemplo siguiente, una matriz de cadenas se inicializa y pasa como un argumento a un método `DisplayArray` para cadenas.</span><span class="sxs-lookup"><span data-stu-id="492d3-111">In the following example, an array of strings is initialized and passed as an argument to a `DisplayArray` method for strings.</span></span> <span data-ttu-id="492d3-112">El método muestra los elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="492d3-112">The method displays the elements of the array.</span></span> <span data-ttu-id="492d3-113">A continuación, el método `ChangeArray` invierte los elementos de la matriz y, después, el método `ChangeArrayElements` modifica los tres primeros elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="492d3-113">Next, the `ChangeArray` method reverses the array elements, and then the `ChangeArrayElements` method modifies the first three elements of the array.</span></span> <span data-ttu-id="492d3-114">Después de cada devolución de método, el método `DisplayArray` muestra que pasar una matriz por valor no impide que se cambien los elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="492d3-114">After each method returns, the `DisplayArray` method shows that passing an array by value doesn't prevent changes to the array elements.</span></span>

[!code-csharp[csProgGuideArrays#30](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/ArrayExample.cs)]

## <a name="passing-multidimensional-arrays-as-arguments"></a><span data-ttu-id="492d3-115">Pasar matrices multidimensionales como argumentos</span><span class="sxs-lookup"><span data-stu-id="492d3-115">Passing multidimensional arrays as arguments</span></span>

<span data-ttu-id="492d3-116">Pase una matriz multidimensional inicializada a un método de la misma manera que pasa una matriz unidimensional.</span><span class="sxs-lookup"><span data-stu-id="492d3-116">You pass an initialized multidimensional array to a method in the same way that you pass a one-dimensional array.</span></span>

[!code-csharp[csProgGuideArrays#41](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#41)]

<span data-ttu-id="492d3-117">En el código siguiente, se muestra una declaración parcial de un método de impresión que acepta una matriz bidimensional como su argumento.</span><span class="sxs-lookup"><span data-stu-id="492d3-117">The following code shows a partial declaration of a print method that accepts a two-dimensional array as its argument.</span></span>

[!code-csharp[csProgGuideArrays#36](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#36)]

<span data-ttu-id="492d3-118">Puede inicializar y pasar una matriz nueva en un solo paso, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="492d3-118">You can initialize and pass a new array in one step, as is shown in the following example:</span></span>

[!code-csharp[csProgGuideArrays#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#32)]

### <a name="example"></a><span data-ttu-id="492d3-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="492d3-119">Example</span></span>

<span data-ttu-id="492d3-120">En el ejemplo siguiente, una matriz bidimensional de enteros se inicializa y pasa al método `Print2DArray`.</span><span class="sxs-lookup"><span data-stu-id="492d3-120">In the following example, a two-dimensional array of integers is initialized and passed to the `Print2DArray` method.</span></span> <span data-ttu-id="492d3-121">El método muestra los elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="492d3-121">The method displays the elements of the array.</span></span>

[!code-csharp[csProgGuideArrays#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#31)]

## <a name="see-also"></a><span data-ttu-id="492d3-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="492d3-122">See also</span></span>

- [<span data-ttu-id="492d3-123">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="492d3-123">C# Programming Guide</span></span>](../index.md)  
- [<span data-ttu-id="492d3-124">Matrices</span><span class="sxs-lookup"><span data-stu-id="492d3-124">Arrays</span></span>](index.md)  
- [<span data-ttu-id="492d3-125">Matrices unidimensionales</span><span class="sxs-lookup"><span data-stu-id="492d3-125">Single-Dimensional Arrays</span></span>](single-dimensional-arrays.md)  
- [<span data-ttu-id="492d3-126">Matrices multidimensionales</span><span class="sxs-lookup"><span data-stu-id="492d3-126">Multidimensional Arrays</span></span>](multidimensional-arrays.md)  
- [<span data-ttu-id="492d3-127">Matrices escalonadas</span><span class="sxs-lookup"><span data-stu-id="492d3-127">Jagged Arrays</span></span>](jagged-arrays.md)  