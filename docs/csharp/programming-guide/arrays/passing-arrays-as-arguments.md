---
title: Pasar matrices como argumentos (Guía de programación de C#)
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], passing as arguments
ms.assetid: f3a0971e-c87c-4a1f-8262-bc0a3b712772
ms.openlocfilehash: d863cdc33a8a1a844aabbea9ba5876614e6e8dba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33315521"
---
# <a name="passing-arrays-as-arguments-c-programming-guide"></a><span data-ttu-id="540bd-102">Pasar matrices como argumentos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="540bd-102">Passing Arrays as Arguments (C# Programming Guide)</span></span>
<span data-ttu-id="540bd-103">Las matrices se pueden pasar como argumentos a parámetros de método.</span><span class="sxs-lookup"><span data-stu-id="540bd-103">Arrays can be passed as arguments to method parameters.</span></span> <span data-ttu-id="540bd-104">Dado que las matrices son tipos de referencia, el método puede cambiar el valor de los elementos.</span><span class="sxs-lookup"><span data-stu-id="540bd-104">Because arrays are reference types, the method can change the value of the elements.</span></span>  
  
## <a name="passing-single-dimensional-arrays-as-arguments"></a><span data-ttu-id="540bd-105">Pasar matrices unidimensionales como argumentos</span><span class="sxs-lookup"><span data-stu-id="540bd-105">Passing Single-Dimensional Arrays As Arguments</span></span>  
 <span data-ttu-id="540bd-106">Puede pasar una matriz unidimensional inicializada a un método.</span><span class="sxs-lookup"><span data-stu-id="540bd-106">You can pass an initialized single-dimensional array to a method.</span></span> <span data-ttu-id="540bd-107">Por ejemplo, la siguiente instrucción envía una matriz a un método de impresión.</span><span class="sxs-lookup"><span data-stu-id="540bd-107">For example, the following statement sends an array to a print method.</span></span>  
  
 [!code-csharp[csProgGuideArrays#34](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_1.cs)]  
  
 <span data-ttu-id="540bd-108">En el siguiente código, se muestra una implementación parcial del método de impresión.</span><span class="sxs-lookup"><span data-stu-id="540bd-108">The following code shows a partial implementation of the print method.</span></span>  
  
 [!code-csharp[csProgGuideArrays#33](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_2.cs)]  
  
 <span data-ttu-id="540bd-109">Puede inicializar y pasar una nueva matriz en un solo paso, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="540bd-109">You can initialize and pass a new array in one step, as is shown in the following example.</span></span>  
  
 [!code-csharp[CsProgGuideArrays#35](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_3.cs)]  
  
## <a name="example"></a><span data-ttu-id="540bd-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="540bd-110">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="540bd-111">Description</span><span class="sxs-lookup"><span data-stu-id="540bd-111">Description</span></span>  
 <span data-ttu-id="540bd-112">En el ejemplo siguiente, una matriz de cadenas se inicializa y pasa como un argumento a un método `PrintArray` para cadenas.</span><span class="sxs-lookup"><span data-stu-id="540bd-112">In the following example, an array of strings is initialized and passed as an argument to a `PrintArray` method for strings.</span></span> <span data-ttu-id="540bd-113">El método muestra los elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="540bd-113">The method displays the elements of the array.</span></span> <span data-ttu-id="540bd-114">Después, se llama a los métodos `ChangeArray` y `ChangeArrayElement` para demostrar que enviar un argumento de matriz en función del valor no evita los cambios a los elementos de matriz.</span><span class="sxs-lookup"><span data-stu-id="540bd-114">Next, methods `ChangeArray` and `ChangeArrayElement` are called to demonstrate that sending an array argument by value does not prevent changes to the array elements.</span></span>  
  
### <a name="code"></a><span data-ttu-id="540bd-115">Código</span><span class="sxs-lookup"><span data-stu-id="540bd-115">Code</span></span>  
 [!code-csharp[csProgGuideArrays#30](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_4.cs)]  
  
## <a name="passing-multidimensional-arrays-as-arguments"></a><span data-ttu-id="540bd-116">Pasar matrices multidimensionales como argumentos</span><span class="sxs-lookup"><span data-stu-id="540bd-116">Passing Multidimensional Arrays As Arguments</span></span>  
 <span data-ttu-id="540bd-117">Pase una matriz multidimensional inicializada a un método de la misma manera que pasa una matriz unidimensional.</span><span class="sxs-lookup"><span data-stu-id="540bd-117">You pass an initialized multidimensional array to a method in the same way that you pass a one-dimensional array.</span></span>  
  
 [!code-csharp[csProgGuideArrays#41](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_5.cs)]  
  
 <span data-ttu-id="540bd-118">En el código siguiente, se muestra una declaración parcial de un método de impresión que acepta una matriz bidimensional como su argumento.</span><span class="sxs-lookup"><span data-stu-id="540bd-118">The following code shows a partial declaration of a print method that accepts a two-dimensional array as its argument.</span></span>  
  
 [!code-csharp[csProgGuideArrays#36](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_6.cs)]  
  
 <span data-ttu-id="540bd-119">Puede inicializar y pasar una nueva matriz en un solo paso, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="540bd-119">You can initialize and pass a new array in one step, as is shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideArrays#32](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_7.cs)]  
  
## <a name="example"></a><span data-ttu-id="540bd-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="540bd-120">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="540bd-121">Description</span><span class="sxs-lookup"><span data-stu-id="540bd-121">Description</span></span>  
 <span data-ttu-id="540bd-122">En el ejemplo siguiente, una matriz bidimensional de enteros se inicializa y pasa al método `Print2DArray`.</span><span class="sxs-lookup"><span data-stu-id="540bd-122">In the following example, a two-dimensional array of integers is initialized and passed to the `Print2DArray` method.</span></span> <span data-ttu-id="540bd-123">El método muestra los elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="540bd-123">The method displays the elements of the array.</span></span>  
  
### <a name="code"></a><span data-ttu-id="540bd-124">Código</span><span class="sxs-lookup"><span data-stu-id="540bd-124">Code</span></span>  
 [!code-csharp[csProgGuideArrays#31](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_8.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="540bd-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="540bd-125">See Also</span></span>  
 [<span data-ttu-id="540bd-126">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="540bd-126">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="540bd-127">Matrices</span><span class="sxs-lookup"><span data-stu-id="540bd-127">Arrays</span></span>](../../../csharp/programming-guide/arrays/index.md)  
 [<span data-ttu-id="540bd-128">Matrices unidimensionales</span><span class="sxs-lookup"><span data-stu-id="540bd-128">Single-Dimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)  
 [<span data-ttu-id="540bd-129">Matrices multidimensionales</span><span class="sxs-lookup"><span data-stu-id="540bd-129">Multidimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)  
 [<span data-ttu-id="540bd-130">Matrices escalonadas</span><span class="sxs-lookup"><span data-stu-id="540bd-130">Jagged Arrays</span></span>](../../../csharp/programming-guide/arrays/jagged-arrays.md)
