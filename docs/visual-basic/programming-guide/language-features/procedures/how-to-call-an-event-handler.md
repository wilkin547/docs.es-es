---
title: 'How to: Call an Event Handler'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- event handlers [Visual Basic], calling
- event handlers
- procedures [Visual Basic], event handlers
- procedures [Visual Basic], calling
ms.assetid: 72e18ef8-144e-40df-a1f4-066a57271e28
ms.openlocfilehash: 0c626a9ad92fe2cd0ea117a9abdd2965a09df2ea
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74340424"
---
# <a name="how-to-call-an-event-handler-in-visual-basic"></a><span data-ttu-id="26c7e-102">Cómo: Llamar a un controlador de eventos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="26c7e-102">How to: Call an Event Handler in Visual Basic</span></span>

<span data-ttu-id="26c7e-103">An *event* is an action or occurrence — such as a mouse click or a credit limit exceeded — that is recognized by some program component, and for which you can write code to respond.</span><span class="sxs-lookup"><span data-stu-id="26c7e-103">An *event* is an action or occurrence — such as a mouse click or a credit limit exceeded — that is recognized by some program component, and for which you can write code to respond.</span></span> <span data-ttu-id="26c7e-104">An *event handler* is the code you write to respond to an event.</span><span class="sxs-lookup"><span data-stu-id="26c7e-104">An *event handler* is the code you write to respond to an event.</span></span>

 <span data-ttu-id="26c7e-105">An event handler in Visual Basic is a `Sub` procedure.</span><span class="sxs-lookup"><span data-stu-id="26c7e-105">An event handler in Visual Basic is a `Sub` procedure.</span></span> <span data-ttu-id="26c7e-106">However, you do not normally call it the same way as other `Sub` procedures.</span><span class="sxs-lookup"><span data-stu-id="26c7e-106">However, you do not normally call it the same way as other `Sub` procedures.</span></span> <span data-ttu-id="26c7e-107">Instead, you identify the procedure as a handler for the event.</span><span class="sxs-lookup"><span data-stu-id="26c7e-107">Instead, you identify the procedure as a handler for the event.</span></span> <span data-ttu-id="26c7e-108">You can do this either with a [Handles](../../../language-reference/statements/handles-clause.md) clause and a [WithEvents](../../../language-reference/modifiers/withevents.md) variable, or with an [AddHandler Statement](../../../language-reference/statements/addhandler-statement.md).</span><span class="sxs-lookup"><span data-stu-id="26c7e-108">You can do this either with a [Handles](../../../language-reference/statements/handles-clause.md) clause and a [WithEvents](../../../language-reference/modifiers/withevents.md) variable, or with an [AddHandler Statement](../../../language-reference/statements/addhandler-statement.md).</span></span> <span data-ttu-id="26c7e-109">Using a `Handles` clause is the default way to declare an event handler in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="26c7e-109">Using a `Handles` clause is the default way to declare an event handler in Visual Basic.</span></span> <span data-ttu-id="26c7e-110">This is the way the event handlers are written by the designers when you program in the integrated development environment (IDE).</span><span class="sxs-lookup"><span data-stu-id="26c7e-110">This is the way the event handlers are written by the designers when you program in the integrated development environment (IDE).</span></span> <span data-ttu-id="26c7e-111">The `AddHandler` statement is suitable for raising events dynamically at run time.</span><span class="sxs-lookup"><span data-stu-id="26c7e-111">The `AddHandler` statement is suitable for raising events dynamically at run time.</span></span>

 <span data-ttu-id="26c7e-112">When the event occurs, Visual Basic automatically calls the event handler procedure.</span><span class="sxs-lookup"><span data-stu-id="26c7e-112">When the event occurs, Visual Basic automatically calls the event handler procedure.</span></span> <span data-ttu-id="26c7e-113">Any code that has access to the event can cause it to occur by executing a [RaiseEvent Statement](../../../language-reference/statements/raiseevent-statement.md).</span><span class="sxs-lookup"><span data-stu-id="26c7e-113">Any code that has access to the event can cause it to occur by executing a [RaiseEvent Statement](../../../language-reference/statements/raiseevent-statement.md).</span></span>

 <span data-ttu-id="26c7e-114">You can associate more than one event handler with the same event.</span><span class="sxs-lookup"><span data-stu-id="26c7e-114">You can associate more than one event handler with the same event.</span></span> <span data-ttu-id="26c7e-115">In some cases you can dissociate a handler from an event.</span><span class="sxs-lookup"><span data-stu-id="26c7e-115">In some cases you can dissociate a handler from an event.</span></span> <span data-ttu-id="26c7e-116">Para más información, vea [Eventos](../events/index.md).</span><span class="sxs-lookup"><span data-stu-id="26c7e-116">For more information, see [Events](../events/index.md).</span></span>

