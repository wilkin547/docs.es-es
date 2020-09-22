---
title: Implementar el modelo asincrónico basado en eventos
description: Aprenda a implementar el modelo asincrónico basado en eventos (EAP) en .NET. EAP es una manera estándar de empaquetar una clase que tiene características asincrónicas.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET Framework], asynchronous
- Asynchronous Pattern
- AsyncOperationManager class
- threading [.NET Framework], asynchronous features
- components [.NET Framework], asynchronous
- AsyncOperation class
- AsyncCompletedEventArgs class
ms.assetid: 43402d19-8d30-426d-8785-1a4478233bfa
ms.openlocfilehash: 466a0dd8a827cd869894106a0901bdab89601e25
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90559101"
---
# <a name="implementing-the-event-based-asynchronous-pattern"></a><span data-ttu-id="50267-104">Implementar el modelo asincrónico basado en eventos</span><span class="sxs-lookup"><span data-stu-id="50267-104">Implementing the Event-based Asynchronous Pattern</span></span>

<span data-ttu-id="50267-105">Si escribe una clase con algunas operaciones que pueden dar lugar a retrasos evidentes, considere la posibilidad de darle funcionalidad asincrónica implementando el [modelo asincrónico basado en eventos](event-based-asynchronous-pattern-overview.md).</span><span class="sxs-lookup"><span data-stu-id="50267-105">If you are writing a class with some operations that may incur noticeable delays, consider giving it asynchronous functionality by implementing the [Event-based Asynchronous Pattern](event-based-asynchronous-pattern-overview.md).</span></span>

<span data-ttu-id="50267-106">El modelo asincrónico basado en eventos proporciona una forma estandarizada de empaquetar una clase que tenga características asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="50267-106">The Event-based Asynchronous Pattern provides a standardized way to package a class that has asynchronous features.</span></span> <span data-ttu-id="50267-107">Si se implementa con clases auxiliares como <xref:System.ComponentModel.AsyncOperationManager>, la clase funciona correctamente en cualquier modelo de aplicación, incluidas aplicaciones de ASP.NET, de consola y de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="50267-107">If implemented with helper classes like <xref:System.ComponentModel.AsyncOperationManager>, your class will work correctly under any application model, including ASP.NET, Console applications, and Windows Forms applications.</span></span>

