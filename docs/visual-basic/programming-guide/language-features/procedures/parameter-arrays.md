---
title: "Matrices de parámetros (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- parameter arrays [Visual Basic], about parameter arrays
- ParamArray keyword [Visual Basic], parameter arrays
- Visual Basic code, procedures
- parameters [Visual Basic], parameter arrays
- arguments [Visual Basic], parameter arrays
- procedures [Visual Basic], indefinite number of argument values
- arrays [Visual Basic], parameter arrays
ms.assetid: c43edfae-9114-4096-9ebc-8c5c957a1067
caps.latest.revision: "26"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8ca2b5f02ac4fb3eb613488c8a9852eb2aa4ce5d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="parameter-arrays-visual-basic"></a><span data-ttu-id="746ec-102">Matrices de parámetros (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="746ec-102">Parameter Arrays (Visual Basic)</span></span>
<span data-ttu-id="746ec-103">Por lo general, no se puede llamar a un procedimiento con más argumentos de la declaración de procedimiento especifica.</span><span class="sxs-lookup"><span data-stu-id="746ec-103">Usually, you cannot call a procedure with more arguments than the procedure declaration specifies.</span></span> <span data-ttu-id="746ec-104">Si necesita un número indefinido de argumentos, puede declarar un *matriz de parámetros*, lo que permite que un procedimiento aceptar una matriz de valores para un parámetro.</span><span class="sxs-lookup"><span data-stu-id="746ec-104">When you need an indefinite number of arguments, you can declare a *parameter array*, which allows a procedure to accept an array of values for a parameter.</span></span> <span data-ttu-id="746ec-105">No es necesario saber el número de elementos de la matriz de parámetros cuando se define el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="746ec-105">You do not have to know the number of elements in the parameter array when you define the procedure.</span></span> <span data-ttu-id="746ec-106">El tamaño de la matriz se determina individualmente por cada llamada al procedimiento.</span><span class="sxs-lookup"><span data-stu-id="746ec-106">The array size is determined individually by each call to the procedure.</span></span>  
  
## <a name="declaring-a-paramarray"></a><span data-ttu-id="746ec-107">Declarar una matriz de parámetros</span><span class="sxs-lookup"><span data-stu-id="746ec-107">Declaring a ParamArray</span></span>  
 <span data-ttu-id="746ec-108">Usa el [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) palabra clave para denotar una matriz de parámetros en la lista de parámetros.</span><span class="sxs-lookup"><span data-stu-id="746ec-108">You use the [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) keyword to denote a parameter array in the parameter list.</span></span> <span data-ttu-id="746ec-109">Se aplican las siguientes reglas:</span><span class="sxs-lookup"><span data-stu-id="746ec-109">The following rules apply:</span></span>  
  
-   <span data-ttu-id="746ec-110">Un procedimiento puede definir solo una matriz de parámetros y debe ser el último parámetro en la definición del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="746ec-110">A procedure can define only one parameter array, and it must be the last parameter in the procedure definition.</span></span>  
  
-   <span data-ttu-id="746ec-111">La matriz de parámetros debe pasarse por valor.</span><span class="sxs-lookup"><span data-stu-id="746ec-111">The parameter array must be passed by value.</span></span> <span data-ttu-id="746ec-112">Es conveniente incluir explícitamente una práctica de programación la [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) palabra clave en la definición del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="746ec-112">It is good programming practice to explicitly include the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) keyword in the procedure definition.</span></span>  
  
-   <span data-ttu-id="746ec-113">La matriz de parámetros es opcional de forma automática.</span><span class="sxs-lookup"><span data-stu-id="746ec-113">The parameter array is automatically optional.</span></span> <span data-ttu-id="746ec-114">Su valor predeterminado es una matriz unidimensional vacía del tipo de elemento de la matriz de parámetros.</span><span class="sxs-lookup"><span data-stu-id="746ec-114">Its default value is an empty one-dimensional array of the parameter array's element type.</span></span>  
  
-   <span data-ttu-id="746ec-115">Todos los parámetros que preceden a la matriz de parámetros deben ser obligatorios.</span><span class="sxs-lookup"><span data-stu-id="746ec-115">All parameters preceding the parameter array must be required.</span></span> <span data-ttu-id="746ec-116">La matriz de parámetros debe ser el único parámetro opcional.</span><span class="sxs-lookup"><span data-stu-id="746ec-116">The parameter array must be the only optional parameter.</span></span>  
  
## <a name="calling-a-paramarray"></a><span data-ttu-id="746ec-117">Llamar a una matriz de parámetros</span><span class="sxs-lookup"><span data-stu-id="746ec-117">Calling a ParamArray</span></span>  
 <span data-ttu-id="746ec-118">Cuando se llama a un procedimiento que define una matriz de parámetros, puede proporcionar el argumento en cualquiera de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="746ec-118">When you call a procedure that defines a parameter array, you can supply the argument in any one of the following ways:</span></span>  
  
