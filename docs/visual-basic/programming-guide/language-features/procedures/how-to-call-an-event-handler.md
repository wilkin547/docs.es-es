---
description: 'Más información sobre: cómo llamar a un controlador de eventos en Visual Basic'
title: Cómo llamar a un controlador de eventos
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- event handlers [Visual Basic], calling
- event handlers
- procedures [Visual Basic], event handlers
- procedures [Visual Basic], calling
no-loc:
- WithEvents
ms.assetid: 72e18ef8-144e-40df-a1f4-066a57271e28
ms.openlocfilehash: 7e65b36d392211be533bb4881658b1cdb8057d5d
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100476259"
---
# <a name="how-to-call-an-event-handler-in-visual-basic"></a><span data-ttu-id="46123-103">Cómo llamar a un controlador de eventos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="46123-103">How to call an event handler in Visual Basic</span></span>

<span data-ttu-id="46123-104">Un *evento* es una acción o una repetición, como un clic del mouse o un límite de crédito superado, que es reconocido por algún componente del programa y para el que puede escribir código para responder.</span><span class="sxs-lookup"><span data-stu-id="46123-104">An *event* is an action or occurrence — such as a mouse click or a credit limit exceeded — that is recognized by some program component, and for which you can write code to respond.</span></span> <span data-ttu-id="46123-105">Un *controlador de eventos* es el código que se escribe para responder a un evento.</span><span class="sxs-lookup"><span data-stu-id="46123-105">An *event handler* is the code you write to respond to an event.</span></span>

<span data-ttu-id="46123-106">Un controlador de eventos en Visual Basic es un `Sub` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="46123-106">An event handler in Visual Basic is a `Sub` procedure.</span></span> <span data-ttu-id="46123-107">Sin embargo, normalmente no se llama de la misma manera que otros `Sub` procedimientos.</span><span class="sxs-lookup"><span data-stu-id="46123-107">However, you do not normally call it the same way as other `Sub` procedures.</span></span> <span data-ttu-id="46123-108">En su lugar, identifique el procedimiento como un controlador para el evento.</span><span class="sxs-lookup"><span data-stu-id="46123-108">Instead, you identify the procedure as a handler for the event.</span></span> <span data-ttu-id="46123-109">Puede hacerlo con una [`Handles`](../../../language-reference/statements/handles-clause.md) cláusula y una [`WithEvents`](../../../language-reference/modifiers/withevents.md) variable, o con una [instrucción AddHandler](../../../language-reference/statements/addhandler-statement.md).</span><span class="sxs-lookup"><span data-stu-id="46123-109">You can do this either with a [`Handles`](../../../language-reference/statements/handles-clause.md) clause and a [`WithEvents`](../../../language-reference/modifiers/withevents.md) variable, or with an [AddHandler Statement](../../../language-reference/statements/addhandler-statement.md).</span></span> <span data-ttu-id="46123-110">El uso de una `Handles` cláusula es la forma predeterminada de declarar un controlador de eventos en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="46123-110">Using a `Handles` clause is the default way to declare an event handler in Visual Basic.</span></span> <span data-ttu-id="46123-111">Esta es la forma en que los diseñadores escriben los controladores de eventos cuando se programa en el entorno de desarrollo integrado (IDE).</span><span class="sxs-lookup"><span data-stu-id="46123-111">This is the way the event handlers are written by the designers when you program in the integrated development environment (IDE).</span></span> <span data-ttu-id="46123-112">La `AddHandler` instrucción es adecuada para generar eventos dinámicamente en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="46123-112">The `AddHandler` statement is suitable for raising events dynamically at run time.</span></span>

