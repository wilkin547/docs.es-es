---
description: 'Más información acerca de: consideraciones sobre la sobrecarga de procedimientos (Visual Basic)'
title: Consideraciones sobre la sobrecarga de procedimientos
ms.date: 07/20/2015
helpviewer_keywords:
- signatures [Visual Basic], ParamArray arguments
- ParamArray keyword [Visual Basic], parameter arrays
- ParamArray keyword [Visual Basic], arguments and signatures
- function overloading [Visual Basic], implicit overloads for ParamArray
- ParamArray keyword [Visual Basic], signatures
- Visual Basic code, procedures
- arguments [Visual Basic], parameter arrays
- procedures [Visual Basic], overloading
- parameters [Visual Basic], lists
- function overloading [Visual Basic], typeless programming
- typeless programming
- function overloading [Visual Basic], restrictions
- arguments [Visual Basic], optional
- optional arguments [Visual Basic], overloading
- signatures [Visual Basic], procedure
- parameter lists [Visual Basic]
- parameter arrays [Visual Basic], overloading arguments
- Visual Basic code, parameter lists
- procedure overloading [Visual Basic], considerations
- Option Explicit statement [Visual Basic]
- restrictions [Visual Basic], overloading procedures
- procedures [Visual Basic], parameter lists
ms.assetid: a2001248-10d0-42c5-b0ce-eeedc987319f
ms.openlocfilehash: ee6dc0ce23f0706f52ac58673d37d1b72936d2bc
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100472623"
---
# <a name="considerations-in-overloading-procedures-visual-basic"></a><span data-ttu-id="c0c7b-103">Consideraciones sobre la sobrecarga de procedimientos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c0c7b-103">Considerations in Overloading Procedures (Visual Basic)</span></span>

