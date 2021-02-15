---
description: 'Más información sobre: otras estructuras de control (Visual Basic)'
title: Estructuras de control adicionales
ms.date: 07/20/2015
helpviewer_keywords:
- statements [Visual Basic], control flow
- control structures [Visual Basic]
ms.assetid: 24b811f7-98ba-40ec-8dd3-4d528cfa4574
ms.openlocfilehash: 39654b8c780369eeea043087c8a04e2ba1f928c2
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100473581"
---
# <a name="other-control-structures-visual-basic"></a><span data-ttu-id="095c6-103">Estructuras de control adicionales (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="095c6-103">Other Control Structures (Visual Basic)</span></span>

<span data-ttu-id="095c6-104">Visual Basic proporciona estructuras de control que le ayudan a desechar un recurso o a reducir el número de veces que tiene que repetir una referencia de objeto.</span><span class="sxs-lookup"><span data-stu-id="095c6-104">Visual Basic provides control structures that help you dispose of a resource or reduce the number of times you have to repeat an object reference.</span></span>  
  
## <a name="usingend-using-construction"></a><span data-ttu-id="095c6-105">Usar... End using</span><span class="sxs-lookup"><span data-stu-id="095c6-105">Using...End Using Construction</span></span>  

 <span data-ttu-id="095c6-106">La `Using...End Using` construcción establece un bloque de instrucciones en el que se usa un recurso como una conexión SQL.</span><span class="sxs-lookup"><span data-stu-id="095c6-106">The `Using...End Using` construction establishes a statement block within which you make use of a resource such as a SQL connection.</span></span> <span data-ttu-id="095c6-107">Opcionalmente, puede adquirir el recurso con la `Using` instrucción.</span><span class="sxs-lookup"><span data-stu-id="095c6-107">You can optionally acquire the resource with the `Using` statement.</span></span> <span data-ttu-id="095c6-108">Al salir del `Using` bloque, Visual Basic desecha automáticamente el recurso para que esté disponible para que lo use otro código.</span><span class="sxs-lookup"><span data-stu-id="095c6-108">When you exit the `Using` block, Visual Basic automatically disposes of the resource so that it is available for other code to use.</span></span> <span data-ttu-id="095c6-109">El recurso debe ser local y descartable.</span><span class="sxs-lookup"><span data-stu-id="095c6-109">The resource must be local and disposable.</span></span> <span data-ttu-id="095c6-110">Para obtener más información, vea [Using (Instrucción)](../../../language-reference/statements/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="095c6-110">For more information, see [Using Statement](../../../language-reference/statements/using-statement.md).</span></span>  
  
## <a name="withend-with-construction"></a><span data-ttu-id="095c6-111">Con... End with (construcción)</span><span class="sxs-lookup"><span data-stu-id="095c6-111">With...End With Construction</span></span>  

 <span data-ttu-id="095c6-112">La `With...End With` construcción permite especificar una sola referencia de objeto y, a continuación, ejecutar una serie de instrucciones que tienen acceso a sus miembros.</span><span class="sxs-lookup"><span data-stu-id="095c6-112">The `With...End With` construction lets you specify an object reference once and then run a series of statements that access its members.</span></span> <span data-ttu-id="095c6-113">Esto puede simplificar el código y mejorar el rendimiento, ya que Visual Basic no tiene que volver a establecer la referencia para cada instrucción que tiene acceso a ella.</span><span class="sxs-lookup"><span data-stu-id="095c6-113">This can simplify your code and improve performance because Visual Basic does not have to re-establish the reference for each statement that accesses it.</span></span> <span data-ttu-id="095c6-114">Para obtener más información, vea [con... End with](../../../language-reference/statements/with-end-with-statement.md).</span><span class="sxs-lookup"><span data-stu-id="095c6-114">For more information, see [With...End With Statement](../../../language-reference/statements/with-end-with-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="095c6-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="095c6-115">See also</span></span>

- [<span data-ttu-id="095c6-116">Flujo de control</span><span class="sxs-lookup"><span data-stu-id="095c6-116">Control Flow</span></span>](index.md)
- [<span data-ttu-id="095c6-117">Estructuras de decisión</span><span class="sxs-lookup"><span data-stu-id="095c6-117">Decision Structures</span></span>](decision-structures.md)
- [<span data-ttu-id="095c6-118">Estructuras de bucle</span><span class="sxs-lookup"><span data-stu-id="095c6-118">Loop Structures</span></span>](loop-structures.md)
- [<span data-ttu-id="095c6-119">Estructuras de control anidadas</span><span class="sxs-lookup"><span data-stu-id="095c6-119">Nested Control Structures</span></span>](nested-control-structures.md)
- [<span data-ttu-id="095c6-120">Instrucción Using</span><span class="sxs-lookup"><span data-stu-id="095c6-120">Using Statement</span></span>](../../../language-reference/statements/using-statement.md)
- [<span data-ttu-id="095c6-121">Instrucción With...End With</span><span class="sxs-lookup"><span data-stu-id="095c6-121">With...End With Statement</span></span>](../../../language-reference/statements/with-end-with-statement.md)
