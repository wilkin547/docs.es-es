---
title: Estructuras de control adicionales (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- statements [Visual Basic], control flow
- control structures [Visual Basic]
ms.assetid: 24b811f7-98ba-40ec-8dd3-4d528cfa4574
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4e1ea44cf2f0405dc55f8df60fb842691e50a9a0
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="other-control-structures-visual-basic"></a><span data-ttu-id="10efa-102">Estructuras de control adicionales (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="10efa-102">Other Control Structures (Visual Basic)</span></span>
<span data-ttu-id="10efa-103">Visual Basic proporciona estructuras de control que le ayudarán a deshacerse de un recurso o reducen el número de veces que tiene que repetir una referencia de objeto.</span><span class="sxs-lookup"><span data-stu-id="10efa-103">Visual Basic provides control structures that help you dispose of a resource or reduce the number of times you have to repeat an object reference.</span></span>  
  
## <a name="usingend-using-construction"></a><span data-ttu-id="10efa-104">Uso de... Finalizar utilizando una construcción</span><span class="sxs-lookup"><span data-stu-id="10efa-104">Using...End Using Construction</span></span>  
 <span data-ttu-id="10efa-105">El `Using...End Using` construcción establece un bloque de instrucciones dentro del cual el uso de un recurso como una conexión de SQL.</span><span class="sxs-lookup"><span data-stu-id="10efa-105">The `Using...End Using` construction establishes a statement block within which you make use of a resource such as a SQL connection.</span></span> <span data-ttu-id="10efa-106">Opcionalmente, puede adquirir el recurso con el `Using` instrucción.</span><span class="sxs-lookup"><span data-stu-id="10efa-106">You can optionally acquire the resource with the `Using` statement.</span></span> <span data-ttu-id="10efa-107">Al salir del `Using` bloque, Visual Basic se elimina automáticamente del recurso para que esté disponible para otro código.</span><span class="sxs-lookup"><span data-stu-id="10efa-107">When you exit the `Using` block, Visual Basic automatically disposes of the resource so that it is available for other code to use.</span></span> <span data-ttu-id="10efa-108">El recurso debe ser local y descartable.</span><span class="sxs-lookup"><span data-stu-id="10efa-108">The resource must be local and disposable.</span></span> <span data-ttu-id="10efa-109">Para obtener más información, vea [Using (Instrucción)](../../../../visual-basic/language-reference/statements/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="10efa-109">For more information, see [Using Statement](../../../../visual-basic/language-reference/statements/using-statement.md).</span></span>  
  
## <a name="withend-with-construction"></a><span data-ttu-id="10efa-110">Con... Finalizar con la construcción</span><span class="sxs-lookup"><span data-stu-id="10efa-110">With...End With Construction</span></span>  
 <span data-ttu-id="10efa-111">El `With...End With` construcción le permite especificar una referencia de objeto una vez y, a continuación, ejecutar una serie de instrucciones que tienen acceso a sus miembros.</span><span class="sxs-lookup"><span data-stu-id="10efa-111">The `With...End With` construction lets you specify an object reference once and then run a series of statements that access its members.</span></span> <span data-ttu-id="10efa-112">Esto puede simplificar el código y mejorar el rendimiento porque Visual Basic no tiene que volver a establecer la referencia para cada instrucción que tiene acceso a él.</span><span class="sxs-lookup"><span data-stu-id="10efa-112">This can simplify your code and improve performance because Visual Basic does not have to re-establish the reference for each statement that accesses it.</span></span> <span data-ttu-id="10efa-113">Para obtener más información, consulte [con... Terminar con la instrucción](../../../../visual-basic/language-reference/statements/with-end-with-statement.md).</span><span class="sxs-lookup"><span data-stu-id="10efa-113">For more information, see [With...End With Statement](../../../../visual-basic/language-reference/statements/with-end-with-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10efa-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="10efa-114">See Also</span></span>  
 [<span data-ttu-id="10efa-115">Flujo de control</span><span class="sxs-lookup"><span data-stu-id="10efa-115">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)  
 [<span data-ttu-id="10efa-116">Estructuras de decisión</span><span class="sxs-lookup"><span data-stu-id="10efa-116">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)  
 [<span data-ttu-id="10efa-117">Estructuras de bucle</span><span class="sxs-lookup"><span data-stu-id="10efa-117">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [<span data-ttu-id="10efa-118">Estructuras de control anidadas</span><span class="sxs-lookup"><span data-stu-id="10efa-118">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [<span data-ttu-id="10efa-119">Using (instrucción)</span><span class="sxs-lookup"><span data-stu-id="10efa-119">Using Statement</span></span>](../../../../visual-basic/language-reference/statements/using-statement.md)  
 [<span data-ttu-id="10efa-120">With...End With (instrucción)</span><span class="sxs-lookup"><span data-stu-id="10efa-120">With...End With Statement</span></span>](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)
