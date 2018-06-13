---
title: Estructuras de control adicionales (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- statements [Visual Basic], control flow
- control structures [Visual Basic]
ms.assetid: 24b811f7-98ba-40ec-8dd3-4d528cfa4574
ms.openlocfilehash: 272ebcf0639b83a51e87de5ebbf93d7e750c03a7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33654114"
---
# <a name="other-control-structures-visual-basic"></a><span data-ttu-id="b3376-102">Estructuras de control adicionales (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b3376-102">Other Control Structures (Visual Basic)</span></span>
<span data-ttu-id="b3376-103">Visual Basic proporciona estructuras de control que le ayudarán a deshacerse de un recurso o reducen el número de veces que tiene que repetir una referencia de objeto.</span><span class="sxs-lookup"><span data-stu-id="b3376-103">Visual Basic provides control structures that help you dispose of a resource or reduce the number of times you have to repeat an object reference.</span></span>  
  
## <a name="usingend-using-construction"></a><span data-ttu-id="b3376-104">Uso de... Finalizar utilizando una construcción</span><span class="sxs-lookup"><span data-stu-id="b3376-104">Using...End Using Construction</span></span>  
 <span data-ttu-id="b3376-105">El `Using...End Using` construcción establece un bloque de instrucciones dentro del cual el uso de un recurso como una conexión de SQL.</span><span class="sxs-lookup"><span data-stu-id="b3376-105">The `Using...End Using` construction establishes a statement block within which you make use of a resource such as a SQL connection.</span></span> <span data-ttu-id="b3376-106">Opcionalmente, puede adquirir el recurso con el `Using` instrucción.</span><span class="sxs-lookup"><span data-stu-id="b3376-106">You can optionally acquire the resource with the `Using` statement.</span></span> <span data-ttu-id="b3376-107">Al salir del `Using` bloque, Visual Basic se elimina automáticamente del recurso para que esté disponible para otro código.</span><span class="sxs-lookup"><span data-stu-id="b3376-107">When you exit the `Using` block, Visual Basic automatically disposes of the resource so that it is available for other code to use.</span></span> <span data-ttu-id="b3376-108">El recurso debe ser local y descartable.</span><span class="sxs-lookup"><span data-stu-id="b3376-108">The resource must be local and disposable.</span></span> <span data-ttu-id="b3376-109">Para obtener más información, vea [Using (Instrucción)](../../../../visual-basic/language-reference/statements/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b3376-109">For more information, see [Using Statement](../../../../visual-basic/language-reference/statements/using-statement.md).</span></span>  
  
## <a name="withend-with-construction"></a><span data-ttu-id="b3376-110">Con... Finalizar con la construcción</span><span class="sxs-lookup"><span data-stu-id="b3376-110">With...End With Construction</span></span>  
 <span data-ttu-id="b3376-111">El `With...End With` construcción le permite especificar una referencia de objeto una vez y, a continuación, ejecutar una serie de instrucciones que tienen acceso a sus miembros.</span><span class="sxs-lookup"><span data-stu-id="b3376-111">The `With...End With` construction lets you specify an object reference once and then run a series of statements that access its members.</span></span> <span data-ttu-id="b3376-112">Esto puede simplificar el código y mejorar el rendimiento porque Visual Basic no tiene que volver a establecer la referencia para cada instrucción que tiene acceso a él.</span><span class="sxs-lookup"><span data-stu-id="b3376-112">This can simplify your code and improve performance because Visual Basic does not have to re-establish the reference for each statement that accesses it.</span></span> <span data-ttu-id="b3376-113">Para obtener más información, consulte [con... Terminar con la instrucción](../../../../visual-basic/language-reference/statements/with-end-with-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b3376-113">For more information, see [With...End With Statement](../../../../visual-basic/language-reference/statements/with-end-with-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3376-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="b3376-114">See Also</span></span>  
 [<span data-ttu-id="b3376-115">Flujo de control</span><span class="sxs-lookup"><span data-stu-id="b3376-115">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)  
 [<span data-ttu-id="b3376-116">Estructuras de decisión</span><span class="sxs-lookup"><span data-stu-id="b3376-116">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)  
 [<span data-ttu-id="b3376-117">Estructuras de bucle</span><span class="sxs-lookup"><span data-stu-id="b3376-117">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [<span data-ttu-id="b3376-118">Estructuras de control anidadas</span><span class="sxs-lookup"><span data-stu-id="b3376-118">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [<span data-ttu-id="b3376-119">Using (instrucción)</span><span class="sxs-lookup"><span data-stu-id="b3376-119">Using Statement</span></span>](../../../../visual-basic/language-reference/statements/using-statement.md)  
 [<span data-ttu-id="b3376-120">With...End With (instrucción)</span><span class="sxs-lookup"><span data-stu-id="b3376-120">With...End With Statement</span></span>](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)
