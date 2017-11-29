---
title: Estructuras de control adicionales (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- statements [Visual Basic], control flow
- control structures [Visual Basic]
ms.assetid: 24b811f7-98ba-40ec-8dd3-4d528cfa4574
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 09e59d25b3b2fc89026295e8500c30dad7b75086
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="other-control-structures-visual-basic"></a><span data-ttu-id="97ac8-102">Estructuras de control adicionales (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="97ac8-102">Other Control Structures (Visual Basic)</span></span>
[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="97ac8-103">proporciona estructuras de control que le ayudarán a deshacerse de un recurso o reducen el número de veces que tiene que repetir una referencia de objeto.</span><span class="sxs-lookup"><span data-stu-id="97ac8-103"> provides control structures that help you dispose of a resource or reduce the number of times you have to repeat an object reference.</span></span>  
  
## <a name="usingend-using-construction"></a><span data-ttu-id="97ac8-104">Uso de... Finalizar utilizando una construcción</span><span class="sxs-lookup"><span data-stu-id="97ac8-104">Using...End Using Construction</span></span>  
 <span data-ttu-id="97ac8-105">El `Using...End Using` construcción establece un bloque de instrucciones dentro del cual el uso de un recurso como una conexión de SQL.</span><span class="sxs-lookup"><span data-stu-id="97ac8-105">The `Using...End Using` construction establishes a statement block within which you make use of a resource such as a SQL connection.</span></span> <span data-ttu-id="97ac8-106">Opcionalmente, puede adquirir el recurso con el `Using` instrucción.</span><span class="sxs-lookup"><span data-stu-id="97ac8-106">You can optionally acquire the resource with the `Using` statement.</span></span> <span data-ttu-id="97ac8-107">Al salir del `Using` bloque, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] elimina automáticamente el recurso para que esté disponible para otro código.</span><span class="sxs-lookup"><span data-stu-id="97ac8-107">When you exit the `Using` block, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] automatically disposes of the resource so that it is available for other code to use.</span></span> <span data-ttu-id="97ac8-108">El recurso debe ser local y descartable.</span><span class="sxs-lookup"><span data-stu-id="97ac8-108">The resource must be local and disposable.</span></span> <span data-ttu-id="97ac8-109">Para obtener más información, vea [Using (Instrucción)](../../../../visual-basic/language-reference/statements/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="97ac8-109">For more information, see [Using Statement](../../../../visual-basic/language-reference/statements/using-statement.md).</span></span>  
  
## <a name="withend-with-construction"></a><span data-ttu-id="97ac8-110">Con... Finalizar con la construcción</span><span class="sxs-lookup"><span data-stu-id="97ac8-110">With...End With Construction</span></span>  
 <span data-ttu-id="97ac8-111">El `With...End With` construcción le permite especificar una referencia de objeto una vez y, a continuación, ejecutar una serie de instrucciones que tienen acceso a sus miembros.</span><span class="sxs-lookup"><span data-stu-id="97ac8-111">The `With...End With` construction lets you specify an object reference once and then run a series of statements that access its members.</span></span> <span data-ttu-id="97ac8-112">Esto puede simplificar el código y mejorar el rendimiento porque [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] no tiene que volver a establecer la referencia para cada instrucción que tiene acceso a él.</span><span class="sxs-lookup"><span data-stu-id="97ac8-112">This can simplify your code and improve performance because [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] does not have to re-establish the reference for each statement that accesses it.</span></span> <span data-ttu-id="97ac8-113">Para obtener más información, consulte [con... Terminar con la instrucción](../../../../visual-basic/language-reference/statements/with-end-with-statement.md).</span><span class="sxs-lookup"><span data-stu-id="97ac8-113">For more information, see [With...End With Statement](../../../../visual-basic/language-reference/statements/with-end-with-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97ac8-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="97ac8-114">See Also</span></span>  
 [<span data-ttu-id="97ac8-115">Flujo de control</span><span class="sxs-lookup"><span data-stu-id="97ac8-115">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)  
 [<span data-ttu-id="97ac8-116">Estructuras de decisión</span><span class="sxs-lookup"><span data-stu-id="97ac8-116">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)  
 [<span data-ttu-id="97ac8-117">Estructuras de bucle</span><span class="sxs-lookup"><span data-stu-id="97ac8-117">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [<span data-ttu-id="97ac8-118">Estructuras de control anidadas</span><span class="sxs-lookup"><span data-stu-id="97ac8-118">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [<span data-ttu-id="97ac8-119">Using (instrucción)</span><span class="sxs-lookup"><span data-stu-id="97ac8-119">Using Statement</span></span>](../../../../visual-basic/language-reference/statements/using-statement.md)  
 [<span data-ttu-id="97ac8-120">With...End With (instrucción)</span><span class="sxs-lookup"><span data-stu-id="97ac8-120">With...End With Statement</span></span>](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)