<span data-ttu-id="c0c7b-104">Al sobrecargar un procedimiento, debe usar una *firma* diferente para cada versión sobrecargada.</span><span class="sxs-lookup"><span data-stu-id="c0c7b-104">When you overload a procedure, you must use a different *signature* for each overloaded version.</span></span> <span data-ttu-id="c0c7b-105">Normalmente, esto significa que cada versión debe especificar una lista de parámetros diferente.</span><span class="sxs-lookup"><span data-stu-id="c0c7b-105">This usually means each version must specify a different parameter list.</span></span> <span data-ttu-id="c0c7b-106">Para obtener más información, vea "firma diferente" en [sobrecarga de procedimientos](./procedure-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="c0c7b-106">For more information, see "Different Signature" in [Procedure Overloading](./procedure-overloading.md).</span></span>  
  
 <span data-ttu-id="c0c7b-107">Puede sobrecargar un `Function` procedimiento con un `Sub` procedimiento y viceversa, siempre que tengan firmas diferentes.</span><span class="sxs-lookup"><span data-stu-id="c0c7b-107">You can overload a `Function` procedure with a `Sub` procedure, and vice versa, provided they have different signatures.</span></span> <span data-ttu-id="c0c7b-108">Dos sobrecargas no pueden diferir solo en que una tenga un valor devuelto y la otra no.</span><span class="sxs-lookup"><span data-stu-id="c0c7b-108">Two overloads cannot differ only in that one has a return value and the other does not.</span></span>  
  
 <span data-ttu-id="c0c7b-109">Puede sobrecargar una propiedad de la misma manera que sobrecarga un procedimiento y con las mismas restricciones.</span><span class="sxs-lookup"><span data-stu-id="c0c7b-109">You can overload a property the same way you overload a procedure, and with the same restrictions.</span></span> <span data-ttu-id="c0c7b-110">Sin embargo, no se puede sobrecargar un procedimiento con una propiedad, o viceversa.</span><span class="sxs-lookup"><span data-stu-id="c0c7b-110">However, you cannot overload a procedure with a property, or vice versa.</span></span>  
  
## <a name="alternatives-to-overloaded-versions"></a><span data-ttu-id="c0c7b-111">Alternativas a las versiones sobrecargadas</span><span class="sxs-lookup"><span data-stu-id="c0c7b-111">Alternatives to Overloaded Versions</span></span>  

 <span data-ttu-id="c0c7b-112">A veces tiene alternativas a las versiones sobrecargadas, especialmente cuando la presencia de argumentos es opcional o su número es variable.</span><span class="sxs-lookup"><span data-stu-id="c0c7b-112">You sometimes have alternatives to overloaded versions, particularly when the presence of arguments is optional or their number is variable.</span></span>  
  
 <span data-ttu-id="c0c7b-113">Tenga en cuenta que los argumentos opcionales no se admiten necesariamente en todos los lenguajes, y las matrices de parámetros se limitan a Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c0c7b-113">Keep in mind that optional arguments are not necessarily supported by all languages, and parameter arrays are limited to Visual Basic.</span></span> <span data-ttu-id="c0c7b-114">Si está escribiendo un procedimiento que es probable que se llame desde el código escrito en cualquiera de los distintos lenguajes, las versiones sobrecargadas ofrecen la máxima flexibilidad.</span><span class="sxs-lookup"><span data-stu-id="c0c7b-114">If you are writing a procedure that is likely to be called from code written in any of several different languages, overloaded versions offer the greatest flexibility.</span></span>  
  
### <a name="overloads-and-optional-arguments"></a><span data-ttu-id="c0c7b-115">Sobrecargas y argumentos opcionales</span><span class="sxs-lookup"><span data-stu-id="c0c7b-115">Overloads and Optional Arguments</span></span>  

 <span data-ttu-id="c0c7b-116">Cuando el código de llamada puede proporcionar u omitir uno o más argumentos de manera opcional, puede definir varias versiones sobrecargadas o usar parámetros opcionales.</span><span class="sxs-lookup"><span data-stu-id="c0c7b-116">When the calling code can optionally supply or omit one or more arguments, you can define multiple overloaded versions or use optional parameters.</span></span>  
  
#### <a name="when-to-use-overloaded-versions"></a><span data-ttu-id="c0c7b-117">Cuándo usar versiones sobrecargadas</span><span class="sxs-lookup"><span data-stu-id="c0c7b-117">When to Use Overloaded Versions</span></span>  

 <span data-ttu-id="c0c7b-118">Puede considerar la posibilidad de definir una serie de versiones sobrecargadas en los casos siguientes:</span><span class="sxs-lookup"><span data-stu-id="c0c7b-118">You can consider defining a series of overloaded versions in the following cases:</span></span>  
  
- <span data-ttu-id="c0c7b-119">La lógica en el código del procedimiento es significativamente diferente en función de si el código de llamada proporciona un argumento opcional o no.</span><span class="sxs-lookup"><span data-stu-id="c0c7b-119">The logic in the procedure code is significantly different depending on whether the calling code supplies an optional argument or not.</span></span>  
  
- <span data-ttu-id="c0c7b-120">El código de procedimiento no puede comprobar de forma confiable si el código de llamada ha proporcionado un argumento opcional.</span><span class="sxs-lookup"><span data-stu-id="c0c7b-120">The procedure code cannot reliably test whether the calling code has supplied an optional argument.</span></span> <span data-ttu-id="c0c7b-121">Este es el caso, por ejemplo, si no hay ningún candidato posible para un valor predeterminado que el código de llamada no se pudiera esperar proporcionar.</span><span class="sxs-lookup"><span data-stu-id="c0c7b-121">This is the case, for example, if there is no possible candidate for a default value that the calling code could not be expected to supply.</span></span>  
  
#### <a name="when-to-use-optional-parameters"></a><span data-ttu-id="c0c7b-122">Cuándo usar parámetros opcionales</span><span class="sxs-lookup"><span data-stu-id="c0c7b-122">When to Use Optional Parameters</span></span>  

 <span data-ttu-id="c0c7b-123">Podría preferir uno o varios parámetros opcionales en los casos siguientes:</span><span class="sxs-lookup"><span data-stu-id="c0c7b-123">You might prefer one or more optional parameters in the following cases:</span></span>  
  
- <span data-ttu-id="c0c7b-124">La única acción necesaria cuando el código de llamada no proporciona un argumento opcional es establecer el parámetro en un valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="c0c7b-124">The only required action when the calling code does not supply an optional argument is to set the parameter to a default value.</span></span> <span data-ttu-id="c0c7b-125">En tal caso, el código de procedimiento puede ser menos complicado si se define una versión única con uno o más `Optional` parámetros.</span><span class="sxs-lookup"><span data-stu-id="c0c7b-125">In such a case, the procedure code can be less complicated if you define a single version with one or more `Optional` parameters.</span></span>  
  
 <span data-ttu-id="c0c7b-126">Para obtener más información, vea [parámetros opcionales](./optional-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="c0c7b-126">For more information, see [Optional Parameters](./optional-parameters.md).</span></span>  
  
### <a name="overloads-and-paramarrays"></a><span data-ttu-id="c0c7b-127">Sobrecargas y ParamArray</span><span class="sxs-lookup"><span data-stu-id="c0c7b-127">Overloads and ParamArrays</span></span>  

 <span data-ttu-id="c0c7b-128">Cuando el código de llamada puede pasar un número variable de argumentos, puede definir varias versiones sobrecargadas o utilizar una matriz de parámetros.</span><span class="sxs-lookup"><span data-stu-id="c0c7b-128">When the calling code can pass a variable number of arguments, you can define multiple overloaded versions or use a parameter array.</span></span>  
  
#### <a name="when-to-use-overloaded-versions"></a><span data-ttu-id="c0c7b-129">Cuándo usar versiones sobrecargadas</span><span class="sxs-lookup"><span data-stu-id="c0c7b-129">When to Use Overloaded Versions</span></span>  

 <span data-ttu-id="c0c7b-130">Puede considerar la posibilidad de definir una serie de versiones sobrecargadas en los casos siguientes:</span><span class="sxs-lookup"><span data-stu-id="c0c7b-130">You can consider defining a series of overloaded versions in the following cases:</span></span>  
  
- <span data-ttu-id="c0c7b-131">Sabe que el código de llamada nunca pasa más de un número pequeño de valores a la matriz de parámetros.</span><span class="sxs-lookup"><span data-stu-id="c0c7b-131">You know that the calling code never passes more than a small number of values to the parameter array.</span></span>  
  
- <span data-ttu-id="c0c7b-132">La lógica en el código del procedimiento es significativamente diferente en función del número de valores que pase el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="c0c7b-132">The logic in the procedure code is significantly different depending on how many values the calling code passes.</span></span>  
  
- <span data-ttu-id="c0c7b-133">El código de llamada puede pasar valores de tipos de datos diferentes.</span><span class="sxs-lookup"><span data-stu-id="c0c7b-133">The calling code can pass values of different data types.</span></span>  
  
#### <a name="when-to-use-a-parameter-array"></a><span data-ttu-id="c0c7b-134">Cuándo usar una matriz de parámetros</span><span class="sxs-lookup"><span data-stu-id="c0c7b-134">When to Use a Parameter Array</span></span>  

 <span data-ttu-id="c0c7b-135">Un parámetro se sirve mejor `ParamArray` en los casos siguientes:</span><span class="sxs-lookup"><span data-stu-id="c0c7b-135">You are better served by a `ParamArray` parameter in the following cases:</span></span>  
  
- <span data-ttu-id="c0c7b-136">No es posible predecir cuántos valores puede pasar el código de llamada a la matriz de parámetros y podría ser un número grande.</span><span class="sxs-lookup"><span data-stu-id="c0c7b-136">You are not able to predict how many values the calling code can pass to the parameter array, and it could be a large number.</span></span>  
  
- <span data-ttu-id="c0c7b-137">La lógica del procedimiento se presta a recorrer en iteración todos los valores que pasa el código que realiza la llamada, con lo que se realizan esencialmente las mismas operaciones en cada valor.</span><span class="sxs-lookup"><span data-stu-id="c0c7b-137">The procedure logic lends itself to iterating through all the values the calling code passes, performing essentially the same operations on every value.</span></span>  
  
 <span data-ttu-id="c0c7b-138">Para obtener más información, consulte [matrices de parámetros](./parameter-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="c0c7b-138">For more information, see [Parameter Arrays](./parameter-arrays.md).</span></span>  
  
## <a name="implicit-overloads-for-optional-parameters"></a><span data-ttu-id="c0c7b-139">Sobrecargas implícitas para los parámetros opcionales</span><span class="sxs-lookup"><span data-stu-id="c0c7b-139">Implicit Overloads for Optional Parameters</span></span>  

 <span data-ttu-id="c0c7b-140">Un procedimiento con un parámetro [opcional](../../../language-reference/modifiers/optional.md) equivale a dos procedimientos sobrecargados, uno con el parámetro opcional y otro sin él.</span><span class="sxs-lookup"><span data-stu-id="c0c7b-140">A procedure with an [Optional](../../../language-reference/modifiers/optional.md) parameter is equivalent to two overloaded procedures, one with the optional parameter and one without it.</span></span> <span data-ttu-id="c0c7b-141">No se puede sobrecargar este procedimiento con una lista de parámetros correspondiente a cualquiera de ellos.</span><span class="sxs-lookup"><span data-stu-id="c0c7b-141">You cannot overload such a procedure with a parameter list corresponding to either of these.</span></span> <span data-ttu-id="c0c7b-142">Las declaraciones siguientes muestran esto.</span><span class="sxs-lookup"><span data-stu-id="c0c7b-142">The following declarations illustrate this.</span></span>  
  
 [!code-vb[VbVbcnProcedures#58](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#58)]  
  
 [!code-vb[VbVbcnProcedures#60](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#60)]  
  
 [!code-vb[VbVbcnProcedures#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#61)]  
  
 <span data-ttu-id="c0c7b-143">En el caso de un procedimiento con más de un parámetro opcional, existe un conjunto de sobrecargas IMPLÍCITAS, que llegó a través de una lógica similar a la del ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="c0c7b-143">For a procedure with more than one optional parameter, there is a set of implicit overloads, arrived at by logic similar to that in the preceding example.</span></span>  
  
## <a name="implicit-overloads-for-a-paramarray-parameter"></a><span data-ttu-id="c0c7b-144">Sobrecargas implícitas para un parámetro paramarray</span><span class="sxs-lookup"><span data-stu-id="c0c7b-144">Implicit Overloads for a ParamArray Parameter</span></span>  

 <span data-ttu-id="c0c7b-145">El compilador considera que un procedimiento con un parámetro [ParamArray](../../../language-reference/modifiers/paramarray.md) tiene un número infinito de sobrecargas, que difieren entre sí en lo que el código de llamada pasa a la matriz de parámetros, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="c0c7b-145">The compiler considers a procedure with a [ParamArray](../../../language-reference/modifiers/paramarray.md) parameter to have an infinite number of overloads, differing from each other in what the calling code passes to the parameter array, as follows:</span></span>  
  
- <span data-ttu-id="c0c7b-146">Una sobrecarga para cuando el código de llamada no proporciona un argumento al parámetro `ParamArray`</span><span class="sxs-lookup"><span data-stu-id="c0c7b-146">One overload for when the calling code does not supply an argument to the `ParamArray`</span></span>  
  
- <span data-ttu-id="c0c7b-147">Una sobrecarga para cuando el código de llamada proporciona una matriz unidimensional del `ParamArray` tipo de elemento.</span><span class="sxs-lookup"><span data-stu-id="c0c7b-147">One overload for when the calling code supplies a one-dimensional array of the `ParamArray` element type</span></span>  
  
- <span data-ttu-id="c0c7b-148">Para cada entero positivo, una sobrecarga para cuando el código de llamada proporciona ese número de argumentos, cada uno de los `ParamArray` tipos de elemento.</span><span class="sxs-lookup"><span data-stu-id="c0c7b-148">For every positive integer, one overload for when the calling code supplies that number of arguments, each of the `ParamArray` element type</span></span>  
  
 <span data-ttu-id="c0c7b-149">Las declaraciones siguientes muestran estas sobrecargas implícitas.</span><span class="sxs-lookup"><span data-stu-id="c0c7b-149">The following declarations illustrate these implicit overloads.</span></span>  
  
 [!code-vb[VbVbcnProcedures#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#68)]  
  
 [!code-vb[VbVbcnProcedures#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#70)]  
  
 <span data-ttu-id="c0c7b-150">No se puede sobrecargar este procedimiento con una lista de parámetros que tome una matriz unidimensional para la matriz de parámetros.</span><span class="sxs-lookup"><span data-stu-id="c0c7b-150">You cannot overload such a procedure with a parameter list that takes a one-dimensional array for the parameter array.</span></span> <span data-ttu-id="c0c7b-151">Sin embargo, puede utilizar las firmas de las otras sobrecargas implícitas.</span><span class="sxs-lookup"><span data-stu-id="c0c7b-151">However, you can use the signatures of the other implicit overloads.</span></span> <span data-ttu-id="c0c7b-152">Las declaraciones siguientes muestran esto.</span><span class="sxs-lookup"><span data-stu-id="c0c7b-152">The following declarations illustrate this.</span></span>  
  
 [!code-vb[VbVbcnProcedures#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#71)]  
  
## <a name="typeless-programming-as-an-alternative-to-overloading"></a><span data-ttu-id="c0c7b-153">Programación sin tipos como alternativa a la sobrecarga</span><span class="sxs-lookup"><span data-stu-id="c0c7b-153">Typeless Programming as an Alternative to Overloading</span></span>  

 <span data-ttu-id="c0c7b-154">Si desea permitir que el código de llamada pase tipos de datos diferentes a un parámetro, un enfoque alternativo es la programación sin tipos.</span><span class="sxs-lookup"><span data-stu-id="c0c7b-154">If you want to allow the calling code to pass different data types to a parameter, an alternative approach is typeless programming.</span></span> <span data-ttu-id="c0c7b-155">Puede establecer el modificador de comprobación de tipos en `Off` con la [instrucción Option Strict](../../../language-reference/statements/option-strict-statement.md) o la opción del compilador [-OptionStrict](../../../reference/command-line-compiler/optionstrict.md) .</span><span class="sxs-lookup"><span data-stu-id="c0c7b-155">You can set the type checking switch to `Off` with either the [Option Strict Statement](../../../language-reference/statements/option-strict-statement.md) or the [-optionstrict](../../../reference/command-line-compiler/optionstrict.md) compiler option.</span></span> <span data-ttu-id="c0c7b-156">No es necesario declarar el tipo de datos del parámetro.</span><span class="sxs-lookup"><span data-stu-id="c0c7b-156">Then you do not have to declare the parameter's data type.</span></span> <span data-ttu-id="c0c7b-157">Sin embargo, este enfoque tiene las siguientes desventajas en comparación con la sobrecarga:</span><span class="sxs-lookup"><span data-stu-id="c0c7b-157">However, this approach has the following disadvantages compared to overloading:</span></span>  
  
- <span data-ttu-id="c0c7b-158">La programación sin tipos genera código de ejecución menos eficaz.</span><span class="sxs-lookup"><span data-stu-id="c0c7b-158">Typeless programming produces less efficient execution code.</span></span>  
  
- <span data-ttu-id="c0c7b-159">El procedimiento debe comprobar todos los tipos de datos que prevé que se pasan.</span><span class="sxs-lookup"><span data-stu-id="c0c7b-159">The procedure must test for every data type it anticipates being passed.</span></span>  
  
- <span data-ttu-id="c0c7b-160">El compilador no puede indicar un error si el código de llamada pasa un tipo de datos no admitido por el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="c0c7b-160">The compiler cannot signal an error if the calling code passes a data type that the procedure does not support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0c7b-161">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c0c7b-161">See also</span></span>

- [<span data-ttu-id="c0c7b-162">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="c0c7b-162">Procedures</span></span>](./index.md)
- [<span data-ttu-id="c0c7b-163">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="c0c7b-163">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="c0c7b-164">Solución de problemas de procedimientos</span><span class="sxs-lookup"><span data-stu-id="c0c7b-164">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)
- [<span data-ttu-id="c0c7b-165">Procedimiento para definir varias versiones de un procedimiento</span><span class="sxs-lookup"><span data-stu-id="c0c7b-165">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)
- [<span data-ttu-id="c0c7b-166">Procedimiento para llamar a un procedimiento sobrecargado</span><span class="sxs-lookup"><span data-stu-id="c0c7b-166">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)
- [<span data-ttu-id="c0c7b-167">Procedimiento para sobrecargar un procedimiento que toma parámetros opcionales</span><span class="sxs-lookup"><span data-stu-id="c0c7b-167">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [<span data-ttu-id="c0c7b-168">Procedimiento para sobrecargar un procedimiento que toma un número indefinido de parámetros</span><span class="sxs-lookup"><span data-stu-id="c0c7b-168">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [<span data-ttu-id="c0c7b-169">Overload Resolution</span><span class="sxs-lookup"><span data-stu-id="c0c7b-169">Overload Resolution</span></span>](./overload-resolution.md)
- [<span data-ttu-id="c0c7b-170">Sobrecargas</span><span class="sxs-lookup"><span data-stu-id="c0c7b-170">Overloads</span></span>](../../../language-reference/modifiers/overloads.md)
