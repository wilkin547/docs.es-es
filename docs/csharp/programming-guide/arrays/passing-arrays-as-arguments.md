---
title: "Pasar matrices como argumentos (Guía de programación de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: arrays [C#], passing as arguments
ms.assetid: f3a0971e-c87c-4a1f-8262-bc0a3b712772
caps.latest.revision: "21"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f152173b747a171052ab99f261ed91ced9465fdc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="passing-arrays-as-arguments-c-programming-guide"></a><span data-ttu-id="26b45-102">Pasar matrices como argumentos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="26b45-102">Passing Arrays as Arguments (C# Programming Guide)</span></span>
<span data-ttu-id="26b45-103">Las matrices se pueden pasar como argumentos a parámetros de método.</span><span class="sxs-lookup"><span data-stu-id="26b45-103">Arrays can be passed as arguments to method parameters.</span></span> <span data-ttu-id="26b45-104">Dado que las matrices son tipos de referencia, el método puede cambiar el valor de los elementos.</span><span class="sxs-lookup"><span data-stu-id="26b45-104">Because arrays are reference types, the method can change the value of the elements.</span></span>  
  
## <a name="passing-single-dimensional-arrays-as-arguments"></a><span data-ttu-id="26b45-105">Pasar matrices unidimensionales como argumentos</span><span class="sxs-lookup"><span data-stu-id="26b45-105">Passing Single-Dimensional Arrays As Arguments</span></span>  
 <span data-ttu-id="26b45-106">Puede pasar una matriz unidimensional inicializada a un método.</span><span class="sxs-lookup"><span data-stu-id="26b45-106">You can pass an initialized single-dimensional array to a method.</span></span> <span data-ttu-id="26b45-107">Por ejemplo, la siguiente instrucción envía una matriz a un método de impresión.</span><span class="sxs-lookup"><span data-stu-id="26b45-107">For example, the following statement sends an array to a print method.</span></span>  
  
 [!code-csharp[csProgGuideArrays#34](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_1.cs)]  
  
 <span data-ttu-id="26b45-108">En el siguiente código, se muestra una implementación parcial del método de impresión.</span><span class="sxs-lookup"><span data-stu-id="26b45-108">The following code shows a partial implementation of the print method.</span></span>  
  
 [!code-csharp[csProgGuideArrays#33](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_2.cs)]  
  
 <span data-ttu-id="26b45-109">Puede inicializar y pasar una nueva matriz en un solo paso, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="26b45-109">You can initialize and pass a new array in one step, as is shown in the following example.</span></span>  
  
 [!code-csharp[CsProgGuideArrays#35](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_3.cs)]  
  
## <a name="example"></a><span data-ttu-id="26b45-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="26b45-110">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="26b45-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="26b45-111">Description</span></span>  
 <span data-ttu-id="26b45-112">En el ejemplo siguiente, una matriz de cadenas se inicializa y pasa como un argumento a un método `PrintArray` para cadenas.</span><span class="sxs-lookup"><span data-stu-id="26b45-112">In the following example, an array of strings is initialized and passed as an argument to a `PrintArray` method for strings.</span></span> <span data-ttu-id="26b45-113">El método muestra los elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="26b45-113">The method displays the elements of the array.</span></span> <span data-ttu-id="26b45-114">Después, se llama a los métodos `ChangeArray` y `ChangeArrayElement` para demostrar que enviar un argumento de matriz en función del valor no evita los cambios a los elementos de matriz.</span><span class="sxs-lookup"><span data-stu-id="26b45-114">Next, methods `ChangeArray` and `ChangeArrayElement` are called to demonstrate that sending an array argument by value does not prevent changes to the array elements.</span></span>  
  
### <a name="code"></a><span data-ttu-id="26b45-115">Código</span><span class="sxs-lookup"><span data-stu-id="26b45-115">Code</span></span>  
 [!code-csharp[csProgGuideArrays#30](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_4.cs)]  
  
## <a name="passing-multidimensional-arrays-as-arguments"></a><span data-ttu-id="26b45-116">Pasar matrices multidimensionales como argumentos</span><span class="sxs-lookup"><span data-stu-id="26b45-116">Passing Multidimensional Arrays As Arguments</span></span>  
 <span data-ttu-id="26b45-117">Pase una matriz multidimensional inicializada a un método de la misma manera que pasa una matriz unidimensional.</span><span class="sxs-lookup"><span data-stu-id="26b45-117">You pass an initialized multidimensional array to a method in the same way that you pass a one-dimensional array.</span></span>  
  
 [!code-csharp[csProgGuideArrays#41](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_5.cs)]  
  
 <span data-ttu-id="26b45-118">En el código siguiente, se muestra una declaración parcial de un método de impresión que acepta una matriz bidimensional como su argumento.</span><span class="sxs-lookup"><span data-stu-id="26b45-118">The following code shows a partial declaration of a print method that accepts a two-dimensional array as its argument.</span></span>  
  
 [!code-csharp[csProgGuideArrays#36](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_6.cs)]  
  
 <span data-ttu-id="26b45-119">Puede inicializar y pasar una nueva matriz en un solo paso, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="26b45-119">You can initialize and pass a new array in one step, as is shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideArrays#32](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_7.cs)]  
  
## <a name="example"></a><span data-ttu-id="26b45-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="26b45-120">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="26b45-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="26b45-121">Description</span></span>  
 <span data-ttu-id="26b45-122">En el ejemplo siguiente, una matriz bidimensional de enteros se inicializa y pasa al método `Print2DArray`.</span><span class="sxs-lookup"><span data-stu-id="26b45-122">In the following example, a two-dimensional array of integers is initialized and passed to the `Print2DArray` method.</span></span> <span data-ttu-id="26b45-123">El método muestra los elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="26b45-123">The method displays the elements of the array.</span></span>  
  
### <a name="code"></a><span data-ttu-id="26b45-124">Código</span><span class="sxs-lookup"><span data-stu-id="26b45-124">Code</span></span>  
 [!code-csharp[csProgGuideArrays#31](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_8.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="26b45-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="26b45-125">See Also</span></span>  
 [<span data-ttu-id="26b45-126">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="26b45-126">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="26b45-127">Matrices</span><span class="sxs-lookup"><span data-stu-id="26b45-127">Arrays</span></span>](../../../csharp/programming-guide/arrays/index.md)  
 [<span data-ttu-id="26b45-128">Matrices unidimensionales</span><span class="sxs-lookup"><span data-stu-id="26b45-128">Single-Dimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)  
 [<span data-ttu-id="26b45-129">Matrices multidimensionales</span><span class="sxs-lookup"><span data-stu-id="26b45-129">Multidimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)  
 [<span data-ttu-id="26b45-130">Matrices escalonadas</span><span class="sxs-lookup"><span data-stu-id="26b45-130">Jagged Arrays</span></span>](../../../csharp/programming-guide/arrays/jagged-arrays.md)
