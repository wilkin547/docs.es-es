---
title: Declarar y generar eventos (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], events
- events [Visual Basic], walkthroughs
- declaring events [Visual Basic], walkthroughs
- events [Visual Basic], declaring
- events [Visual Basic], raising
- raising events [Visual Basic], walkthroughs
ms.assetid: 8ffb3be8-097d-4d3c-b71e-04555ebda2a2
ms.openlocfilehash: 20e2b0efbf40597049c515134f408927f18d5603
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956329"
---
# <a name="walkthrough-declaring-and-raising-events-visual-basic"></a><span data-ttu-id="f02f1-102">Tutorial: Declarar y generar eventos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f02f1-102">Walkthrough: Declaring and Raising Events (Visual Basic)</span></span>
<span data-ttu-id="f02f1-103">En este tutorial se muestra cómo declarar y generar eventos para una clase `Widget`denominada.</span><span class="sxs-lookup"><span data-stu-id="f02f1-103">This walkthrough demonstrates how to declare and raise events for a class named `Widget`.</span></span> <span data-ttu-id="f02f1-104">Después de completar los pasos, es posible que desee leer el tema [complementario: Control de](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)eventos, que muestra cómo utilizar los eventos `Widget` de los objetos para proporcionar información de estado en una aplicación.</span><span class="sxs-lookup"><span data-stu-id="f02f1-104">After you complete the steps, you might want to read the companion topic, [Walkthrough: Handling Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md), which shows how to use events from `Widget` objects to provide status information in an application.</span></span>  
  
## <a name="the-widget-class"></a><span data-ttu-id="f02f1-105">La clase widget</span><span class="sxs-lookup"><span data-stu-id="f02f1-105">The Widget Class</span></span>  
 <span data-ttu-id="f02f1-106">Supongamos por el momento que tiene `Widget` una clase.</span><span class="sxs-lookup"><span data-stu-id="f02f1-106">Assume for the moment that you have a `Widget` class.</span></span> <span data-ttu-id="f02f1-107">La `Widget` clase tiene un método que puede tardar mucho tiempo en ejecutarse y desea que la aplicación pueda incluir algún tipo de indicador de finalización.</span><span class="sxs-lookup"><span data-stu-id="f02f1-107">Your `Widget` class has a method that can take a long time to execute, and you want your application to be able to put up some kind of completion indicator.</span></span>  
  
 <span data-ttu-id="f02f1-108">Por supuesto, puede hacer que el `Widget` objeto muestre un cuadro de diálogo porcentaje de finalización, pero a continuación se bloqueará este cuadro de diálogo en todos los proyectos en los `Widget` que se haya utilizado la clase.</span><span class="sxs-lookup"><span data-stu-id="f02f1-108">Of course, you could make the `Widget` object show a percent-complete dialog box, but then you would be stuck with that dialog box in every project in which you used the `Widget` class.</span></span> <span data-ttu-id="f02f1-109">Un buen principio de diseño de objetos es permitir que la aplicación que usa un objeto controle la interfaz de usuario, a menos que el propósito completo del objeto sea administrar un formulario o un cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="f02f1-109">A good principle of object design is to let the application that uses an object handle the user interface—unless the whole purpose of the object is to manage a form or dialog box.</span></span>  
  
 <span data-ttu-id="f02f1-110">El propósito de `Widget` es realizar otras tareas, por lo que es mejor agregar un `PercentDone` evento y dejar que el procedimiento que llama `Widget`a los métodos de llame a ese evento y muestre las actualizaciones de estado.</span><span class="sxs-lookup"><span data-stu-id="f02f1-110">The purpose of `Widget` is to perform other tasks, so it is better to add a `PercentDone` event and let the procedure that calls `Widget`'s methods handle that event and display status updates.</span></span> <span data-ttu-id="f02f1-111">El `PercentDone` evento también puede proporcionar un mecanismo para cancelar la tarea.</span><span class="sxs-lookup"><span data-stu-id="f02f1-111">The `PercentDone` event can also provide a mechanism for canceling the task.</span></span>  
  
#### <a name="to-build-the-code-example-for-this-topic"></a><span data-ttu-id="f02f1-112">Para compilar el ejemplo de código de este tema</span><span class="sxs-lookup"><span data-stu-id="f02f1-112">To build the code example for this topic</span></span>  
  
1. <span data-ttu-id="f02f1-113">Abra un nuevo proyecto de aplicación de Windows Visual Basic y cree un `Form1`formulario denominado.</span><span class="sxs-lookup"><span data-stu-id="f02f1-113">Open a new Visual Basic Windows Application project and create a form named `Form1`.</span></span>  
  
2. <span data-ttu-id="f02f1-114">Agregue dos botones y una etiqueta a `Form1`.</span><span class="sxs-lookup"><span data-stu-id="f02f1-114">Add two buttons and a label to `Form1`.</span></span>  
  
