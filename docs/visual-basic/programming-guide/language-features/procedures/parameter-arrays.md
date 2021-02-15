---
description: 'Más información sobre: matrices de parámetros (Visual Basic)'
title: Matrices de parámetros
ms.date: 07/20/2015
helpviewer_keywords:
- parameter arrays [Visual Basic], about parameter arrays
- ParamArray keyword [Visual Basic], parameter arrays
- Visual Basic code, procedures
- parameters [Visual Basic], parameter arrays
- arguments [Visual Basic], parameter arrays
- procedures [Visual Basic], indefinite number of argument values
- arrays [Visual Basic], parameter arrays
ms.assetid: c43edfae-9114-4096-9ebc-8c5c957a1067
ms.openlocfilehash: e71524d9d62f0ece3a8310934eba15e9db16aaa1
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100427588"
---
# <a name="parameter-arrays-visual-basic"></a><span data-ttu-id="f90ba-103">Matrices de parámetros (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f90ba-103">Parameter Arrays (Visual Basic)</span></span>

<span data-ttu-id="f90ba-104">Normalmente, no se puede llamar a un procedimiento con más argumentos de los especificados en la declaración de procedimiento.</span><span class="sxs-lookup"><span data-stu-id="f90ba-104">Usually, you cannot call a procedure with more arguments than the procedure declaration specifies.</span></span> <span data-ttu-id="f90ba-105">Si necesita un número indefinido de argumentos, puede declarar una *matriz de parámetros*, que permite que un procedimiento acepte una matriz de valores para un parámetro.</span><span class="sxs-lookup"><span data-stu-id="f90ba-105">When you need an indefinite number of arguments, you can declare a *parameter array*, which allows a procedure to accept an array of values for a parameter.</span></span> <span data-ttu-id="f90ba-106">No es necesario conocer el número de elementos de la matriz de parámetros al definir el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="f90ba-106">You do not have to know the number of elements in the parameter array when you define the procedure.</span></span> <span data-ttu-id="f90ba-107">Cada llamada al procedimiento determina el tamaño de la matriz de forma individual.</span><span class="sxs-lookup"><span data-stu-id="f90ba-107">The array size is determined individually by each call to the procedure.</span></span>  
  
## <a name="declaring-a-paramarray"></a><span data-ttu-id="f90ba-108">Declaración de ParamArray</span><span class="sxs-lookup"><span data-stu-id="f90ba-108">Declaring a ParamArray</span></span>  

 <span data-ttu-id="f90ba-109">La palabra clave [ParamArray](../../../language-reference/modifiers/paramarray.md) se utiliza para denotar una matriz de parámetros en la lista de parámetros.</span><span class="sxs-lookup"><span data-stu-id="f90ba-109">You use the [ParamArray](../../../language-reference/modifiers/paramarray.md) keyword to denote a parameter array in the parameter list.</span></span> <span data-ttu-id="f90ba-110">Se aplican las reglas siguientes:</span><span class="sxs-lookup"><span data-stu-id="f90ba-110">The following rules apply:</span></span>  
  
- <span data-ttu-id="f90ba-111">Un procedimiento solo puede definir una matriz de parámetros y debe ser el último parámetro de la definición de procedimiento.</span><span class="sxs-lookup"><span data-stu-id="f90ba-111">A procedure can define only one parameter array, and it must be the last parameter in the procedure definition.</span></span>  
  
- <span data-ttu-id="f90ba-112">La matriz de parámetros debe pasarse por valor.</span><span class="sxs-lookup"><span data-stu-id="f90ba-112">The parameter array must be passed by value.</span></span> <span data-ttu-id="f90ba-113">Se recomienda incluir explícitamente la palabra clave [ByVal](../../../language-reference/modifiers/byval.md) en la definición de procedimiento.</span><span class="sxs-lookup"><span data-stu-id="f90ba-113">It is good programming practice to explicitly include the [ByVal](../../../language-reference/modifiers/byval.md) keyword in the procedure definition.</span></span>  
  
- <span data-ttu-id="f90ba-114">La matriz de parámetros es opcional de forma automática.</span><span class="sxs-lookup"><span data-stu-id="f90ba-114">The parameter array is automatically optional.</span></span> <span data-ttu-id="f90ba-115">Su valor predeterminado es una matriz unidimensional vacía del tipo de elemento de la matriz de parámetros.</span><span class="sxs-lookup"><span data-stu-id="f90ba-115">Its default value is an empty one-dimensional array of the parameter array's element type.</span></span>  
  
- <span data-ttu-id="f90ba-116">Deben ser necesarios todos los parámetros que preceden a la matriz de parámetros.</span><span class="sxs-lookup"><span data-stu-id="f90ba-116">All parameters preceding the parameter array must be required.</span></span> <span data-ttu-id="f90ba-117">La matriz de parámetros debe ser el único parámetro opcional.</span><span class="sxs-lookup"><span data-stu-id="f90ba-117">The parameter array must be the only optional parameter.</span></span>  
  
## <a name="calling-a-paramarray"></a><span data-ttu-id="f90ba-118">Llamar a ParamArray</span><span class="sxs-lookup"><span data-stu-id="f90ba-118">Calling a ParamArray</span></span>  

 <span data-ttu-id="f90ba-119">Cuando se llama a un procedimiento que define una matriz de parámetros, se puede proporcionar el argumento de cualquiera de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="f90ba-119">When you call a procedure that defines a parameter array, you can supply the argument in any one of the following ways:</span></span>  
  
