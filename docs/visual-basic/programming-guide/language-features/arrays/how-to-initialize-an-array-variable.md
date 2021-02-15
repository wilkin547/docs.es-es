---
description: 'Más información acerca de cómo: inicializar una variable de matriz en Visual Basic'
title: Procedimiento para inicializar una variable de matriz
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], initializing
- arrays [Visual Basic], variables
- arrays [Visual Basic], initializing
- arrays [Visual Basic], declaring
ms.assetid: aadd7a60-7ca4-4608-b986-091f19e7fc10
ms.openlocfilehash: 05cca98457a56db52ee99cfc4ac93c860da7a51d
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100427614"
---
# <a name="how-to-initialize-an-array-variable-in-visual-basic"></a><span data-ttu-id="8bf6e-103">Cómo: Inicializar una variable de matriz en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8bf6e-103">How to: Initialize an Array Variable in Visual Basic</span></span>

<span data-ttu-id="8bf6e-104">Para inicializar una variable de matriz, incluya un literal de matriz en una `New` cláusula y especifique los valores iniciales de la matriz.</span><span class="sxs-lookup"><span data-stu-id="8bf6e-104">You initialize an array variable by including an array literal in a `New` clause and specifying the initial values of the array.</span></span> <span data-ttu-id="8bf6e-105">Puede especificar el tipo o permitir que se infiera de los valores del literal de matriz.</span><span class="sxs-lookup"><span data-stu-id="8bf6e-105">You can either specify the type or allow it to be inferred from the values in the array literal.</span></span> <span data-ttu-id="8bf6e-106">Para obtener más información sobre cómo se deduce el tipo, vea "rellenar una matriz con valores iniciales" en [matrices](index.md).</span><span class="sxs-lookup"><span data-stu-id="8bf6e-106">For more information about how the type is inferred, see "Populating an Array with Initial Values" in [Arrays](index.md).</span></span>  
  
### <a name="to-initialize-an-array-variable-by-using-an-array-literal"></a><span data-ttu-id="8bf6e-107">Para inicializar una variable de matriz mediante un literal de matriz</span><span class="sxs-lookup"><span data-stu-id="8bf6e-107">To initialize an array variable by using an array literal</span></span>  
  
