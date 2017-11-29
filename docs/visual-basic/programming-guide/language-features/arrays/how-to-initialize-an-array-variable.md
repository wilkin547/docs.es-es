---
title: "Cómo: Inicializar una variable de matriz en Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- variables [Visual Basic], initializing
- arrays [Visual Basic], variables
- arrays [Visual Basic], initializing
- arrays [Visual Basic], declaring
ms.assetid: aadd7a60-7ca4-4608-b986-091f19e7fc10
caps.latest.revision: "42"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3ccdbed601d3fa87acb0833bc153c199b17a4eba
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-initialize-an-array-variable-in-visual-basic"></a><span data-ttu-id="52815-102">Cómo: Inicializar una variable de matriz en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="52815-102">How to: Initialize an Array Variable in Visual Basic</span></span>
<span data-ttu-id="52815-103">Inicializar una variable de matriz mediante la inclusión de una matriz literal en una `New` cláusula y especificar los valores iniciales de la matriz.</span><span class="sxs-lookup"><span data-stu-id="52815-103">You initialize an array variable by including an array literal in a `New` clause and specifying the initial values of the array.</span></span> <span data-ttu-id="52815-104">Puede especificar el tipo o permitir que se pueden inferir de los valores del literal de matriz.</span><span class="sxs-lookup"><span data-stu-id="52815-104">You can either specify the type or allow it to be inferred from the values in the array literal.</span></span> <span data-ttu-id="52815-105">Para obtener más información acerca de cómo se deduce el tipo, vea "Rellenar una matriz con valores iniciales" en [matrices](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="52815-105">For more information about how the type is inferred, see "Populating an Array with Initial Values" in [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
### <a name="to-initialize-an-array-variable-by-using-an-array-literal"></a><span data-ttu-id="52815-106">Para inicializar una variable de matriz mediante un literal de matriz</span><span class="sxs-lookup"><span data-stu-id="52815-106">To initialize an array variable by using an array literal</span></span>  
  
-   <span data-ttu-id="52815-107">En el `New` cláusula, o cuando se asigna el valor de matriz, proporcione los valores de elementos entre llaves (`{}`).</span><span class="sxs-lookup"><span data-stu-id="52815-107">Either in the `New` clause, or when you assign the array value, supply the element values inside braces (`{}`).</span></span> <span data-ttu-id="52815-108">En el ejemplo siguiente se muestra varias maneras de declarar, crear e inicializar una variable para contener una matriz que contiene elementos de tipo `Char`.</span><span class="sxs-lookup"><span data-stu-id="52815-108">The following example shows several ways to declare, create, and initialize a variable to contain an array that has elements of type `Char`.</span></span>  
  
     [!code-vb[VbVbalrArrays#16](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/how-to-initialize-an-array-variable_1.vb)]  
  
     <span data-ttu-id="52815-109">Después de que se ejecuta cada instrucción, la matriz que se crea tiene una longitud de 3, con elementos en el índice 0 hasta el índice 2 que contiene los valores iniciales.</span><span class="sxs-lookup"><span data-stu-id="52815-109">After each statement executes, the array that's created has a length of 3, with elements at index 0 through index 2 containing the initial values.</span></span> <span data-ttu-id="52815-110">Si proporciona el límite superior y los valores, debe incluir un valor para cada elemento desde el índice 0 hasta el límite superior.</span><span class="sxs-lookup"><span data-stu-id="52815-110">If you supply both the upper bound and the values, you must include a value for every element from index 0 through the upper bound.</span></span>  
  
     <span data-ttu-id="52815-111">Tenga en cuenta que no es necesario especificar el límite superior del índice si proporciona valores de elemento en un literal de matriz.</span><span class="sxs-lookup"><span data-stu-id="52815-111">Notice that you do not have to specify the index upper bound if you supply element values in an array literal.</span></span> <span data-ttu-id="52815-112">Si no se especifica ningún límite superior, el tamaño de la matriz se deduce en función del número de valores en el literal de matriz.</span><span class="sxs-lookup"><span data-stu-id="52815-112">If no upper bound is specified, the size of the array is inferred based on the number of values in the array literal.</span></span>  
  
### <a name="to-initialize-a-multidimensional-array-variable-by-using-array-literals"></a><span data-ttu-id="52815-113">Para inicializar una variable de matriz multidimensional con literales de matriz</span><span class="sxs-lookup"><span data-stu-id="52815-113">To initialize a multidimensional array variable by using array literals</span></span>  
  
-   <span data-ttu-id="52815-114">Anide los valores entre llaves (`{}`) dentro de llaves.</span><span class="sxs-lookup"><span data-stu-id="52815-114">Nest values inside braces (`{}`) within braces.</span></span> <span data-ttu-id="52815-115">Asegúrese de que los literales de matriz anidados que todos deducir como matrices del mismo tipo y longitud.</span><span class="sxs-lookup"><span data-stu-id="52815-115">Ensure that the nested array literals all infer as arrays of the same type and length.</span></span> <span data-ttu-id="52815-116">El ejemplo de código siguiente muestra varios ejemplos de inicialización de matriz multidimensional.</span><span class="sxs-lookup"><span data-stu-id="52815-116">The following code example shows several examples of multidimensional array initialization.</span></span>  
  
     [!code-vb[VbVbalrArrays#17](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/how-to-initialize-an-array-variable_2.vb)]  
  
-   <span data-ttu-id="52815-117">Explícitamente puede especificar los límites de matriz, o dejarlos fuera y hacer que el compilador deduzca los límites de matriz basados en los valores del literal de matriz.</span><span class="sxs-lookup"><span data-stu-id="52815-117">You can explicitly specify the array bounds, or leave them out and have the compiler infer the array bounds based on the values in the array literal.</span></span> <span data-ttu-id="52815-118">Si proporciona los límites superiores y los valores, debe incluir un valor para cada elemento desde el índice 0 hasta el límite superior de cada dimensión.</span><span class="sxs-lookup"><span data-stu-id="52815-118">If you supply both the upper bounds and the values, you must include a value for every element from index 0 through the upper bound in every dimension.</span></span> <span data-ttu-id="52815-119">En el ejemplo siguiente se muestra varias maneras de declarar, crear e inicializar una variable para contener una matriz bidimensional con elementos de tipo`Short`</span><span class="sxs-lookup"><span data-stu-id="52815-119">The following example shows several ways to declare, create, and initialize a variable to contain a two-dimensional array that has elements of type `Short`</span></span>  
  
     [!code-vb[VbVbalrArrays#18](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/how-to-initialize-an-array-variable_3.vb)]  
  
     <span data-ttu-id="52815-120">Después de que se ejecuta cada instrucción, la matriz creada contiene seis elementos inicializados que tienen índices `(0,0)`, `(0,1)`, `(0,2)`, `(1,0)`, `(1,1)`, y `(1,2)`.</span><span class="sxs-lookup"><span data-stu-id="52815-120">After each statement executes, the created array contains six initialized elements that have indexes `(0,0)`, `(0,1)`, `(0,2)`, `(1,0)`, `(1,1)`, and `(1,2)`.</span></span> <span data-ttu-id="52815-121">Cada ubicación de la matriz contiene el valor `10`.</span><span class="sxs-lookup"><span data-stu-id="52815-121">Each array location contains the value `10`.</span></span>  
  
-   <span data-ttu-id="52815-122">En el ejemplo siguiente se recorre en iteración una matriz multidimensional.</span><span class="sxs-lookup"><span data-stu-id="52815-122">The following example iterates through a multidimensional array.</span></span> <span data-ttu-id="52815-123">En una aplicación de consola de Windows que se escribe en Visual Basic, pegue el código dentro de la `Sub Main()` método.</span><span class="sxs-lookup"><span data-stu-id="52815-123">In a Windows console application that is written in Visual Basic, paste the code inside the `Sub Main()` method.</span></span> <span data-ttu-id="52815-124">Los comentarios de la última muestran la salida.</span><span class="sxs-lookup"><span data-stu-id="52815-124">The last comments show the output.</span></span>  
  
     [!code-vb[VbVbalrArrays#31](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/how-to-initialize-an-array-variable_4.vb)]  
  
### <a name="to-initialize-a-jagged-array-variable-by-using-array-literals"></a><span data-ttu-id="52815-125">Para inicializar una variable de matriz escalonada mediante literales de matriz</span><span class="sxs-lookup"><span data-stu-id="52815-125">To initialize a jagged array variable by using array literals</span></span>  
  
-   <span data-ttu-id="52815-126">Anidar los valores de objeto dentro de llaves (`{}`).</span><span class="sxs-lookup"><span data-stu-id="52815-126">Nest object values inside braces (`{}`).</span></span> <span data-ttu-id="52815-127">Aunque también puede anidar los literales de matriz que especifican matrices de longitudes diferentes, en el caso de una matriz escalonada, asegúrese que los literales de matriz anidados se encierran entre paréntesis (`()`).</span><span class="sxs-lookup"><span data-stu-id="52815-127">Although you can also nest array literals that specify arrays of different lengths, in the case of a jagged array, make sure that that the nested array literals are enclosed in parentheses (`()`).</span></span> <span data-ttu-id="52815-128">Los paréntesis fuerzan la evaluación de los literales de matriz anidados y las matrices resultantes se utilizan como los valores iniciales de la matriz escalonada.</span><span class="sxs-lookup"><span data-stu-id="52815-128">The parentheses force the evaluation of the nested array literals, and the resulting arrays are used as the initial values of the jagged array.</span></span> <span data-ttu-id="52815-129">En el ejemplo de código siguiente se muestra dos ejemplos de inicialización de matriz escalonada.</span><span class="sxs-lookup"><span data-stu-id="52815-129">The following code example shows two examples of jagged array initialization.</span></span>  
  
     [!code-vb[VbVbalrArrays#19](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/how-to-initialize-an-array-variable_5.vb)]  
  
-   <span data-ttu-id="52815-130">En el ejemplo siguiente se recorre en iteración una matriz escalonada.</span><span class="sxs-lookup"><span data-stu-id="52815-130">The following example iterates through a jagged array.</span></span> <span data-ttu-id="52815-131">En una aplicación de consola de Windows que se escribe en Visual Basic, pegue el código dentro de la `Sub Main()` método.</span><span class="sxs-lookup"><span data-stu-id="52815-131">In a Windows console application that is written in Visual Basic, paste the code inside the `Sub Main()` method.</span></span>  <span data-ttu-id="52815-132">El último comentarios en el código muestran la salida.</span><span class="sxs-lookup"><span data-stu-id="52815-132">The last comments in the code show the output.</span></span>  
  
     [!code-vb[VbVbalrArrays#32](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/how-to-initialize-an-array-variable_6.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="52815-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="52815-133">See Also</span></span>  
 [<span data-ttu-id="52815-134">Matrices</span><span class="sxs-lookup"><span data-stu-id="52815-134">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [<span data-ttu-id="52815-135">Solución de problemas de matrices</span><span class="sxs-lookup"><span data-stu-id="52815-135">Troubleshooting Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)