- <span data-ttu-id="f90ba-120">Nothing, es decir, puede omitir el argumento [ParamArray](../../../language-reference/modifiers/paramarray.md) .</span><span class="sxs-lookup"><span data-stu-id="f90ba-120">Nothing — that is, you can omit the [ParamArray](../../../language-reference/modifiers/paramarray.md) argument.</span></span> <span data-ttu-id="f90ba-121">En este caso, se pasa una matriz vacía al procedimiento.</span><span class="sxs-lookup"><span data-stu-id="f90ba-121">In this case, an empty array is passed to the procedure.</span></span> <span data-ttu-id="f90ba-122">Si se pasa explícitamente la palabra clave [Nothing](../../../language-reference/nothing.md) , se pasa una matriz null al procedimiento y se puede producir una excepción NullReferenceException si el procedimiento llamado no comprueba esta condición.</span><span class="sxs-lookup"><span data-stu-id="f90ba-122">If you explicitly pass the [Nothing](../../../language-reference/nothing.md) keyword, a null array is passed to the procedure and may result in a NullReferenceException if the called procedure does not check for this condition.</span></span>
  
- <span data-ttu-id="f90ba-123">Una lista de un número arbitrario de argumentos, separados por comas.</span><span class="sxs-lookup"><span data-stu-id="f90ba-123">A list of an arbitrary number of arguments, separated by commas.</span></span> <span data-ttu-id="f90ba-124">El tipo de datos de cada argumento se debe poder convertir implícitamente al `ParamArray` tipo de elemento.</span><span class="sxs-lookup"><span data-stu-id="f90ba-124">The data type of each argument must be implicitly convertible to the `ParamArray` element type.</span></span>  
  
- <span data-ttu-id="f90ba-125">Matriz con el mismo tipo de elemento que el tipo de elemento de la matriz de parámetros.</span><span class="sxs-lookup"><span data-stu-id="f90ba-125">An array with the same element type as the parameter array's element type.</span></span>  
  
 <span data-ttu-id="f90ba-126">En todos los casos, el código del procedimiento trata la matriz de parámetros como una matriz unidimensional con elementos del mismo tipo de datos que el `ParamArray` tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="f90ba-126">In all cases, the code within the procedure treats the parameter array as a one-dimensional array with elements of the same data type as the `ParamArray` data type.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="f90ba-127">Siempre que se trata de una matriz que puede ser indefinidamente grande, existe el riesgo de que se produzca una gran cantidad de capacidad interna de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f90ba-127">Whenever you deal with an array which can be indefinitely large, there is a risk of overrunning some internal capacity of your application.</span></span> <span data-ttu-id="f90ba-128">Si acepta una matriz de parámetros, debe probar el tamaño de la matriz que le ha pasado el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="f90ba-128">If you accept a parameter array, you should test for the size of the array that the calling code passed to it.</span></span> <span data-ttu-id="f90ba-129">Siga los pasos adecuados si es demasiado grande para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f90ba-129">Take appropriate steps if it is too large for your application.</span></span> <span data-ttu-id="f90ba-130">Para más información, consulte [Matrices](../arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="f90ba-130">For more information, see [Arrays](../arrays/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f90ba-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f90ba-131">Example</span></span>  

 <span data-ttu-id="f90ba-132">En el ejemplo siguiente se define y se llama a la función `calcSum` .</span><span class="sxs-lookup"><span data-stu-id="f90ba-132">The following example defines and calls the function `calcSum`.</span></span> <span data-ttu-id="f90ba-133">El `ParamArray` modificador del parámetro `args` permite que la función acepte un número variable de argumentos.</span><span class="sxs-lookup"><span data-stu-id="f90ba-133">The `ParamArray` modifier for the parameter `args` enables the function to accept a variable number of arguments.</span></span>  
  
 [!code-vb[VbVbalrStatements#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#26)]  
  
 <span data-ttu-id="f90ba-134">En el ejemplo siguiente se define un procedimiento con una matriz de parámetros y se generan los valores de todos los elementos de matriz pasados a la matriz de parámetros.</span><span class="sxs-lookup"><span data-stu-id="f90ba-134">The following example defines a procedure with a parameter array, and outputs the values of all the array elements passed to the parameter array.</span></span>  
  
 [!code-vb[VbVbcnProcedures#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#48)]  
  
 [!code-vb[VbVbcnProcedures#49](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#49)]  
  
## <a name="see-also"></a><span data-ttu-id="f90ba-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f90ba-135">See also</span></span>

- <xref:Microsoft.VisualBasic.Information.UBound%2A>
- [<span data-ttu-id="f90ba-136">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="f90ba-136">Procedures</span></span>](./index.md)
- [<span data-ttu-id="f90ba-137">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="f90ba-137">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="f90ba-138">Pasar argumentos por valor y por referencia</span><span class="sxs-lookup"><span data-stu-id="f90ba-138">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="f90ba-139">Paso de argumentos por posición o por nombre</span><span class="sxs-lookup"><span data-stu-id="f90ba-139">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="f90ba-140">Parámetros opcionales</span><span class="sxs-lookup"><span data-stu-id="f90ba-140">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="f90ba-141">Sobrecarga de procedimientos</span><span class="sxs-lookup"><span data-stu-id="f90ba-141">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="f90ba-142">Matrices</span><span class="sxs-lookup"><span data-stu-id="f90ba-142">Arrays</span></span>](../arrays/index.md)
- [<span data-ttu-id="f90ba-143">Opcional</span><span class="sxs-lookup"><span data-stu-id="f90ba-143">Optional</span></span>](../../../language-reference/modifiers/optional.md)
