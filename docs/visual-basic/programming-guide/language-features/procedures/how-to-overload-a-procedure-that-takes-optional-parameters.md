---
title: Procedimiento Sobrecargar un procedimiento que toma parámetros opcionales (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], parameters
- procedure overloading [Visual Basic], optional parameters
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedure parameters
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
ms.assetid: 825f9d56-4cde-43fd-993a-b9171717e2eb
ms.openlocfilehash: 58c52a7d73efbd96d772dd85d6bf2c9084fb1241
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59320238"
---
# <a name="how-to-overload-a-procedure-that-takes-optional-parameters-visual-basic"></a><span data-ttu-id="45481-102">Procedimiento Sobrecargar un procedimiento que toma parámetros opcionales (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="45481-102">How to: Overload a Procedure that Takes Optional Parameters (Visual Basic)</span></span>
<span data-ttu-id="45481-103">Si un procedimiento tiene uno o varios [opcional](../../../../visual-basic/language-reference/modifiers/optional.md) parámetros, no se puede definir una versión sobrecargada que coincida con alguno de sus sobrecargas implícitas.</span><span class="sxs-lookup"><span data-stu-id="45481-103">If a procedure has one or more [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) parameters, you cannot define an overloaded version matching any of its implicit overloads.</span></span> <span data-ttu-id="45481-104">Para obtener más información, vea "Implícita sobrecargas para parámetros opcionales" en [consideraciones en sobrecarga de procedimientos](./considerations-in-overloading-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="45481-104">For more information, see "Implicit Overloads for Optional Parameters" in [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
## <a name="one-optional-parameter"></a><span data-ttu-id="45481-105">Un parámetro opcional</span><span class="sxs-lookup"><span data-stu-id="45481-105">One Optional Parameter</span></span>  
  
#### <a name="to-overload-a-procedure-that-takes-one-optional-parameter"></a><span data-ttu-id="45481-106">Sobrecargar un procedimiento que toma un parámetro opcional</span><span class="sxs-lookup"><span data-stu-id="45481-106">To overload a procedure that takes one optional parameter</span></span>  
  
1. <span data-ttu-id="45481-107">Escribir un `Sub` o `Function` instrucción de declaración que incluye el parámetro opcional en la lista de parámetros.</span><span class="sxs-lookup"><span data-stu-id="45481-107">Write a `Sub` or `Function` declaration statement that includes the optional parameter in the parameter list.</span></span> <span data-ttu-id="45481-108">No utilice el `Optional` palabra clave en esta versión sobrecargada.</span><span class="sxs-lookup"><span data-stu-id="45481-108">Do not use the `Optional` keyword in this overloaded version.</span></span>  
  
2. <span data-ttu-id="45481-109">Preceder el `Sub` o `Function` palabra clave con el [sobrecargas](../../../../visual-basic/language-reference/modifiers/overloads.md) palabra clave.</span><span class="sxs-lookup"><span data-stu-id="45481-109">Precede the `Sub` or `Function` keyword with the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword.</span></span>  
  
3. <span data-ttu-id="45481-110">Escribir el código del procedimiento que se debe ejecutar cuando el código de llamada proporciona el argumento opcional.</span><span class="sxs-lookup"><span data-stu-id="45481-110">Write the procedure code that should execute when the calling code supplies the optional argument.</span></span>  
  
4. <span data-ttu-id="45481-111">Finalice el procedimiento con el `End Sub` o `End Function` instrucción según corresponda.</span><span class="sxs-lookup"><span data-stu-id="45481-111">Terminate the procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
5. <span data-ttu-id="45481-112">Escribir una segunda instrucción de declaración que es idéntica a la primera declaración, salvo que no incluye el parámetro opcional en la lista de parámetros.</span><span class="sxs-lookup"><span data-stu-id="45481-112">Write a second declaration statement that is identical to the first declaration except that it does not include the optional parameter in the parameter list.</span></span>  
  
6. <span data-ttu-id="45481-113">Escribir el código del procedimiento que se debe ejecutar cuando el código de llamada no proporciona el argumento opcional.</span><span class="sxs-lookup"><span data-stu-id="45481-113">Write the procedure code that should execute when the calling code does not supply the optional argument.</span></span> <span data-ttu-id="45481-114">Finalice el procedimiento con el `End Sub` o `End Function` instrucción según corresponda.</span><span class="sxs-lookup"><span data-stu-id="45481-114">Terminate the procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
     <span data-ttu-id="45481-115">El ejemplo siguiente muestra un procedimiento definido con un parámetro opcional, un conjunto equivalente de dos procedimientos sobrecargados y, finalmente, ejemplos de versiones sobrecargadas válidas y no válidos.</span><span class="sxs-lookup"><span data-stu-id="45481-115">The following example shows a procedure defined with an optional parameter,  an equivalent set of two overloaded procedures, and finally examples of both invalid and valid overloaded versions.</span></span>  
  
     [!code-vb[VbVbcnProcedures#59](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#59)]  
  
     [!code-vb[VbVbcnProcedures#60](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#60)]  
  
     [!code-vb[VbVbcnProcedures#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#61)]  
  
## <a name="multiple-optional-parameters"></a><span data-ttu-id="45481-116">Varios parámetros opcionales</span><span class="sxs-lookup"><span data-stu-id="45481-116">Multiple Optional Parameters</span></span>  
 <span data-ttu-id="45481-117">Para obtener un procedimiento con más de un parámetro opcional, normalmente necesita más de dos versiones sobrecargadas.</span><span class="sxs-lookup"><span data-stu-id="45481-117">For a procedure with more than one optional parameter, you normally need more than two overloaded versions.</span></span> <span data-ttu-id="45481-118">Por ejemplo, si hay dos parámetros opcionales, y el código de llamada puede proporcionar u omitir cada uno de ellos independientemente de la otra, necesitará cuatro versiones sobrecargadas, uno para cada combinación posible de los argumentos proporcionados.</span><span class="sxs-lookup"><span data-stu-id="45481-118">For example, if there are two optional parameters, and the calling code can supply or omit each one independently of the other, you need four overloaded versions, one for each possible combination of supplied arguments.</span></span>  
  
 <span data-ttu-id="45481-119">A medida que aumenta el número de parámetros opcionales, aumenta la complejidad de la sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="45481-119">As the number of optional parameters increases, the complexity of the overloading increases.</span></span> <span data-ttu-id="45481-120">A menos que algunas combinaciones de argumentos proporcionados no son aceptables, para los parámetros opcionales de N necesita 2 ^ N versiones sobrecargadas.</span><span class="sxs-lookup"><span data-stu-id="45481-120">Unless some combinations of supplied arguments are not acceptable, for N optional parameters you need 2 ^ N overloaded versions.</span></span> <span data-ttu-id="45481-121">Según la naturaleza del procedimiento, es posible que la claridad de la lógica de justifica el esfuerzo adicional de definir todas las versiones sobrecargadas.</span><span class="sxs-lookup"><span data-stu-id="45481-121">Depending on the nature of the procedure, you might find that the clarity of logic justifies the extra effort of defining all the overloaded versions.</span></span>  
  
#### <a name="to-overload-a-procedure-that-takes-more-than-one-optional-parameter"></a><span data-ttu-id="45481-122">Sobrecargar un procedimiento que toma más de un parámetro opcional</span><span class="sxs-lookup"><span data-stu-id="45481-122">To overload a procedure that takes more than one optional parameter</span></span>  
  
1. <span data-ttu-id="45481-123">Determine qué combinaciones de argumentos opcionales proporcionados son aceptables para la lógica del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="45481-123">Determine which combinations of supplied optional arguments are acceptable to the logic of the procedure.</span></span> <span data-ttu-id="45481-124">Si un parámetro opcional que depende de otro, podría surgir una combinación inaceptable.</span><span class="sxs-lookup"><span data-stu-id="45481-124">An unacceptable combination might arise if one optional parameter depends on another.</span></span> <span data-ttu-id="45481-125">Por ejemplo, si un parámetro acepta el nombre del cónyuge y otro acepta la edad del cónyuge, una combinación de argumentos que proporcione la edad pero omita el nombre no es aceptable.</span><span class="sxs-lookup"><span data-stu-id="45481-125">For example, if one parameter accepts a spouse's name and another accepts the spouse's age, a combination of arguments supplying the age but omitting the name is unacceptable.</span></span>  
  
2. <span data-ttu-id="45481-126">Para cada combinación aceptable de argumentos opcionales proporcionados, escribir un `Sub` o `Function` instrucción de declaración que define la lista de parámetros correspondientes.</span><span class="sxs-lookup"><span data-stu-id="45481-126">For each acceptable combination of supplied optional arguments, write a `Sub` or `Function` declaration statement that defines the corresponding parameter list.</span></span> <span data-ttu-id="45481-127">No utilice el `Optional` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="45481-127">Do not use the `Optional` keyword.</span></span>  
  
3. <span data-ttu-id="45481-128">En cada declaración, anteponga la `Sub` o `Function` palabra clave con el [sobrecargas](../../../../visual-basic/language-reference/modifiers/overloads.md) palabra clave.</span><span class="sxs-lookup"><span data-stu-id="45481-128">In each declaration, precede the `Sub` or `Function` keyword with the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword.</span></span>  
  
4. <span data-ttu-id="45481-129">Después de cada declaración, escriba el código de procedimiento que se debe ejecutar cuando el código de llamada proporciona una lista de argumentos correspondientes a la lista de parámetros de declaración.</span><span class="sxs-lookup"><span data-stu-id="45481-129">Following each declaration, write the procedure code that should execute when the calling code supplies an argument list corresponding to that declaration's parameter list.</span></span>  
  
5. <span data-ttu-id="45481-130">Finalizar cada procedimiento con el `End Sub` o `End Function` instrucción según corresponda.</span><span class="sxs-lookup"><span data-stu-id="45481-130">Terminate each procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45481-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="45481-131">See also</span></span>

- [<span data-ttu-id="45481-132">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="45481-132">Procedures</span></span>](./index.md)
- [<span data-ttu-id="45481-133">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="45481-133">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="45481-134">Parámetros opcionales</span><span class="sxs-lookup"><span data-stu-id="45481-134">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="45481-135">Matrices de parámetros</span><span class="sxs-lookup"><span data-stu-id="45481-135">Parameter Arrays</span></span>](./parameter-arrays.md)
- [<span data-ttu-id="45481-136">Sobrecarga de procedimientos</span><span class="sxs-lookup"><span data-stu-id="45481-136">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="45481-137">Solución de problemas de procedimientos</span><span class="sxs-lookup"><span data-stu-id="45481-137">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)
- [<span data-ttu-id="45481-138">Cómo: Definir varias versiones de un procedimiento</span><span class="sxs-lookup"><span data-stu-id="45481-138">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)
- [<span data-ttu-id="45481-139">Cómo: Llamar a un procedimiento sobrecargado</span><span class="sxs-lookup"><span data-stu-id="45481-139">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)
- [<span data-ttu-id="45481-140">Cómo: Sobrecargar un procedimiento que toma un número indefinido de parámetros</span><span class="sxs-lookup"><span data-stu-id="45481-140">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [<span data-ttu-id="45481-141">Resolución de sobrecargas</span><span class="sxs-lookup"><span data-stu-id="45481-141">Overload Resolution</span></span>](./overload-resolution.md)
