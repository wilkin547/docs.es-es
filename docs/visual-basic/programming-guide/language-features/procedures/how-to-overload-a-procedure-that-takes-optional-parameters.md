---
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
ms.openlocfilehash: 78ca6b2b95dfd5a7f208e5251f08dfccc5514946
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91071526"
---
# <a name="how-to-overload-a-procedure-that-takes-optional-parameters-visual-basic"></a><span data-ttu-id="405f9-102">Cómo: Sobrecargar un procedimiento que toma parámetros opcionales (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="405f9-102">How to: Overload a Procedure that Takes Optional Parameters (Visual Basic)</span></span>

<span data-ttu-id="405f9-103">Si un procedimiento tiene uno o varios parámetros [opcionales](../../../language-reference/modifiers/optional.md) , no se puede definir una versión sobrecargada que coincida con cualquiera de sus sobrecargas implícitas.</span><span class="sxs-lookup"><span data-stu-id="405f9-103">If a procedure has one or more [Optional](../../../language-reference/modifiers/optional.md) parameters, you cannot define an overloaded version matching any of its implicit overloads.</span></span> <span data-ttu-id="405f9-104">Para obtener más información, vea "sobrecargas implícitas para los parámetros opcionales" en [consideraciones sobre la sobrecarga de procedimientos](./considerations-in-overloading-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="405f9-104">For more information, see "Implicit Overloads for Optional Parameters" in [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
## <a name="one-optional-parameter"></a><span data-ttu-id="405f9-105">Un parámetro opcional</span><span class="sxs-lookup"><span data-stu-id="405f9-105">One Optional Parameter</span></span>  
  
#### <a name="to-overload-a-procedure-that-takes-one-optional-parameter"></a><span data-ttu-id="405f9-106">Para sobrecargar un procedimiento que toma un parámetro opcional</span><span class="sxs-lookup"><span data-stu-id="405f9-106">To overload a procedure that takes one optional parameter</span></span>  
  
1. <span data-ttu-id="405f9-107">Escriba una `Sub` `Function` instrucción de declaración o que incluya el parámetro opcional en la lista de parámetros.</span><span class="sxs-lookup"><span data-stu-id="405f9-107">Write a `Sub` or `Function` declaration statement that includes the optional parameter in the parameter list.</span></span> <span data-ttu-id="405f9-108">No use la `Optional` palabra clave en esta versión sobrecargada.</span><span class="sxs-lookup"><span data-stu-id="405f9-108">Do not use the `Optional` keyword in this overloaded version.</span></span>  
  
2. <span data-ttu-id="405f9-109">Preceda `Sub` `Function` a la palabra clave o con la palabra clave [Overloads](../../../language-reference/modifiers/overloads.md) .</span><span class="sxs-lookup"><span data-stu-id="405f9-109">Precede the `Sub` or `Function` keyword with the [Overloads](../../../language-reference/modifiers/overloads.md) keyword.</span></span>  
  
3. <span data-ttu-id="405f9-110">Escriba el código de procedimiento que debe ejecutarse cuando el código que realiza la llamada proporcione el argumento opcional.</span><span class="sxs-lookup"><span data-stu-id="405f9-110">Write the procedure code that should execute when the calling code supplies the optional argument.</span></span>  
  
4. <span data-ttu-id="405f9-111">Finalice el procedimiento con la `End Sub` `End Function` instrucción o según corresponda.</span><span class="sxs-lookup"><span data-stu-id="405f9-111">Terminate the procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
5. <span data-ttu-id="405f9-112">Escriba una segunda instrucción de declaración que sea idéntica a la primera declaración, salvo que no incluya el parámetro opcional en la lista de parámetros.</span><span class="sxs-lookup"><span data-stu-id="405f9-112">Write a second declaration statement that is identical to the first declaration except that it does not include the optional parameter in the parameter list.</span></span>  
  
6. <span data-ttu-id="405f9-113">Escriba el código de procedimiento que debe ejecutarse cuando el código de llamada no proporcione el argumento opcional.</span><span class="sxs-lookup"><span data-stu-id="405f9-113">Write the procedure code that should execute when the calling code does not supply the optional argument.</span></span> <span data-ttu-id="405f9-114">Finalice el procedimiento con la `End Sub` `End Function` instrucción o según corresponda.</span><span class="sxs-lookup"><span data-stu-id="405f9-114">Terminate the procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
     <span data-ttu-id="405f9-115">En el ejemplo siguiente se muestra un procedimiento definido con un parámetro opcional, un conjunto equivalente de dos procedimientos sobrecargados y, por último, ejemplos de versiones sobrecargadas y no válidas.</span><span class="sxs-lookup"><span data-stu-id="405f9-115">The following example shows a procedure defined with an optional parameter,  an equivalent set of two overloaded procedures, and finally examples of both invalid and valid overloaded versions.</span></span>  
  
     [!code-vb[VbVbcnProcedures#59](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#59)]  
  
     [!code-vb[VbVbcnProcedures#60](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#60)]  
  
     [!code-vb[VbVbcnProcedures#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#61)]  
  
## <a name="multiple-optional-parameters"></a><span data-ttu-id="405f9-116">Varios parámetros opcionales</span><span class="sxs-lookup"><span data-stu-id="405f9-116">Multiple Optional Parameters</span></span>  

 <span data-ttu-id="405f9-117">Para un procedimiento con más de un parámetro opcional, normalmente se necesitan más de dos versiones sobrecargadas.</span><span class="sxs-lookup"><span data-stu-id="405f9-117">For a procedure with more than one optional parameter, you normally need more than two overloaded versions.</span></span> <span data-ttu-id="405f9-118">Por ejemplo, si hay dos parámetros opcionales y el código de llamada puede proporcionar u omitir cada uno de ellos de forma independiente, se necesitan cuatro versiones sobrecargadas, una para cada combinación posible de argumentos proporcionados.</span><span class="sxs-lookup"><span data-stu-id="405f9-118">For example, if there are two optional parameters, and the calling code can supply or omit each one independently of the other, you need four overloaded versions, one for each possible combination of supplied arguments.</span></span>  
  
 <span data-ttu-id="405f9-119">A medida que aumenta el número de parámetros opcionales, aumenta la complejidad de la sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="405f9-119">As the number of optional parameters increases, the complexity of the overloading increases.</span></span> <span data-ttu-id="405f9-120">A menos que algunas combinaciones de los argumentos proporcionados no sean aceptables, para N parámetros opcionales necesita 2 ^ N versiones sobrecargadas.</span><span class="sxs-lookup"><span data-stu-id="405f9-120">Unless some combinations of supplied arguments are not acceptable, for N optional parameters you need 2 ^ N overloaded versions.</span></span> <span data-ttu-id="405f9-121">En función de la naturaleza del procedimiento, podría encontrar que la claridad de la lógica justifica el esfuerzo adicional de definir todas las versiones sobrecargadas.</span><span class="sxs-lookup"><span data-stu-id="405f9-121">Depending on the nature of the procedure, you might find that the clarity of logic justifies the extra effort of defining all the overloaded versions.</span></span>  
  
#### <a name="to-overload-a-procedure-that-takes-more-than-one-optional-parameter"></a><span data-ttu-id="405f9-122">Para sobrecargar un procedimiento que toma más de un parámetro opcional</span><span class="sxs-lookup"><span data-stu-id="405f9-122">To overload a procedure that takes more than one optional parameter</span></span>  
  
1. <span data-ttu-id="405f9-123">Determine qué combinaciones de argumentos opcionales proporcionados son aceptables para la lógica del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="405f9-123">Determine which combinations of supplied optional arguments are acceptable to the logic of the procedure.</span></span> <span data-ttu-id="405f9-124">Podría producirse una combinación inaceptable si un parámetro opcional depende de otro.</span><span class="sxs-lookup"><span data-stu-id="405f9-124">An unacceptable combination might arise if one optional parameter depends on another.</span></span> <span data-ttu-id="405f9-125">Por ejemplo, si un parámetro acepta el nombre de una persona y otro acepta la edad de la persona, una combinación de argumentos que proporcione la edad pero que omita el nombre es inaceptable.</span><span class="sxs-lookup"><span data-stu-id="405f9-125">For example, if one parameter accepts a person's name and another accepts the person's age, a combination of arguments supplying the age but omitting the name is unacceptable.</span></span>  
  
2. <span data-ttu-id="405f9-126">Para cada combinación aceptable de argumentos opcionales proporcionados, escriba `Sub` una `Function` instrucción de declaración o que defina la lista de parámetros correspondiente.</span><span class="sxs-lookup"><span data-stu-id="405f9-126">For each acceptable combination of supplied optional arguments, write a `Sub` or `Function` declaration statement that defines the corresponding parameter list.</span></span> <span data-ttu-id="405f9-127">No use la `Optional` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="405f9-127">Do not use the `Optional` keyword.</span></span>  
  
3. <span data-ttu-id="405f9-128">En cada declaración, preceda `Sub` `Function` a la palabra clave o con la palabra clave [Overloads](../../../language-reference/modifiers/overloads.md) .</span><span class="sxs-lookup"><span data-stu-id="405f9-128">In each declaration, precede the `Sub` or `Function` keyword with the [Overloads](../../../language-reference/modifiers/overloads.md) keyword.</span></span>  
  
4. <span data-ttu-id="405f9-129">Después de cada declaración, escriba el código de procedimiento que debe ejecutarse cuando el código de llamada proporciona una lista de argumentos correspondiente a la lista de parámetros de la declaración.</span><span class="sxs-lookup"><span data-stu-id="405f9-129">Following each declaration, write the procedure code that should execute when the calling code supplies an argument list corresponding to that declaration's parameter list.</span></span>  
  
5. <span data-ttu-id="405f9-130">Finalice cada procedimiento con la `End Sub` `End Function` instrucción o según corresponda.</span><span class="sxs-lookup"><span data-stu-id="405f9-130">Terminate each procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="405f9-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="405f9-131">See also</span></span>

- [<span data-ttu-id="405f9-132">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="405f9-132">Procedures</span></span>](./index.md)
- [<span data-ttu-id="405f9-133">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="405f9-133">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="405f9-134">Parámetros opcionales</span><span class="sxs-lookup"><span data-stu-id="405f9-134">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="405f9-135">Matrices de parámetros</span><span class="sxs-lookup"><span data-stu-id="405f9-135">Parameter Arrays</span></span>](./parameter-arrays.md)
- [<span data-ttu-id="405f9-136">Sobrecarga de procedimientos</span><span class="sxs-lookup"><span data-stu-id="405f9-136">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="405f9-137">Solución de problemas de procedimientos</span><span class="sxs-lookup"><span data-stu-id="405f9-137">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)
- [<span data-ttu-id="405f9-138">Procedimiento para definir varias versiones de un procedimiento</span><span class="sxs-lookup"><span data-stu-id="405f9-138">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)
- [<span data-ttu-id="405f9-139">Procedimiento para llamar a un procedimiento sobrecargado</span><span class="sxs-lookup"><span data-stu-id="405f9-139">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)
- [<span data-ttu-id="405f9-140">Procedimiento para sobrecargar un procedimiento que toma un número indefinido de parámetros</span><span class="sxs-lookup"><span data-stu-id="405f9-140">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [<span data-ttu-id="405f9-141">Overload Resolution</span><span class="sxs-lookup"><span data-stu-id="405f9-141">Overload Resolution</span></span>](./overload-resolution.md)