3. <span data-ttu-id="f02f1-115">Asigne nombre a los objetos tal y como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="f02f1-115">Name the objects as shown in the following table.</span></span>  
  
    |<span data-ttu-id="f02f1-116">Objeto</span><span class="sxs-lookup"><span data-stu-id="f02f1-116">Object</span></span>|<span data-ttu-id="f02f1-117">Propiedad</span><span class="sxs-lookup"><span data-stu-id="f02f1-117">Property</span></span>|<span data-ttu-id="f02f1-118">Parámetro</span><span class="sxs-lookup"><span data-stu-id="f02f1-118">Setting</span></span>|  
    |------------|--------------|-------------|  
    |`Button1`|`Text`|<span data-ttu-id="f02f1-119">Tarea de inicio</span><span class="sxs-lookup"><span data-stu-id="f02f1-119">Start Task</span></span>|  
    |`Button2`|`Text`|<span data-ttu-id="f02f1-120">Cancelar</span><span class="sxs-lookup"><span data-stu-id="f02f1-120">Cancel</span></span>|  
    |`Label`|<span data-ttu-id="f02f1-121">`(Name)`, `Text`</span><span class="sxs-lookup"><span data-stu-id="f02f1-121">`(Name)`, `Text`</span></span>|<span data-ttu-id="f02f1-122">lblPercentDone, 0</span><span class="sxs-lookup"><span data-stu-id="f02f1-122">lblPercentDone, 0</span></span>|  
  
4. <span data-ttu-id="f02f1-123">En el menú **proyecto** , elija **Agregar clase** para agregar una clase denominada `Widget.vb` al proyecto.</span><span class="sxs-lookup"><span data-stu-id="f02f1-123">On the **Project** menu, choose **Add Class** to add a class named `Widget.vb` to the project.</span></span>  
  
#### <a name="to-declare-an-event-for-the-widget-class"></a><span data-ttu-id="f02f1-124">Para declarar un evento para la clase widget</span><span class="sxs-lookup"><span data-stu-id="f02f1-124">To declare an event for the Widget class</span></span>  
  
- <span data-ttu-id="f02f1-125">Use la `Event` palabra clave para declarar un evento en `Widget` la clase.</span><span class="sxs-lookup"><span data-stu-id="f02f1-125">Use the `Event` keyword to declare an event in the `Widget` class.</span></span> <span data-ttu-id="f02f1-126">Tenga en cuenta que un evento `ByVal` puede `ByRef` tener argumentos y `Widget`, `PercentDone` como se muestra en el evento:</span><span class="sxs-lookup"><span data-stu-id="f02f1-126">Note that an event can have `ByVal` and `ByRef` arguments, as `Widget`'s `PercentDone` event demonstrates:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#1)]  
  
 <span data-ttu-id="f02f1-127">Cuando el objeto que realiza la `PercentDone` llamada recibe un `Percent` evento, el argumento contiene el porcentaje de la tarea que ha finalizado.</span><span class="sxs-lookup"><span data-stu-id="f02f1-127">When the calling object receives a `PercentDone` event, the `Percent` argument contains the percentage of the task that is complete.</span></span> <span data-ttu-id="f02f1-128">El `Cancel` argumento se puede establecer en `True` para cancelar el método que provocó el evento.</span><span class="sxs-lookup"><span data-stu-id="f02f1-128">The `Cancel` argument can be set to `True` to cancel the method that raised the event.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f02f1-129">Puede declarar argumentos de evento del mismo modo que los argumentos de procedimientos, con las siguientes excepciones: Los eventos no `Optional` pueden `ParamArray` tener argumentos o, y los eventos no tienen valores devueltos.</span><span class="sxs-lookup"><span data-stu-id="f02f1-129">You can declare event arguments just as you do arguments of procedures, with the following exceptions: Events cannot have `Optional` or `ParamArray` arguments, and events do not have return values.</span></span>  
  
 <span data-ttu-id="f02f1-130">El evento es desencadenado por `LongTask` el método de `Widget` la clase. `PercentDone`</span><span class="sxs-lookup"><span data-stu-id="f02f1-130">The `PercentDone` event is raised by the `LongTask` method of the `Widget` class.</span></span> <span data-ttu-id="f02f1-131">`LongTask`toma dos argumentos: la cantidad de tiempo que el método está realizando el trabajo y el intervalo de tiempo mínimo antes `LongTask` de que se ponga en pausa para generar el `PercentDone` evento.</span><span class="sxs-lookup"><span data-stu-id="f02f1-131">`LongTask` takes two arguments: the length of time the method pretends to be doing work, and the minimum time interval before `LongTask` pauses to raise the `PercentDone` event.</span></span>  
  
#### <a name="to-raise-the-percentdone-event"></a><span data-ttu-id="f02f1-132">Para generar el evento PercentDone</span><span class="sxs-lookup"><span data-stu-id="f02f1-132">To raise the PercentDone event</span></span>  
  
