---
title: Estructuras de decisión (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- statements [Visual Basic], control flow
- If statement [Visual Basic], decision structures
- If statement [Visual Basic], If...Then...Else
- control flow [Visual Basic], decision structures
- decision structures [Visual Basic]
- conditional statements [Visual Basic], decision structures
ms.assetid: 2e2e0895-4483-442a-b17c-26aead751ec2
ms.openlocfilehash: f8b653b941c5959036256cde097a41f8c6251c7a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64601242"
---
# <a name="decision-structures-visual-basic"></a><span data-ttu-id="07df9-102">Estructuras de decisión (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="07df9-102">Decision Structures (Visual Basic)</span></span>
<span data-ttu-id="07df9-103">Visual Basic le permite probar condiciones y realizar diferentes operaciones en función de los resultados de la prueba.</span><span class="sxs-lookup"><span data-stu-id="07df9-103">Visual Basic lets you test conditions and perform different operations depending on the results of that test.</span></span> <span data-ttu-id="07df9-104">Se puede comprobar una condición es true o false para distintos valores de una expresión, o varias excepciones que se genera cuando se ejecuta una serie de instrucciones.</span><span class="sxs-lookup"><span data-stu-id="07df9-104">You can test for a condition being true or false, for various values of an expression, or for various exceptions generated when you execute a series of statements.</span></span>  
  
 <span data-ttu-id="07df9-105">La siguiente ilustración muestra una estructura de decisión que comprueba una condición es true y realiza acciones diferentes dependiendo de si es true o false.</span><span class="sxs-lookup"><span data-stu-id="07df9-105">The following illustration shows a decision structure that tests for a condition being true and takes different actions depending on whether it is true or false.</span></span>  
  
 ![Un diagrama de flujo de If... Entonces... Otra construcción.](./media/decision-structures/if-then-else-construction.gif)  
  
## <a name="ifthenelse-construction"></a><span data-ttu-id="07df9-107">If... Entonces... Construcción else</span><span class="sxs-lookup"><span data-stu-id="07df9-107">If...Then...Else Construction</span></span>  
 <span data-ttu-id="07df9-108">`If...Then...Else` construcciones le permiten probar uno o más condiciones y ejecutar una o varias instrucciones según cada condición.</span><span class="sxs-lookup"><span data-stu-id="07df9-108">`If...Then...Else` constructions let you test for one or more conditions and run one or more statements depending on each condition.</span></span> <span data-ttu-id="07df9-109">Puede probar condiciones y realizar acciones de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="07df9-109">You can test conditions and take actions in the following ways:</span></span>  
  
- <span data-ttu-id="07df9-110">Ejecutar una o varias instrucciones si una condición es `True`</span><span class="sxs-lookup"><span data-stu-id="07df9-110">Run one or more statements if a condition is `True`</span></span>  
  
- <span data-ttu-id="07df9-111">Ejecutar una o varias instrucciones si una condición es `False`</span><span class="sxs-lookup"><span data-stu-id="07df9-111">Run one or more statements if a condition is `False`</span></span>  
  
- <span data-ttu-id="07df9-112">Ejecutar algunas instrucciones si una condición es `True` y otros usuarios si es `False`</span><span class="sxs-lookup"><span data-stu-id="07df9-112">Run some statements if a condition is `True` and others if it is `False`</span></span>  
  
- <span data-ttu-id="07df9-113">Probar una condición adicional si es un requisito previo `False`</span><span class="sxs-lookup"><span data-stu-id="07df9-113">Test an additional condition if a prior condition is `False`</span></span>  
  
 <span data-ttu-id="07df9-114">La estructura de control que ofrece todas estas posibilidades es la [si... Entonces... Else (instrucción)](../../../../visual-basic/language-reference/statements/if-then-else-statement.md).</span><span class="sxs-lookup"><span data-stu-id="07df9-114">The control structure that offers all these possibilities is the [If...Then...Else Statement](../../../../visual-basic/language-reference/statements/if-then-else-statement.md).</span></span> <span data-ttu-id="07df9-115">Puede usar una versión de línea, si tiene una prueba y una instrucción para ejecutar.</span><span class="sxs-lookup"><span data-stu-id="07df9-115">You can use a single-line version if you have just one test and one statement to run.</span></span> <span data-ttu-id="07df9-116">Si tiene un conjunto de condiciones y acciones más complejo, puede usar la versión de varias líneas.</span><span class="sxs-lookup"><span data-stu-id="07df9-116">If you have a more complex set of conditions and actions, you can use the multiple-line version.</span></span>  
  
## <a name="selectcase-construction"></a><span data-ttu-id="07df9-117">Seleccione... Construcción de casos</span><span class="sxs-lookup"><span data-stu-id="07df9-117">Select...Case Construction</span></span>  
 <span data-ttu-id="07df9-118">El `Select...Case` construcción que le permite evaluar una expresión una vez y ejecutar distintos conjuntos de instrucciones basadas en diferentes valores posibles.</span><span class="sxs-lookup"><span data-stu-id="07df9-118">The `Select...Case` construction lets you evaluate an expression one time and run different sets of statements based on different possible values.</span></span> <span data-ttu-id="07df9-119">Para obtener más información, consulte [seleccione... Instrucción de caso](../../../../visual-basic/language-reference/statements/select-case-statement.md).</span><span class="sxs-lookup"><span data-stu-id="07df9-119">For more information, see [Select...Case Statement](../../../../visual-basic/language-reference/statements/select-case-statement.md).</span></span>  
  
## <a name="trycatchfinally-construction"></a><span data-ttu-id="07df9-120">Try... Catch... Por último, construcción</span><span class="sxs-lookup"><span data-stu-id="07df9-120">Try...Catch...Finally Construction</span></span>  
 <span data-ttu-id="07df9-121">`Try...Catch...Finally` permiten ejecutar un conjunto de instrucciones en un entorno que conserva el control si cualquiera de las instrucciones provoca una excepción.</span><span class="sxs-lookup"><span data-stu-id="07df9-121">`Try...Catch...Finally` constructions let you run a set of statements under an environment that retains control if any one of your statements causes an exception.</span></span> <span data-ttu-id="07df9-122">Puede realizar acciones diferentes para diferentes excepciones.</span><span class="sxs-lookup"><span data-stu-id="07df9-122">You can take different actions for different exceptions.</span></span> <span data-ttu-id="07df9-123">También puede especificar un bloque de código que se ejecuta antes de salir de la totalidad `Try...Catch...Finally` construcción, independientemente de lo que ocurre.</span><span class="sxs-lookup"><span data-stu-id="07df9-123">You can optionally specify a block of code that runs before you exit the whole `Try...Catch...Finally` construction, regardless of what occurs.</span></span> <span data-ttu-id="07df9-124">Para obtener más información, vea [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) (Try...Catch...Finally [Instrucción, Visual Basic]).</span><span class="sxs-lookup"><span data-stu-id="07df9-124">For more information, see [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="07df9-125">Para muchas de las estructuras de control, al hacer clic en una palabra clave, se resaltan todas las palabras clave en la estructura.</span><span class="sxs-lookup"><span data-stu-id="07df9-125">For many control structures, when you click a keyword, all of the keywords in the structure are highlighted.</span></span> <span data-ttu-id="07df9-126">Por ejemplo, al hacer clic en `If` en un `If...Then...Else` construcción, todas las instancias de `If`, `Then`, `ElseIf`, `Else`, y `End If` se resaltan en la construcción.</span><span class="sxs-lookup"><span data-stu-id="07df9-126">For instance, when you click `If` in an `If...Then...Else` construction, all instances of `If`, `Then`, `ElseIf`, `Else`, and `End If` in the construction are highlighted.</span></span> <span data-ttu-id="07df9-127">Para mover a la palabra clave resaltada siguiente o anterior, presione CTRL + MAYÚS + flecha abajo o CTRL + MAYÚS + flecha arriba.</span><span class="sxs-lookup"><span data-stu-id="07df9-127">To move to the next or previous highlighted keyword, press CTRL+SHIFT+DOWN ARROW or CTRL+SHIFT+UP ARROW.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07df9-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="07df9-128">See also</span></span>

- [<span data-ttu-id="07df9-129">Flujo de control</span><span class="sxs-lookup"><span data-stu-id="07df9-129">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [<span data-ttu-id="07df9-130">Estructuras de bucle</span><span class="sxs-lookup"><span data-stu-id="07df9-130">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="07df9-131">Estructuras de control adicionales</span><span class="sxs-lookup"><span data-stu-id="07df9-131">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
- [<span data-ttu-id="07df9-132">Estructuras de control anidadas</span><span class="sxs-lookup"><span data-stu-id="07df9-132">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="07df9-133">If (operador)</span><span class="sxs-lookup"><span data-stu-id="07df9-133">If Operator</span></span>](../../../../visual-basic/language-reference/operators/if-operator.md)
