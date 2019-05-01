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
ms.openlocfilehash: 3cf75fc6221364704379eb23d308481c34e6c0d6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61955746"
---
# <a name="how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters-visual-basic"></a><span data-ttu-id="46d13-102">Procedimiento Sobrecargar un procedimiento que toma un número indefinido de parámetros (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="46d13-102">How to: Overload a Procedure that Takes an Indefinite Number of Parameters (Visual Basic)</span></span>
<span data-ttu-id="46d13-103">Si un procedimiento tiene un [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parámetro, no se puede definir una versión sobrecargada que tome una matriz unidimensional de la matriz de parámetros.</span><span class="sxs-lookup"><span data-stu-id="46d13-103">If a procedure has a [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parameter, you cannot define an overloaded version taking a one-dimensional array for the parameter array.</span></span> <span data-ttu-id="46d13-104">Para obtener más información, vea "Implícita sobrecargas de un parámetro ParamArray" en [consideraciones en sobrecarga de procedimientos](./considerations-in-overloading-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="46d13-104">For more information, see "Implicit Overloads for a ParamArray Parameter" in [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
### <a name="to-overload-a-procedure-that-takes-a-variable-number-of-parameters"></a><span data-ttu-id="46d13-105">Sobrecargar un procedimiento que toma un número variable de parámetros</span><span class="sxs-lookup"><span data-stu-id="46d13-105">To overload a procedure that takes a variable number of parameters</span></span>  
  
1. <span data-ttu-id="46d13-106">Confirmar que el procedimiento y llamar a código lógica beneficia sobrecargado versiones más de un `ParamArray` parámetro.</span><span class="sxs-lookup"><span data-stu-id="46d13-106">Ascertain that the procedure and calling code logic benefits from overloaded versions more than from a `ParamArray` parameter.</span></span> <span data-ttu-id="46d13-107">Vea "Sobrecargas y ParamArray" en [consideraciones sobre la sobrecarga de procedimientos](./considerations-in-overloading-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="46d13-107">See "Overloads and ParamArrays" in [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
2. <span data-ttu-id="46d13-108">Determinar qué número de valores proporcionados en la parte variable de la lista de parámetros debe aceptar el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="46d13-108">Determine which numbers of supplied values the procedure should accept in the variable part of the parameter list.</span></span> <span data-ttu-id="46d13-109">Esto podría incluir el caso de ningún valor y podría incluir el caso de una matriz unidimensional.</span><span class="sxs-lookup"><span data-stu-id="46d13-109">This might include the case of no value, and it might include the case of a single one-dimensional array.</span></span>  
  
3. <span data-ttu-id="46d13-110">Para cada número aceptable de valores proporcionados, escribir un `Sub` o `Function` instrucción de declaración que define la lista de parámetros correspondientes.</span><span class="sxs-lookup"><span data-stu-id="46d13-110">For each acceptable number of supplied values, write a `Sub` or `Function` declaration statement that defines the corresponding parameter list.</span></span> <span data-ttu-id="46d13-111">No use ninguno el `Optional` o `ParamArray` palabra clave en esta versión sobrecargada.</span><span class="sxs-lookup"><span data-stu-id="46d13-111">Do not use either the `Optional` or the `ParamArray` keyword in this overloaded version.</span></span>  
  
4. <span data-ttu-id="46d13-112">En cada declaración, anteponga la `Sub` o `Function` palabra clave con el [sobrecargas](../../../../visual-basic/language-reference/modifiers/overloads.md) palabra clave.</span><span class="sxs-lookup"><span data-stu-id="46d13-112">In each declaration, precede the `Sub` or `Function` keyword with the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword.</span></span>  
  
5. <span data-ttu-id="46d13-113">Después de cada declaración, escriba el código de procedimiento que se debe ejecutar cuando el código de llamada proporciona los valores correspondientes a la lista de parámetros de declaración.</span><span class="sxs-lookup"><span data-stu-id="46d13-113">Following each declaration, write the procedure code that should execute when the calling code supplies values corresponding to that declaration's parameter list.</span></span>  
  
6. <span data-ttu-id="46d13-114">Finalizar cada procedimiento con el `End Sub` o `End Function` instrucción según corresponda.</span><span class="sxs-lookup"><span data-stu-id="46d13-114">Terminate each procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="46d13-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="46d13-115">Example</span></span>  
 <span data-ttu-id="46d13-116">El ejemplo siguiente muestra un procedimiento definido con un [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parámetro y, a continuación, un conjunto equivalente de procedimientos sobrecargados.</span><span class="sxs-lookup"><span data-stu-id="46d13-116">The following example shows a procedure defined with a [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parameter, and then an equivalent set of overloaded procedures.</span></span>  
  
 [!code-vb[VbVbcnProcedures#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#69)]  
  
 [!code-vb[VbVbcnProcedures#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#70)]  
  
 <span data-ttu-id="46d13-117">No se puede sobrecargar un procedimiento con una lista de parámetros que toma una matriz unidimensional de la matriz de parámetros.</span><span class="sxs-lookup"><span data-stu-id="46d13-117">You cannot overload such a procedure with a parameter list that takes a one-dimensional array for the parameter array.</span></span> <span data-ttu-id="46d13-118">Sin embargo, puede usar las firmas de las otras sobrecargas implícitas.</span><span class="sxs-lookup"><span data-stu-id="46d13-118">However, you can use the signatures of the other implicit overloads.</span></span> <span data-ttu-id="46d13-119">Las declaraciones siguientes ilustran esto.</span><span class="sxs-lookup"><span data-stu-id="46d13-119">The following declarations illustrate this.</span></span>  
  
 [!code-vb[VbVbcnProcedures#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#71)]  
  
 <span data-ttu-id="46d13-120">El código en las versiones sobrecargadas no tiene que comprobar si el código de llamada proporciona uno o varios valores para el `ParamArray` parámetro, o si es así, cuántos.</span><span class="sxs-lookup"><span data-stu-id="46d13-120">The code in the overloaded versions does not have to test whether the calling code supplied one or more values for the `ParamArray` parameter, or if so, how many.</span></span> <span data-ttu-id="46d13-121">Visual Basic pasa el control a la versión que coincida con la lista de argumentos que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="46d13-121">Visual Basic passes control to the version matching the calling argument list.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="46d13-122">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="46d13-122">Compiling the Code</span></span>  
 <span data-ttu-id="46d13-123">Dado que un procedimiento con un `ParamArray` parámetro es equivalente a un conjunto de versiones sobrecargadas, no se puede sobrecargar un procedimiento con una lista de parámetros correspondientes a cualquiera de estas sobrecargas implícitas.</span><span class="sxs-lookup"><span data-stu-id="46d13-123">Because a procedure with a `ParamArray` parameter is equivalent to a set of overloaded versions, you cannot overload such a procedure with a parameter list corresponding to any of these implicit overloads.</span></span> <span data-ttu-id="46d13-124">Para obtener más información, consulte [consideraciones en sobrecarga de procedimientos](./considerations-in-overloading-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="46d13-124">For more information, see [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="46d13-125">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="46d13-125">.NET Framework Security</span></span>  
 <span data-ttu-id="46d13-126">Si se trabaja con una matriz que puede ser excesivamente grande, hay un riesgo de sobrecargar alguna capacidad interna de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="46d13-126">Whenever you deal with an array which can be indefinitely large, there is a risk of overrunning some internal capacity of your application.</span></span> <span data-ttu-id="46d13-127">Si acepta una matriz de parámetros, debe comprobar la longitud de la matriz el código de llamada pasado a él y seguir los pasos adecuados si es demasiado grande para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="46d13-127">If you accept a parameter array, you should test for the length of the array the calling code passed to it, and take appropriate steps if it is too large for your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46d13-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="46d13-128">See also</span></span>

- [<span data-ttu-id="46d13-129">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="46d13-129">Procedures</span></span>](./index.md)
- [<span data-ttu-id="46d13-130">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="46d13-130">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="46d13-131">Parámetros opcionales</span><span class="sxs-lookup"><span data-stu-id="46d13-131">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="46d13-132">Matrices de parámetros</span><span class="sxs-lookup"><span data-stu-id="46d13-132">Parameter Arrays</span></span>](./parameter-arrays.md)
- [<span data-ttu-id="46d13-133">Sobrecarga de procedimientos</span><span class="sxs-lookup"><span data-stu-id="46d13-133">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="46d13-134">Solución de problemas de procedimientos</span><span class="sxs-lookup"><span data-stu-id="46d13-134">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)
- [<span data-ttu-id="46d13-135">Cómo: Definir varias versiones de un procedimiento</span><span class="sxs-lookup"><span data-stu-id="46d13-135">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)
- [<span data-ttu-id="46d13-136">Cómo: Llamar a un procedimiento sobrecargado</span><span class="sxs-lookup"><span data-stu-id="46d13-136">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)
- [<span data-ttu-id="46d13-137">Cómo: Sobrecargar un procedimiento que toma parámetros opcionales</span><span class="sxs-lookup"><span data-stu-id="46d13-137">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [<span data-ttu-id="46d13-138">Resolución de sobrecargas</span><span class="sxs-lookup"><span data-stu-id="46d13-138">Overload Resolution</span></span>](./overload-resolution.md)
