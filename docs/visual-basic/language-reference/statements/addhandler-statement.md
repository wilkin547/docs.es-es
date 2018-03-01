---
title: "AddHandler (Instrucción)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.AddHandlerMethod
- addhandler
- vb.addhandler
helpviewer_keywords:
- AddHandler statement [Visual Basic]
ms.assetid: cfe69799-2a0f-42c0-a99e-09fed954da01
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 07fbfe04ccd01b7d0f99338ef2682238830099dc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="addhandler-statement"></a><span data-ttu-id="6b164-102">AddHandler (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="6b164-102">AddHandler Statement</span></span>
<span data-ttu-id="6b164-103">Asocia un evento a un controlador de eventos en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="6b164-103">Associates an event with an event handler at run time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b164-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6b164-104">Syntax</span></span>  
  
```  
AddHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="6b164-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="6b164-105">Parts</span></span>  
 `event`  
 <span data-ttu-id="6b164-106">El nombre del evento que se va a controlar.</span><span class="sxs-lookup"><span data-stu-id="6b164-106">The name of the event to handle.</span></span>  
  
 `eventhandler`  
 <span data-ttu-id="6b164-107">El nombre de un procedimiento que controla el evento.</span><span class="sxs-lookup"><span data-stu-id="6b164-107">The name of a procedure that handles the event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6b164-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6b164-108">Remarks</span></span>  
 <span data-ttu-id="6b164-109">El `AddHandler` y `RemoveHandler` instrucciones permiten iniciar y detener el control de eventos en cualquier momento durante la ejecución del programa.</span><span class="sxs-lookup"><span data-stu-id="6b164-109">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling at any time during program execution.</span></span>  
  
 <span data-ttu-id="6b164-110">La firma de la `eventhandler` procedimiento debe coincidir con la firma del evento `event`.</span><span class="sxs-lookup"><span data-stu-id="6b164-110">The signature of the `eventhandler` procedure must match the signature of the event `event`.</span></span>  
  
 <span data-ttu-id="6b164-111">La palabra clave `Handles` y la instrucción `AddHandler` permiten especificar que determinados procedimientos controlen eventos determinados, pero hay diferencias.</span><span class="sxs-lookup"><span data-stu-id="6b164-111">The `Handles` keyword and the `AddHandler` statement both allow you to specify that particular procedures handle particular events, but there are differences.</span></span> <span data-ttu-id="6b164-112">La instrucción `AddHandler` conecta los procedimientos a los eventos en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="6b164-112">The `AddHandler` statement connects procedures to events at run time.</span></span> <span data-ttu-id="6b164-113">Use la palabra clave `Handles` al definir un procedimiento para especificar que controla un evento determinado.</span><span class="sxs-lookup"><span data-stu-id="6b164-113">Use the `Handles` keyword when defining a procedure to specify that it handles a particular event.</span></span> <span data-ttu-id="6b164-114">Para obtener más información, consulte [controla](../../../visual-basic/language-reference/statements/handles-clause.md).</span><span class="sxs-lookup"><span data-stu-id="6b164-114">For more information, see [Handles](../../../visual-basic/language-reference/statements/handles-clause.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6b164-115">Para los eventos personalizados, la `AddHandler` instrucción invoca el evento `AddHandler` descriptor de acceso.</span><span class="sxs-lookup"><span data-stu-id="6b164-115">For custom events, the `AddHandler` statement invokes the event's `AddHandler` accessor.</span></span> <span data-ttu-id="6b164-116">Para obtener más información sobre eventos personalizados, vea [Event (instrucción)](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="6b164-116">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b164-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6b164-117">Example</span></span>  
 [!code-vb[VbVbalrEvents#17](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/addhandler-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="6b164-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="6b164-118">See Also</span></span>  
 [<span data-ttu-id="6b164-119">RemoveHandler (instrucción)</span><span class="sxs-lookup"><span data-stu-id="6b164-119">RemoveHandler Statement</span></span>](../../../visual-basic/language-reference/statements/removehandler-statement.md)  
 [<span data-ttu-id="6b164-120">Handles</span><span class="sxs-lookup"><span data-stu-id="6b164-120">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)  
 [<span data-ttu-id="6b164-121">Event (instrucción)</span><span class="sxs-lookup"><span data-stu-id="6b164-121">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
 [<span data-ttu-id="6b164-122">Eventos</span><span class="sxs-lookup"><span data-stu-id="6b164-122">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
