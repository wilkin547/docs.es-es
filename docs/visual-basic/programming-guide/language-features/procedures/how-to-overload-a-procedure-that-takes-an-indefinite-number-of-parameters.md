---
title: Procedimiento Sobrecargar un procedimiento que toma un número indefinido de parámetros (Visual Basic)
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
ms.openlocfilehash: 54a8a65db6e1f532cd21e36eeb5b98670efd4289
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54506399"
---
# <a name="how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters-visual-basic"></a><span data-ttu-id="41e1d-102">Procedimiento Sobrecargar un procedimiento que toma un número indefinido de parámetros (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="41e1d-102">How to: Overload a Procedure that Takes an Indefinite Number of Parameters (Visual Basic)</span></span>
<span data-ttu-id="41e1d-103">Si un procedimiento tiene un [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parámetro, no se puede definir una versión sobrecargada que tome una matriz unidimensional de la matriz de parámetros.</span><span class="sxs-lookup"><span data-stu-id="41e1d-103">If a procedure has a [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parameter, you cannot define an overloaded version taking a one-dimensional array for the parameter array.</span></span> <span data-ttu-id="41e1d-104">Para obtener más información, vea "Implícita sobrecargas de un parámetro ParamArray" en [consideraciones en sobrecarga de procedimientos](./considerations-in-overloading-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="41e1d-104">For more information, see "Implicit Overloads for a ParamArray Parameter" in [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
### <a name="to-overload-a-procedure-that-takes-a-variable-number-of-parameters"></a><span data-ttu-id="41e1d-105">Sobrecargar un procedimiento que toma un número variable de parámetros</span><span class="sxs-lookup"><span data-stu-id="41e1d-105">To overload a procedure that takes a variable number of parameters</span></span>  
  
1.  <span data-ttu-id="41e1d-106">Confirmar que el procedimiento y llamar a código lógica beneficia sobrecargado versiones más de un `ParamArray` parámetro.</span><span class="sxs-lookup"><span data-stu-id="41e1d-106">Ascertain that the procedure and calling code logic benefits from overloaded versions more than from a `ParamArray` parameter.</span></span> <span data-ttu-id="41e1d-107">Vea "Sobrecargas y ParamArray" en [consideraciones sobre la sobrecarga de procedimientos](./considerations-in-overloading-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="41e1d-107">See "Overloads and ParamArrays" in [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
2.  <span data-ttu-id="41e1d-108">Determinar qué número de valores proporcionados en la parte variable de la lista de parámetros debe aceptar el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="41e1d-108">Determine which numbers of supplied values the procedure should accept in the variable part of the parameter list.</span></span> <span data-ttu-id="41e1d-109">Esto podría incluir el caso de ningún valor y podría incluir el caso de una matriz unidimensional.</span><span class="sxs-lookup"><span data-stu-id="41e1d-109">This might include the case of no value, and it might include the case of a single one-dimensional array.</span></span>  
  
3.  <span data-ttu-id="41e1d-110">Para cada número aceptable de valores proporcionados, escribir un `Sub` o `Function` instrucción de declaración que define la lista de parámetros correspondientes.</span><span class="sxs-lookup"><span data-stu-id="41e1d-110">For each acceptable number of supplied values, write a `Sub` or `Function` declaration statement that defines the corresponding parameter list.</span></span> <span data-ttu-id="41e1d-111">No use ninguno el `Optional` o `ParamArray` palabra clave en esta versión sobrecargada.</span><span class="sxs-lookup"><span data-stu-id="41e1d-111">Do not use either the `Optional` or the `ParamArray` keyword in this overloaded version.</span></span>  
  
4.  <span data-ttu-id="41e1d-112">En cada declaración, anteponga la `Sub` o `Function` palabra clave con el [sobrecargas](../../../../visual-basic/language-reference/modifiers/overloads.md) palabra clave.</span><span class="sxs-lookup"><span data-stu-id="41e1d-112">In each declaration, precede the `Sub` or `Function` keyword with the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword.</span></span>  
  
5.  <span data-ttu-id="41e1d-113">Después de cada declaración, escriba el código de procedimiento que se debe ejecutar cuando el código de llamada proporciona los valores correspondientes a la lista de parámetros de declaración.</span><span class="sxs-lookup"><span data-stu-id="41e1d-113">Following each declaration, write the procedure code that should execute when the calling code supplies values corresponding to that declaration's parameter list.</span></span>  
  
6.  <span data-ttu-id="41e1d-114">Finalizar cada procedimiento con el `End Sub` o `End Function` instrucción según corresponda.</span><span class="sxs-lookup"><span data-stu-id="41e1d-114">Terminate each procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="41e1d-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="41e1d-115">Example</span></span>  
 <span data-ttu-id="41e1d-116">El ejemplo siguiente muestra un procedimiento definido con un [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parámetro y, a continuación, un conjunto equivalente de procedimientos sobrecargados.</span><span class="sxs-lookup"><span data-stu-id="41e1d-116">The following example shows a procedure defined with a [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parameter, and then an equivalent set of overloaded procedures.</span></span>  
  
 [!code-vb[VbVbcnProcedures#69](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#70](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_2.vb)]  
  
 <span data-ttu-id="41e1d-117">No se puede sobrecargar un procedimiento con una lista de parámetros que toma una matriz unidimensional de la matriz de parámetros.</span><span class="sxs-lookup"><span data-stu-id="41e1d-117">You cannot overload such a procedure with a parameter list that takes a one-dimensional array for the parameter array.</span></span> <span data-ttu-id="41e1d-118">Sin embargo, puede usar las firmas de las otras sobrecargas implícitas.</span><span class="sxs-lookup"><span data-stu-id="41e1d-118">However, you can use the signatures of the other implicit overloads.</span></span> <span data-ttu-id="41e1d-119">Las declaraciones siguientes ilustran esto.</span><span class="sxs-lookup"><span data-stu-id="41e1d-119">The following declarations illustrate this.</span></span>  
  
 [!code-vb[VbVbcnProcedures#71](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_3.vb)]  
  
 <span data-ttu-id="41e1d-120">El código en las versiones sobrecargadas no tiene que comprobar si el código de llamada proporciona uno o varios valores para el `ParamArray` parámetro, o si es así, cuántos.</span><span class="sxs-lookup"><span data-stu-id="41e1d-120">The code in the overloaded versions does not have to test whether the calling code supplied one or more values for the `ParamArray` parameter, or if so, how many.</span></span> <span data-ttu-id="41e1d-121">Visual Basic pasa el control a la versión que coincida con la lista de argumentos que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="41e1d-121">Visual Basic passes control to the version matching the calling argument list.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="41e1d-122">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="41e1d-122">Compiling the Code</span></span>  
 <span data-ttu-id="41e1d-123">Dado que un procedimiento con un `ParamArray` parámetro es equivalente a un conjunto de versiones sobrecargadas, no se puede sobrecargar un procedimiento con una lista de parámetros correspondientes a cualquiera de estas sobrecargas implícitas.</span><span class="sxs-lookup"><span data-stu-id="41e1d-123">Because a procedure with a `ParamArray` parameter is equivalent to a set of overloaded versions, you cannot overload such a procedure with a parameter list corresponding to any of these implicit overloads.</span></span> <span data-ttu-id="41e1d-124">Para obtener más información, consulte [consideraciones en sobrecarga de procedimientos](./considerations-in-overloading-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="41e1d-124">For more information, see [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="41e1d-125">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="41e1d-125">.NET Framework Security</span></span>  
 <span data-ttu-id="41e1d-126">Si se trabaja con una matriz que puede ser excesivamente grande, hay un riesgo de sobrecargar alguna capacidad interna de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="41e1d-126">Whenever you deal with an array which can be indefinitely large, there is a risk of overrunning some internal capacity of your application.</span></span> <span data-ttu-id="41e1d-127">Si acepta una matriz de parámetros, debe comprobar la longitud de la matriz el código de llamada pasado a él y seguir los pasos adecuados si es demasiado grande para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="41e1d-127">If you accept a parameter array, you should test for the length of the array the calling code passed to it, and take appropriate steps if it is too large for your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41e1d-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="41e1d-128">See also</span></span>
- [<span data-ttu-id="41e1d-129">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="41e1d-129">Procedures</span></span>](./index.md)
- [<span data-ttu-id="41e1d-130">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="41e1d-130">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="41e1d-131">Parámetros opcionales</span><span class="sxs-lookup"><span data-stu-id="41e1d-131">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="41e1d-132">Matrices de parámetros</span><span class="sxs-lookup"><span data-stu-id="41e1d-132">Parameter Arrays</span></span>](./parameter-arrays.md)
- [<span data-ttu-id="41e1d-133">Sobrecarga de procedimientos</span><span class="sxs-lookup"><span data-stu-id="41e1d-133">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="41e1d-134">Solución de problemas de procedimientos</span><span class="sxs-lookup"><span data-stu-id="41e1d-134">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)
- [<span data-ttu-id="41e1d-135">Cómo: Definir varias versiones de un procedimiento</span><span class="sxs-lookup"><span data-stu-id="41e1d-135">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)
- [<span data-ttu-id="41e1d-136">Cómo: Llamar a un procedimiento sobrecargado</span><span class="sxs-lookup"><span data-stu-id="41e1d-136">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)
- [<span data-ttu-id="41e1d-137">Cómo: Sobrecargar un procedimiento que toma parámetros opcionales</span><span class="sxs-lookup"><span data-stu-id="41e1d-137">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [<span data-ttu-id="41e1d-138">Resolución de sobrecargas</span><span class="sxs-lookup"><span data-stu-id="41e1d-138">Overload Resolution</span></span>](./overload-resolution.md)
