---
title: 'Cómo: Llamar a un controlador de eventos en Visual Basic'
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic code, procedures
- event handlers [Visual Basic], calling
- event handlers
- procedures [Visual Basic], event handlers
- procedures [Visual Basic], calling
ms.assetid: 72e18ef8-144e-40df-a1f4-066a57271e28
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2b8a35459fdeb7cce0b494a9b3024a79bd4173cc
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-call-an-event-handler-in-visual-basic"></a><span data-ttu-id="7cfca-102">Cómo: Llamar a un controlador de eventos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7cfca-102">How to: Call an Event Handler in Visual Basic</span></span>
<span data-ttu-id="7cfca-103">Un *eventos* es una acción o una aparición, como un mouse, haga clic en o un límite de crédito superado, que es reconocido por algún componente del programa y, por lo que puede escribir código para responder.</span><span class="sxs-lookup"><span data-stu-id="7cfca-103">An *event* is an action or occurrence — such as a mouse click or a credit limit exceeded — that is recognized by some program component, and for which you can write code to respond.</span></span> <span data-ttu-id="7cfca-104">Un *controlador de eventos* es el código que escribe para responder a un evento.</span><span class="sxs-lookup"><span data-stu-id="7cfca-104">An *event handler* is the code you write to respond to an event.</span></span>  
  
 <span data-ttu-id="7cfca-105">Un controlador de eventos en Visual Basic es un `Sub` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="7cfca-105">An event handler in Visual Basic is a `Sub` procedure.</span></span> <span data-ttu-id="7cfca-106">Sin embargo, no normalmente se llama, la misma manera que otras `Sub` procedimientos.</span><span class="sxs-lookup"><span data-stu-id="7cfca-106">However, you do not normally call it the same way as other `Sub` procedures.</span></span> <span data-ttu-id="7cfca-107">En su lugar, se identifica el procedimiento como un controlador para el evento.</span><span class="sxs-lookup"><span data-stu-id="7cfca-107">Instead, you identify the procedure as a handler for the event.</span></span> <span data-ttu-id="7cfca-108">Puede hacerlo con un [controla](../../../../visual-basic/language-reference/statements/handles-clause.md) cláusula y un [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) variable, o con un [AddHandler (instrucción)](../../../../visual-basic/language-reference/statements/addhandler-statement.md).</span><span class="sxs-lookup"><span data-stu-id="7cfca-108">You can do this either with a [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) clause and a [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) variable, or with an [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md).</span></span> <span data-ttu-id="7cfca-109">Mediante un `Handles` cláusula es el modo predeterminado para declarar un controlador de eventos en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="7cfca-109">Using a `Handles` clause is the default way to declare an event handler in Visual Basic.</span></span> <span data-ttu-id="7cfca-110">Esta es la manera en que los controladores de eventos se escriben los diseñadores al programar en el entorno de desarrollo integrado (IDE).</span><span class="sxs-lookup"><span data-stu-id="7cfca-110">This is the way the event handlers are written by the designers when you program in the integrated development environment (IDE).</span></span> <span data-ttu-id="7cfca-111">El `AddHandler` instrucción es adecuada para generar eventos de forma dinámica en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="7cfca-111">The `AddHandler` statement is suitable for raising events dynamically at run time.</span></span>  
  
 <span data-ttu-id="7cfca-112">Cuando se produce el evento, Visual Basic llama automáticamente al procedimiento del controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="7cfca-112">When the event occurs, Visual Basic automatically calls the event handler procedure.</span></span> <span data-ttu-id="7cfca-113">Cualquier código que tenga acceso al evento puede hacer que se producen al ejecutar un [RaiseEvent (instrucción)](../../../../visual-basic/language-reference/statements/raiseevent-statement.md).</span><span class="sxs-lookup"><span data-stu-id="7cfca-113">Any code that has access to the event can cause it to occur by executing a [RaiseEvent Statement](../../../../visual-basic/language-reference/statements/raiseevent-statement.md).</span></span>  
  
 <span data-ttu-id="7cfca-114">Puede asociar más de un controlador de eventos con el mismo evento.</span><span class="sxs-lookup"><span data-stu-id="7cfca-114">You can associate more than one event handler with the same event.</span></span> <span data-ttu-id="7cfca-115">En algunos casos puede desasociar un controlador de un evento.</span><span class="sxs-lookup"><span data-stu-id="7cfca-115">In some cases you can dissociate a handler from an event.</span></span> <span data-ttu-id="7cfca-116">Para más información, vea [Eventos](../../../../visual-basic/programming-guide/language-features/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="7cfca-116">For more information, see [Events](../../../../visual-basic/programming-guide/language-features/events/index.md).</span></span>  
  
### <a name="to-call-an-event-handler-using-handles-and-withevents"></a><span data-ttu-id="7cfca-117">Para llamar a un controlador de eventos utilizando Handles y WithEvents</span><span class="sxs-lookup"><span data-stu-id="7cfca-117">To call an event handler using Handles and WithEvents</span></span>  
  
1.  <span data-ttu-id="7cfca-118">Asegúrese de que el evento se declara con un [Event (instrucción)](../../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="7cfca-118">Make sure the event is declared with an [Event Statement](../../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
2.  <span data-ttu-id="7cfca-119">Declare una variable de objeto en el módulo o clase nivel, con el [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) palabra clave.</span><span class="sxs-lookup"><span data-stu-id="7cfca-119">Declare an object variable at module or class level, using the [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) keyword.</span></span> <span data-ttu-id="7cfca-120">El `As` cláusula para esta variable debe especificar la clase que provoca el evento.</span><span class="sxs-lookup"><span data-stu-id="7cfca-120">The `As` clause for this variable must specify the class that raises the event.</span></span>  
  
3.  <span data-ttu-id="7cfca-121">En la declaración de control de eventos `Sub` procedimiento, agregue un [controla](../../../../visual-basic/language-reference/statements/handles-clause.md) cláusula que especifica la `WithEvents` variable y el nombre del evento.</span><span class="sxs-lookup"><span data-stu-id="7cfca-121">In the declaration of the event-handling `Sub` procedure, add a [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) clause that specifies the `WithEvents` variable and the event name.</span></span>  
  
4.  <span data-ttu-id="7cfca-122">Cuando se produce el evento, Visual Basic llama automáticamente a la `Sub` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="7cfca-122">When the event occurs, Visual Basic automatically calls the `Sub` procedure.</span></span> <span data-ttu-id="7cfca-123">El código puede usar un `RaiseEvent` instrucción que se va a hacer que se produzca el evento.</span><span class="sxs-lookup"><span data-stu-id="7cfca-123">Your code can use a `RaiseEvent` statement to make the event occur.</span></span>  
  
     <span data-ttu-id="7cfca-124">En el ejemplo siguiente se define un evento y un `WithEvents` variable que hace referencia a la clase que provoca el evento.</span><span class="sxs-lookup"><span data-stu-id="7cfca-124">The following example defines an event and a `WithEvents` variable that refers to the class that raises the event.</span></span> <span data-ttu-id="7cfca-125">El control de eventos `Sub` procedimiento usa un `Handles` cláusula para especificar la clase y controla el evento.</span><span class="sxs-lookup"><span data-stu-id="7cfca-125">The event-handling `Sub` procedure uses a `Handles` clause to specify the class and event it handles.</span></span>  
  
     [!code-vb[VbVbcnProcedures#4](./codesnippet/VisualBasic/how-to-call-an-event-handler_1.vb)]  
  
### <a name="to-call-an-event-handler-using-addhandler"></a><span data-ttu-id="7cfca-126">Para llamar a un controlador de eventos utilizando AddHandler</span><span class="sxs-lookup"><span data-stu-id="7cfca-126">To call an event handler using AddHandler</span></span>  
  
1.  <span data-ttu-id="7cfca-127">Asegúrese de que el evento se declara con un `Event` instrucción.</span><span class="sxs-lookup"><span data-stu-id="7cfca-127">Make sure the event is declared with an `Event` statement.</span></span>  
  
2.  <span data-ttu-id="7cfca-128">Ejecutar un [AddHandler (instrucción)](../../../../visual-basic/language-reference/statements/addhandler-statement.md) para conectar de forma dinámica el control de eventos `Sub` procedimiento con el evento.</span><span class="sxs-lookup"><span data-stu-id="7cfca-128">Execute an [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md) to dynamically connect the event-handling `Sub` procedure with the event.</span></span>  
  
3.  <span data-ttu-id="7cfca-129">Cuando se produce el evento, Visual Basic llama automáticamente a la `Sub` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="7cfca-129">When the event occurs, Visual Basic automatically calls the `Sub` procedure.</span></span> <span data-ttu-id="7cfca-130">El código puede usar un `RaiseEvent` instrucción que se va a hacer que se produzca el evento.</span><span class="sxs-lookup"><span data-stu-id="7cfca-130">Your code can use a `RaiseEvent` statement to make the event occur.</span></span>  
  
     <span data-ttu-id="7cfca-131">En el ejemplo siguiente se define un `Sub` procedimiento para controlar la <xref:System.Windows.Forms.Form.Closing> eventos de un formulario.</span><span class="sxs-lookup"><span data-stu-id="7cfca-131">The following example defines a `Sub` procedure to handle the <xref:System.Windows.Forms.Form.Closing> event of a form.</span></span> <span data-ttu-id="7cfca-132">A continuación, utiliza el [AddHandler (instrucción)](../../../../visual-basic/language-reference/statements/addhandler-statement.md) para asociar el `catchClose` procedimiento como un controlador de eventos para <xref:System.Windows.Forms.Form.Closing>.</span><span class="sxs-lookup"><span data-stu-id="7cfca-132">It then uses the [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md) to associate the `catchClose` procedure as an event handler for <xref:System.Windows.Forms.Form.Closing>.</span></span>  
  
     [!code-vb[VbVbcnProcedures#5](./codesnippet/VisualBasic/how-to-call-an-event-handler_2.vb)]  
  
     <span data-ttu-id="7cfca-133">Puede anular la asociación de un controlador de eventos de un evento mediante la ejecución de la [RemoveHandler (instrucción)](../../../../visual-basic/language-reference/statements/removehandler-statement.md).</span><span class="sxs-lookup"><span data-stu-id="7cfca-133">You can dissociate an event handler from an event by executing the [RemoveHandler Statement](../../../../visual-basic/language-reference/statements/removehandler-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cfca-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="7cfca-134">See Also</span></span>  
 [<span data-ttu-id="7cfca-135">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="7cfca-135">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="7cfca-136">Subprocedimientos</span><span class="sxs-lookup"><span data-stu-id="7cfca-136">Sub Procedures</span></span>](./sub-procedures.md)  
 [<span data-ttu-id="7cfca-137">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="7cfca-137">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="7cfca-138">AddressOf (operador)</span><span class="sxs-lookup"><span data-stu-id="7cfca-138">AddressOf Operator</span></span>](../../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [<span data-ttu-id="7cfca-139">Crear un procedimiento</span><span class="sxs-lookup"><span data-stu-id="7cfca-139">How to: Create a Procedure</span></span>](./how-to-create-a-procedure.md)  
 [<span data-ttu-id="7cfca-140">Llamar a un procedimiento que no devuelve un valor</span><span class="sxs-lookup"><span data-stu-id="7cfca-140">How to: Call a Procedure that Does Not Return a Value</span></span>](./how-to-call-a-procedure-that-does-not-return-a-value.md)