<span data-ttu-id="46123-113">Cuando se produce el evento, Visual Basic llama automáticamente al procedimiento de controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="46123-113">When the event occurs, Visual Basic automatically calls the event handler procedure.</span></span> <span data-ttu-id="46123-114">Cualquier código que tenga acceso al evento puede hacer que se produzca ejecutando una [instrucción RaiseEvent](../../../language-reference/statements/raiseevent-statement.md).</span><span class="sxs-lookup"><span data-stu-id="46123-114">Any code that has access to the event can cause it to occur by executing a [RaiseEvent Statement](../../../language-reference/statements/raiseevent-statement.md).</span></span>

<span data-ttu-id="46123-115">Puede asociar más de un controlador de eventos con el mismo evento.</span><span class="sxs-lookup"><span data-stu-id="46123-115">You can associate more than one event handler with the same event.</span></span> <span data-ttu-id="46123-116">En algunos casos, puede desasociar un controlador de un evento.</span><span class="sxs-lookup"><span data-stu-id="46123-116">In some cases you can dissociate a handler from an event.</span></span> <span data-ttu-id="46123-117">Para más información, vea [Eventos](../events/index.md).</span><span class="sxs-lookup"><span data-stu-id="46123-117">For more information, see [Events](../events/index.md).</span></span>

## <a name="call-an-event-handler-using-no-loc-texthandles-and-withevents"></a><span data-ttu-id="46123-118">Llamar a un controlador de eventos mediante :::no-loc text="Handles"::: y WithEvents</span><span class="sxs-lookup"><span data-stu-id="46123-118">Call an event handler using :::no-loc text="Handles"::: and WithEvents</span></span>

