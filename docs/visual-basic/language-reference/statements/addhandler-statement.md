---
title: AddHandler (Instrucción)
ms.date: 07/20/2015
f1_keywords:
- vb.AddHandlerMethod
- addhandler
- vb.addhandler
helpviewer_keywords:
- AddHandler statement [Visual Basic]
ms.assetid: cfe69799-2a0f-42c0-a99e-09fed954da01
ms.openlocfilehash: c110116af75d4fb39c016b8d6afcdb707fa6599b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350188"
---
# <a name="addhandler-statement"></a><span data-ttu-id="3be85-102">AddHandler (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="3be85-102">AddHandler Statement</span></span>
<span data-ttu-id="3be85-103">Associates an event with an event handler at run time.</span><span class="sxs-lookup"><span data-stu-id="3be85-103">Associates an event with an event handler at run time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3be85-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3be85-104">Syntax</span></span>  
  
```vb  
AddHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="3be85-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="3be85-105">Parts</span></span>  
|||
|---|---|
|<span data-ttu-id="3be85-106">evento</span><span class="sxs-lookup"><span data-stu-id="3be85-106">event</span></span>|<span data-ttu-id="3be85-107">The name of the event to handle.</span><span class="sxs-lookup"><span data-stu-id="3be85-107">The name of the event to handle.</span></span>|  
|`eventhandler`|<span data-ttu-id="3be85-108">The name of a procedure that handles the event.</span><span class="sxs-lookup"><span data-stu-id="3be85-108">The name of a procedure that handles the event.</span></span>|
|||
  
## <a name="remarks"></a><span data-ttu-id="3be85-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3be85-109">Remarks</span></span>  
 <span data-ttu-id="3be85-110">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling at any time during program execution.</span><span class="sxs-lookup"><span data-stu-id="3be85-110">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling at any time during program execution.</span></span>  
  
 <span data-ttu-id="3be85-111">The signature of the `eventhandler` procedure must match the signature of the event `event`.</span><span class="sxs-lookup"><span data-stu-id="3be85-111">The signature of the `eventhandler` procedure must match the signature of the event `event`.</span></span>  
  
 <span data-ttu-id="3be85-112">La palabra clave `Handles` y la instrucción `AddHandler` permiten especificar que determinados procedimientos controlen eventos determinados, pero hay diferencias.</span><span class="sxs-lookup"><span data-stu-id="3be85-112">The `Handles` keyword and the `AddHandler` statement both allow you to specify that particular procedures handle particular events, but there are differences.</span></span> <span data-ttu-id="3be85-113">La instrucción `AddHandler` conecta los procedimientos a los eventos en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="3be85-113">The `AddHandler` statement connects procedures to events at run time.</span></span> <span data-ttu-id="3be85-114">Use la palabra clave `Handles` al definir un procedimiento para especificar que controla un evento determinado.</span><span class="sxs-lookup"><span data-stu-id="3be85-114">Use the `Handles` keyword when defining a procedure to specify that it handles a particular event.</span></span> <span data-ttu-id="3be85-115">For more information, see [Handles](../../../visual-basic/language-reference/statements/handles-clause.md).</span><span class="sxs-lookup"><span data-stu-id="3be85-115">For more information, see [Handles](../../../visual-basic/language-reference/statements/handles-clause.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3be85-116">For custom events, the `AddHandler` statement invokes the event's `AddHandler` accessor.</span><span class="sxs-lookup"><span data-stu-id="3be85-116">For custom events, the `AddHandler` statement invokes the event's `AddHandler` accessor.</span></span> <span data-ttu-id="3be85-117">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="3be85-117">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3be85-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3be85-118">Example</span></span>  
 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="3be85-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="3be85-119">See also</span></span>

- [<span data-ttu-id="3be85-120">RemoveHandler (instrucción)</span><span class="sxs-lookup"><span data-stu-id="3be85-120">RemoveHandler Statement</span></span>](../../../visual-basic/language-reference/statements/removehandler-statement.md)
- [<span data-ttu-id="3be85-121">Handles</span><span class="sxs-lookup"><span data-stu-id="3be85-121">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)
- [<span data-ttu-id="3be85-122">Event (instrucción)</span><span class="sxs-lookup"><span data-stu-id="3be85-122">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="3be85-123">Eventos</span><span class="sxs-lookup"><span data-stu-id="3be85-123">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
