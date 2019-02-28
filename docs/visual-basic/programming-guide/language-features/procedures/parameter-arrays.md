---
title: Matrices de parámetros (Visual Basic)
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
ms.openlocfilehash: e059f471f78262320f1968c12192de710876aef4
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56966585"
---
# <a name="parameter-arrays-visual-basic"></a><span data-ttu-id="22b6d-102">Matrices de parámetros (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="22b6d-102">Parameter Arrays (Visual Basic)</span></span>
<span data-ttu-id="22b6d-103">Por lo general, no se puede llamar a un procedimiento con más argumentos de la declaración de procedimiento especifica.</span><span class="sxs-lookup"><span data-stu-id="22b6d-103">Usually, you cannot call a procedure with more arguments than the procedure declaration specifies.</span></span> <span data-ttu-id="22b6d-104">Cuando se necesita un número indefinido de argumentos, se puede declarar un *matriz de parámetros*, lo que permite que un procedimiento aceptar una matriz de valores para un parámetro.</span><span class="sxs-lookup"><span data-stu-id="22b6d-104">When you need an indefinite number of arguments, you can declare a *parameter array*, which allows a procedure to accept an array of values for a parameter.</span></span> <span data-ttu-id="22b6d-105">No es necesario saber el número de elementos de la matriz de parámetros cuando se define el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="22b6d-105">You do not have to know the number of elements in the parameter array when you define the procedure.</span></span> <span data-ttu-id="22b6d-106">El tamaño de la matriz se determina individualmente por cada llamada al procedimiento.</span><span class="sxs-lookup"><span data-stu-id="22b6d-106">The array size is determined individually by each call to the procedure.</span></span>  
  
## <a name="declaring-a-paramarray"></a><span data-ttu-id="22b6d-107">Declarar una matriz de parámetros</span><span class="sxs-lookup"><span data-stu-id="22b6d-107">Declaring a ParamArray</span></span>  
 <span data-ttu-id="22b6d-108">Usa el [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) palabra clave para denotar una matriz de parámetros en la lista de parámetros.</span><span class="sxs-lookup"><span data-stu-id="22b6d-108">You use the [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) keyword to denote a parameter array in the parameter list.</span></span> <span data-ttu-id="22b6d-109">Se aplican las siguientes reglas:</span><span class="sxs-lookup"><span data-stu-id="22b6d-109">The following rules apply:</span></span>  
  
-   <span data-ttu-id="22b6d-110">Un procedimiento puede definir solo una matriz de parámetros y debe ser el último parámetro en la definición del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="22b6d-110">A procedure can define only one parameter array, and it must be the last parameter in the procedure definition.</span></span>  
  
-   <span data-ttu-id="22b6d-111">La matriz de parámetros debe pasarse por valor.</span><span class="sxs-lookup"><span data-stu-id="22b6d-111">The parameter array must be passed by value.</span></span> <span data-ttu-id="22b6d-112">Lo programación es recomendable incluir explícitamente el [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) palabra clave en la definición del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="22b6d-112">It is good programming practice to explicitly include the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) keyword in the procedure definition.</span></span>  
  
-   <span data-ttu-id="22b6d-113">La matriz de parámetros es opcional de forma automática.</span><span class="sxs-lookup"><span data-stu-id="22b6d-113">The parameter array is automatically optional.</span></span> <span data-ttu-id="22b6d-114">Su valor predeterminado es una matriz unidimensional vacía del tipo de elemento de la matriz de parámetros.</span><span class="sxs-lookup"><span data-stu-id="22b6d-114">Its default value is an empty one-dimensional array of the parameter array's element type.</span></span>  
  
-   <span data-ttu-id="22b6d-115">Todos los parámetros que precede a la matriz de parámetros deben ser obligatorios.</span><span class="sxs-lookup"><span data-stu-id="22b6d-115">All parameters preceding the parameter array must be required.</span></span> <span data-ttu-id="22b6d-116">La matriz de parámetros debe ser el único parámetro opcional.</span><span class="sxs-lookup"><span data-stu-id="22b6d-116">The parameter array must be the only optional parameter.</span></span>  
  
## <a name="calling-a-paramarray"></a><span data-ttu-id="22b6d-117">Una llamada a una matriz de parámetros</span><span class="sxs-lookup"><span data-stu-id="22b6d-117">Calling a ParamArray</span></span>  
 <span data-ttu-id="22b6d-118">Cuando se llama a un procedimiento que se define una matriz de parámetros, puede proporcionar el argumento en cualquiera de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="22b6d-118">When you call a procedure that defines a parameter array, you can supply the argument in any one of the following ways:</span></span>  
  