1. <span data-ttu-id="46123-119">Asegúrese de que el evento se declara con una [instrucción de evento](../../../language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="46123-119">Make sure the event is declared with an [Event Statement](../../../language-reference/statements/event-statement.md).</span></span>

2. <span data-ttu-id="46123-120">Declare una variable de objeto en el nivel de módulo o de clase, mediante la [`WithEvents`](../../../language-reference/modifiers/withevents.md) palabra clave.</span><span class="sxs-lookup"><span data-stu-id="46123-120">Declare an object variable at module or class level, using the [`WithEvents`](../../../language-reference/modifiers/withevents.md) keyword.</span></span> <span data-ttu-id="46123-121">La `As` cláusula para esta variable debe especificar la clase que genera el evento.</span><span class="sxs-lookup"><span data-stu-id="46123-121">The `As` clause for this variable must specify the class that raises the event.</span></span>

3. <span data-ttu-id="46123-122">En la declaración del procedimiento de control de eventos `Sub` , agregue una [`Handles`](../../../language-reference/statements/handles-clause.md) cláusula que especifique la `WithEvents` variable y el nombre del evento.</span><span class="sxs-lookup"><span data-stu-id="46123-122">In the declaration of the event-handling `Sub` procedure, add a [`Handles`](../../../language-reference/statements/handles-clause.md) clause that specifies the `WithEvents` variable and the event name.</span></span>

4. <span data-ttu-id="46123-123">Cuando se produce el evento, Visual Basic llama automáticamente al `Sub` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="46123-123">When the event occurs, Visual Basic automatically calls the `Sub` procedure.</span></span> <span data-ttu-id="46123-124">El código puede utilizar una `RaiseEvent` instrucción para que se produzca el evento.</span><span class="sxs-lookup"><span data-stu-id="46123-124">Your code can use a `RaiseEvent` statement to make the event occur.</span></span>

    <span data-ttu-id="46123-125">En el ejemplo siguiente se define un evento y una `WithEvents` variable que hace referencia a la clase que genera el evento.</span><span class="sxs-lookup"><span data-stu-id="46123-125">The following example defines an event and a `WithEvents` variable that refers to the class that raises the event.</span></span> <span data-ttu-id="46123-126">El procedimiento de control de eventos `Sub` utiliza una `Handles` cláusula para especificar la clase y el evento que administra.</span><span class="sxs-lookup"><span data-stu-id="46123-126">The event-handling `Sub` procedure uses a `Handles` clause to specify the class and event it handles.</span></span>

    :::code language="vb" source="snippets/how-to-call-an-event-handler/SpecialForm.vb" id="4":::

## <a name="call-an-event-handler-using-addhandler"></a><span data-ttu-id="46123-127">Llamar a un controlador de eventos mediante AddHandler</span><span class="sxs-lookup"><span data-stu-id="46123-127">Call an event handler using AddHandler</span></span>

1. <span data-ttu-id="46123-128">Asegúrese de que el evento se declara con una `Event` instrucción.</span><span class="sxs-lookup"><span data-stu-id="46123-128">Make sure the event is declared with an `Event` statement.</span></span>

2. <span data-ttu-id="46123-129">Ejecute una [instrucción AddHandler](../../../language-reference/statements/addhandler-statement.md) para conectar dinámicamente el procedimiento de control de eventos `Sub` con el evento.</span><span class="sxs-lookup"><span data-stu-id="46123-129">Execute an [AddHandler statement](../../../language-reference/statements/addhandler-statement.md) to dynamically connect the event-handling `Sub` procedure with the event.</span></span>

3. <span data-ttu-id="46123-130">Cuando se produce el evento, Visual Basic llama automáticamente al `Sub` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="46123-130">When the event occurs, Visual Basic automatically calls the `Sub` procedure.</span></span> <span data-ttu-id="46123-131">El código puede utilizar una `RaiseEvent` instrucción para que se produzca el evento.</span><span class="sxs-lookup"><span data-stu-id="46123-131">Your code can use a `RaiseEvent` statement to make the event occur.</span></span>

    <span data-ttu-id="46123-132">En el ejemplo siguiente se usa la [instrucción AddHandler](../../../language-reference/statements/addhandler-statement.md) en el constructor para asociar el `OnFormClosing` procedimiento como un controlador de eventos para <xref:System.Windows.Forms.Form.FormClosing> .</span><span class="sxs-lookup"><span data-stu-id="46123-132">The following example uses the [AddHandler statement](../../../language-reference/statements/addhandler-statement.md) in the constructor to associate the `OnFormClosing` procedure as an event handler for <xref:System.Windows.Forms.Form.FormClosing>.</span></span>

    :::code language="vb" source="snippets/how-to-call-an-event-handler/SpecialForm.vb" id="5":::

    <span data-ttu-id="46123-133">Puede desasociar un controlador de eventos de un evento ejecutando la [instrucción RemoveHandler](../../../language-reference/statements/removehandler-statement.md).</span><span class="sxs-lookup"><span data-stu-id="46123-133">You can dissociate an event handler from an event by executing the [RemoveHandler statement](../../../language-reference/statements/removehandler-statement.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="46123-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="46123-134">See also</span></span>

- [<span data-ttu-id="46123-135">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="46123-135">Procedures</span></span>](index.md)
- [<span data-ttu-id="46123-136">Procedimientos Sub</span><span class="sxs-lookup"><span data-stu-id="46123-136">Sub Procedures</span></span>](sub-procedures.md)
- [<span data-ttu-id="46123-137">Instrucción Sub</span><span class="sxs-lookup"><span data-stu-id="46123-137">Sub Statement</span></span>](../../../language-reference/statements/sub-statement.md)
- [<span data-ttu-id="46123-138">Operador AddressOf</span><span class="sxs-lookup"><span data-stu-id="46123-138">AddressOf Operator</span></span>](../../../language-reference/operators/addressof-operator.md)
- [<span data-ttu-id="46123-139">Procedimiento para crear un procedimiento</span><span class="sxs-lookup"><span data-stu-id="46123-139">How to: Create a Procedure</span></span>](how-to-create-a-procedure.md)
- [<span data-ttu-id="46123-140">Procedimiento apara llamar a un procedimiento que no devuelve un valor</span><span class="sxs-lookup"><span data-stu-id="46123-140">How to: Call a Procedure that Does Not Return a Value</span></span>](how-to-call-a-procedure-that-does-not-return-a-value.md)