-   <span data-ttu-id="746ec-119">Ninguno, es decir, puede omitir el [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) argumento.</span><span class="sxs-lookup"><span data-stu-id="746ec-119">Nothing — that is, you can omit the [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) argument.</span></span> <span data-ttu-id="746ec-120">En este caso, se pasa una matriz vacía al procedimiento.</span><span class="sxs-lookup"><span data-stu-id="746ec-120">In this case, an empty array is passed to the procedure.</span></span> <span data-ttu-id="746ec-121">También puede pasar la [nada](../../../../visual-basic/language-reference/nothing.md) (palabra clave), con el mismo efecto.</span><span class="sxs-lookup"><span data-stu-id="746ec-121">You can also pass the [Nothing](../../../../visual-basic/language-reference/nothing.md) keyword, with the same effect.</span></span>  
  
-   <span data-ttu-id="746ec-122">Una lista de un número arbitrario de argumentos, separados por comas.</span><span class="sxs-lookup"><span data-stu-id="746ec-122">A list of an arbitrary number of arguments, separated by commas.</span></span> <span data-ttu-id="746ec-123">El tipo de datos de cada argumento debe ser implícitamente convertible a la `ParamArray` tipo de elemento.</span><span class="sxs-lookup"><span data-stu-id="746ec-123">The data type of each argument must be implicitly convertible to the `ParamArray` element type.</span></span>  
  
-   <span data-ttu-id="746ec-124">Una matriz con el mismo tipo de elemento como tipo de elemento de la matriz de parámetros.</span><span class="sxs-lookup"><span data-stu-id="746ec-124">An array with the same element type as the parameter array's element type.</span></span>  
  
 <span data-ttu-id="746ec-125">En todos los casos, el código dentro del procedimiento trata la matriz de parámetros como una matriz unidimensional con elementos del mismo tipo de datos como el `ParamArray` tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="746ec-125">In all cases, the code within the procedure treats the parameter array as a one-dimensional array with elements of the same data type as the `ParamArray` data type.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="746ec-126">Cuando se trabaja con una matriz que puede ser excesivamente grande, se corre el riesgo de saturar alguna capacidad interna de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="746ec-126">Whenever you deal with an array which can be indefinitely large, there is a risk of overrunning some internal capacity of your application.</span></span> <span data-ttu-id="746ec-127">Si acepta una matriz de parámetros, debe comprobar el tamaño de la matriz que el código que realiza la llamada pasa a él.</span><span class="sxs-lookup"><span data-stu-id="746ec-127">If you accept a parameter array, you should test for the size of the array that the calling code passed to it.</span></span> <span data-ttu-id="746ec-128">Siga los pasos apropiados si es demasiado grande para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="746ec-128">Take appropriate steps if it is too large for your application.</span></span> <span data-ttu-id="746ec-129">Para obtener más información, consulte [matrices](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="746ec-129">For more information, see [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="746ec-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="746ec-130">Example</span></span>  
 <span data-ttu-id="746ec-131">En el ejemplo siguiente se define y llama a la función `calcSum`.</span><span class="sxs-lookup"><span data-stu-id="746ec-131">The following example defines and calls the function `calcSum`.</span></span> <span data-ttu-id="746ec-132">El `ParamArray` modificador para el parámetro `args` permite que la función aceptar un número variable de argumentos.</span><span class="sxs-lookup"><span data-stu-id="746ec-132">The `ParamArray` modifier for the parameter `args` enables the function to accept a variable number of arguments.</span></span>  
  
 [!code-vb[VbVbalrStatements#26](../../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/parameter-arrays_1.vb)]  
  
 <span data-ttu-id="746ec-133">En el ejemplo siguiente se define un procedimiento con una matriz de parámetros y escribe los valores de todos los elementos de matriz que se pasa a la matriz de parámetros.</span><span class="sxs-lookup"><span data-stu-id="746ec-133">The following example defines a procedure with a parameter array, and outputs the values of all the array elements passed to the parameter array.</span></span>  
  
 [!code-vb[VbVbcnProcedures#48](./codesnippet/VisualBasic/parameter-arrays_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#49](./codesnippet/VisualBasic/parameter-arrays_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="746ec-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="746ec-134">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Information.UBound%2A>  
 [<span data-ttu-id="746ec-135">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="746ec-135">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="746ec-136">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="746ec-136">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="746ec-137">Paso de argumentos por valor y por referencia</span><span class="sxs-lookup"><span data-stu-id="746ec-137">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="746ec-138">Paso de argumentos por posición o por nombre</span><span class="sxs-lookup"><span data-stu-id="746ec-138">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)  
 [<span data-ttu-id="746ec-139">Parámetros opcionales</span><span class="sxs-lookup"><span data-stu-id="746ec-139">Optional Parameters</span></span>](./optional-parameters.md)  
 [<span data-ttu-id="746ec-140">Sobrecarga de procedimientos</span><span class="sxs-lookup"><span data-stu-id="746ec-140">Procedure Overloading</span></span>](./procedure-overloading.md)  
 [<span data-ttu-id="746ec-141">Matrices</span><span class="sxs-lookup"><span data-stu-id="746ec-141">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [<span data-ttu-id="746ec-142">Opcional</span><span class="sxs-lookup"><span data-stu-id="746ec-142">Optional</span></span>](../../../../visual-basic/language-reference/modifiers/optional.md)