-   <span data-ttu-id="22b6d-119">Nada, es decir, puede omitir el [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) argumento.</span><span class="sxs-lookup"><span data-stu-id="22b6d-119">Nothing — that is, you can omit the [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) argument.</span></span> <span data-ttu-id="22b6d-120">En este caso, se pasa una matriz vacía para el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="22b6d-120">In this case, an empty array is passed to the procedure.</span></span> <span data-ttu-id="22b6d-121">También puede pasar la [nada](../../../../visual-basic/language-reference/nothing.md) palabra clave, con el mismo efecto.</span><span class="sxs-lookup"><span data-stu-id="22b6d-121">You can also pass the [Nothing](../../../../visual-basic/language-reference/nothing.md) keyword, with the same effect.</span></span>  
  
-   <span data-ttu-id="22b6d-122">Una lista de un número arbitrario de argumentos, separados por comas.</span><span class="sxs-lookup"><span data-stu-id="22b6d-122">A list of an arbitrary number of arguments, separated by commas.</span></span> <span data-ttu-id="22b6d-123">El tipo de datos de cada argumento debe ser implícitamente convertible a la `ParamArray` tipo de elemento.</span><span class="sxs-lookup"><span data-stu-id="22b6d-123">The data type of each argument must be implicitly convertible to the `ParamArray` element type.</span></span>  
  
-   <span data-ttu-id="22b6d-124">Una matriz con el mismo tipo de elemento como tipo de elemento de la matriz de parámetros.</span><span class="sxs-lookup"><span data-stu-id="22b6d-124">An array with the same element type as the parameter array's element type.</span></span>  
  
 <span data-ttu-id="22b6d-125">En todos los casos, el código dentro del procedimiento considera la matriz de parámetros como una matriz unidimensional con elementos del mismo tipo de datos como el `ParamArray` tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="22b6d-125">In all cases, the code within the procedure treats the parameter array as a one-dimensional array with elements of the same data type as the `ParamArray` data type.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="22b6d-126">Si se trabaja con una matriz que puede ser excesivamente grande, hay un riesgo de sobrecargar alguna capacidad interna de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="22b6d-126">Whenever you deal with an array which can be indefinitely large, there is a risk of overrunning some internal capacity of your application.</span></span> <span data-ttu-id="22b6d-127">Si acepta una matriz de parámetros, se debe comprobar el tamaño de la matriz que el código que realiza la llamada pasa a él.</span><span class="sxs-lookup"><span data-stu-id="22b6d-127">If you accept a parameter array, you should test for the size of the array that the calling code passed to it.</span></span> <span data-ttu-id="22b6d-128">Si es demasiado grande para su aplicación, tome medidas oportunas.</span><span class="sxs-lookup"><span data-stu-id="22b6d-128">Take appropriate steps if it is too large for your application.</span></span> <span data-ttu-id="22b6d-129">Para obtener más información, consulte [matrices](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="22b6d-129">For more information, see [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="22b6d-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="22b6d-130">Example</span></span>  
 <span data-ttu-id="22b6d-131">El ejemplo siguiente se define y llama a la función `calcSum`.</span><span class="sxs-lookup"><span data-stu-id="22b6d-131">The following example defines and calls the function `calcSum`.</span></span> <span data-ttu-id="22b6d-132">El `ParamArray` modificador para el parámetro `args` permite que la función que acepte un número variable de argumentos.</span><span class="sxs-lookup"><span data-stu-id="22b6d-132">The `ParamArray` modifier for the parameter `args` enables the function to accept a variable number of arguments.</span></span>  
  
 [!code-vb[VbVbalrStatements#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#26)]  
  
 <span data-ttu-id="22b6d-133">El ejemplo siguiente define un procedimiento con una matriz de parámetros y genera los valores de todos los elementos de matriz que se pasa a la matriz de parámetros.</span><span class="sxs-lookup"><span data-stu-id="22b6d-133">The following example defines a procedure with a parameter array, and outputs the values of all the array elements passed to the parameter array.</span></span>  
  
 [!code-vb[VbVbcnProcedures#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#48)]  
  
 [!code-vb[VbVbcnProcedures#49](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#49)]  
  
## <a name="see-also"></a><span data-ttu-id="22b6d-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="22b6d-134">See also</span></span>
- <xref:Microsoft.VisualBasic.Information.UBound%2A>
- [<span data-ttu-id="22b6d-135">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="22b6d-135">Procedures</span></span>](./index.md)
- [<span data-ttu-id="22b6d-136">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="22b6d-136">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="22b6d-137">Paso de argumentos por valor y por referencia</span><span class="sxs-lookup"><span data-stu-id="22b6d-137">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="22b6d-138">Paso de argumentos por posición o por nombre</span><span class="sxs-lookup"><span data-stu-id="22b6d-138">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="22b6d-139">Parámetros opcionales</span><span class="sxs-lookup"><span data-stu-id="22b6d-139">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="22b6d-140">Sobrecarga de procedimientos</span><span class="sxs-lookup"><span data-stu-id="22b6d-140">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="22b6d-141">Matrices</span><span class="sxs-lookup"><span data-stu-id="22b6d-141">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="22b6d-142">Opcional</span><span class="sxs-lookup"><span data-stu-id="22b6d-142">Optional</span></span>](../../../../visual-basic/language-reference/modifiers/optional.md)
