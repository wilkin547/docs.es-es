---
title: Estructuras de control adicionales
ms.date: 07/20/2015
helpviewer_keywords:
- statements [Visual Basic], control flow
- control structures [Visual Basic]
ms.assetid: 24b811f7-98ba-40ec-8dd3-4d528cfa4574
ms.openlocfilehash: 8e7ca699e532ac7cfbe7918d850e7a28d1b27bcf
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91058617"
---
# <a name="other-control-structures-visual-basic"></a><span data-ttu-id="8a57c-102">Estructuras de control adicionales (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8a57c-102">Other Control Structures (Visual Basic)</span></span>

<span data-ttu-id="8a57c-103">Visual Basic proporciona estructuras de control que le ayudan a desechar un recurso o a reducir el número de veces que tiene que repetir una referencia de objeto.</span><span class="sxs-lookup"><span data-stu-id="8a57c-103">Visual Basic provides control structures that help you dispose of a resource or reduce the number of times you have to repeat an object reference.</span></span>  
  
## <a name="usingend-using-construction"></a><span data-ttu-id="8a57c-104">Usar... End using</span><span class="sxs-lookup"><span data-stu-id="8a57c-104">Using...End Using Construction</span></span>  

 <span data-ttu-id="8a57c-105">La `Using...End Using` construcción establece un bloque de instrucciones en el que se usa un recurso como una conexión SQL.</span><span class="sxs-lookup"><span data-stu-id="8a57c-105">The `Using...End Using` construction establishes a statement block within which you make use of a resource such as a SQL connection.</span></span> <span data-ttu-id="8a57c-106">Opcionalmente, puede adquirir el recurso con la `Using` instrucción.</span><span class="sxs-lookup"><span data-stu-id="8a57c-106">You can optionally acquire the resource with the `Using` statement.</span></span> <span data-ttu-id="8a57c-107">Al salir del `Using` bloque, Visual Basic desecha automáticamente el recurso para que esté disponible para que lo use otro código.</span><span class="sxs-lookup"><span data-stu-id="8a57c-107">When you exit the `Using` block, Visual Basic automatically disposes of the resource so that it is available for other code to use.</span></span> <span data-ttu-id="8a57c-108">El recurso debe ser local y descartable.</span><span class="sxs-lookup"><span data-stu-id="8a57c-108">The resource must be local and disposable.</span></span> <span data-ttu-id="8a57c-109">Para obtener más información, vea [using (instrucción](../../../language-reference/statements/using-statement.md)).</span><span class="sxs-lookup"><span data-stu-id="8a57c-109">For more information, see [Using Statement](../../../language-reference/statements/using-statement.md).</span></span>  
  
## <a name="withend-with-construction"></a><span data-ttu-id="8a57c-110">Con... End with (construcción)</span><span class="sxs-lookup"><span data-stu-id="8a57c-110">With...End With Construction</span></span>  

 <span data-ttu-id="8a57c-111">La `With...End With` construcción permite especificar una sola referencia de objeto y, a continuación, ejecutar una serie de instrucciones que tienen acceso a sus miembros.</span><span class="sxs-lookup"><span data-stu-id="8a57c-111">The `With...End With` construction lets you specify an object reference once and then run a series of statements that access its members.</span></span> <span data-ttu-id="8a57c-112">Esto puede simplificar el código y mejorar el rendimiento, ya que Visual Basic no tiene que volver a establecer la referencia para cada instrucción que tiene acceso a ella.</span><span class="sxs-lookup"><span data-stu-id="8a57c-112">This can simplify your code and improve performance because Visual Basic does not have to re-establish the reference for each statement that accesses it.</span></span> <span data-ttu-id="8a57c-113">Para obtener más información, vea [con... End with](../../../language-reference/statements/with-end-with-statement.md).</span><span class="sxs-lookup"><span data-stu-id="8a57c-113">For more information, see [With...End With Statement](../../../language-reference/statements/with-end-with-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a57c-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="8a57c-114">See also</span></span>

- [<span data-ttu-id="8a57c-115">Flujo de control</span><span class="sxs-lookup"><span data-stu-id="8a57c-115">Control Flow</span></span>](index.md)
- [<span data-ttu-id="8a57c-116">Estructuras de decisión</span><span class="sxs-lookup"><span data-stu-id="8a57c-116">Decision Structures</span></span>](decision-structures.md)
- [<span data-ttu-id="8a57c-117">Estructuras de bucle</span><span class="sxs-lookup"><span data-stu-id="8a57c-117">Loop Structures</span></span>](loop-structures.md)
- [<span data-ttu-id="8a57c-118">Estructuras de control anidadas</span><span class="sxs-lookup"><span data-stu-id="8a57c-118">Nested Control Structures</span></span>](nested-control-structures.md)
- [<span data-ttu-id="8a57c-119">Using (instrucción)</span><span class="sxs-lookup"><span data-stu-id="8a57c-119">Using Statement</span></span>](../../../language-reference/statements/using-statement.md)
- [<span data-ttu-id="8a57c-120">Instrucción With...End With</span><span class="sxs-lookup"><span data-stu-id="8a57c-120">With...End With Statement</span></span>](../../../language-reference/statements/with-end-with-statement.md)
