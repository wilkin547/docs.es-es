---
title: RaiseEvent (instrucción Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.RaiseEventMethod
- vb.RaiseEvent
- RaiseEvent
helpviewer_keywords:
- raising events [Visual Basic], RaiseEvent statement
- RaiseEvent statement [Visual Basic]
- event handlers, connecting events to
ms.assetid: f82e380a-1e6b-4047-bea8-c853f4d2c742
ms.openlocfilehash: ee52b4adf893ea0926c4016fcb6a89d0010ee6ad
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957778"
---
# <a name="raiseevent-statement"></a><span data-ttu-id="ca03b-102">RaiseEvent (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="ca03b-102">RaiseEvent Statement</span></span>
<span data-ttu-id="ca03b-103">Desencadena un evento declarado en el nivel de módulo dentro de una clase, formulario o documento.</span><span class="sxs-lookup"><span data-stu-id="ca03b-103">Triggers an event declared at module level within a class, form, or document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca03b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ca03b-104">Syntax</span></span>  
  
```  
RaiseEvent eventname[( argumentlist )]  
```  
  
## <a name="parts"></a><span data-ttu-id="ca03b-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="ca03b-105">Parts</span></span>  
 `eventname`  
 <span data-ttu-id="ca03b-106">Necesario.</span><span class="sxs-lookup"><span data-stu-id="ca03b-106">Required.</span></span> <span data-ttu-id="ca03b-107">Nombre del evento que se va a desencadenar.</span><span class="sxs-lookup"><span data-stu-id="ca03b-107">Name of the event to trigger.</span></span>  
  
 `argumentlist`  
 <span data-ttu-id="ca03b-108">Opcional.</span><span class="sxs-lookup"><span data-stu-id="ca03b-108">Optional.</span></span> <span data-ttu-id="ca03b-109">Lista delimitada por comas de variables, matrices o expresiones.</span><span class="sxs-lookup"><span data-stu-id="ca03b-109">Comma-delimited list of variables, arrays, or expressions.</span></span> <span data-ttu-id="ca03b-110">El `argumentlist` argumento debe ir entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="ca03b-110">The `argumentlist` argument must be enclosed by parentheses.</span></span> <span data-ttu-id="ca03b-111">Si no hay ningún argumento, se deben omitir los paréntesis.</span><span class="sxs-lookup"><span data-stu-id="ca03b-111">If there are no arguments, the parentheses must be omitted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ca03b-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ca03b-112">Remarks</span></span>  
 <span data-ttu-id="ca03b-113">El requerido `eventname` es el nombre de un evento declarado en el módulo.</span><span class="sxs-lookup"><span data-stu-id="ca03b-113">The required `eventname` is the name of an event declared within the module.</span></span> <span data-ttu-id="ca03b-114">Sigue Visual Basic convenciones de nomenclatura de variables.</span><span class="sxs-lookup"><span data-stu-id="ca03b-114">It follows Visual Basic variable naming conventions.</span></span>  
  
 <span data-ttu-id="ca03b-115">Si el evento no se ha declarado en el módulo en el que se genera, se produce un error.</span><span class="sxs-lookup"><span data-stu-id="ca03b-115">If the event has not been declared within the module in which it is raised, an error occurs.</span></span> <span data-ttu-id="ca03b-116">En el fragmento de código siguiente se muestra una declaración de evento y un procedimiento en el que se genera el evento.</span><span class="sxs-lookup"><span data-stu-id="ca03b-116">The following code fragment illustrates an event declaration and a procedure in which the event is raised.</span></span>  
  
 [!code-vb[VbVbalrEvents#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#37)]  
  
 <span data-ttu-id="ca03b-117">No se puede `RaiseEvent` usar para generar eventos que no se declaran explícitamente en el módulo.</span><span class="sxs-lookup"><span data-stu-id="ca03b-117">You cannot use `RaiseEvent` to raise events that are not explicitly declared in the module.</span></span> <span data-ttu-id="ca03b-118">Por ejemplo, todos los formularios heredan <xref:System.Windows.Forms.Control.Click> un <xref:System.Windows.Forms.Form?displayProperty=nameWithType>evento de, no se pueden `RaiseEvent` generar usando en un formulario derivado.</span><span class="sxs-lookup"><span data-stu-id="ca03b-118">For example, all forms inherit a <xref:System.Windows.Forms.Control.Click> event from <xref:System.Windows.Forms.Form?displayProperty=nameWithType>, it cannot be raised using `RaiseEvent` in a derived form.</span></span> <span data-ttu-id="ca03b-119">Si declara un `Click` evento en el módulo de formulario, sombrea el <xref:System.Windows.Forms.Control.Click> evento del formulario.</span><span class="sxs-lookup"><span data-stu-id="ca03b-119">If you declare a `Click` event in the form module, it shadows the form's own <xref:System.Windows.Forms.Control.Click> event.</span></span> <span data-ttu-id="ca03b-120">Todavía puede invocar el evento del <xref:System.Windows.Forms.Control.Click> formulario llamando al <xref:System.Windows.Forms.Control.OnClick%2A> método.</span><span class="sxs-lookup"><span data-stu-id="ca03b-120">You can still invoke the form's <xref:System.Windows.Forms.Control.Click> event by calling the <xref:System.Windows.Forms.Control.OnClick%2A> method.</span></span>  
  
 <span data-ttu-id="ca03b-121">De forma predeterminada, un evento definido en Visual Basic genera sus controladores de eventos en el orden en que se establecen las conexiones.</span><span class="sxs-lookup"><span data-stu-id="ca03b-121">By default, an event defined in Visual Basic raises its event handlers in the order that the connections are established.</span></span> <span data-ttu-id="ca03b-122">Dado que los eventos `ByRef` pueden tener parámetros, un proceso que se conecta tarde puede recibir parámetros modificados por un controlador de eventos anterior.</span><span class="sxs-lookup"><span data-stu-id="ca03b-122">Because events can have `ByRef` parameters, a process that connects late may receive parameters that have been changed by an earlier event handler.</span></span> <span data-ttu-id="ca03b-123">Una vez que se ejecutan los controladores de eventos, se devuelve el control a la subrutina que provocó el evento.</span><span class="sxs-lookup"><span data-stu-id="ca03b-123">After the event handlers execute, control is returned to the subroutine that raised the event.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ca03b-124">Los eventos no compartidos no se deben generar en el constructor de la clase en la que se declaran.</span><span class="sxs-lookup"><span data-stu-id="ca03b-124">Non-shared events should not be raised within the constructor of the class in which they are declared.</span></span> <span data-ttu-id="ca03b-125">Aunque estos eventos no causan errores en tiempo de ejecución, pueden no ser detectados por los controladores de eventos asociados.</span><span class="sxs-lookup"><span data-stu-id="ca03b-125">Although such events do not cause run-time errors, they may fail to be caught by associated event handlers.</span></span> <span data-ttu-id="ca03b-126">Utilice el `Shared` modificador para crear un evento compartido si necesita generar un evento desde un constructor.</span><span class="sxs-lookup"><span data-stu-id="ca03b-126">Use the `Shared` modifier to create a shared event if you need to raise an event from a constructor.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ca03b-127">Puede cambiar el comportamiento predeterminado de los eventos mediante la definición de un evento personalizado.</span><span class="sxs-lookup"><span data-stu-id="ca03b-127">You can change the default behavior of events by defining a custom event.</span></span> <span data-ttu-id="ca03b-128">En el caso de los `RaiseEvent` eventos personalizados, la instrucción invoca `RaiseEvent` al descriptor de acceso del evento.</span><span class="sxs-lookup"><span data-stu-id="ca03b-128">For custom events, the `RaiseEvent` statement invokes the event's `RaiseEvent` accessor.</span></span> <span data-ttu-id="ca03b-129">Para obtener más información sobre los eventos personalizados, vea [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ca03b-129">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ca03b-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ca03b-130">Example</span></span>  
 <span data-ttu-id="ca03b-131">En el ejemplo siguiente se usan eventos para contar los segundos de 10 a 0.</span><span class="sxs-lookup"><span data-stu-id="ca03b-131">The following example uses events to count down seconds from 10 to 0.</span></span> <span data-ttu-id="ca03b-132">El código muestra algunos de los métodos, las propiedades y las instrucciones relacionados con eventos, incluida la `RaiseEvent` instrucción.</span><span class="sxs-lookup"><span data-stu-id="ca03b-132">The code illustrates several of the event-related methods, properties, and statements, including the `RaiseEvent` statement.</span></span>  
  
 <span data-ttu-id="ca03b-133">La clase que provoca un evento es el origen del evento, y los métodos que procesan el evento son los controladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="ca03b-133">The class that raises an event is the event source, and the methods that process the event are the event handlers.</span></span> <span data-ttu-id="ca03b-134">Un origen de eventos puede tener varios controladores para los eventos que genera.</span><span class="sxs-lookup"><span data-stu-id="ca03b-134">An event source can have multiple handlers for the events it generates.</span></span> <span data-ttu-id="ca03b-135">Cuando la clase genera el evento, ese evento se genera en cada clase que eligió controlar eventos para esa instancia del objeto.</span><span class="sxs-lookup"><span data-stu-id="ca03b-135">When the class raises the event, that event is raised on every class that has elected to handle events for that instance of the object.</span></span>  
  
 <span data-ttu-id="ca03b-136">El ejemplo también usa un formulario (`Form1`) con un botón (`Button1`) y un cuadro de texto (`TextBox1`).</span><span class="sxs-lookup"><span data-stu-id="ca03b-136">The example also uses a form (`Form1`) with a button (`Button1`) and a text box (`TextBox1`).</span></span> <span data-ttu-id="ca03b-137">Al hacer clic en el botón, el primer cuadro de texto muestra una cuenta atrás de 10 a 0 segundos.</span><span class="sxs-lookup"><span data-stu-id="ca03b-137">When you click the button, the first text box displays a countdown from 10 to 0 seconds.</span></span> <span data-ttu-id="ca03b-138">Cuando transcurre el tiempo (10 segundos), el primer cuadro de texto muestra "Done".</span><span class="sxs-lookup"><span data-stu-id="ca03b-138">When the full time (10 seconds) has elapsed, the first text box displays "Done".</span></span>  
  
 <span data-ttu-id="ca03b-139">El código de `Form1` especifica los estados inicial y terminal del formulario.</span><span class="sxs-lookup"><span data-stu-id="ca03b-139">The code for `Form1` specifies the initial and terminal states of the form.</span></span> <span data-ttu-id="ca03b-140">También contiene el código que se ejecuta cuando se producen eventos.</span><span class="sxs-lookup"><span data-stu-id="ca03b-140">It also contains the code executed when events are raised.</span></span>  
  
 <span data-ttu-id="ca03b-141">Para usar este ejemplo, abra un nuevo proyecto de aplicación para Windows, agregue un `Button1` botón denominado y un cuadro `TextBox1` de texto denominado al formulario principal `Form1`, denominado.</span><span class="sxs-lookup"><span data-stu-id="ca03b-141">To use this example, open a new Windows Application project, add a button named `Button1` and a text box named `TextBox1` to the main form, named `Form1`.</span></span> <span data-ttu-id="ca03b-142">A continuación, haga clic con el botón secundario en el formulario y haga clic en **Ver código** para abrir el editor de código.</span><span class="sxs-lookup"><span data-stu-id="ca03b-142">Then right-click the form and click **View Code** to open the Code Editor.</span></span>  
  
 <span data-ttu-id="ca03b-143">Agregue una `WithEvents` variable a la sección de declaraciones de la `Form1` clase.</span><span class="sxs-lookup"><span data-stu-id="ca03b-143">Add a `WithEvents` variable to the declarations section of the `Form1` class.</span></span>  
  
 [!code-vb[VbVbalrEvents#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#14)]  
  
## <a name="example"></a><span data-ttu-id="ca03b-144">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ca03b-144">Example</span></span>  
 <span data-ttu-id="ca03b-145">Agregue el código siguiente al código de `Form1`.</span><span class="sxs-lookup"><span data-stu-id="ca03b-145">Add the following code to the code for `Form1`.</span></span> <span data-ttu-id="ca03b-146">Reemplace los procedimientos duplicados que puedan existir, como `Form_Load`o. `Button_Click`</span><span class="sxs-lookup"><span data-stu-id="ca03b-146">Replace any duplicate procedures that may exist, such as `Form_Load`, or `Button_Click`.</span></span>  
  
 [!code-vb[VbVbalrEvents#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#15)]  
  
 <span data-ttu-id="ca03b-147">Presione F5 para ejecutar el ejemplo anterior y haga clic en el botón **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="ca03b-147">Press F5 to run the preceding example, and click the button labeled **Start**.</span></span> <span data-ttu-id="ca03b-148">El primer cuadro de texto empieza la cuenta atrás de los segundos.</span><span class="sxs-lookup"><span data-stu-id="ca03b-148">The first text box starts to count down the seconds.</span></span> <span data-ttu-id="ca03b-149">Cuando transcurre el tiempo (10 segundos), el primer cuadro de texto muestra "Done".</span><span class="sxs-lookup"><span data-stu-id="ca03b-149">When the full time (10 seconds) has elapsed, the first text box displays "Done".</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ca03b-150">El `My.Application.DoEvents` método no procesa los eventos exactamente del mismo modo que el formulario.</span><span class="sxs-lookup"><span data-stu-id="ca03b-150">The `My.Application.DoEvents` method does not process events in exactly the same way as the form does.</span></span> <span data-ttu-id="ca03b-151">Para permitir que el formulario controle los eventos directamente, puede usar multithreading.</span><span class="sxs-lookup"><span data-stu-id="ca03b-151">To allow the form to handle the events directly, you can use multithreading.</span></span> <span data-ttu-id="ca03b-152">Para obtener más información, vea [subprocesamiento administrado](../../../standard/threading/index.md).</span><span class="sxs-lookup"><span data-stu-id="ca03b-152">For more information, see [Managed Threading](../../../standard/threading/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca03b-153">Vea también</span><span class="sxs-lookup"><span data-stu-id="ca03b-153">See also</span></span>

- [<span data-ttu-id="ca03b-154">Eventos</span><span class="sxs-lookup"><span data-stu-id="ca03b-154">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
- [<span data-ttu-id="ca03b-155">Event (instrucción)</span><span class="sxs-lookup"><span data-stu-id="ca03b-155">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="ca03b-156">AddHandler (instrucción)</span><span class="sxs-lookup"><span data-stu-id="ca03b-156">AddHandler Statement</span></span>](../../../visual-basic/language-reference/statements/addhandler-statement.md)
- [<span data-ttu-id="ca03b-157">RemoveHandler (instrucción)</span><span class="sxs-lookup"><span data-stu-id="ca03b-157">RemoveHandler Statement</span></span>](../../../visual-basic/language-reference/statements/removehandler-statement.md)
- [<span data-ttu-id="ca03b-158">Handles</span><span class="sxs-lookup"><span data-stu-id="ca03b-158">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)
