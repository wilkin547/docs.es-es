---
title: Declarar y provocar eventos (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], events
- events [Visual Basic], walkthroughs
- declaring events [Visual Basic], walkthroughs
- events [Visual Basic], declaring
- events [Visual Basic], raising
- raising events [Visual Basic], walkthroughs
ms.assetid: 8ffb3be8-097d-4d3c-b71e-04555ebda2a2
ms.openlocfilehash: cab6c90947eae8abeb9387535eadb2f89e71454a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61973095"
---
# <a name="walkthrough-declaring-and-raising-events-visual-basic"></a><span data-ttu-id="60f6f-102">Tutorial: Declarar y provocar eventos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="60f6f-102">Walkthrough: Declaring and Raising Events (Visual Basic)</span></span>
<span data-ttu-id="60f6f-103">Este tutorial muestra cómo declarar y provocar eventos para una clase denominada `Widget`.</span><span class="sxs-lookup"><span data-stu-id="60f6f-103">This walkthrough demonstrates how to declare and raise events for a class named `Widget`.</span></span> <span data-ttu-id="60f6f-104">Después de completar los pasos, que es posible que desee leer el tema complementario, [Tutorial: Control de eventos](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md), que muestra cómo utilizar eventos de `Widget` objetos que se va a proporcionar información de estado en una aplicación.</span><span class="sxs-lookup"><span data-stu-id="60f6f-104">After you complete the steps, you might want to read the companion topic, [Walkthrough: Handling Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md), which shows how to use events from `Widget` objects to provide status information in an application.</span></span>  
  
## <a name="the-widget-class"></a><span data-ttu-id="60f6f-105">La clase Widget</span><span class="sxs-lookup"><span data-stu-id="60f6f-105">The Widget Class</span></span>  
 <span data-ttu-id="60f6f-106">Suponga por un momento que tenga un `Widget` clase.</span><span class="sxs-lookup"><span data-stu-id="60f6f-106">Assume for the moment that you have a `Widget` class.</span></span> <span data-ttu-id="60f6f-107">Su `Widget` clase tiene un método que puede tardar mucho tiempo en ejecutarse, y desea que su aplicación pueda poner a algún tipo de indicador de finalización.</span><span class="sxs-lookup"><span data-stu-id="60f6f-107">Your `Widget` class has a method that can take a long time to execute, and you want your application to be able to put up some kind of completion indicator.</span></span>  
  
 <span data-ttu-id="60f6f-108">Por supuesto, puede hacer que el `Widget` objeto mostrar un cuadro de diálogo de porcentaje completado, pero, a continuación, aparecería con ese cuadro de diálogo en todos los proyectos en el que utilizó el `Widget` clase.</span><span class="sxs-lookup"><span data-stu-id="60f6f-108">Of course, you could make the `Widget` object show a percent-complete dialog box, but then you would be stuck with that dialog box in every project in which you used the `Widget` class.</span></span> <span data-ttu-id="60f6f-109">Un buen principio de diseño de objeto es dejar que la aplicación que utiliza un objeto controle la interfaz de usuario, a menos que sea la única finalidad del objeto administrar un formulario o cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="60f6f-109">A good principle of object design is to let the application that uses an object handle the user interface—unless the whole purpose of the object is to manage a form or dialog box.</span></span>  
  
 <span data-ttu-id="60f6f-110">El propósito de `Widget` consiste en realizar otras tareas, por lo que es mejor agregar una `PercentDone` eventos y permita que el procedimiento que llama `Widget`del métodos controlan que actualiza el estado de evento y la presentación.</span><span class="sxs-lookup"><span data-stu-id="60f6f-110">The purpose of `Widget` is to perform other tasks, so it is better to add a `PercentDone` event and let the procedure that calls `Widget`'s methods handle that event and display status updates.</span></span> <span data-ttu-id="60f6f-111">El `PercentDone` evento también puede proporcionar un mecanismo para cancelar la tarea.</span><span class="sxs-lookup"><span data-stu-id="60f6f-111">The `PercentDone` event can also provide a mechanism for canceling the task.</span></span>  
  
#### <a name="to-build-the-code-example-for-this-topic"></a><span data-ttu-id="60f6f-112">Para compilar el ejemplo de código de este tema</span><span class="sxs-lookup"><span data-stu-id="60f6f-112">To build the code example for this topic</span></span>  
  
1. <span data-ttu-id="60f6f-113">Abra un nuevo proyecto de aplicación de Windows de Visual Basic y cree un formulario denominado `Form1`.</span><span class="sxs-lookup"><span data-stu-id="60f6f-113">Open a new Visual Basic Windows Application project and create a form named `Form1`.</span></span>  
  
2. <span data-ttu-id="60f6f-114">Agregue dos botones y una etiqueta para `Form1`.</span><span class="sxs-lookup"><span data-stu-id="60f6f-114">Add two buttons and a label to `Form1`.</span></span>  
  