- <span data-ttu-id="8bf6e-108">En la `New` cláusula o al asignar el valor de matriz, proporcione los valores de elemento entre llaves ( `{}` ).</span><span class="sxs-lookup"><span data-stu-id="8bf6e-108">Either in the `New` clause, or when you assign the array value, supply the element values inside braces (`{}`).</span></span> <span data-ttu-id="8bf6e-109">En el ejemplo siguiente se muestran varias maneras de declarar, crear e inicializar una variable que contenga una matriz con elementos de tipo `Char` .</span><span class="sxs-lookup"><span data-stu-id="8bf6e-109">The following example shows several ways to declare, create, and initialize a variable to contain an array that has elements of type `Char`.</span></span>  
  
     [!code-vb[VbVbalrArrays#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#16)]  
  
     <span data-ttu-id="8bf6e-110">Una vez ejecutada cada instrucción, la matriz que se crea tiene una longitud de 3, con elementos en el índice 0 hasta el índice 2 que contiene los valores iniciales.</span><span class="sxs-lookup"><span data-stu-id="8bf6e-110">After each statement executes, the array that's created has a length of 3, with elements at index 0 through index 2 containing the initial values.</span></span> <span data-ttu-id="8bf6e-111">Si proporciona el límite superior y los valores, debe incluir un valor para cada elemento desde el índice 0 hasta el límite superior.</span><span class="sxs-lookup"><span data-stu-id="8bf6e-111">If you supply both the upper bound and the values, you must include a value for every element from index 0 through the upper bound.</span></span>  
  
     <span data-ttu-id="8bf6e-112">Tenga en cuenta que no es necesario especificar el límite superior del índice si se proporcionan valores de elemento en un literal de matriz.</span><span class="sxs-lookup"><span data-stu-id="8bf6e-112">Notice that you do not have to specify the index upper bound if you supply element values in an array literal.</span></span> <span data-ttu-id="8bf6e-113">Si no se especifica ningún límite superior, el tamaño de la matriz se deduce en función del número de valores del literal de matriz.</span><span class="sxs-lookup"><span data-stu-id="8bf6e-113">If no upper bound is specified, the size of the array is inferred based on the number of values in the array literal.</span></span>  
  
### <a name="to-initialize-a-multidimensional-array-variable-by-using-array-literals"></a><span data-ttu-id="8bf6e-114">Para inicializar una variable de matriz multidimensional utilizando literales de matriz</span><span class="sxs-lookup"><span data-stu-id="8bf6e-114">To initialize a multidimensional array variable by using array literals</span></span>  
  
- <span data-ttu-id="8bf6e-115">Anide los valores entre llaves ( `{}` ) entre llaves.</span><span class="sxs-lookup"><span data-stu-id="8bf6e-115">Nest values inside braces (`{}`) within braces.</span></span> <span data-ttu-id="8bf6e-116">Asegúrese de que todos los literales de matriz anidados se deducen como matrices del mismo tipo y longitud.</span><span class="sxs-lookup"><span data-stu-id="8bf6e-116">Ensure that the nested array literals all infer as arrays of the same type and length.</span></span> <span data-ttu-id="8bf6e-117">En el ejemplo de código siguiente se muestran varios ejemplos de inicialización de la matriz multidimensional.</span><span class="sxs-lookup"><span data-stu-id="8bf6e-117">The following code example shows several examples of multidimensional array initialization.</span></span>  
  
     [!code-vb[VbVbalrArrays#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#17)]  
  
- <span data-ttu-id="8bf6e-118">Puede especificar explícitamente los límites de la matriz o dejarlos fuera y hacer que el compilador deduzca los límites de la matriz basándose en los valores del literal de matriz.</span><span class="sxs-lookup"><span data-stu-id="8bf6e-118">You can explicitly specify the array bounds, or leave them out and have the compiler infer the array bounds based on the values in the array literal.</span></span> <span data-ttu-id="8bf6e-119">Si proporciona los límites superiores y los valores, debe incluir un valor para cada elemento desde el índice 0 hasta el límite superior de cada dimensión.</span><span class="sxs-lookup"><span data-stu-id="8bf6e-119">If you supply both the upper bounds and the values, you must include a value for every element from index 0 through the upper bound in every dimension.</span></span> <span data-ttu-id="8bf6e-120">En el ejemplo siguiente se muestran varias maneras de declarar, crear e inicializar una variable para que contenga una matriz bidimensional que tiene elementos de tipo `Short`</span><span class="sxs-lookup"><span data-stu-id="8bf6e-120">The following example shows several ways to declare, create, and initialize a variable to contain a two-dimensional array that has elements of type `Short`</span></span>  
  
     [!code-vb[VbVbalrArrays#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#18)]  
  
     <span data-ttu-id="8bf6e-121">Una vez ejecutada cada instrucción, la matriz creada contiene seis elementos inicializados que tienen índices `(0,0)` , `(0,1)` , `(0,2)` , `(1,0)` , `(1,1)` y `(1,2)` .</span><span class="sxs-lookup"><span data-stu-id="8bf6e-121">After each statement executes, the created array contains six initialized elements that have indexes `(0,0)`, `(0,1)`, `(0,2)`, `(1,0)`, `(1,1)`, and `(1,2)`.</span></span> <span data-ttu-id="8bf6e-122">Cada ubicación de la matriz contiene el valor `10` .</span><span class="sxs-lookup"><span data-stu-id="8bf6e-122">Each array location contains the value `10`.</span></span>  
  
- <span data-ttu-id="8bf6e-123">En el ejemplo siguiente se recorre en iteración una matriz multidimensional.</span><span class="sxs-lookup"><span data-stu-id="8bf6e-123">The following example iterates through a multidimensional array.</span></span> <span data-ttu-id="8bf6e-124">En una aplicación de consola de Windows escrita en Visual Basic, pegue el código dentro del `Sub Main()` método.</span><span class="sxs-lookup"><span data-stu-id="8bf6e-124">In a Windows console application that is written in Visual Basic, paste the code inside the `Sub Main()` method.</span></span> <span data-ttu-id="8bf6e-125">Los últimos Comentarios muestran el resultado.</span><span class="sxs-lookup"><span data-stu-id="8bf6e-125">The last comments show the output.</span></span>  
  
     [!code-vb[VbVbalrArrays#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#31)]  
  
### <a name="to-initialize-a-jagged-array-variable-by-using-array-literals"></a><span data-ttu-id="8bf6e-126">Para inicializar una variable de matriz escalonada mediante literales de matriz</span><span class="sxs-lookup"><span data-stu-id="8bf6e-126">To initialize a jagged array variable by using array literals</span></span>  
  
- <span data-ttu-id="8bf6e-127">Anide los valores de objeto entre llaves ( `{}` ).</span><span class="sxs-lookup"><span data-stu-id="8bf6e-127">Nest object values inside braces (`{}`).</span></span> <span data-ttu-id="8bf6e-128">Aunque también puede anidar literales de matriz que especifican matrices de longitudes diferentes, en el caso de una matriz escalonada, asegúrese de que los literales de matriz anidados se incluyen entre paréntesis ( `()` ).</span><span class="sxs-lookup"><span data-stu-id="8bf6e-128">Although you can also nest array literals that specify arrays of different lengths, in the case of a jagged array, make sure that the nested array literals are enclosed in parentheses (`()`).</span></span> <span data-ttu-id="8bf6e-129">Los paréntesis fuerzan la evaluación de los literales de matriz anidados y las matrices resultantes se utilizan como valores iniciales de la matriz escalonada.</span><span class="sxs-lookup"><span data-stu-id="8bf6e-129">The parentheses force the evaluation of the nested array literals, and the resulting arrays are used as the initial values of the jagged array.</span></span> <span data-ttu-id="8bf6e-130">En el ejemplo de código siguiente se muestran dos ejemplos de inicialización de matriz escalonada.</span><span class="sxs-lookup"><span data-stu-id="8bf6e-130">The following code example shows two examples of jagged array initialization.</span></span>  
  
     [!code-vb[VbVbalrArrays#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#19)]  
  
- <span data-ttu-id="8bf6e-131">En el ejemplo siguiente se recorre en iteración una matriz escalonada.</span><span class="sxs-lookup"><span data-stu-id="8bf6e-131">The following example iterates through a jagged array.</span></span> <span data-ttu-id="8bf6e-132">En una aplicación de consola de Windows escrita en Visual Basic, pegue el código dentro del `Sub Main()` método.</span><span class="sxs-lookup"><span data-stu-id="8bf6e-132">In a Windows console application that is written in Visual Basic, paste the code inside the `Sub Main()` method.</span></span>  <span data-ttu-id="8bf6e-133">Los últimos Comentarios del código muestran la salida.</span><span class="sxs-lookup"><span data-stu-id="8bf6e-133">The last comments in the code show the output.</span></span>  
  
     [!code-vb[VbVbalrArrays#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#32)]  
  
## <a name="see-also"></a><span data-ttu-id="8bf6e-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="8bf6e-134">See also</span></span>

- [<span data-ttu-id="8bf6e-135">Matrices</span><span class="sxs-lookup"><span data-stu-id="8bf6e-135">Arrays</span></span>](index.md)
- [<span data-ttu-id="8bf6e-136">Solución de problemas de matrices</span><span class="sxs-lookup"><span data-stu-id="8bf6e-136">Troubleshooting Arrays</span></span>](troubleshooting-arrays.md)