1. <span data-ttu-id="f02f1-133">Para simplificar el acceso `Timer` a la propiedad utilizada por esta clase, `Imports` agregue una instrucción al principio de la sección de declaraciones del módulo de clase, encima `Class Widget` de la instrucción.</span><span class="sxs-lookup"><span data-stu-id="f02f1-133">To simplify access to the `Timer` property used by this class, add an `Imports` statement to the top of the declarations section of your class module, above the `Class Widget` statement.</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#2)]  
  
2. <span data-ttu-id="f02f1-134">Agregue el código siguiente a la clase `Widget`:</span><span class="sxs-lookup"><span data-stu-id="f02f1-134">Add the following code to the `Widget` class:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#3)]  
  
 <span data-ttu-id="f02f1-135">Cuando la aplicación llama al `LongTask` método, la `Widget` clase genera el `PercentDone` evento cada `MinimumInterval` segundos.</span><span class="sxs-lookup"><span data-stu-id="f02f1-135">When your application calls the `LongTask` method, the `Widget` class raises the `PercentDone` event every `MinimumInterval` seconds.</span></span> <span data-ttu-id="f02f1-136">Cuando el evento vuelve, `LongTask` comprueba si el `Cancel` argumento se estableció en `True`.</span><span class="sxs-lookup"><span data-stu-id="f02f1-136">When the event returns, `LongTask` checks to see if the `Cancel` argument was set to `True`.</span></span>  
  
 <span data-ttu-id="f02f1-137">Aquí se necesitan algunas renuncias.</span><span class="sxs-lookup"><span data-stu-id="f02f1-137">A few disclaimers are necessary here.</span></span> <span data-ttu-id="f02f1-138">Para simplificar, `LongTask` el procedimiento presupone que sabe de antemano cuánto tiempo tardará la tarea en realizarse.</span><span class="sxs-lookup"><span data-stu-id="f02f1-138">For simplicity, the `LongTask` procedure assumes you know in advance how long the task will take.</span></span> <span data-ttu-id="f02f1-139">Esto casi nunca es el caso.</span><span class="sxs-lookup"><span data-stu-id="f02f1-139">This is almost never the case.</span></span> <span data-ttu-id="f02f1-140">Dividir las tareas en fragmentos de tamaño uniforme puede ser difícil y, a menudo, lo más importante para los usuarios es simplemente la cantidad de tiempo que pasa antes de que obtengan una indicación de que se está produciendo algo.</span><span class="sxs-lookup"><span data-stu-id="f02f1-140">Dividing tasks into chunks of even size can be difficult, and often what matters most to users is simply the amount of time that passes before they get an indication that something is happening.</span></span>  
  
 <span data-ttu-id="f02f1-141">Es posible que haya detectado otro problema en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="f02f1-141">You may have spotted another flaw in this sample.</span></span> <span data-ttu-id="f02f1-142">La `Timer` propiedad devuelve el número de segundos transcurridos desde la medianoche; por lo tanto, la aplicación se bloquea si se inicia justo antes de medianoche.</span><span class="sxs-lookup"><span data-stu-id="f02f1-142">The `Timer` property returns the number of seconds that have passed since midnight; therefore, the application gets stuck if it is started just before midnight.</span></span> <span data-ttu-id="f02f1-143">Un enfoque más cuidadoso para medir el tiempo tomaría condiciones de límite, como esto, o evitar que se consuman por completo `Now`, mediante propiedades como.</span><span class="sxs-lookup"><span data-stu-id="f02f1-143">A more careful approach to measuring time would take boundary conditions such as this into consideration, or avoid them altogether, using properties such as `Now`.</span></span>  
  
 <span data-ttu-id="f02f1-144">Ahora que la `Widget` clase puede generar eventos, puede pasar al siguiente tutorial.</span><span class="sxs-lookup"><span data-stu-id="f02f1-144">Now that the `Widget` class can raise events, you can move to the next walkthrough.</span></span> <span data-ttu-id="f02f1-145">[Tutorial: El `WithEvents` ](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) controlde`PercentDone` eventos muestra cómo utilizar para asociar un controlador de eventos al evento.</span><span class="sxs-lookup"><span data-stu-id="f02f1-145">[Walkthrough: Handling Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) demonstrates how to use `WithEvents` to associate an event handler with the `PercentDone` event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f02f1-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="f02f1-146">See also</span></span>

- <xref:Microsoft.VisualBasic.DateAndTime.Timer%2A>
- <xref:Microsoft.VisualBasic.DateAndTime.Now%2A>
- [<span data-ttu-id="f02f1-147">Tutorial: Controlar eventos</span><span class="sxs-lookup"><span data-stu-id="f02f1-147">Walkthrough: Handling Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)
- [<span data-ttu-id="f02f1-148">Eventos</span><span class="sxs-lookup"><span data-stu-id="f02f1-148">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)
