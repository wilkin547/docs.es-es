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
ms.openlocfilehash: b08a06a07f134b7c95251848862d39339e59fe61
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274339"
---
# <a name="recursive-procedures-visual-basic"></a><span data-ttu-id="1092a-102">Procedimientos recursivos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1092a-102">Recursive Procedures (Visual Basic)</span></span>

<span data-ttu-id="1092a-103">Un procedimiento *recursivo* es uno que se llama a sí mismo.</span><span class="sxs-lookup"><span data-stu-id="1092a-103">A *recursive* procedure is one that calls itself.</span></span> <span data-ttu-id="1092a-104">En general, esta no es la forma más eficaz de escribir código de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="1092a-104">In general, this is not the most effective way to write Visual Basic code.</span></span>  
  
 <span data-ttu-id="1092a-105">En el procedimiento siguiente se usa la recursividad para calcular el factorial de su argumento original.</span><span class="sxs-lookup"><span data-stu-id="1092a-105">The following procedure uses recursion to calculate the factorial of its original argument.</span></span>  
  
 [!code-vb[VbVbcnProcedures#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#51)]  
  
## <a name="considerations-with-recursive-procedures"></a><span data-ttu-id="1092a-106">Consideraciones con procedimientos recursivos</span><span class="sxs-lookup"><span data-stu-id="1092a-106">Considerations with Recursive Procedures</span></span>

 <span data-ttu-id="1092a-107">**Condiciones de limitación**.</span><span class="sxs-lookup"><span data-stu-id="1092a-107">**Limiting Conditions**.</span></span> <span data-ttu-id="1092a-108">Debe diseñar un procedimiento recursivo para probar al menos una condición que pueda finalizar la recursividad, y también debe controlar el caso en el que no se cumpla esa condición en un número razonable de llamadas recursivas.</span><span class="sxs-lookup"><span data-stu-id="1092a-108">You must design a recursive procedure to test for at least one condition that can terminate the recursion, and you must also handle the case where no such condition is satisfied within a reasonable number of recursive calls.</span></span> <span data-ttu-id="1092a-109">Si no hay al menos una condición que pueda cumplirse sin errores, el procedimiento ejecuta un alto riesgo de ejecutarse en un bucle infinito.</span><span class="sxs-lookup"><span data-stu-id="1092a-109">Without at least one condition that can be met without fail, your procedure runs a high risk of executing in an infinite loop.</span></span>

 <span data-ttu-id="1092a-110">**Uso de memoria**.</span><span class="sxs-lookup"><span data-stu-id="1092a-110">**Memory Usage**.</span></span> <span data-ttu-id="1092a-111">La aplicación tiene una cantidad limitada de espacio para las variables locales.</span><span class="sxs-lookup"><span data-stu-id="1092a-111">Your application has a limited amount of space for local variables.</span></span> <span data-ttu-id="1092a-112">Cada vez que un procedimiento se llama a sí mismo, usa más espacio para las copias adicionales de sus variables locales.</span><span class="sxs-lookup"><span data-stu-id="1092a-112">Each time a procedure calls itself, it uses more of that space for additional copies of its local variables.</span></span> <span data-ttu-id="1092a-113">Si este proceso continúa indefinidamente, se produce un <xref:System.StackOverflowException> error.</span><span class="sxs-lookup"><span data-stu-id="1092a-113">If this process continues indefinitely, it eventually causes a <xref:System.StackOverflowException> error.</span></span>

 <span data-ttu-id="1092a-114">**Eficacia**.</span><span class="sxs-lookup"><span data-stu-id="1092a-114">**Efficiency**.</span></span> <span data-ttu-id="1092a-115">Casi siempre se puede sustituir un bucle por recursividad.</span><span class="sxs-lookup"><span data-stu-id="1092a-115">You can almost always substitute a loop for recursion.</span></span> <span data-ttu-id="1092a-116">Un bucle no tiene la sobrecarga de pasar argumentos, inicializar almacenamiento adicional y devolver valores.</span><span class="sxs-lookup"><span data-stu-id="1092a-116">A loop does not have the overhead of passing arguments, initializing additional storage, and returning values.</span></span> <span data-ttu-id="1092a-117">El rendimiento puede ser mucho mejor sin llamadas recursivas.</span><span class="sxs-lookup"><span data-stu-id="1092a-117">Your performance can be much better without recursive calls.</span></span>

 <span data-ttu-id="1092a-118">**Recursividad mutua**.</span><span class="sxs-lookup"><span data-stu-id="1092a-118">**Mutual Recursion**.</span></span> <span data-ttu-id="1092a-119">Es posible que observe un rendimiento muy deficiente, o incluso un bucle infinito, si dos procedimientos se llaman entre sí.</span><span class="sxs-lookup"><span data-stu-id="1092a-119">You might observe very poor performance, or even an infinite loop, if two procedures call each other.</span></span> <span data-ttu-id="1092a-120">Este tipo de diseño presenta los mismos problemas que un único procedimiento recursivo, pero puede ser más difícil de detectar y depurar.</span><span class="sxs-lookup"><span data-stu-id="1092a-120">Such a design presents the same problems as a single recursive procedure, but can be harder to detect and debug.</span></span>

 <span data-ttu-id="1092a-121">**Llamar a con paréntesis**.</span><span class="sxs-lookup"><span data-stu-id="1092a-121">**Calling with Parentheses**.</span></span> <span data-ttu-id="1092a-122">Cuando un `Function` procedimiento se llama a sí mismo de forma recursiva, debe seguir el nombre del procedimiento entre paréntesis, incluso si no hay ninguna lista de argumentos.</span><span class="sxs-lookup"><span data-stu-id="1092a-122">When a `Function` procedure calls itself recursively, you must follow the procedure name with parentheses, even if there is no argument list.</span></span> <span data-ttu-id="1092a-123">De lo contrario, el nombre de la función se toma como representa el valor devuelto de la función.</span><span class="sxs-lookup"><span data-stu-id="1092a-123">Otherwise, the function name is taken as representing the return value of the function.</span></span>

 <span data-ttu-id="1092a-124">**Pruebas**.</span><span class="sxs-lookup"><span data-stu-id="1092a-124">**Testing**.</span></span> <span data-ttu-id="1092a-125">Si escribe un procedimiento recursivo, debe probarlo con cuidado para asegurarse de que siempre cumple alguna condición de limitación.</span><span class="sxs-lookup"><span data-stu-id="1092a-125">If you write a recursive procedure, you should test it very carefully to make sure it always meets some limiting condition.</span></span> <span data-ttu-id="1092a-126">También debe asegurarse de que no se puede quedarse sin memoria debido a que hay demasiadas llamadas recursivas.</span><span class="sxs-lookup"><span data-stu-id="1092a-126">You should also ensure that you cannot run out of memory due to having too many recursive calls.</span></span>

## <a name="see-also"></a><span data-ttu-id="1092a-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="1092a-127">See also</span></span>

- <xref:System.StackOverflowException>
- [<span data-ttu-id="1092a-128">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="1092a-128">Procedures</span></span>](index.md)
- [<span data-ttu-id="1092a-129">Subprocedimientos</span><span class="sxs-lookup"><span data-stu-id="1092a-129">Sub Procedures</span></span>](sub-procedures.md)
- [<span data-ttu-id="1092a-130">Procedimientos de función</span><span class="sxs-lookup"><span data-stu-id="1092a-130">Function Procedures</span></span>](function-procedures.md)
- [<span data-ttu-id="1092a-131">Procedimientos de propiedades</span><span class="sxs-lookup"><span data-stu-id="1092a-131">Property Procedures</span></span>](property-procedures.md)
- [<span data-ttu-id="1092a-132">Procedimientos de operadores</span><span class="sxs-lookup"><span data-stu-id="1092a-132">Operator Procedures</span></span>](operator-procedures.md)
- [<span data-ttu-id="1092a-133">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="1092a-133">Procedure Parameters and Arguments</span></span>](procedure-parameters-and-arguments.md)
- [<span data-ttu-id="1092a-134">Sobrecarga de procedimientos</span><span class="sxs-lookup"><span data-stu-id="1092a-134">Procedure Overloading</span></span>](procedure-overloading.md)
- [<span data-ttu-id="1092a-135">Solución de problemas de procedimientos</span><span class="sxs-lookup"><span data-stu-id="1092a-135">Troubleshooting Procedures</span></span>](troubleshooting-procedures.md)
- [<span data-ttu-id="1092a-136">Estructuras de bucle</span><span class="sxs-lookup"><span data-stu-id="1092a-136">Loop Structures</span></span>](../control-flow/loop-structures.md)