### <a name="to-call-an-event-handler-using-handles-and-withevents"></a><span data-ttu-id="26c7e-117">To call an event handler using Handles and WithEvents</span><span class="sxs-lookup"><span data-stu-id="26c7e-117">To call an event handler using Handles and WithEvents</span></span>

1. <span data-ttu-id="26c7e-118">Make sure the event is declared with an [Event Statement](../../../language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="26c7e-118">Make sure the event is declared with an [Event Statement](../../../language-reference/statements/event-statement.md).</span></span>

2. <span data-ttu-id="26c7e-119">Declare an object variable at module or class level, using the [WithEvents](../../../language-reference/modifiers/withevents.md) keyword.</span><span class="sxs-lookup"><span data-stu-id="26c7e-119">Declare an object variable at module or class level, using the [WithEvents](../../../language-reference/modifiers/withevents.md) keyword.</span></span> <span data-ttu-id="26c7e-120">The `As` clause for this variable must specify the class that raises the event.</span><span class="sxs-lookup"><span data-stu-id="26c7e-120">The `As` clause for this variable must specify the class that raises the event.</span></span>

3. <span data-ttu-id="26c7e-121">In the declaration of the event-handling `Sub` procedure, add a [Handles](../../../language-reference/statements/handles-clause.md) clause that specifies the `WithEvents` variable and the event name.</span><span class="sxs-lookup"><span data-stu-id="26c7e-121">In the declaration of the event-handling `Sub` procedure, add a [Handles](../../../language-reference/statements/handles-clause.md) clause that specifies the `WithEvents` variable and the event name.</span></span>

4. <span data-ttu-id="26c7e-122">When the event occurs, Visual Basic automatically calls the `Sub` procedure.</span><span class="sxs-lookup"><span data-stu-id="26c7e-122">When the event occurs, Visual Basic automatically calls the `Sub` procedure.</span></span> <span data-ttu-id="26c7e-123">Your code can use a `RaiseEvent` statement to make the event occur.</span><span class="sxs-lookup"><span data-stu-id="26c7e-123">Your code can use a `RaiseEvent` statement to make the event occur.</span></span>

     <span data-ttu-id="26c7e-124">The following example defines an event and a `WithEvents` variable that refers to the class that raises the event.</span><span class="sxs-lookup"><span data-stu-id="26c7e-124">The following example defines an event and a `WithEvents` variable that refers to the class that raises the event.</span></span> <span data-ttu-id="26c7e-125">The event-handling `Sub` procedure uses a `Handles` clause to specify the class and event it handles.</span><span class="sxs-lookup"><span data-stu-id="26c7e-125">The event-handling `Sub` procedure uses a `Handles` clause to specify the class and event it handles.</span></span>

     [!code-vb[VbVbcnProcedures#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#4)]

### <a name="to-call-an-event-handler-using-addhandler"></a><span data-ttu-id="26c7e-126">To call an event handler using AddHandler</span><span class="sxs-lookup"><span data-stu-id="26c7e-126">To call an event handler using AddHandler</span></span>

1. <span data-ttu-id="26c7e-127">Make sure the event is declared with an `Event` statement.</span><span class="sxs-lookup"><span data-stu-id="26c7e-127">Make sure the event is declared with an `Event` statement.</span></span>

2. <span data-ttu-id="26c7e-128">Execute an [AddHandler Statement](../../../language-reference/statements/addhandler-statement.md) to dynamically connect the event-handling `Sub` procedure with the event.</span><span class="sxs-lookup"><span data-stu-id="26c7e-128">Execute an [AddHandler Statement](../../../language-reference/statements/addhandler-statement.md) to dynamically connect the event-handling `Sub` procedure with the event.</span></span>

3. <span data-ttu-id="26c7e-129">When the event occurs, Visual Basic automatically calls the `Sub` procedure.</span><span class="sxs-lookup"><span data-stu-id="26c7e-129">When the event occurs, Visual Basic automatically calls the `Sub` procedure.</span></span> <span data-ttu-id="26c7e-130">Your code can use a `RaiseEvent` statement to make the event occur.</span><span class="sxs-lookup"><span data-stu-id="26c7e-130">Your code can use a `RaiseEvent` statement to make the event occur.</span></span>

     <span data-ttu-id="26c7e-131">The following example defines a `Sub` procedure to handle the <xref:System.Windows.Forms.Form.Closing> event of a form.</span><span class="sxs-lookup"><span data-stu-id="26c7e-131">The following example defines a `Sub` procedure to handle the <xref:System.Windows.Forms.Form.Closing> event of a form.</span></span> <span data-ttu-id="26c7e-132">It then uses the [AddHandler Statement](../../../language-reference/statements/addhandler-statement.md) to associate the `catchClose` procedure as an event handler for <xref:System.Windows.Forms.Form.Closing>.</span><span class="sxs-lookup"><span data-stu-id="26c7e-132">It then uses the [AddHandler Statement](../../../language-reference/statements/addhandler-statement.md) to associate the `catchClose` procedure as an event handler for <xref:System.Windows.Forms.Form.Closing>.</span></span>

     [!code-vb[VbVbcnProcedures#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#5)]

     <span data-ttu-id="26c7e-133">You can dissociate an event handler from an event by executing the [RemoveHandler Statement](../../../language-reference/statements/removehandler-statement.md).</span><span class="sxs-lookup"><span data-stu-id="26c7e-133">You can dissociate an event handler from an event by executing the [RemoveHandler Statement](../../../language-reference/statements/removehandler-statement.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="26c7e-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="26c7e-134">See also</span></span>

- [<span data-ttu-id="26c7e-135">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="26c7e-135">Procedures</span></span>](index.md)
- [<span data-ttu-id="26c7e-136">Subprocedimientos</span><span class="sxs-lookup"><span data-stu-id="26c7e-136">Sub Procedures</span></span>](sub-procedures.md)
- [<span data-ttu-id="26c7e-137">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="26c7e-137">Sub Statement</span></span>](../../../language-reference/statements/sub-statement.md)
- [<span data-ttu-id="26c7e-138">AddressOf (operador)</span><span class="sxs-lookup"><span data-stu-id="26c7e-138">AddressOf Operator</span></span>](../../../language-reference/operators/addressof-operator.md)
- [<span data-ttu-id="26c7e-139">Crear un procedimiento</span><span class="sxs-lookup"><span data-stu-id="26c7e-139">How to: Create a Procedure</span></span>](how-to-create-a-procedure.md)
- [<span data-ttu-id="26c7e-140">Llamar a un procedimiento que no devuelve un valor</span><span class="sxs-lookup"><span data-stu-id="26c7e-140">How to: Call a Procedure that Does Not Return a Value</span></span>](how-to-call-a-procedure-that-does-not-return-a-value.md)
