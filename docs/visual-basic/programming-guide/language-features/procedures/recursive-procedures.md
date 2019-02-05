---
title: Procedimientos recursivos (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], that call themselves
- procedures [Visual Basic], recursive
- procedures [Visual Basic], calling
- recursive procedures
- functions [Visual Basic], calling recursively
- recursion
ms.assetid: ba1d3962-b4c3-48d3-875e-96fdb4198327
ms.openlocfilehash: b5cbe0dfa8053a93cde9c92ffe87f0eae15d3efd
ms.sourcegitcommit: facefcacd7ae2e5645e463bc841df213c505ffd4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2019
ms.locfileid: "55739298"
---
# <a name="recursive-procedures-visual-basic"></a><span data-ttu-id="a493a-102">Procedimientos recursivos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a493a-102">Recursive Procedures (Visual Basic)</span></span>
<span data-ttu-id="a493a-103">Un *recursiva* procedimiento es aquella que se llama a sí mismo.</span><span class="sxs-lookup"><span data-stu-id="a493a-103">A *recursive* procedure is one that calls itself.</span></span> <span data-ttu-id="a493a-104">En general, esto no es la manera más eficaz para escribir código de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="a493a-104">In general, this is not the most effective way to write Visual Basic code.</span></span>  
  
 <span data-ttu-id="a493a-105">El siguiente procedimiento usa la recursividad para calcular el factorial de su argumento original.</span><span class="sxs-lookup"><span data-stu-id="a493a-105">The following procedure uses recursion to calculate the factorial of its original argument.</span></span>  
  
 [!code-vb[VbVbcnProcedures#51](./codesnippet/VisualBasic/recursive-procedures_1.vb)]  
  
## <a name="considerations-with-recursive-procedures"></a><span data-ttu-id="a493a-106">Consideraciones sobre procedimientos recursivos</span><span class="sxs-lookup"><span data-stu-id="a493a-106">Considerations with Recursive Procedures</span></span>  
 <span data-ttu-id="a493a-107">**Condiciones de limitación**.</span><span class="sxs-lookup"><span data-stu-id="a493a-107">**Limiting Conditions**.</span></span> <span data-ttu-id="a493a-108">Debe diseñar un procedimiento recursivo para probar al menos una condición que puede dificultar la recursión y también deben considerar el caso donde no se cumple ninguna condición de ese tipo dentro de un número razonable de las llamadas recursivas.</span><span class="sxs-lookup"><span data-stu-id="a493a-108">You must design a recursive procedure to test for at least one condition that can terminate the recursion, and you must also handle the case where no such condition is satisfied within a reasonable number of recursive calls.</span></span> <span data-ttu-id="a493a-109">Sin al menos una condición que se puede cumplir sin errores, el procedimiento ejecuta un alto riesgo de la ejecución en un bucle infinito.</span><span class="sxs-lookup"><span data-stu-id="a493a-109">Without at least one condition that can be met without fail, your procedure runs a high risk of executing in an infinite loop.</span></span>  
  
 <span data-ttu-id="a493a-110">**Uso de memoria**.</span><span class="sxs-lookup"><span data-stu-id="a493a-110">**Memory Usage**.</span></span> <span data-ttu-id="a493a-111">La aplicación tiene una cantidad limitada de espacio para las variables locales.</span><span class="sxs-lookup"><span data-stu-id="a493a-111">Your application has a limited amount of space for local variables.</span></span> <span data-ttu-id="a493a-112">Cada vez que un procedimiento llama a sí mismo, utiliza más espacio para las copias adicionales de sus variables locales.</span><span class="sxs-lookup"><span data-stu-id="a493a-112">Each time a procedure calls itself, it uses more of that space for additional copies of its local variables.</span></span> <span data-ttu-id="a493a-113">Si este proceso continúa indefinidamente, finalmente provoca un <xref:System.StackOverflowException> error.</span><span class="sxs-lookup"><span data-stu-id="a493a-113">If this process continues indefinitely, it eventually causes a <xref:System.StackOverflowException> error.</span></span>  
  
 <span data-ttu-id="a493a-114">**Eficiencia**.</span><span class="sxs-lookup"><span data-stu-id="a493a-114">**Efficiency**.</span></span> <span data-ttu-id="a493a-115">Casi siempre se puede sustituir un bucle de recursión.</span><span class="sxs-lookup"><span data-stu-id="a493a-115">You can almost always substitute a loop for recursion.</span></span> <span data-ttu-id="a493a-116">Un bucle no tiene la sobrecarga de pasar argumentos, inicializar el almacenamiento adicional y devolver valores.</span><span class="sxs-lookup"><span data-stu-id="a493a-116">A loop does not have the overhead of passing arguments, initializing additional storage, and returning values.</span></span> <span data-ttu-id="a493a-117">El rendimiento puede ser mucho mayor sin llamadas recursivas.</span><span class="sxs-lookup"><span data-stu-id="a493a-117">Your performance can be much better without recursive calls.</span></span>  
  
 <span data-ttu-id="a493a-118">**Recursividad mutua**.</span><span class="sxs-lookup"><span data-stu-id="a493a-118">**Mutual Recursion**.</span></span> <span data-ttu-id="a493a-119">Es posible que observe un rendimiento muy deficiente o incluso un bucle infinito, si dos procedimientos llaman entre sí.</span><span class="sxs-lookup"><span data-stu-id="a493a-119">You might observe very poor performance, or even an infinite loop, if two procedures call each other.</span></span> <span data-ttu-id="a493a-120">Este tipo de diseño presenta los mismos problemas que un procedimiento recursivo único, pero puede ser difícil de detectar y depurar.</span><span class="sxs-lookup"><span data-stu-id="a493a-120">Such a design presents the same problems as a single recursive procedure, but can be harder to detect and debug.</span></span>  
  
 <span data-ttu-id="a493a-121">**Llamadas con paréntesis**.</span><span class="sxs-lookup"><span data-stu-id="a493a-121">**Calling with Parentheses**.</span></span> <span data-ttu-id="a493a-122">Cuando un `Function` procedimiento llama a sí mismo recursivamente, debe seguir el nombre del procedimiento con paréntesis, incluso si no hay ninguna lista de argumentos.</span><span class="sxs-lookup"><span data-stu-id="a493a-122">When a `Function` procedure calls itself recursively, you must follow the procedure name with parentheses, even if there is no argument list.</span></span> <span data-ttu-id="a493a-123">En caso contrario, se toma el nombre de la función representa el valor devuelto de la función.</span><span class="sxs-lookup"><span data-stu-id="a493a-123">Otherwise, the function name is taken as representing the return value of the function.</span></span>  
  
 <span data-ttu-id="a493a-124">**Las pruebas**.</span><span class="sxs-lookup"><span data-stu-id="a493a-124">**Testing**.</span></span> <span data-ttu-id="a493a-125">Si escribe un procedimiento recursivo, debe probarla con mucho cuidado para asegurarse de que siempre cumple alguna condición de limitación.</span><span class="sxs-lookup"><span data-stu-id="a493a-125">If you write a recursive procedure, you should test it very carefully to make sure it always meets some limiting condition.</span></span> <span data-ttu-id="a493a-126">También debe asegurarse de que no se ejecuta fuera de memoria debido a que hay demasiadas llamadas recursivas.</span><span class="sxs-lookup"><span data-stu-id="a493a-126">You should also ensure that you cannot run out of memory due to having too many recursive calls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a493a-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="a493a-127">See also</span></span>
- <xref:System.StackOverflowException>
- [<span data-ttu-id="a493a-128">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="a493a-128">Procedures</span></span>](./index.md)
- [<span data-ttu-id="a493a-129">Subprocedimientos</span><span class="sxs-lookup"><span data-stu-id="a493a-129">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="a493a-130">Procedimientos de función</span><span class="sxs-lookup"><span data-stu-id="a493a-130">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="a493a-131">Procedimientos de propiedades</span><span class="sxs-lookup"><span data-stu-id="a493a-131">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="a493a-132">Procedimientos de operadores</span><span class="sxs-lookup"><span data-stu-id="a493a-132">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="a493a-133">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="a493a-133">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="a493a-134">Sobrecarga de procedimientos</span><span class="sxs-lookup"><span data-stu-id="a493a-134">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="a493a-135">Solución de problemas de procedimientos</span><span class="sxs-lookup"><span data-stu-id="a493a-135">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)
- [<span data-ttu-id="a493a-136">Estructuras de bucle</span><span class="sxs-lookup"><span data-stu-id="a493a-136">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
