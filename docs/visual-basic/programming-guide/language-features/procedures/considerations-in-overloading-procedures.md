---
title: Consideraciones sobre la sobrecarga de procedimientos (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
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
caps.latest.revision: 26
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ac4bc47f9e781f83c7930efffedd40d9c25c2ec2
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="considerations-in-overloading-procedures-visual-basic"></a><span data-ttu-id="fe5c6-102">Consideraciones sobre la sobrecarga de procedimientos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fe5c6-102">Considerations in Overloading Procedures (Visual Basic)</span></span>
<span data-ttu-id="fe5c6-103">Cuando se sobrecarga un procedimiento, debe usar otro *firma* para cada versión sobrecargada.</span><span class="sxs-lookup"><span data-stu-id="fe5c6-103">When you overload a procedure, you must use a different *signature* for each overloaded version.</span></span> <span data-ttu-id="fe5c6-104">Esto suele significar que cada versión debe especificar una lista de parámetros distinta.</span><span class="sxs-lookup"><span data-stu-id="fe5c6-104">This usually means each version must specify a different parameter list.</span></span> <span data-ttu-id="fe5c6-105">Para obtener más información, vea "Firmas diferentes" en [sobrecarga de procedimientos](./procedure-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="fe5c6-105">For more information, see "Different Signature" in [Procedure Overloading](./procedure-overloading.md).</span></span>  
  
 <span data-ttu-id="fe5c6-106">Puede sobrecargar un `Function` procedimiento con un `Sub` procedimiento y viceversa, siempre tienen firmas diferentes.</span><span class="sxs-lookup"><span data-stu-id="fe5c6-106">You can overload a `Function` procedure with a `Sub` procedure, and vice versa, provided they have different signatures.</span></span> <span data-ttu-id="fe5c6-107">Dos sobrecargas no pueden distinguirse sólo en que una tiene un valor devuelto y el otro no.</span><span class="sxs-lookup"><span data-stu-id="fe5c6-107">Two overloads cannot differ only in that one has a return value and the other does not.</span></span>  
  
 <span data-ttu-id="fe5c6-108">Puede sobrecargar una propiedad del mismo modo que se sobrecarga un procedimiento y con las mismas restricciones.</span><span class="sxs-lookup"><span data-stu-id="fe5c6-108">You can overload a property the same way you overload a procedure, and with the same restrictions.</span></span> <span data-ttu-id="fe5c6-109">Sin embargo, no se pueden sobrecargar un procedimiento con una propiedad, o viceversa.</span><span class="sxs-lookup"><span data-stu-id="fe5c6-109">However, you cannot overload a procedure with a property, or vice versa.</span></span>  
  
## <a name="alternatives-to-overloaded-versions"></a><span data-ttu-id="fe5c6-110">Alternativas a las versiones sobrecargadas</span><span class="sxs-lookup"><span data-stu-id="fe5c6-110">Alternatives to Overloaded Versions</span></span>  
 <span data-ttu-id="fe5c6-111">A veces tienen alternativas a las versiones sobrecargadas, especialmente cuando la presencia de argumentos es opcional o su número es variable.</span><span class="sxs-lookup"><span data-stu-id="fe5c6-111">You sometimes have alternatives to overloaded versions, particularly when the presence of arguments is optional or their number is variable.</span></span>  
  
 <span data-ttu-id="fe5c6-112">Tenga en cuenta que todos los lenguajes no admiten necesariamente los argumentos opcionales y matrices de parámetros están limitadas a Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="fe5c6-112">Keep in mind that optional arguments are not necessarily supported by all languages, and parameter arrays are limited to Visual Basic.</span></span> <span data-ttu-id="fe5c6-113">Si va a escribir un procedimiento que es probable que se llame desde código escrito en cualquiera de varios idiomas, las versiones sobrecargadas ofrecen la máxima flexibilidad.</span><span class="sxs-lookup"><span data-stu-id="fe5c6-113">If you are writing a procedure that is likely to be called from code written in any of several different languages, overloaded versions offer the greatest flexibility.</span></span>  
  
### <a name="overloads-and-optional-arguments"></a><span data-ttu-id="fe5c6-114">Sobrecargas y argumentos opcionales</span><span class="sxs-lookup"><span data-stu-id="fe5c6-114">Overloads and Optional Arguments</span></span>  
 <span data-ttu-id="fe5c6-115">Cuando el código de llamada, opcionalmente, puede proporcionar u omitir uno o más argumentos, puede definir varias versiones sobrecargadas o utilizar parámetros opcionales.</span><span class="sxs-lookup"><span data-stu-id="fe5c6-115">When the calling code can optionally supply or omit one or more arguments, you can define multiple overloaded versions or use optional parameters.</span></span>  
  
#### <a name="when-to-use-overloaded-versions"></a><span data-ttu-id="fe5c6-116">Cuándo utilizar versiones sobrecargadas</span><span class="sxs-lookup"><span data-stu-id="fe5c6-116">When to Use Overloaded Versions</span></span>  
 <span data-ttu-id="fe5c6-117">Se puede pensar en definir una serie de versiones sobrecargadas en los casos siguientes:</span><span class="sxs-lookup"><span data-stu-id="fe5c6-117">You can consider defining a series of overloaded versions in the following cases:</span></span>  
  
-   <span data-ttu-id="fe5c6-118">La lógica en el código de procedimiento es significativamente diferente dependiendo de si el código de llamada proporciona un argumento opcional o no.</span><span class="sxs-lookup"><span data-stu-id="fe5c6-118">The logic in the procedure code is significantly different depending on whether the calling code supplies an optional argument or not.</span></span>  
  
-   <span data-ttu-id="fe5c6-119">El código del procedimiento no puede probar de forma confiable si el código que realiza la llamada ha suministrado un argumento opcional.</span><span class="sxs-lookup"><span data-stu-id="fe5c6-119">The procedure code cannot reliably test whether the calling code has supplied an optional argument.</span></span> <span data-ttu-id="fe5c6-120">Este es el caso, por ejemplo, si no hay ningún candidato posible a un valor predeterminado que el código que realiza la llamada podría no se espera que proporcione.</span><span class="sxs-lookup"><span data-stu-id="fe5c6-120">This is the case, for example, if there is no possible candidate for a default value that the calling code could not be expected to supply.</span></span>  
  
#### <a name="when-to-use-optional-parameters"></a><span data-ttu-id="fe5c6-121">Cuándo utilizar parámetros opcionales</span><span class="sxs-lookup"><span data-stu-id="fe5c6-121">When to Use Optional Parameters</span></span>  
 <span data-ttu-id="fe5c6-122">Es posible que prefiera uno o varios parámetros opcionales en los casos siguientes:</span><span class="sxs-lookup"><span data-stu-id="fe5c6-122">You might prefer one or more optional parameters in the following cases:</span></span>  
  
-   <span data-ttu-id="fe5c6-123">La única acción necesaria cuando el código de llamada no proporciona un argumento opcional es establecer el parámetro en un valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="fe5c6-123">The only required action when the calling code does not supply an optional argument is to set the parameter to a default value.</span></span> <span data-ttu-id="fe5c6-124">En tal caso, el código del procedimiento puede ser menos complicado si define una única versión con uno o varios `Optional` parámetros.</span><span class="sxs-lookup"><span data-stu-id="fe5c6-124">In such a case, the procedure code can be less complicated if you define a single version with one or more `Optional` parameters.</span></span>  
  
 <span data-ttu-id="fe5c6-125">Para obtener más información, consulte [parámetros opcionales](./optional-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="fe5c6-125">For more information, see [Optional Parameters](./optional-parameters.md).</span></span>  
  
### <a name="overloads-and-paramarrays"></a><span data-ttu-id="fe5c6-126">Las sobrecargas y matrices de parámetros</span><span class="sxs-lookup"><span data-stu-id="fe5c6-126">Overloads and ParamArrays</span></span>  
 <span data-ttu-id="fe5c6-127">Cuando el código de llamada puede pasar un número variable de argumentos, puede definir varias versiones sobrecargadas o utilizar una matriz de parámetros.</span><span class="sxs-lookup"><span data-stu-id="fe5c6-127">When the calling code can pass a variable number of arguments, you can define multiple overloaded versions or use a parameter array.</span></span>  
  
#### <a name="when-to-use-overloaded-versions"></a><span data-ttu-id="fe5c6-128">Cuándo utilizar versiones sobrecargadas</span><span class="sxs-lookup"><span data-stu-id="fe5c6-128">When to Use Overloaded Versions</span></span>  
 <span data-ttu-id="fe5c6-129">Se puede pensar en definir una serie de versiones sobrecargadas en los casos siguientes:</span><span class="sxs-lookup"><span data-stu-id="fe5c6-129">You can consider defining a series of overloaded versions in the following cases:</span></span>  
  
-   <span data-ttu-id="fe5c6-130">Sabrá que el código de llamada nunca pasa más de un número pequeño de valores a la matriz de parámetros.</span><span class="sxs-lookup"><span data-stu-id="fe5c6-130">You know that the calling code never passes more than a small number of values to the parameter array.</span></span>  
  
-   <span data-ttu-id="fe5c6-131">La lógica en el código de procedimiento es significativamente diferente dependiendo de cuántos valores que pasa el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="fe5c6-131">The logic in the procedure code is significantly different depending on how many values the calling code passes.</span></span>  
  
-   <span data-ttu-id="fe5c6-132">El código de llamada puede pasar valores de distintos tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="fe5c6-132">The calling code can pass values of different data types.</span></span>  
  
#### <a name="when-to-use-a-parameter-array"></a><span data-ttu-id="fe5c6-133">Cuándo usar una matriz de parámetros</span><span class="sxs-lookup"><span data-stu-id="fe5c6-133">When to Use a Parameter Array</span></span>  
 <span data-ttu-id="fe5c6-134">Se recomienda por un `ParamArray` parámetro en los casos siguientes:</span><span class="sxs-lookup"><span data-stu-id="fe5c6-134">You are better served by a `ParamArray` parameter in the following cases:</span></span>  
  
-   <span data-ttu-id="fe5c6-135">No es posible predecir cuántos valores puede pasar el código que realiza la llamada a la matriz de parámetros, y podría ser un número elevado.</span><span class="sxs-lookup"><span data-stu-id="fe5c6-135">You are not able to predict how many values the calling code can pass to the parameter array, and it could be a large number.</span></span>  
  
-   <span data-ttu-id="fe5c6-136">La lógica del procedimiento se presta a recorrer en iteración todos los valores que pasa el código de llamada, realizar esencialmente las mismas operaciones en cada valor.</span><span class="sxs-lookup"><span data-stu-id="fe5c6-136">The procedure logic lends itself to iterating through all the values the calling code passes, performing essentially the same operations on every value.</span></span>  
  
 <span data-ttu-id="fe5c6-137">Para obtener más información, consulte [matrices de parámetros](./parameter-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="fe5c6-137">For more information, see [Parameter Arrays](./parameter-arrays.md).</span></span>  
  
## <a name="implicit-overloads-for-optional-parameters"></a><span data-ttu-id="fe5c6-138">Sobrecargas implícitas para parámetros opcionales</span><span class="sxs-lookup"><span data-stu-id="fe5c6-138">Implicit Overloads for Optional Parameters</span></span>  
 <span data-ttu-id="fe5c6-139">Un procedimiento con un [opcional](../../../../visual-basic/language-reference/modifiers/optional.md) parámetro es equivalente a dos procedimientos sobrecargados, uno con el parámetro opcional y otro sin él.</span><span class="sxs-lookup"><span data-stu-id="fe5c6-139">A procedure with an [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) parameter is equivalent to two overloaded procedures, one with the optional parameter and one without it.</span></span> <span data-ttu-id="fe5c6-140">No se puede sobrecargar un procedimiento con una lista de parámetros que se corresponda con cualquiera de estos.</span><span class="sxs-lookup"><span data-stu-id="fe5c6-140">You cannot overload such a procedure with a parameter list corresponding to either of these.</span></span> <span data-ttu-id="fe5c6-141">Las declaraciones siguientes ilustran esto.</span><span class="sxs-lookup"><span data-stu-id="fe5c6-141">The following declarations illustrate this.</span></span>  
  
 [!code-vb[VbVbcnProcedures#58](./codesnippet/VisualBasic/considerations-in-overloading-procedures_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#60](./codesnippet/VisualBasic/considerations-in-overloading-procedures_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#61](./codesnippet/VisualBasic/considerations-in-overloading-procedures_3.vb)]  
  
 <span data-ttu-id="fe5c6-142">Para un procedimiento con más de un parámetro opcional, hay un conjunto de sobrecargas implícitas, llegado por una lógica similar al utilizado en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="fe5c6-142">For a procedure with more than one optional parameter, there is a set of implicit overloads, arrived at by logic similar to that in the preceding example.</span></span>  
  
## <a name="implicit-overloads-for-a-paramarray-parameter"></a><span data-ttu-id="fe5c6-143">Sobrecargas implícitas para un parámetro ParamArray.</span><span class="sxs-lookup"><span data-stu-id="fe5c6-143">Implicit Overloads for a ParamArray Parameter</span></span>  
 <span data-ttu-id="fe5c6-144">El compilador considera que un procedimiento con un [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parámetro tenga un número infinito de sobrecargas, que se diferencian entre sí por lo que el código de llamada como se indica a continuación pasa a la matriz de parámetros:</span><span class="sxs-lookup"><span data-stu-id="fe5c6-144">The compiler considers a procedure with a [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parameter to have an infinite number of overloads, differing from each other in what the calling code passes to the parameter array, as follows:</span></span>  
  
-   <span data-ttu-id="fe5c6-145">Una sobrecarga cuando el código de llamada no proporciona ningún argumento a la `ParamArray`</span><span class="sxs-lookup"><span data-stu-id="fe5c6-145">One overload for when the calling code does not supply an argument to the `ParamArray`</span></span>  
  
-   <span data-ttu-id="fe5c6-146">Una sobrecarga cuando el código de llamada proporciona una matriz unidimensional de la `ParamArray` tipo de elemento</span><span class="sxs-lookup"><span data-stu-id="fe5c6-146">One overload for when the calling code supplies a one-dimensional array of the `ParamArray` element type</span></span>  
  
-   <span data-ttu-id="fe5c6-147">Para cada entero positivo, una sobrecarga cuando el código de llamada proporciona ese número de argumentos, cada uno de los `ParamArray` tipo de elemento</span><span class="sxs-lookup"><span data-stu-id="fe5c6-147">For every positive integer, one overload for when the calling code supplies that number of arguments, each of the `ParamArray` element type</span></span>  
  
 <span data-ttu-id="fe5c6-148">Las siguientes declaraciones ilustran estas sobrecargas implícitas.</span><span class="sxs-lookup"><span data-stu-id="fe5c6-148">The following declarations illustrate these implicit overloads.</span></span>  
  
 [!code-vb[VbVbcnProcedures#68](./codesnippet/VisualBasic/considerations-in-overloading-procedures_4.vb)]  
  
 [!code-vb[VbVbcnProcedures#70](./codesnippet/VisualBasic/considerations-in-overloading-procedures_5.vb)]  
  
 <span data-ttu-id="fe5c6-149">No se pueden sobrecargar un procedimiento así con una lista de parámetros que toma una matriz unidimensional de la matriz de parámetros.</span><span class="sxs-lookup"><span data-stu-id="fe5c6-149">You cannot overload such a procedure with a parameter list that takes a one-dimensional array for the parameter array.</span></span> <span data-ttu-id="fe5c6-150">Sin embargo, puede utilizar las firmas de las otras sobrecargas implícitas.</span><span class="sxs-lookup"><span data-stu-id="fe5c6-150">However, you can use the signatures of the other implicit overloads.</span></span> <span data-ttu-id="fe5c6-151">Las declaraciones siguientes ilustran esto.</span><span class="sxs-lookup"><span data-stu-id="fe5c6-151">The following declarations illustrate this.</span></span>  
  
 [!code-vb[VbVbcnProcedures#71](./codesnippet/VisualBasic/considerations-in-overloading-procedures_6.vb)]  
  
## <a name="typeless-programming-as-an-alternative-to-overloading"></a><span data-ttu-id="fe5c6-152">Programación sin tipos como alternativa a la sobrecarga</span><span class="sxs-lookup"><span data-stu-id="fe5c6-152">Typeless Programming as an Alternative to Overloading</span></span>  
 <span data-ttu-id="fe5c6-153">Si desea permitir que el código que realiza la llamada pasar tipos de datos diferentes a un parámetro, un enfoque alternativo es programación sin tipos.</span><span class="sxs-lookup"><span data-stu-id="fe5c6-153">If you want to allow the calling code to pass different data types to a parameter, an alternative approach is typeless programming.</span></span> <span data-ttu-id="fe5c6-154">Puede establecer el tipo de conmutador para la comprobación `Off` con cualquiera el [Option Strict (instrucción)](../../../../visual-basic/language-reference/statements/option-strict-statement.md) o [/optionstrict](../../../../visual-basic/reference/command-line-compiler/optionstrict.md) opción del compilador.</span><span class="sxs-lookup"><span data-stu-id="fe5c6-154">You can set the type checking switch to `Off` with either the [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) or the [/optionstrict](../../../../visual-basic/reference/command-line-compiler/optionstrict.md) compiler option.</span></span> <span data-ttu-id="fe5c6-155">A continuación, no tienes que volver a declarar el tipo de datos del parámetro.</span><span class="sxs-lookup"><span data-stu-id="fe5c6-155">Then you do not have to declare the parameter's data type.</span></span> <span data-ttu-id="fe5c6-156">Sin embargo, este enfoque tiene las siguientes desventajas en comparación con la sobrecarga:</span><span class="sxs-lookup"><span data-stu-id="fe5c6-156">However, this approach has the following disadvantages compared to overloading:</span></span>  
  
-   <span data-ttu-id="fe5c6-157">Programación sin tipos genera código de ejecución menos eficiente.</span><span class="sxs-lookup"><span data-stu-id="fe5c6-157">Typeless programming produces less efficient execution code.</span></span>  
  
-   <span data-ttu-id="fe5c6-158">Debe probar el procedimiento para cada tipo de datos que se prevé que se pasa.</span><span class="sxs-lookup"><span data-stu-id="fe5c6-158">The procedure must test for every data type it anticipates being passed.</span></span>  
  
-   <span data-ttu-id="fe5c6-159">El compilador no puede notificar un error si el código que realiza la llamada pasa un tipo de datos que no es compatible con el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="fe5c6-159">The compiler cannot signal an error if the calling code passes a data type that the procedure does not support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe5c6-160">Vea también</span><span class="sxs-lookup"><span data-stu-id="fe5c6-160">See Also</span></span>  
 [<span data-ttu-id="fe5c6-161">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="fe5c6-161">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="fe5c6-162">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="fe5c6-162">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="fe5c6-163">Solución de problemas de procedimientos</span><span class="sxs-lookup"><span data-stu-id="fe5c6-163">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)  
 [<span data-ttu-id="fe5c6-164">Definir varias versiones de un procedimiento</span><span class="sxs-lookup"><span data-stu-id="fe5c6-164">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)  
 [<span data-ttu-id="fe5c6-165">Llamar a un procedimiento sobrecargado</span><span class="sxs-lookup"><span data-stu-id="fe5c6-165">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)  
 [<span data-ttu-id="fe5c6-166">Sobrecargar un procedimiento que toma parámetros opcionales</span><span class="sxs-lookup"><span data-stu-id="fe5c6-166">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)  
 [<span data-ttu-id="fe5c6-167">Sobrecargar un procedimiento que toma un número indefinido de parámetros</span><span class="sxs-lookup"><span data-stu-id="fe5c6-167">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)  
 [<span data-ttu-id="fe5c6-168">Resolución de sobrecargas</span><span class="sxs-lookup"><span data-stu-id="fe5c6-168">Overload Resolution</span></span>](./overload-resolution.md)  
 [<span data-ttu-id="fe5c6-169">Sobrecargas</span><span class="sxs-lookup"><span data-stu-id="fe5c6-169">Overloads</span></span>](../../../../visual-basic/language-reference/modifiers/overloads.md)