3. <span data-ttu-id="60f6f-115">Asigne nombre a los objetos tal y como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="60f6f-115">Name the objects as shown in the following table.</span></span>  
  
    |<span data-ttu-id="60f6f-116">Objeto</span><span class="sxs-lookup"><span data-stu-id="60f6f-116">Object</span></span>|<span data-ttu-id="60f6f-117">Propiedad</span><span class="sxs-lookup"><span data-stu-id="60f6f-117">Property</span></span>|<span data-ttu-id="60f6f-118">Parámetro</span><span class="sxs-lookup"><span data-stu-id="60f6f-118">Setting</span></span>|  
    |------------|--------------|-------------|  
    |`Button1`|`Text`|<span data-ttu-id="60f6f-119">Tarea de inicio</span><span class="sxs-lookup"><span data-stu-id="60f6f-119">Start Task</span></span>|  
    |`Button2`|`Text`|<span data-ttu-id="60f6f-120">Cancelar</span><span class="sxs-lookup"><span data-stu-id="60f6f-120">Cancel</span></span>|  
    |`Label`|<span data-ttu-id="60f6f-121">`(Name)`, `Text`</span><span class="sxs-lookup"><span data-stu-id="60f6f-121">`(Name)`, `Text`</span></span>|<span data-ttu-id="60f6f-122">lblPercentDone, 0</span><span class="sxs-lookup"><span data-stu-id="60f6f-122">lblPercentDone, 0</span></span>|  
  
4. <span data-ttu-id="60f6f-123">En el **proyecto** menú, elija **Agregar clase** para agregar una clase denominada `Widget.vb` al proyecto.</span><span class="sxs-lookup"><span data-stu-id="60f6f-123">On the **Project** menu, choose **Add Class** to add a class named `Widget.vb` to the project.</span></span>  
  
#### <a name="to-declare-an-event-for-the-widget-class"></a><span data-ttu-id="60f6f-124">Para declarar un evento para la clase de Widget</span><span class="sxs-lookup"><span data-stu-id="60f6f-124">To declare an event for the Widget class</span></span>  
  
- <span data-ttu-id="60f6f-125">Use la `Event` palabra clave para declarar un evento en el `Widget` clase.</span><span class="sxs-lookup"><span data-stu-id="60f6f-125">Use the `Event` keyword to declare an event in the `Widget` class.</span></span> <span data-ttu-id="60f6f-126">Tenga en cuenta que puede tener un evento `ByVal` y `ByRef` argumentos, como `Widget`del `PercentDone` muestra eventos:</span><span class="sxs-lookup"><span data-stu-id="60f6f-126">Note that an event can have `ByVal` and `ByRef` arguments, as `Widget`'s `PercentDone` event demonstrates:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#1)]  
  
 <span data-ttu-id="60f6f-127">Cuando el objeto de llamada recibe una `PercentDone` eventos, el `Percent` argumento contiene el porcentaje de la tarea que se ha completado.</span><span class="sxs-lookup"><span data-stu-id="60f6f-127">When the calling object receives a `PercentDone` event, the `Percent` argument contains the percentage of the task that is complete.</span></span> <span data-ttu-id="60f6f-128">El `Cancel` argumento se puede establecer en `True` para cancelar el método que generó el evento.</span><span class="sxs-lookup"><span data-stu-id="60f6f-128">The `Cancel` argument can be set to `True` to cancel the method that raised the event.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="60f6f-129">Puede declarar argumentos de evento, tal como se hace con los argumentos de procedimientos, con las siguientes excepciones: No pueden tener eventos `Optional` o `ParamArray` argumentos y los eventos no tienen valores devueltos.</span><span class="sxs-lookup"><span data-stu-id="60f6f-129">You can declare event arguments just as you do arguments of procedures, with the following exceptions: Events cannot have `Optional` or `ParamArray` arguments, and events do not have return values.</span></span>  
  
 <span data-ttu-id="60f6f-130">El `PercentDone` evento es desencadenado por la `LongTask` método de la `Widget` clase.</span><span class="sxs-lookup"><span data-stu-id="60f6f-130">The `PercentDone` event is raised by the `LongTask` method of the `Widget` class.</span></span> <span data-ttu-id="60f6f-131">`LongTask` toma dos argumentos: el período de tiempo que el método finge hasta la realización de trabajo y el intervalo de tiempo mínimo antes de `LongTask` pausas para generar el `PercentDone` eventos.</span><span class="sxs-lookup"><span data-stu-id="60f6f-131">`LongTask` takes two arguments: the length of time the method pretends to be doing work, and the minimum time interval before `LongTask` pauses to raise the `PercentDone` event.</span></span>  
  
#### <a name="to-raise-the-percentdone-event"></a><span data-ttu-id="60f6f-132">Para generar el evento PercentDone</span><span class="sxs-lookup"><span data-stu-id="60f6f-132">To raise the PercentDone event</span></span>  
  