<span data-ttu-id="50267-108">Para obtener un ejemplo en el que se implementa el modelo asincrónico basado en eventos, vea: [Procedimiento: Implementación de un componente que admita el modelo asincrónico basado en eventos](component-that-supports-the-event-based-asynchronous-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="50267-108">For an example that implements the Event-based Asynchronous Pattern, see [How to: Implement a Component That Supports the Event-based Asynchronous Pattern](component-that-supports-the-event-based-asynchronous-pattern.md).</span></span>

<span data-ttu-id="50267-109">Para las operaciones asincrónicas sencillas, puede encontrar el componente <xref:System.ComponentModel.BackgroundWorker> adecuado.</span><span class="sxs-lookup"><span data-stu-id="50267-109">For simple asynchronous operations, you may find the <xref:System.ComponentModel.BackgroundWorker> component suitable.</span></span> <span data-ttu-id="50267-110">Para más información sobre <xref:System.ComponentModel.BackgroundWorker>, vea [Cómo: Ejecutar una operación en segundo plano](/dotnet/desktop/winforms/controls/how-to-run-an-operation-in-the-background).</span><span class="sxs-lookup"><span data-stu-id="50267-110">For more information about <xref:System.ComponentModel.BackgroundWorker>, see [How to: Run an Operation in the Background](/dotnet/desktop/winforms/controls/how-to-run-an-operation-in-the-background).</span></span>

<span data-ttu-id="50267-111">En la siguiente lista se describen las características del modelo asincrónico basado en eventos tratadas en este tema.</span><span class="sxs-lookup"><span data-stu-id="50267-111">The following list describes the features of the Event-based Asynchronous Pattern discussed in this topic.</span></span>

- <span data-ttu-id="50267-112">Oportunidades para implementar el modelo asincrónico basado en eventos</span><span class="sxs-lookup"><span data-stu-id="50267-112">Opportunities for Implementing the Event-based Asynchronous Pattern</span></span>

- <span data-ttu-id="50267-113">Métodos asincrónicos de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="50267-113">Naming Asynchronous Methods</span></span>

- <span data-ttu-id="50267-114">Opcionalmente, admiten la cancelación</span><span class="sxs-lookup"><span data-stu-id="50267-114">Optionally Support Cancellation</span></span>

- <span data-ttu-id="50267-115">Opcionalmente, admiten la propiedad IsBusy</span><span class="sxs-lookup"><span data-stu-id="50267-115">Optionally Support the IsBusy Property</span></span>

- <span data-ttu-id="50267-116">Opcionalmente, proporcionan compatibilidad para el informe de progreso</span><span class="sxs-lookup"><span data-stu-id="50267-116">Optionally Provide Support for Progress Reporting</span></span>

- <span data-ttu-id="50267-117">Opcionalmente, proporcionan compatibilidad para devolver resultados incrementales</span><span class="sxs-lookup"><span data-stu-id="50267-117">Optionally Provide Support for Returning Incremental Results</span></span>

- <span data-ttu-id="50267-118">Control de los parámetros Out y Ref en los métodos</span><span class="sxs-lookup"><span data-stu-id="50267-118">Handling Out and Ref Parameters in Methods</span></span>

## <a name="opportunities-for-implementing-the-event-based-asynchronous-pattern"></a><span data-ttu-id="50267-119">Oportunidades para implementar el modelo asincrónico basado en eventos</span><span class="sxs-lookup"><span data-stu-id="50267-119">Opportunities for Implementing the Event-based Asynchronous Pattern</span></span>

<span data-ttu-id="50267-120">Considere la posibilidad de implementar el modelo asincrónico basado en eventos en estos casos:</span><span class="sxs-lookup"><span data-stu-id="50267-120">Consider implementing the Event-based Asynchronous Pattern when:</span></span>

- <span data-ttu-id="50267-121">Los clientes de la clase no necesitan que los objetos <xref:System.Threading.WaitHandle> y <xref:System.IAsyncResult> estén disponibles para operaciones asincrónicas, lo que significa que el sondeo y <xref:System.Threading.WaitHandle.WaitAll%2A> o <xref:System.Threading.WaitHandle.WaitAny%2A> deberá crearlos el cliente.</span><span class="sxs-lookup"><span data-stu-id="50267-121">Clients of your class do not need <xref:System.Threading.WaitHandle> and <xref:System.IAsyncResult> objects available for asynchronous operations, meaning that polling and <xref:System.Threading.WaitHandle.WaitAll%2A> or <xref:System.Threading.WaitHandle.WaitAny%2A> will need to be built up by the client.</span></span>

- <span data-ttu-id="50267-122">Desea que el cliente administre las operaciones asincrónicas con el modelo delegado o de evento familiar.</span><span class="sxs-lookup"><span data-stu-id="50267-122">You want asynchronous operations to be managed by the client with the familiar event/delegate model.</span></span>

<span data-ttu-id="50267-123">Cualquier operación es candidata para una implementación asincrónica, pero deben tenerse en cuenta aquellas que espera que incurran en latencias de larga duración.</span><span class="sxs-lookup"><span data-stu-id="50267-123">Any operation is a candidate for an asynchronous implementation, but those you expect to incur long latencies should be considered.</span></span> <span data-ttu-id="50267-124">Son especialmente adecuadas las operaciones en las cuales los clientes llaman a un método y reciben una notificación de su conclusión, sin necesidad de ninguna otra intervención.</span><span class="sxs-lookup"><span data-stu-id="50267-124">Especially appropriate are operations in which clients call a method and are notified on completion, with no further intervention required.</span></span> <span data-ttu-id="50267-125">También son adecuadas aquellas que se ejecutan continuamente, notificando a los clientes de forma periódica del progreso, los resultados incrementales o los cambios de estado.</span><span class="sxs-lookup"><span data-stu-id="50267-125">Also appropriate are operations which run continuously, periodically notifying clients of progress, incremental results, or state changes.</span></span>

<span data-ttu-id="50267-126">Para más información sobre cómo decidir cuándo admitir el modelo asincrónico basado en eventos, consulte [Decisión de cuándo implementar el modelo asincrónico basado en eventos](deciding-when-to-implement-the-event-based-asynchronous-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="50267-126">For more information on deciding when to support the Event-based Asynchronous Pattern, see [Deciding When to Implement the Event-based Asynchronous Pattern](deciding-when-to-implement-the-event-based-asynchronous-pattern.md).</span></span>

## <a name="naming-asynchronous-methods"></a><span data-ttu-id="50267-127">Métodos asincrónicos de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="50267-127">Naming Asynchronous Methods</span></span>

<span data-ttu-id="50267-128">Para cada método sincrónico *MethodName* para el cual desee proporcionar un homólogo asincrónico:</span><span class="sxs-lookup"><span data-stu-id="50267-128">For each synchronous method *MethodName* for which you want to provide an asynchronous counterpart:</span></span>

<span data-ttu-id="50267-129">Defina un método _MethodName_**Async** que:</span><span class="sxs-lookup"><span data-stu-id="50267-129">Define a _MethodName_**Async** method that:</span></span>

- <span data-ttu-id="50267-130">Devuelve `void`.</span><span class="sxs-lookup"><span data-stu-id="50267-130">Returns `void`.</span></span>

- <span data-ttu-id="50267-131">Tome los mismos parámetros que el método *MethodName*.</span><span class="sxs-lookup"><span data-stu-id="50267-131">Takes the same parameters as the *MethodName* method.</span></span>

- <span data-ttu-id="50267-132">Acepte varias invocaciones.</span><span class="sxs-lookup"><span data-stu-id="50267-132">Accepts multiple invocations.</span></span>

<span data-ttu-id="50267-133">Opcionalmente, defina una sobrecarga _MethodName_**Async**, idéntica a _MethodName_**Async**, pero con un parámetro con valor de objeto adicional denominado `userState`.</span><span class="sxs-lookup"><span data-stu-id="50267-133">Optionally define a _MethodName_**Async** overload, identical to _MethodName_**Async**, but with an additional object-valued parameter called `userState`.</span></span> <span data-ttu-id="50267-134">Haga esto si está preparado para administrar varias invocaciones simultáneas de su método, en cuyo caso, el valor `userState` se entregará de nuevo a todos los controladores de eventos para diferenciar las invocaciones del método.</span><span class="sxs-lookup"><span data-stu-id="50267-134">Do this if you're prepared to manage multiple concurrent invocations of your method, in which case the `userState` value will be delivered back to all event handlers to distinguish invocations of the method.</span></span> <span data-ttu-id="50267-135">También puede decidir hacerlo sencillamente como un lugar donde almacenar el estado del usuario para su posterior recuperación.</span><span class="sxs-lookup"><span data-stu-id="50267-135">You may also choose to do this simply as a place to store user state for later retrieval.</span></span>

<span data-ttu-id="50267-136">Para cada signatura del método _MethodName_**Async** independiente:</span><span class="sxs-lookup"><span data-stu-id="50267-136">For each separate _MethodName_**Async** method signature:</span></span>

1. <span data-ttu-id="50267-137">Defina el siguiente evento en la misma clase que el método:</span><span class="sxs-lookup"><span data-stu-id="50267-137">Define the following event in the same class as the method:</span></span>

    ```vb
    Public Event MethodNameCompleted As MethodNameCompletedEventHandler
    ```

    ```csharp
    public event MethodNameCompletedEventHandler MethodNameCompleted;
    ```

2. <span data-ttu-id="50267-138">Defina el delegado siguiente y <xref:System.ComponentModel.AsyncCompletedEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="50267-138">Define the following delegate and <xref:System.ComponentModel.AsyncCompletedEventArgs>.</span></span> <span data-ttu-id="50267-139">Es probable que estos se definan fuera de la propia clase, pero en el mismo espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="50267-139">These will likely be defined outside of the class itself, but in the same namespace.</span></span>

    ```vb
    Public Delegate Sub MethodNameCompletedEventHandler( _
        ByVal sender As Object, _
        ByVal e As MethodNameCompletedEventArgs)

    Public Class MethodNameCompletedEventArgs
        Inherits System.ComponentModel.AsyncCompletedEventArgs
    Public ReadOnly Property Result() As MyReturnType
    End Property
    ```

    ```csharp
    public delegate void MethodNameCompletedEventHandler(object sender,
        MethodNameCompletedEventArgs e);

    public class MethodNameCompletedEventArgs : System.ComponentModel.AsyncCompletedEventArgs
    {
        public MyReturnType Result { get; }
    }
    ```

    - <span data-ttu-id="50267-140">Asegúrese de que la clase _MethodName_**CompletedEventArgs** expone sus miembros como propiedades de solo lectura y no como campos, ya que estos impiden el enlace de datos.</span><span class="sxs-lookup"><span data-stu-id="50267-140">Ensure that the _MethodName_**CompletedEventArgs** class exposes its members as read-only properties, and not fields, as fields prevent data binding.</span></span>

    - <span data-ttu-id="50267-141">No defina ninguna clase derivada de <xref:System.ComponentModel.AsyncCompletedEventArgs> para métodos que no producen resultados.</span><span class="sxs-lookup"><span data-stu-id="50267-141">Do not define any <xref:System.ComponentModel.AsyncCompletedEventArgs>-derived classes for methods that do not produce results.</span></span> <span data-ttu-id="50267-142">Simplemente se usa una instancia de <xref:System.ComponentModel.AsyncCompletedEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="50267-142">Simply use an instance of <xref:System.ComponentModel.AsyncCompletedEventArgs> itself.</span></span>

      > [!NOTE]
      > <span data-ttu-id="50267-143">Es perfectamente aceptable, cuando sea posible y apropiado, para reutilizar el delegado y los tipos <xref:System.ComponentModel.AsyncCompletedEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="50267-143">It is perfectly acceptable, when feasible and appropriate, to reuse delegate and <xref:System.ComponentModel.AsyncCompletedEventArgs> types.</span></span> <span data-ttu-id="50267-144">En este caso, la nomenclatura no será tan coherente con el nombre del método, ya que ni un delegado especificado ni <xref:System.ComponentModel.AsyncCompletedEventArgs> se vincularán a un solo método.</span><span class="sxs-lookup"><span data-stu-id="50267-144">In this case, the naming will not be as consistent with the method name, since a given delegate and <xref:System.ComponentModel.AsyncCompletedEventArgs> won't be tied to a single method.</span></span>

## <a name="optionally-support-cancellation"></a><span data-ttu-id="50267-145">Opcionalmente, admiten la cancelación</span><span class="sxs-lookup"><span data-stu-id="50267-145">Optionally Support Cancellation</span></span>

<span data-ttu-id="50267-146">Si su clase admite la cancelación de operaciones asincrónicas, la cancelación debe exponerse al cliente como se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="50267-146">If your class will support canceling asynchronous operations, cancellation should be exposed to the client as described below.</span></span> <span data-ttu-id="50267-147">Tenga en cuenta que hay dos puntos de decisión que deben alcanzarse antes de definir la compatibilidad de cancelación:</span><span class="sxs-lookup"><span data-stu-id="50267-147">Note that there are two decision points that need to be reached before defining your cancellation support:</span></span>

- <span data-ttu-id="50267-148">¿Tiene su clase, incluidas las futuras adiciones a la misma previstas, solo una operación asincrónica que admita la cancelación?</span><span class="sxs-lookup"><span data-stu-id="50267-148">Does your class, including future anticipated additions to it, have only one asynchronous operation that supports cancellation?</span></span>

- <span data-ttu-id="50267-149">¿Pueden las operaciones asincrónicas que admiten la cancelación admitir varias operaciones pendientes?</span><span class="sxs-lookup"><span data-stu-id="50267-149">Can the asynchronous operations that support cancellation support multiple pending operations?</span></span> <span data-ttu-id="50267-150">Es decir, ¿toma el método _MethodName_**Async** un parámetro `userState` y permite varias invocaciones antes de esperar a que finalice alguna?</span><span class="sxs-lookup"><span data-stu-id="50267-150">That is, does the _MethodName_**Async** method take a `userState` parameter, and does it allow multiple invocations before waiting for any to finish?</span></span>

<span data-ttu-id="50267-151">Use las respuestas a estas dos preguntas en la siguiente tabla para determinar cuál debe ser la signatura para el método de cancelación.</span><span class="sxs-lookup"><span data-stu-id="50267-151">Use the answers to these two questions in the table below to determine what the signature for your cancellation method should be.</span></span>

### <a name="visual-basic"></a><span data-ttu-id="50267-152">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="50267-152">Visual Basic</span></span>

||<span data-ttu-id="50267-153">Varias operaciones simultáneas compatibles</span><span class="sxs-lookup"><span data-stu-id="50267-153">Multiple Simultaneous Operations Supported</span></span>|<span data-ttu-id="50267-154">Solo una operación cada vez</span><span class="sxs-lookup"><span data-stu-id="50267-154">Only One Operation at a Time</span></span>|
|------|------------------------------------------------|----------------------------------|
|<span data-ttu-id="50267-155">Una operación asincrónica en toda la clase</span><span class="sxs-lookup"><span data-stu-id="50267-155">One Async Operation in entire class</span></span>|`Sub MethodNameAsyncCancel(ByVal userState As Object)`|`Sub MethodNameAsyncCancel()`|
|<span data-ttu-id="50267-156">Varias operaciones asincrónicas en la clase</span><span class="sxs-lookup"><span data-stu-id="50267-156">Multiple Async Operations in class</span></span>|`Sub CancelAsync(ByVal userState As Object)`|`Sub CancelAsync()`|

### <a name="c"></a><span data-ttu-id="50267-157">C\#</span><span class="sxs-lookup"><span data-stu-id="50267-157">C\#</span></span>

||<span data-ttu-id="50267-158">Varias operaciones simultáneas compatibles</span><span class="sxs-lookup"><span data-stu-id="50267-158">Multiple Simultaneous Operations Supported</span></span>|<span data-ttu-id="50267-159">Solo una operación cada vez</span><span class="sxs-lookup"><span data-stu-id="50267-159">Only One Operation at a Time</span></span>|
|------|------------------------------------------------|----------------------------------|
|<span data-ttu-id="50267-160">Una operación asincrónica en toda la clase</span><span class="sxs-lookup"><span data-stu-id="50267-160">One Async Operation in entire class</span></span>|`void MethodNameAsyncCancel(object userState);`|`void MethodNameAsyncCancel();`|
|<span data-ttu-id="50267-161">Varias operaciones asincrónicas en la clase</span><span class="sxs-lookup"><span data-stu-id="50267-161">Multiple Async Operations in class</span></span>|`void CancelAsync(object userState);`|`void CancelAsync();`|

<span data-ttu-id="50267-162">Si define el método `CancelAsync(object userState)`, los clientes deben ser cuidadosos al elegir su valor de estado para poder diferenciar entre todos los métodos asincrónicos invocados en el objeto y no solo entre todas las invocaciones de un solo método asincrónico.</span><span class="sxs-lookup"><span data-stu-id="50267-162">If you define the `CancelAsync(object userState)` method, clients must be careful when choosing their state values to make them capable of distinguishing among all asynchronous methods invoked on the object, and not just between all invocations of a single asynchronous method.</span></span>

<span data-ttu-id="50267-163">La decisión de asignar un nombre a la versión de operación asincrónica única _MethodName_**AsyncCancel** se basa en la capacidad de detectar más fácilmente el método en un entorno de diseño como IntelliSense de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="50267-163">The decision to name the single-async-operation version _MethodName_**AsyncCancel** is based on being able to more easily discover the method in a design environment like Visual Studio's IntelliSense.</span></span> <span data-ttu-id="50267-164">Esto agrupa a los miembros relacionados y los diferencia de otros miembros que no tienen nada que ver con la funcionalidad asincrónica.</span><span class="sxs-lookup"><span data-stu-id="50267-164">This groups the related members and distinguishes them from other members that have nothing to do with asynchronous functionality.</span></span> <span data-ttu-id="50267-165">Si espera que pueda haber agregadas operaciones asincrónicas adicionales en versiones posteriores, es mejor definir `CancelAsync`.</span><span class="sxs-lookup"><span data-stu-id="50267-165">If you expect that there may be additional asynchronous operations added in subsequent versions, it is better to define `CancelAsync`.</span></span>

<span data-ttu-id="50267-166">No defina varios métodos de la tabla anterior en la misma clase.</span><span class="sxs-lookup"><span data-stu-id="50267-166">Do not define multiple methods from the table above in the same class.</span></span> <span data-ttu-id="50267-167">No tendrá sentido o desordenará la interfaz de clase con una proliferación de métodos.</span><span class="sxs-lookup"><span data-stu-id="50267-167">That will not make sense, or it will clutter the class interface with a proliferation of methods.</span></span>

<span data-ttu-id="50267-168">Normalmente, estos métodos volverán de inmediato y la operación puede cancelarse, o bien puede no hacerlo en realidad.</span><span class="sxs-lookup"><span data-stu-id="50267-168">These methods typically will return immediately, and the operation may or may not actually cancel.</span></span> <span data-ttu-id="50267-169">En el controlador de eventos para el evento _MethodName_**Completed**, el objeto _MethodName_**CompletedEventArgs** contiene un campo `Cancelled` que los clientes pueden usar para determinar si se ha producido la cancelación.</span><span class="sxs-lookup"><span data-stu-id="50267-169">In the event handler for the _MethodName_**Completed** event, the _MethodName_**CompletedEventArgs** object contains a `Cancelled` field, which clients can use to determine whether the cancellation occurred.</span></span>

<span data-ttu-id="50267-170">Cumpla la semántica de cancelación descrita en [Procedimientos recomendados para implementar el modelo asincrónico basado en eventos](best-practices-for-implementing-the-event-based-asynchronous-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="50267-170">Abide by the cancellation semantics described in [Best Practices for Implementing the Event-based Asynchronous Pattern](best-practices-for-implementing-the-event-based-asynchronous-pattern.md).</span></span>

## <a name="optionally-support-the-isbusy-property"></a><span data-ttu-id="50267-171">Opcionalmente, admiten la propiedad IsBusy</span><span class="sxs-lookup"><span data-stu-id="50267-171">Optionally Support the IsBusy Property</span></span>

<span data-ttu-id="50267-172">Si la clase no admite varias invocaciones simultáneas, considere la posibilidad de exponer una propiedad `IsBusy`.</span><span class="sxs-lookup"><span data-stu-id="50267-172">If your class does not support multiple concurrent invocations, consider exposing an `IsBusy` property.</span></span> <span data-ttu-id="50267-173">Esto permite a los desarrolladores determinar si un método _MethodName_**Async** se ejecuta sin detectar una excepción desde el método _MethodName_**Async**.</span><span class="sxs-lookup"><span data-stu-id="50267-173">This allows developers to determine whether a _MethodName_**Async** method is running without catching an exception from the _MethodName_**Async** method.</span></span>

<span data-ttu-id="50267-174">Cumpla la semántica de `IsBusy` descrita en [Procedimientos recomendados para implementar el modelo asincrónico basado en eventos](best-practices-for-implementing-the-event-based-asynchronous-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="50267-174">Abide by the `IsBusy` semantics described in [Best Practices for Implementing the Event-based Asynchronous Pattern](best-practices-for-implementing-the-event-based-asynchronous-pattern.md).</span></span>

## <a name="optionally-provide-support-for-progress-reporting"></a><span data-ttu-id="50267-175">Opcionalmente, proporcionan compatibilidad para el informe de progreso</span><span class="sxs-lookup"><span data-stu-id="50267-175">Optionally Provide Support for Progress Reporting</span></span>

<span data-ttu-id="50267-176">Suele ser recomendable que una operación asincrónica informe sobre el progreso durante su funcionamiento.</span><span class="sxs-lookup"><span data-stu-id="50267-176">It is frequently desirable for an asynchronous operation to report progress during its operation.</span></span> <span data-ttu-id="50267-177">Para ello, el modelo asincrónico basado en eventos proporciona una directriz.</span><span class="sxs-lookup"><span data-stu-id="50267-177">The Event-based Asynchronous Pattern provides a guideline for doing so.</span></span>

- <span data-ttu-id="50267-178">Opcionalmente, defina un evento que la operación asincrónica va a generar y que se va a invocar en el subproceso adecuado.</span><span class="sxs-lookup"><span data-stu-id="50267-178">Optionally define an event to be raised by the asynchronous operation and invoked on the appropriate thread.</span></span> <span data-ttu-id="50267-179">El objeto <xref:System.ComponentModel.ProgressChangedEventArgs> lleva un indicador de progreso con valor entero que se espera que se sitúe entre 0 y 100.</span><span class="sxs-lookup"><span data-stu-id="50267-179">The <xref:System.ComponentModel.ProgressChangedEventArgs> object carries an integer-valued progress indicator that is expected to be between 0 and 100.</span></span>

- <span data-ttu-id="50267-180">Asigne un nombre a este evento como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="50267-180">Name this event as follows:</span></span>

  - <span data-ttu-id="50267-181">`ProgressChanged` si la clase tiene varias operaciones asincrónicas (o se espera que crezca para incluir varias operaciones asincrónicas en futuras versiones);</span><span class="sxs-lookup"><span data-stu-id="50267-181">`ProgressChanged` if the class has multiple asynchronous operations (or is expected to grow to include multiple asynchronous operations in future versions);</span></span>

  - <span data-ttu-id="50267-182">_MethodName_**ProgressChanged** si la clase tiene una sola operación asincrónica.</span><span class="sxs-lookup"><span data-stu-id="50267-182">_MethodName_**ProgressChanged** if the class has a single asynchronous operation.</span></span>

  <span data-ttu-id="50267-183">Esta opción de nomenclatura va paralela a aquella creada para el método de cancelación, como se describe en la sección Opcionalmente, admiten la cancelación.</span><span class="sxs-lookup"><span data-stu-id="50267-183">This naming choice parallels that made for the cancellation method, as described in the Optionally Support Cancellation section.</span></span>

<span data-ttu-id="50267-184">Este evento debería utilizar la firma de delegado <xref:System.ComponentModel.ProgressChangedEventHandler> y la clase <xref:System.ComponentModel.ProgressChangedEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="50267-184">This event should use the <xref:System.ComponentModel.ProgressChangedEventHandler> delegate signature and the <xref:System.ComponentModel.ProgressChangedEventArgs> class.</span></span> <span data-ttu-id="50267-185">De forma alternativa, si puede proporcionarse un indicador de progreso más específico de dominio (por ejemplo, bytes leídos y total de bytes para una operación de descarga), debe definir una clase derivada de <xref:System.ComponentModel.ProgressChangedEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="50267-185">Alternatively, if a more domain-specific progress indicator can be provided (for instance, bytes read and total bytes for a download operation), then you should define a derived class of <xref:System.ComponentModel.ProgressChangedEventArgs>.</span></span>

<span data-ttu-id="50267-186">Tenga en cuenta que solo hay un evento `ProgressChanged` o _MethodName_**ProgressChanged** para la clase, independientemente del número de métodos asincrónicos que admite.</span><span class="sxs-lookup"><span data-stu-id="50267-186">Note that there is only one `ProgressChanged` or _MethodName_**ProgressChanged** event for the class, regardless of the number of asynchronous methods it supports.</span></span> <span data-ttu-id="50267-187">Se espera que los clientes usen el objeto `userState` que se pasa a los métodos _MethodName_**Async** para diferenciar entre las actualizaciones de progreso en varias operaciones simultáneas.</span><span class="sxs-lookup"><span data-stu-id="50267-187">Clients are expected to use the `userState` object that is passed to the _MethodName_**Async** methods to distinguish among progress updates on multiple concurrent operations.</span></span>

<span data-ttu-id="50267-188">Puede haber situaciones en las que varias operaciones admitan el progreso y cada una devuelva un indicador para el progreso diferente.</span><span class="sxs-lookup"><span data-stu-id="50267-188">There may be situations in which multiple operations support progress and each returns a different indicator for progress.</span></span> <span data-ttu-id="50267-189">En este caso, un solo evento `ProgressChanged` no es adecuado, pudiendo considerar la posibilidad de admitir varios eventos `ProgressChanged`.</span><span class="sxs-lookup"><span data-stu-id="50267-189">In this case, a single `ProgressChanged` event is not appropriate, and you may consider supporting multiple `ProgressChanged` events.</span></span> <span data-ttu-id="50267-190">En este caso, use un patrón de nombres de _MethodName_**ProgressChanged** para cada método _MethodName_**Async**.</span><span class="sxs-lookup"><span data-stu-id="50267-190">In this case use a naming pattern of _MethodName_**ProgressChanged** for each _MethodName_**Async** method.</span></span>

<span data-ttu-id="50267-191">Cumpla la semántica de notificación sobre el progreso descrita en [Procedimientos recomendados para implementar el modelo asincrónico basado en eventos](best-practices-for-implementing-the-event-based-asynchronous-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="50267-191">Abide by the progress-reporting semantics described [Best Practices for Implementing the Event-based Asynchronous Pattern](best-practices-for-implementing-the-event-based-asynchronous-pattern.md).</span></span>

## <a name="optionally-provide-support-for-returning-incremental-results"></a><span data-ttu-id="50267-192">Opcionalmente, proporcionan compatibilidad para devolver resultados incrementales</span><span class="sxs-lookup"><span data-stu-id="50267-192">Optionally Provide Support for Returning Incremental Results</span></span>

<span data-ttu-id="50267-193">A veces, una operación asincrónica puede devolver resultados incrementales antes de finalizar.</span><span class="sxs-lookup"><span data-stu-id="50267-193">Sometimes an asynchronous operation can return incremental results prior to completion.</span></span> <span data-ttu-id="50267-194">Hay una serie de opciones que se pueden usar para admitir este escenario.</span><span class="sxs-lookup"><span data-stu-id="50267-194">There are a number of options that can be used to support this scenario.</span></span> <span data-ttu-id="50267-195">A continuación, se presentan algunos ejemplos.</span><span class="sxs-lookup"><span data-stu-id="50267-195">Some examples follow.</span></span>

### <a name="single-operation-class"></a><span data-ttu-id="50267-196">Clase de operación única</span><span class="sxs-lookup"><span data-stu-id="50267-196">Single-operation Class</span></span>

<span data-ttu-id="50267-197">Si la clase solo admite una sola operación asincrónica y dicha operación puede devolver resultados incrementales, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="50267-197">If your class only supports a single asynchronous operation, and that operation is able to return incremental results, then:</span></span>

- <span data-ttu-id="50267-198">Amplíe el tipo <xref:System.ComponentModel.ProgressChangedEventArgs> para llevar los datos del resultado incremental y defina un evento _MethodName_**ProgressChanged** con estos datos extendidos.</span><span class="sxs-lookup"><span data-stu-id="50267-198">Extend the <xref:System.ComponentModel.ProgressChangedEventArgs> type to carry the incremental result data, and define a _MethodName_**ProgressChanged** event with this extended data.</span></span>

- <span data-ttu-id="50267-199">Genere este evento _MethodName_**ProgressChanged** cuando haya un resultado incremental que notificar.</span><span class="sxs-lookup"><span data-stu-id="50267-199">Raise this _MethodName_**ProgressChanged** event when there is an incremental result to report.</span></span>

<span data-ttu-id="50267-200">Esta solución se aplica de forma específica a una clase de operación asincrónica única porque no hay ningún problema con que el mismo evento se produzca para devolver resultados incrementales en "todas las operaciones", como hace el evento _MethodName_**ProgressChanged**.</span><span class="sxs-lookup"><span data-stu-id="50267-200">This solution applies specifically to a single-async-operation class because there is no problem with the same event occurring to return incremental results on "all operations", as the _MethodName_**ProgressChanged** event does.</span></span>

### <a name="multiple-operation-class-with-homogeneous-incremental-results"></a><span data-ttu-id="50267-201">Clase de varias operaciones con resultados incrementales homogéneos</span><span class="sxs-lookup"><span data-stu-id="50267-201">Multiple-operation Class with Homogeneous Incremental Results</span></span>

<span data-ttu-id="50267-202">En este caso, la clase admite varios métodos asincrónicos, cada uno capaz de devolver resultados incrementales. Además, todos estos resultados incrementales tienen el mismo tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="50267-202">In this case, your class supports multiple asynchronous methods, each capable of returning incremental results, and these incremental results all have the same type of data.</span></span>

<span data-ttu-id="50267-203">Siga el modelo descrito anteriormente para las clases de operación única, ya que la misma estructura <xref:System.EventArgs> funcionará para todos los resultados incrementales.</span><span class="sxs-lookup"><span data-stu-id="50267-203">Follow the model described above for single-operation classes, as the same <xref:System.EventArgs> structure will work for all incremental results.</span></span> <span data-ttu-id="50267-204">Defina un evento `ProgressChanged` en lugar de un evento _MethodName_**ProgressChanged**, ya que se aplica a varios métodos asincrónicos.</span><span class="sxs-lookup"><span data-stu-id="50267-204">Define a `ProgressChanged` event instead of a _MethodName_**ProgressChanged** event, since it applies to multiple asynchronous methods.</span></span>

### <a name="multiple-operation-class-with-heterogeneous-incremental-results"></a><span data-ttu-id="50267-205">Clase de varias operaciones con resultados incrementales heterogéneos</span><span class="sxs-lookup"><span data-stu-id="50267-205">Multiple-operation Class with Heterogeneous Incremental Results</span></span>

<span data-ttu-id="50267-206">Si la clase admite varios métodos asincrónicos, devolviendo cada uno un tipo de datos diferente, debe hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="50267-206">If your class supports multiple asynchronous methods, each returning a different type of data, you should:</span></span>

- <span data-ttu-id="50267-207">Separe el informe de resultados del informe de progreso.</span><span class="sxs-lookup"><span data-stu-id="50267-207">Separate your incremental result reporting from your progress reporting.</span></span>

- <span data-ttu-id="50267-208">Defina un evento _MethodName_**ProgressChanged** independiente con el elemento <xref:System.EventArgs> adecuado para cada método asincrónico con el fin de controlar los datos del resultado incremental de ese método.</span><span class="sxs-lookup"><span data-stu-id="50267-208">Define a separate _MethodName_**ProgressChanged** event with appropriate <xref:System.EventArgs> for each asynchronous method to handle that method's incremental result data.</span></span>

<span data-ttu-id="50267-209">Invoque ese controlador de eventos en el subproceso adecuado como se describe en [Procedimientos recomendados para implementar el modelo asincrónico basado en eventos](best-practices-for-implementing-the-event-based-asynchronous-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="50267-209">Invoke that event handler on the appropriate thread as described in [Best Practices for Implementing the Event-based Asynchronous Pattern](best-practices-for-implementing-the-event-based-asynchronous-pattern.md).</span></span>

## <a name="handling-out-and-ref-parameters-in-methods"></a><span data-ttu-id="50267-210">Control de los parámetros Out y Ref en los métodos</span><span class="sxs-lookup"><span data-stu-id="50267-210">Handling Out and Ref Parameters in Methods</span></span>

<span data-ttu-id="50267-211">Aunque, en general, no se aconseja el uso de `out` y `ref` en .NET Framework, estas son las reglas que se deben seguir cuando estén presentes:</span><span class="sxs-lookup"><span data-stu-id="50267-211">Although the use of `out` and `ref` is, in general, discouraged in the .NET Framework, here are the rules to follow when they are present:</span></span>

<span data-ttu-id="50267-212">Dado un método sincrónico *MethodName*:</span><span class="sxs-lookup"><span data-stu-id="50267-212">Given a synchronous method *MethodName*:</span></span>

- <span data-ttu-id="50267-213">Los parámetros `out` de *MethodName* no deben formar parte de _MethodName_**Async**.</span><span class="sxs-lookup"><span data-stu-id="50267-213">`out` parameters to *MethodName* should not be part of _MethodName_**Async**.</span></span> <span data-ttu-id="50267-214">En su lugar, deben formar parte de _MethodName_**CompletedEventArgs** con el mismo nombre que su parámetro equivalente en *MethodName* (a menos que haya un nombre más adecuado).</span><span class="sxs-lookup"><span data-stu-id="50267-214">Instead, they should be part of _MethodName_**CompletedEventArgs** with the same name as its parameter equivalent in *MethodName* (unless there is a more appropriate name).</span></span>

- <span data-ttu-id="50267-215">Los parámetros `ref` de *MethodName* deben aparecer como parte de _MethodName_**Async** y como parte de _MethodName_**CompletedEventArgs** con el mismo nombre que su parámetro equivalente en *MethodName* (a menos que haya un nombre más adecuado).</span><span class="sxs-lookup"><span data-stu-id="50267-215">`ref` parameters to *MethodName* should appear as part of _MethodName_**Async**, and as part of _MethodName_**CompletedEventArgs** with the same name as its parameter equivalent in *MethodName* (unless there is a more appropriate name).</span></span>

<span data-ttu-id="50267-216">Por ejemplo, dado:</span><span class="sxs-lookup"><span data-stu-id="50267-216">For example, given:</span></span>

```vb
Public Function MethodName(ByVal arg1 As String, ByRef arg2 As String, ByRef arg3 As String) As Integer
```

```csharp
public int MethodName(string arg1, ref string arg2, out string arg3);
```

<span data-ttu-id="50267-217">El método asincrónico y su clase <xref:System.ComponentModel.AsyncCompletedEventArgs> tendrían un aspecto similar a este:</span><span class="sxs-lookup"><span data-stu-id="50267-217">Your asynchronous method and its <xref:System.ComponentModel.AsyncCompletedEventArgs> class would look like this:</span></span>

```vb
Public Sub MethodNameAsync(ByVal arg1 As String, ByVal arg2 As String)

Public Class MethodNameCompletedEventArgs
    Inherits System.ComponentModel.AsyncCompletedEventArgs
    Public ReadOnly Property Result() As Integer
    End Property
    Public ReadOnly Property Arg2() As String
    End Property
    Public ReadOnly Property Arg3() As String
    End Property
End Class
```

```csharp
public void MethodNameAsync(string arg1, string arg2);

public class MethodNameCompletedEventArgs : System.ComponentModel.AsyncCompletedEventArgs
{
    public int Result { get; };
    public string Arg2 { get; };
    public string Arg3 { get; };
}
```

## <a name="see-also"></a><span data-ttu-id="50267-218">Vea también</span><span class="sxs-lookup"><span data-stu-id="50267-218">See also</span></span>

- <xref:System.ComponentModel.ProgressChangedEventArgs>
- <xref:System.ComponentModel.AsyncCompletedEventArgs>
- [<span data-ttu-id="50267-219">Cómo: Implementación de un componente que admita el modelo asincrónico basado en eventos</span><span class="sxs-lookup"><span data-stu-id="50267-219">How to: Implement a Component That Supports the Event-based Asynchronous Pattern</span></span>](component-that-supports-the-event-based-asynchronous-pattern.md)
- [<span data-ttu-id="50267-220">Cómo: Ejecutar una operación en segundo plano</span><span class="sxs-lookup"><span data-stu-id="50267-220">How to: Run an Operation in the Background</span></span>](/dotnet/desktop/winforms/controls/how-to-run-an-operation-in-the-background)
- [<span data-ttu-id="50267-221">Cómo: Implementar un formulario que usa una operación en segundo plano</span><span class="sxs-lookup"><span data-stu-id="50267-221">How to: Implement a Form That Uses a Background Operation</span></span>](/dotnet/desktop/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation)
- [<span data-ttu-id="50267-222">Decisión de cuándo implementar el modelo asincrónico basado en eventos</span><span class="sxs-lookup"><span data-stu-id="50267-222">Deciding When to Implement the Event-based Asynchronous Pattern</span></span>](deciding-when-to-implement-the-event-based-asynchronous-pattern.md)
- [<span data-ttu-id="50267-223">Procedimientos recomendados para implementar el modelo asincrónico basado en eventos</span><span class="sxs-lookup"><span data-stu-id="50267-223">Best Practices for Implementing the Event-based Asynchronous Pattern</span></span>](best-practices-for-implementing-the-event-based-asynchronous-pattern.md)
- [<span data-ttu-id="50267-224">Modelo asincrónico basado en eventos (EAP)</span><span class="sxs-lookup"><span data-stu-id="50267-224">Event-based Asynchronous Pattern (EAP)</span></span>](event-based-asynchronous-pattern-eap.md)
