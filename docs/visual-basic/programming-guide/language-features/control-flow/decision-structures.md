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
ms.openlocfilehash: f0df649c4be50e9cadd51258c89137b68b4ffe22
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963197"
---
# <a name="decision-structures-visual-basic"></a><span data-ttu-id="20743-102">Estructuras de decisión (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="20743-102">Decision Structures (Visual Basic)</span></span>
<span data-ttu-id="20743-103">Visual Basic le permite probar condiciones y realizar diferentes operaciones en función de los resultados de esa prueba.</span><span class="sxs-lookup"><span data-stu-id="20743-103">Visual Basic lets you test conditions and perform different operations depending on the results of that test.</span></span> <span data-ttu-id="20743-104">Puede comprobar si una condición es true o false, para varios valores de una expresión o para diversas excepciones generadas al ejecutar una serie de instrucciones.</span><span class="sxs-lookup"><span data-stu-id="20743-104">You can test for a condition being true or false, for various values of an expression, or for various exceptions generated when you execute a series of statements.</span></span>  
  
 <span data-ttu-id="20743-105">En la ilustración siguiente se muestra una estructura de decisión que comprueba si una condición es verdadera y realiza diferentes acciones en función de si es true o false.</span><span class="sxs-lookup"><span data-stu-id="20743-105">The following illustration shows a decision structure that tests for a condition being true and takes different actions depending on whether it is true or false.</span></span>  
  
 ![Un diagrama de flujo de If...Then...Else construcción.](./media/decision-structures/if-then-else-construction.gif)  
  
## <a name="ifthenelse-construction"></a><span data-ttu-id="20743-107">If...Then...Else construcción</span><span class="sxs-lookup"><span data-stu-id="20743-107">If...Then...Else Construction</span></span>  
 <span data-ttu-id="20743-108">`If...Then...Else`las construcciones permiten probar una o varias condiciones y ejecutar una o varias instrucciones en función de cada condición.</span><span class="sxs-lookup"><span data-stu-id="20743-108">`If...Then...Else` constructions let you test for one or more conditions and run one or more statements depending on each condition.</span></span> <span data-ttu-id="20743-109">Puede probar las condiciones y tomar medidas de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="20743-109">You can test conditions and take actions in the following ways:</span></span>  
  
- <span data-ttu-id="20743-110">Ejecutar una o varias instrucciones si una condición es`True`</span><span class="sxs-lookup"><span data-stu-id="20743-110">Run one or more statements if a condition is `True`</span></span>  
  
- <span data-ttu-id="20743-111">Ejecutar una o varias instrucciones si una condición es`False`</span><span class="sxs-lookup"><span data-stu-id="20743-111">Run one or more statements if a condition is `False`</span></span>  
  
- <span data-ttu-id="20743-112">Ejecutar algunas instrucciones si una condición es `True` y otras si es`False`</span><span class="sxs-lookup"><span data-stu-id="20743-112">Run some statements if a condition is `True` and others if it is `False`</span></span>  
  
- <span data-ttu-id="20743-113">Probar una condición adicional si una condición anterior es`False`</span><span class="sxs-lookup"><span data-stu-id="20743-113">Test an additional condition if a prior condition is `False`</span></span>  
  
 <span data-ttu-id="20743-114">La estructura de control que ofrece todas estas posibilidades es el [If...Then...Else instrucción](../../../../visual-basic/language-reference/statements/if-then-else-statement.md).</span><span class="sxs-lookup"><span data-stu-id="20743-114">The control structure that offers all these possibilities is the [If...Then...Else Statement](../../../../visual-basic/language-reference/statements/if-then-else-statement.md).</span></span> <span data-ttu-id="20743-115">Puede usar una versión de una sola línea si solo tiene una prueba y una instrucción para ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="20743-115">You can use a single-line version if you have just one test and one statement to run.</span></span> <span data-ttu-id="20743-116">Si tiene un conjunto más complejo de condiciones y acciones, puede usar la versión de varias líneas.</span><span class="sxs-lookup"><span data-stu-id="20743-116">If you have a more complex set of conditions and actions, you can use the multiple-line version.</span></span>  
  