1. <span data-ttu-id="60f6f-133">Para simplificar el acceso a la `Timer` propiedad utilizada por esta clase, agregue un `Imports` instrucción a la parte superior de la sección de declaraciones de módulo de la clase, por encima el `Class Widget` instrucción.</span><span class="sxs-lookup"><span data-stu-id="60f6f-133">To simplify access to the `Timer` property used by this class, add an `Imports` statement to the top of the declarations section of your class module, above the `Class Widget` statement.</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#2)]  
  
2. <span data-ttu-id="60f6f-134">Agregue el código siguiente a la clase `Widget`:</span><span class="sxs-lookup"><span data-stu-id="60f6f-134">Add the following code to the `Widget` class:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#3)]  
  
 <span data-ttu-id="60f6f-135">Cuando la aplicación llama el `LongTask` método, el `Widget` clase genera el `PercentDone` eventos cada `MinimumInterval` segundos.</span><span class="sxs-lookup"><span data-stu-id="60f6f-135">When your application calls the `LongTask` method, the `Widget` class raises the `PercentDone` event every `MinimumInterval` seconds.</span></span> <span data-ttu-id="60f6f-136">Devuelve el evento `LongTask` comprueba si el `Cancel` argumento se estableció en `True`.</span><span class="sxs-lookup"><span data-stu-id="60f6f-136">When the event returns, `LongTask` checks to see if the `Cancel` argument was set to `True`.</span></span>  
  
 <span data-ttu-id="60f6f-137">Algunas declinaciones de responsabilidades son necesarios.</span><span class="sxs-lookup"><span data-stu-id="60f6f-137">A few disclaimers are necessary here.</span></span> <span data-ttu-id="60f6f-138">Por motivos de simplicidad, el `LongTask` procedimiento se supone que sabe de antemano cuánto tiempo tardará la tarea.</span><span class="sxs-lookup"><span data-stu-id="60f6f-138">For simplicity, the `LongTask` procedure assumes you know in advance how long the task will take.</span></span> <span data-ttu-id="60f6f-139">Esto casi nunca es el caso.</span><span class="sxs-lookup"><span data-stu-id="60f6f-139">This is almost never the case.</span></span> <span data-ttu-id="60f6f-140">Dividir las tareas en fragmentos de tamaño incluso puede resultar difícil y, a menudo lo más importante para los usuarios es simplemente la cantidad de tiempo que transcurre antes de que lleguen a un valor que indica que está ocurriendo algo.</span><span class="sxs-lookup"><span data-stu-id="60f6f-140">Dividing tasks into chunks of even size can be difficult, and often what matters most to users is simply the amount of time that passes before they get an indication that something is happening.</span></span>  
  
 <span data-ttu-id="60f6f-141">Puede haber detectado otro error en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="60f6f-141">You may have spotted another flaw in this sample.</span></span> <span data-ttu-id="60f6f-142">El `Timer` propiedad devuelve el número de segundos que han transcurrido desde medianoche; por lo tanto, la aplicación se bloquea si se ha iniciado justo antes de medianoche.</span><span class="sxs-lookup"><span data-stu-id="60f6f-142">The `Timer` property returns the number of seconds that have passed since midnight; therefore, the application gets stuck if it is started just before midnight.</span></span> <span data-ttu-id="60f6f-143">Un enfoque más cuidadoso para medir el tiempo lleve las condiciones de límite como este en cuenta, o evitar por completo, con propiedades como `Now`.</span><span class="sxs-lookup"><span data-stu-id="60f6f-143">A more careful approach to measuring time would take boundary conditions such as this into consideration, or avoid them altogether, using properties such as `Now`.</span></span>  
  
 <span data-ttu-id="60f6f-144">Ahora que la `Widget` clase puede provocar eventos, puede mover al siguiente tutorial.</span><span class="sxs-lookup"><span data-stu-id="60f6f-144">Now that the `Widget` class can raise events, you can move to the next walkthrough.</span></span> <span data-ttu-id="60f6f-145">[Tutorial: Control de eventos](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) muestra cómo usar `WithEvents` para asociar un controlador de eventos con el `PercentDone` eventos.</span><span class="sxs-lookup"><span data-stu-id="60f6f-145">[Walkthrough: Handling Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) demonstrates how to use `WithEvents` to associate an event handler with the `PercentDone` event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60f6f-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="60f6f-146">See also</span></span>

- <xref:Microsoft.VisualBasic.DateAndTime.Timer%2A>
- <xref:Microsoft.VisualBasic.DateAndTime.Now%2A>
- [<span data-ttu-id="60f6f-147">Tutorial: Control de eventos</span><span class="sxs-lookup"><span data-stu-id="60f6f-147">Walkthrough: Handling Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)
- [<span data-ttu-id="60f6f-148">Eventos</span><span class="sxs-lookup"><span data-stu-id="60f6f-148">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)
