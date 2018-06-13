---
title: 'Cómo: Sobrecargar un procedimiento que toma un número indefinido de parámetros (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], parameters
- procedure overloading [Visual Basic], indefinite number of parameters
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedure parameters
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
ms.assetid: c7042de2-2422-4039-94e8-ac298896af69
ms.openlocfilehash: 026dd59db135e8b195ae014aaff5e3a6a7846fc7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33651497"
---
# <a name="how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters-visual-basic"></a><span data-ttu-id="c3ece-102">Cómo: Sobrecargar un procedimiento que toma un número indefinido de parámetros (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c3ece-102">How to: Overload a Procedure that Takes an Indefinite Number of Parameters (Visual Basic)</span></span>
<span data-ttu-id="c3ece-103">Si un procedimiento tiene un [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parámetro, no se puede definir una versión sobrecargada que tome una matriz unidimensional de la matriz de parámetros.</span><span class="sxs-lookup"><span data-stu-id="c3ece-103">If a procedure has a [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parameter, you cannot define an overloaded version taking a one-dimensional array for the parameter array.</span></span> <span data-ttu-id="c3ece-104">Para obtener más información, vea "Implícita sobrecargas para un parámetro ParamArray" en [consideraciones de sobrecarga de procedimientos](./considerations-in-overloading-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="c3ece-104">For more information, see "Implicit Overloads for a ParamArray Parameter" in [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
### <a name="to-overload-a-procedure-that-takes-a-variable-number-of-parameters"></a><span data-ttu-id="c3ece-105">Para sobrecargar un procedimiento que toma un número variable de parámetros</span><span class="sxs-lookup"><span data-stu-id="c3ece-105">To overload a procedure that takes a variable number of parameters</span></span>  
  
1.  <span data-ttu-id="c3ece-106">Confirmar que el procedimiento y llamar a beneficios de lógica de código de sobrecargado versiones más de un `ParamArray` parámetro.</span><span class="sxs-lookup"><span data-stu-id="c3ece-106">Ascertain that the procedure and calling code logic benefits from overloaded versions more than from a `ParamArray` parameter.</span></span> <span data-ttu-id="c3ece-107">Vea "Sobrecargas y ParamArray" en [consideraciones sobre la sobrecarga de procedimientos](./considerations-in-overloading-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="c3ece-107">See "Overloads and ParamArrays" in [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
2.  <span data-ttu-id="c3ece-108">Determinar qué número de valores proporcionados debe aceptar el procedimiento en la parte variable de la lista de parámetros.</span><span class="sxs-lookup"><span data-stu-id="c3ece-108">Determine which numbers of supplied values the procedure should accept in the variable part of the parameter list.</span></span> <span data-ttu-id="c3ece-109">Esto puede incluir el caso de ningún valor y es posible que incluya el caso de una matriz unidimensional.</span><span class="sxs-lookup"><span data-stu-id="c3ece-109">This might include the case of no value, and it might include the case of a single one-dimensional array.</span></span>  
  
3.  <span data-ttu-id="c3ece-110">Para cada número aceptable de valores proporcionados, escriba un `Sub` o `Function` instrucción de declaración que define la lista de parámetros correspondiente.</span><span class="sxs-lookup"><span data-stu-id="c3ece-110">For each acceptable number of supplied values, write a `Sub` or `Function` declaration statement that defines the corresponding parameter list.</span></span> <span data-ttu-id="c3ece-111">No use la `Optional` o `ParamArray` palabra clave en esta versión sobrecargada.</span><span class="sxs-lookup"><span data-stu-id="c3ece-111">Do not use either the `Optional` or the `ParamArray` keyword in this overloaded version.</span></span>  
  
4.  <span data-ttu-id="c3ece-112">En cada declaración, anteponga la `Sub` o `Function` palabra clave con la [sobrecargas](../../../../visual-basic/language-reference/modifiers/overloads.md) palabra clave.</span><span class="sxs-lookup"><span data-stu-id="c3ece-112">In each declaration, precede the `Sub` or `Function` keyword with the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword.</span></span>  
  
5.  <span data-ttu-id="c3ece-113">Después de cada declaración, escriba el código de procedimiento que se debe ejecutar cuando el código de llamada proporciona los valores correspondientes a la lista de parámetros de esa declaración.</span><span class="sxs-lookup"><span data-stu-id="c3ece-113">Following each declaration, write the procedure code that should execute when the calling code supplies values corresponding to that declaration's parameter list.</span></span>  
  
6.  <span data-ttu-id="c3ece-114">Finalizar cada procedimiento con el `End Sub` o `End Function` instrucción según corresponda.</span><span class="sxs-lookup"><span data-stu-id="c3ece-114">Terminate each procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c3ece-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c3ece-115">Example</span></span>  
 <span data-ttu-id="c3ece-116">En el ejemplo siguiente se muestra un procedimiento definido con un [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parámetro y, a continuación, en un conjunto equivalente de procedimientos sobrecargados.</span><span class="sxs-lookup"><span data-stu-id="c3ece-116">The following example shows a procedure defined with a [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parameter, and then an equivalent set of overloaded procedures.</span></span>  
  
 [!code-vb[VbVbcnProcedures#69](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#70](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_2.vb)]  
  
 <span data-ttu-id="c3ece-117">No se pueden sobrecargar un procedimiento así con una lista de parámetros que toma una matriz unidimensional de la matriz de parámetros.</span><span class="sxs-lookup"><span data-stu-id="c3ece-117">You cannot overload such a procedure with a parameter list that takes a one-dimensional array for the parameter array.</span></span> <span data-ttu-id="c3ece-118">Sin embargo, puede utilizar las firmas de las otras sobrecargas implícitas.</span><span class="sxs-lookup"><span data-stu-id="c3ece-118">However, you can use the signatures of the other implicit overloads.</span></span> <span data-ttu-id="c3ece-119">Las declaraciones siguientes ilustran esto.</span><span class="sxs-lookup"><span data-stu-id="c3ece-119">The following declarations illustrate this.</span></span>  
  
 [!code-vb[VbVbcnProcedures#71](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_3.vb)]  
  
 <span data-ttu-id="c3ece-120">El código en las versiones sobrecargadas no tiene que comprobar si el código de llamada proporciona uno o varios valores para el `ParamArray` parámetro, o si es así, ¿cuántos.</span><span class="sxs-lookup"><span data-stu-id="c3ece-120">The code in the overloaded versions does not have to test whether the calling code supplied one or more values for the `ParamArray` parameter, or if so, how many.</span></span> <span data-ttu-id="c3ece-121">Visual Basic pasa el control a la versión que coincida con la lista de argumentos que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="c3ece-121">Visual Basic passes control to the version matching the calling argument list.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c3ece-122">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="c3ece-122">Compiling the Code</span></span>  
 <span data-ttu-id="c3ece-123">Dado que un procedimiento con un `ParamArray` parámetro es equivalente a un conjunto de versiones sobrecargadas, no se puede sobrecargar un procedimiento con una lista de parámetros que se corresponda con alguna de estas sobrecargas implícitas.</span><span class="sxs-lookup"><span data-stu-id="c3ece-123">Because a procedure with a `ParamArray` parameter is equivalent to a set of overloaded versions, you cannot overload such a procedure with a parameter list corresponding to any of these implicit overloads.</span></span> <span data-ttu-id="c3ece-124">Para obtener más información, consulte [consideraciones de sobrecarga de procedimientos](./considerations-in-overloading-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="c3ece-124">For more information, see [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="c3ece-125">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c3ece-125">.NET Framework Security</span></span>  
 <span data-ttu-id="c3ece-126">Cuando se trabaja con una matriz que puede ser excesivamente grande, se corre el riesgo de saturar alguna capacidad interna de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c3ece-126">Whenever you deal with an array which can be indefinitely large, there is a risk of overrunning some internal capacity of your application.</span></span> <span data-ttu-id="c3ece-127">Si acepta una matriz de parámetros, debe comprobar la longitud de la matriz que se pasa el código de llamada y tomar las medidas apropiadas si es demasiado grande para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c3ece-127">If you accept a parameter array, you should test for the length of the array the calling code passed to it, and take appropriate steps if it is too large for your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3ece-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="c3ece-128">See Also</span></span>  
 [<span data-ttu-id="c3ece-129">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="c3ece-129">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="c3ece-130">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="c3ece-130">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="c3ece-131">Parámetros opcionales</span><span class="sxs-lookup"><span data-stu-id="c3ece-131">Optional Parameters</span></span>](./optional-parameters.md)  
 [<span data-ttu-id="c3ece-132">Matrices de parámetros</span><span class="sxs-lookup"><span data-stu-id="c3ece-132">Parameter Arrays</span></span>](./parameter-arrays.md)  
 [<span data-ttu-id="c3ece-133">Sobrecarga de procedimientos</span><span class="sxs-lookup"><span data-stu-id="c3ece-133">Procedure Overloading</span></span>](./procedure-overloading.md)  
 [<span data-ttu-id="c3ece-134">Solución de problemas de procedimientos</span><span class="sxs-lookup"><span data-stu-id="c3ece-134">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)  
 [<span data-ttu-id="c3ece-135">Definir varias versiones de un procedimiento</span><span class="sxs-lookup"><span data-stu-id="c3ece-135">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)  
 [<span data-ttu-id="c3ece-136">Llamar a un procedimiento sobrecargado</span><span class="sxs-lookup"><span data-stu-id="c3ece-136">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)  
 [<span data-ttu-id="c3ece-137">Sobrecargar un procedimiento que toma parámetros opcionales</span><span class="sxs-lookup"><span data-stu-id="c3ece-137">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)  
 [<span data-ttu-id="c3ece-138">Resolución de sobrecargas</span><span class="sxs-lookup"><span data-stu-id="c3ece-138">Overload Resolution</span></span>](./overload-resolution.md)