## <a name="selectcase-construction"></a><span data-ttu-id="20743-117">Select...Case construcción</span><span class="sxs-lookup"><span data-stu-id="20743-117">Select...Case Construction</span></span>  
 <span data-ttu-id="20743-118">La `Select...Case` construcción permite evaluar una expresión una vez y ejecutar diferentes conjuntos de instrucciones en función de los distintos valores posibles.</span><span class="sxs-lookup"><span data-stu-id="20743-118">The `Select...Case` construction lets you evaluate an expression one time and run different sets of statements based on different possible values.</span></span> <span data-ttu-id="20743-119">Para obtener más información, vea [Instrucción Select...Case](../../../../visual-basic/language-reference/statements/select-case-statement.md).</span><span class="sxs-lookup"><span data-stu-id="20743-119">For more information, see [Select...Case Statement](../../../../visual-basic/language-reference/statements/select-case-statement.md).</span></span>  
  
## <a name="trycatchfinally-construction"></a><span data-ttu-id="20743-120">Try...Catch...Finally, construcción</span><span class="sxs-lookup"><span data-stu-id="20743-120">Try...Catch...Finally Construction</span></span>  
 <span data-ttu-id="20743-121">`Try...Catch...Finally`las construcciones permiten ejecutar un conjunto de instrucciones en un entorno que conserva el control si una de las instrucciones produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="20743-121">`Try...Catch...Finally` constructions let you run a set of statements under an environment that retains control if any one of your statements causes an exception.</span></span> <span data-ttu-id="20743-122">Puede realizar diferentes acciones para diferentes excepciones.</span><span class="sxs-lookup"><span data-stu-id="20743-122">You can take different actions for different exceptions.</span></span> <span data-ttu-id="20743-123">Opcionalmente, puede especificar un bloque de código que se ejecuta antes de salir de `Try...Catch...Finally` la construcción completa, independientemente de lo que suceda.</span><span class="sxs-lookup"><span data-stu-id="20743-123">You can optionally specify a block of code that runs before you exit the whole `Try...Catch...Finally` construction, regardless of what occurs.</span></span> <span data-ttu-id="20743-124">Para obtener más información, vea [Instrucción Try...Catch...Finally](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="20743-124">For more information, see [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="20743-125">En el caso de muchas estructuras de control, al hacer clic en una palabra clave, se resaltan todas las palabras clave de la estructura.</span><span class="sxs-lookup"><span data-stu-id="20743-125">For many control structures, when you click a keyword, all of the keywords in the structure are highlighted.</span></span> <span data-ttu-id="20743-126">Por ejemplo, al hacer clic `If` en en `If...Then...Else` una construcción, se resaltan `ElseIf`todas `Else`las instancias `End If` de `If`, `Then`,, y en la construcción.</span><span class="sxs-lookup"><span data-stu-id="20743-126">For instance, when you click `If` in an `If...Then...Else` construction, all instances of `If`, `Then`, `ElseIf`, `Else`, and `End If` in the construction are highlighted.</span></span> <span data-ttu-id="20743-127">Para desplazarse a la palabra clave resaltada siguiente o anterior, presione CTRL + MAYÚS + flecha abajo o CTRL + MAYÚS + flecha arriba.</span><span class="sxs-lookup"><span data-stu-id="20743-127">To move to the next or previous highlighted keyword, press CTRL+SHIFT+DOWN ARROW or CTRL+SHIFT+UP ARROW.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20743-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="20743-128">See also</span></span>

- [<span data-ttu-id="20743-129">Flujo de control</span><span class="sxs-lookup"><span data-stu-id="20743-129">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [<span data-ttu-id="20743-130">Estructuras de bucle</span><span class="sxs-lookup"><span data-stu-id="20743-130">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="20743-131">Estructuras de control adicionales</span><span class="sxs-lookup"><span data-stu-id="20743-131">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
- [<span data-ttu-id="20743-132">Estructuras de control anidadas</span><span class="sxs-lookup"><span data-stu-id="20743-132">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="20743-133">If (operador)</span><span class="sxs-lookup"><span data-stu-id="20743-133">If Operator</span></span>](../../../../visual-basic/language-reference/operators/if-operator.md)
