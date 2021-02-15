---
description: 'Más información acerca de cómo: sobrecargar un procedimiento que toma parámetros opcionales (Visual Basic)'
title: Procedimiento para sobrecargar un procedimiento que toma parámetros opcionales
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
ms.openlocfilehash: dccef9d27c08ede2f35edc02c8bd5116aa6969b2
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100472949"
---
# <a name="how-to-overload-a-procedure-that-takes-optional-parameters-visual-basic"></a><span data-ttu-id="12296-103">Cómo: Sobrecargar un procedimiento que toma parámetros opcionales (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="12296-103">How to: Overload a Procedure that Takes Optional Parameters (Visual Basic)</span></span>

<span data-ttu-id="12296-104">Si un procedimiento tiene uno o varios parámetros [opcionales](../../../language-reference/modifiers/optional.md) , no se puede definir una versión sobrecargada que coincida con cualquiera de sus sobrecargas implícitas.</span><span class="sxs-lookup"><span data-stu-id="12296-104">If a procedure has one or more [Optional](../../../language-reference/modifiers/optional.md) parameters, you cannot define an overloaded version matching any of its implicit overloads.</span></span> <span data-ttu-id="12296-105">Para obtener más información, vea "sobrecargas implícitas para los parámetros opcionales" en [consideraciones sobre la sobrecarga de procedimientos](./considerations-in-overloading-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="12296-105">For more information, see "Implicit Overloads for Optional Parameters" in [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
## <a name="one-optional-parameter"></a><span data-ttu-id="12296-106">Un parámetro opcional</span><span class="sxs-lookup"><span data-stu-id="12296-106">One Optional Parameter</span></span>  
  
#### <a name="to-overload-a-procedure-that-takes-one-optional-parameter"></a><span data-ttu-id="12296-107">Para sobrecargar un procedimiento que toma un parámetro opcional</span><span class="sxs-lookup"><span data-stu-id="12296-107">To overload a procedure that takes one optional parameter</span></span>  
  
1. <span data-ttu-id="12296-108">Escriba una `Sub` `Function` instrucción de declaración o que incluya el parámetro opcional en la lista de parámetros.</span><span class="sxs-lookup"><span data-stu-id="12296-108">Write a `Sub` or `Function` declaration statement that includes the optional parameter in the parameter list.</span></span> <span data-ttu-id="12296-109">No use la `Optional` palabra clave en esta versión sobrecargada.</span><span class="sxs-lookup"><span data-stu-id="12296-109">Do not use the `Optional` keyword in this overloaded version.</span></span>  
  
2. <span data-ttu-id="12296-110">Preceda `Sub` `Function` a la palabra clave o con la palabra clave [Overloads](../../../language-reference/modifiers/overloads.md) .</span><span class="sxs-lookup"><span data-stu-id="12296-110">Precede the `Sub` or `Function` keyword with the [Overloads](../../../language-reference/modifiers/overloads.md) keyword.</span></span>  
  
3. <span data-ttu-id="12296-111">Escriba el código de procedimiento que debe ejecutarse cuando el código que realiza la llamada proporcione el argumento opcional.</span><span class="sxs-lookup"><span data-stu-id="12296-111">Write the procedure code that should execute when the calling code supplies the optional argument.</span></span>  
  
4. <span data-ttu-id="12296-112">Finalice el procedimiento con la `End Sub` `End Function` instrucción o según corresponda.</span><span class="sxs-lookup"><span data-stu-id="12296-112">Terminate the procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
5. <span data-ttu-id="12296-113">Escriba una segunda instrucción de declaración que sea idéntica a la primera declaración, salvo que no incluya el parámetro opcional en la lista de parámetros.</span><span class="sxs-lookup"><span data-stu-id="12296-113">Write a second declaration statement that is identical to the first declaration except that it does not include the optional parameter in the parameter list.</span></span>  
  
6. <span data-ttu-id="12296-114">Escriba el código de procedimiento que debe ejecutarse cuando el código de llamada no proporcione el argumento opcional.</span><span class="sxs-lookup"><span data-stu-id="12296-114">Write the procedure code that should execute when the calling code does not supply the optional argument.</span></span> <span data-ttu-id="12296-115">Finalice el procedimiento con la `End Sub` `End Function` instrucción o según corresponda.</span><span class="sxs-lookup"><span data-stu-id="12296-115">Terminate the procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
     <span data-ttu-id="12296-116">En el ejemplo siguiente se muestra un procedimiento definido con un parámetro opcional, un conjunto equivalente de dos procedimientos sobrecargados y, por último, ejemplos de versiones sobrecargadas y no válidas.</span><span class="sxs-lookup"><span data-stu-id="12296-116">The following example shows a procedure defined with an optional parameter,  an equivalent set of two overloaded procedures, and finally examples of both invalid and valid overloaded versions.</span></span>  
  
     [!code-vb[VbVbcnProcedures#59](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#59)]  
  
     [!code-vb[VbVbcnProcedures#60](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#60)]  
  
     [!code-vb[VbVbcnProcedures#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#61)]  
  
## <a name="multiple-optional-parameters"></a><span data-ttu-id="12296-117">Varios parámetros opcionales</span><span class="sxs-lookup"><span data-stu-id="12296-117">Multiple Optional Parameters</span></span>  

 <span data-ttu-id="12296-118">Para un procedimiento con más de un parámetro opcional, normalmente se necesitan más de dos versiones sobrecargadas.</span><span class="sxs-lookup"><span data-stu-id="12296-118">For a procedure with more than one optional parameter, you normally need more than two overloaded versions.</span></span> <span data-ttu-id="12296-119">Por ejemplo, si hay dos parámetros opcionales y el código de llamada puede proporcionar u omitir cada uno de ellos de forma independiente, se necesitan cuatro versiones sobrecargadas, una para cada combinación posible de argumentos proporcionados.</span><span class="sxs-lookup"><span data-stu-id="12296-119">For example, if there are two optional parameters, and the calling code can supply or omit each one independently of the other, you need four overloaded versions, one for each possible combination of supplied arguments.</span></span>  
  
 <span data-ttu-id="12296-120">A medida que aumenta el número de parámetros opcionales, aumenta la complejidad de la sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="12296-120">As the number of optional parameters increases, the complexity of the overloading increases.</span></span> <span data-ttu-id="12296-121">A menos que algunas combinaciones de los argumentos proporcionados no sean aceptables, para N parámetros opcionales necesita 2 ^ N versiones sobrecargadas.</span><span class="sxs-lookup"><span data-stu-id="12296-121">Unless some combinations of supplied arguments are not acceptable, for N optional parameters you need 2 ^ N overloaded versions.</span></span> <span data-ttu-id="12296-122">En función de la naturaleza del procedimiento, podría encontrar que la claridad de la lógica justifica el esfuerzo adicional de definir todas las versiones sobrecargadas.</span><span class="sxs-lookup"><span data-stu-id="12296-122">Depending on the nature of the procedure, you might find that the clarity of logic justifies the extra effort of defining all the overloaded versions.</span></span>  
  
#### <a name="to-overload-a-procedure-that-takes-more-than-one-optional-parameter"></a><span data-ttu-id="12296-123">Para sobrecargar un procedimiento que toma más de un parámetro opcional</span><span class="sxs-lookup"><span data-stu-id="12296-123">To overload a procedure that takes more than one optional parameter</span></span>  
  
1. <span data-ttu-id="12296-124">Determine qué combinaciones de argumentos opcionales proporcionados son aceptables para la lógica del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="12296-124">Determine which combinations of supplied optional arguments are acceptable to the logic of the procedure.</span></span> <span data-ttu-id="12296-125">Podría producirse una combinación inaceptable si un parámetro opcional depende de otro.</span><span class="sxs-lookup"><span data-stu-id="12296-125">An unacceptable combination might arise if one optional parameter depends on another.</span></span> <span data-ttu-id="12296-126">Por ejemplo, si un parámetro acepta el nombre de una persona y otro acepta la edad de la persona, una combinación de argumentos que proporcione la edad pero que omita el nombre es inaceptable.</span><span class="sxs-lookup"><span data-stu-id="12296-126">For example, if one parameter accepts a person's name and another accepts the person's age, a combination of arguments supplying the age but omitting the name is unacceptable.</span></span>  
  
2. <span data-ttu-id="12296-127">Para cada combinación aceptable de argumentos opcionales proporcionados, escriba `Sub` una `Function` instrucción de declaración o que defina la lista de parámetros correspondiente.</span><span class="sxs-lookup"><span data-stu-id="12296-127">For each acceptable combination of supplied optional arguments, write a `Sub` or `Function` declaration statement that defines the corresponding parameter list.</span></span> <span data-ttu-id="12296-128">No use la `Optional` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="12296-128">Do not use the `Optional` keyword.</span></span>  
  
3. <span data-ttu-id="12296-129">En cada declaración, preceda `Sub` `Function` a la palabra clave o con la palabra clave [Overloads](../../../language-reference/modifiers/overloads.md) .</span><span class="sxs-lookup"><span data-stu-id="12296-129">In each declaration, precede the `Sub` or `Function` keyword with the [Overloads](../../../language-reference/modifiers/overloads.md) keyword.</span></span>  
  
4. <span data-ttu-id="12296-130">Después de cada declaración, escriba el código de procedimiento que debe ejecutarse cuando el código de llamada proporciona una lista de argumentos correspondiente a la lista de parámetros de la declaración.</span><span class="sxs-lookup"><span data-stu-id="12296-130">Following each declaration, write the procedure code that should execute when the calling code supplies an argument list corresponding to that declaration's parameter list.</span></span>  
  
5. <span data-ttu-id="12296-131">Finalice cada procedimiento con la `End Sub` `End Function` instrucción o según corresponda.</span><span class="sxs-lookup"><span data-stu-id="12296-131">Terminate each procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12296-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="12296-132">See also</span></span>

- [<span data-ttu-id="12296-133">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="12296-133">Procedures</span></span>](./index.md)
- [<span data-ttu-id="12296-134">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="12296-134">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="12296-135">Parámetros opcionales</span><span class="sxs-lookup"><span data-stu-id="12296-135">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="12296-136">Matrices de parámetros</span><span class="sxs-lookup"><span data-stu-id="12296-136">Parameter Arrays</span></span>](./parameter-arrays.md)
- [<span data-ttu-id="12296-137">Sobrecarga de procedimientos</span><span class="sxs-lookup"><span data-stu-id="12296-137">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="12296-138">Solución de problemas de procedimientos</span><span class="sxs-lookup"><span data-stu-id="12296-138">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)
- [<span data-ttu-id="12296-139">Procedimiento para definir varias versiones de un procedimiento</span><span class="sxs-lookup"><span data-stu-id="12296-139">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)
- [<span data-ttu-id="12296-140">Procedimiento para llamar a un procedimiento sobrecargado</span><span class="sxs-lookup"><span data-stu-id="12296-140">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)
- [<span data-ttu-id="12296-141">Procedimiento para sobrecargar un procedimiento que toma un número indefinido de parámetros</span><span class="sxs-lookup"><span data-stu-id="12296-141">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [<span data-ttu-id="12296-142">Overload Resolution</span><span class="sxs-lookup"><span data-stu-id="12296-142">Overload Resolution</span></span>](./overload-resolution.md)
