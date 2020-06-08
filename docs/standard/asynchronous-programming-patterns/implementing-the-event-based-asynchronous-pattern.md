---
title: Implementar el modelo asincrónico basado en eventos
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
ms.openlocfilehash: 484050b45b5da72386e9ac29805d7faf0ca9cbd6
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289387"
---
# <a name="implementing-the-event-based-asynchronous-pattern"></a><span data-ttu-id="cd458-102">Implementar el modelo asincrónico basado en eventos</span><span class="sxs-lookup"><span data-stu-id="cd458-102">Implementing the Event-based Asynchronous Pattern</span></span>

<span data-ttu-id="cd458-103">Si está escribiendo una clase con algunas operaciones que pueden dar lugar a retrasos evidentes, considere la posibilidad de darle funcionalidad asincrónica implementando [Información general sobre el modelo asincrónico basado en eventos](event-based-asynchronous-pattern-overview.md).</span><span class="sxs-lookup"><span data-stu-id="cd458-103">If you are writing a class with some operations that may incur noticeable delays, consider giving it asynchronous functionality by implementing [Event-based Asynchronous Pattern Overview](event-based-asynchronous-pattern-overview.md).</span></span>

<span data-ttu-id="cd458-104">El modelo asincrónico basado en eventos proporciona una forma estandarizada de empaquetar una clase que tenga características asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="cd458-104">The Event-based Asynchronous Pattern provides a standardized way to package a class that has asynchronous features.</span></span> <span data-ttu-id="cd458-105">Si se implementa con clases auxiliares como <xref:System.ComponentModel.AsyncOperationManager>, la clase funciona correctamente en cualquier modelo de aplicación, incluidas aplicaciones de ASP.NET, de consola y de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="cd458-105">If implemented with helper classes like <xref:System.ComponentModel.AsyncOperationManager>, your class will work correctly under any application model, including ASP.NET, Console applications, and Windows Forms applications.</span></span>

<span data-ttu-id="cd458-106">Para obtener un ejemplo que implemente el modelo asincrónico basado en eventos, consulte [How to: Implement a Component That Supports the Event-based Asynchronous Pattern](component-that-supports-the-event-based-asynchronous-pattern.md) (Cómo: Implementar un componente que admita el modelo asincrónico basado en eventos).</span><span class="sxs-lookup"><span data-stu-id="cd458-106">For an example that implements the Event-based Asynchronous Pattern, see [How to: Implement a Component That Supports the Event-based Asynchronous Pattern](component-that-supports-the-event-based-asynchronous-pattern.md).</span></span>

<span data-ttu-id="cd458-107">Para las operaciones asincrónicas sencillas, puede encontrar el componente <xref:System.ComponentModel.BackgroundWorker> adecuado.</span><span class="sxs-lookup"><span data-stu-id="cd458-107">For simple asynchronous operations, you may find the <xref:System.ComponentModel.BackgroundWorker> component suitable.</span></span> <span data-ttu-id="cd458-108">Para más información sobre <xref:System.ComponentModel.BackgroundWorker>, vea [Cómo: Ejecutar una operación en segundo plano](../../framework/winforms/controls/how-to-run-an-operation-in-the-background.md).</span><span class="sxs-lookup"><span data-stu-id="cd458-108">For more information about <xref:System.ComponentModel.BackgroundWorker>, see [How to: Run an Operation in the Background](../../framework/winforms/controls/how-to-run-an-operation-in-the-background.md).</span></span>

<span data-ttu-id="cd458-109">En la siguiente lista se describen las características del modelo asincrónico basado en eventos tratadas en este tema.</span><span class="sxs-lookup"><span data-stu-id="cd458-109">The following list describes the features of the Event-based Asynchronous Pattern discussed in this topic.</span></span>

- <span data-ttu-id="cd458-110">Oportunidades para implementar el modelo asincrónico basado en eventos</span><span class="sxs-lookup"><span data-stu-id="cd458-110">Opportunities for Implementing the Event-based Asynchronous Pattern</span></span>

- <span data-ttu-id="cd458-111">Métodos asincrónicos de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="cd458-111">Naming Asynchronous Methods</span></span>

- <span data-ttu-id="cd458-112">Opcionalmente, admiten la cancelación</span><span class="sxs-lookup"><span data-stu-id="cd458-112">Optionally Support Cancellation</span></span>

- <span data-ttu-id="cd458-113">Opcionalmente, admiten la propiedad IsBusy</span><span class="sxs-lookup"><span data-stu-id="cd458-113">Optionally Support the IsBusy Property</span></span>

- <span data-ttu-id="cd458-114">Opcionalmente, proporcionan compatibilidad para el informe de progreso</span><span class="sxs-lookup"><span data-stu-id="cd458-114">Optionally Provide Support for Progress Reporting</span></span>

- <span data-ttu-id="cd458-115">Opcionalmente, proporcionan compatibilidad para devolver resultados incrementales</span><span class="sxs-lookup"><span data-stu-id="cd458-115">Optionally Provide Support for Returning Incremental Results</span></span>

- <span data-ttu-id="cd458-116">Control de los parámetros Out y Ref en los métodos</span><span class="sxs-lookup"><span data-stu-id="cd458-116">Handling Out and Ref Parameters in Methods</span></span>

## <a name="opportunities-for-implementing-the-event-based-asynchronous-pattern"></a><span data-ttu-id="cd458-117">Oportunidades para implementar el modelo asincrónico basado en eventos</span><span class="sxs-lookup"><span data-stu-id="cd458-117">Opportunities for Implementing the Event-based Asynchronous Pattern</span></span>

<span data-ttu-id="cd458-118">Considere la posibilidad de implementar el modelo asincrónico basado en eventos en estos casos:</span><span class="sxs-lookup"><span data-stu-id="cd458-118">Consider implementing the Event-based Asynchronous Pattern when:</span></span>

- <span data-ttu-id="cd458-119">Los clientes de la clase no necesitan que los objetos <xref:System.Threading.WaitHandle> y <xref:System.IAsyncResult> estén disponibles para operaciones asincrónicas, lo que significa que el sondeo y <xref:System.Threading.WaitHandle.WaitAll%2A> o <xref:System.Threading.WaitHandle.WaitAny%2A> deberá crearlos el cliente.</span><span class="sxs-lookup"><span data-stu-id="cd458-119">Clients of your class do not need <xref:System.Threading.WaitHandle> and <xref:System.IAsyncResult> objects available for asynchronous operations, meaning that polling and <xref:System.Threading.WaitHandle.WaitAll%2A> or <xref:System.Threading.WaitHandle.WaitAny%2A> will need to be built up by the client.</span></span>

- <span data-ttu-id="cd458-120">Desea que el cliente administre las operaciones asincrónicas con el modelo delegado o de evento familiar.</span><span class="sxs-lookup"><span data-stu-id="cd458-120">You want asynchronous operations to be managed by the client with the familiar event/delegate model.</span></span>

<span data-ttu-id="cd458-121">Cualquier operación es candidata para una implementación asincrónica, pero deben tenerse en cuenta aquellas que espera que incurran en latencias de larga duración.</span><span class="sxs-lookup"><span data-stu-id="cd458-121">Any operation is a candidate for an asynchronous implementation, but those you expect to incur long latencies should be considered.</span></span> <span data-ttu-id="cd458-122">Son especialmente adecuadas las operaciones en las cuales los clientes llaman a un método y reciben una notificación de su conclusión, sin necesidad de ninguna otra intervención.</span><span class="sxs-lookup"><span data-stu-id="cd458-122">Especially appropriate are operations in which clients call a method and are notified on completion, with no further intervention required.</span></span> <span data-ttu-id="cd458-123">También son adecuadas aquellas que se ejecutan continuamente, notificando a los clientes de forma periódica del progreso, los resultados incrementales o los cambios de estado.</span><span class="sxs-lookup"><span data-stu-id="cd458-123">Also appropriate are operations which run continuously, periodically notifying clients of progress, incremental results, or state changes.</span></span>

<span data-ttu-id="cd458-124">Para más información sobre cómo decidir cuándo admitir el modelo asincrónico basado en eventos, consulte [Decisión de cuándo implementar el modelo asincrónico basado en eventos](deciding-when-to-implement-the-event-based-asynchronous-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="cd458-124">For more information on deciding when to support the Event-based Asynchronous Pattern, see [Deciding When to Implement the Event-based Asynchronous Pattern](deciding-when-to-implement-the-event-based-asynchronous-pattern.md).</span></span>

## <a name="naming-asynchronous-methods"></a><span data-ttu-id="cd458-125">Métodos asincrónicos de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="cd458-125">Naming Asynchronous Methods</span></span>

<span data-ttu-id="cd458-126">Para cada método sincrónico *MethodName* para el cual desee proporcionar un homólogo asincrónico:</span><span class="sxs-lookup"><span data-stu-id="cd458-126">For each synchronous method *MethodName* for which you want to provide an asynchronous counterpart:</span></span>

<span data-ttu-id="cd458-127">Defina un método _MethodName_**Async** que:</span><span class="sxs-lookup"><span data-stu-id="cd458-127">Define a _MethodName_**Async** method that:</span></span>

- <span data-ttu-id="cd458-128">Devuelve `void`.</span><span class="sxs-lookup"><span data-stu-id="cd458-128">Returns `void`.</span></span>

- <span data-ttu-id="cd458-129">Tome los mismos parámetros que el método *MethodName*.</span><span class="sxs-lookup"><span data-stu-id="cd458-129">Takes the same parameters as the *MethodName* method.</span></span>

- <span data-ttu-id="cd458-130">Acepte varias invocaciones.</span><span class="sxs-lookup"><span data-stu-id="cd458-130">Accepts multiple invocations.</span></span>

<span data-ttu-id="cd458-131">Opcionalmente, defina una sobrecarga _MethodName_**Async**, idéntica a _MethodName_**Async**, pero con un parámetro con valor de objeto adicional denominado `userState`.</span><span class="sxs-lookup"><span data-stu-id="cd458-131">Optionally define a _MethodName_**Async** overload, identical to _MethodName_**Async**, but with an additional object-valued parameter called `userState`.</span></span> <span data-ttu-id="cd458-132">Haga esto si está preparado para administrar varias invocaciones simultáneas de su método, en cuyo caso, el valor `userState` se entregará de nuevo a todos los controladores de eventos para diferenciar las invocaciones del método.</span><span class="sxs-lookup"><span data-stu-id="cd458-132">Do this if you're prepared to manage multiple concurrent invocations of your method, in which case the `userState` value will be delivered back to all event handlers to distinguish invocations of the method.</span></span> <span data-ttu-id="cd458-133">También puede decidir hacerlo sencillamente como un lugar donde almacenar el estado del usuario para su posterior recuperación.</span><span class="sxs-lookup"><span data-stu-id="cd458-133">You may also choose to do this simply as a place to store user state for later retrieval.</span></span>

<span data-ttu-id="cd458-134">Para cada signatura del método _MethodName_**Async** independiente:</span><span class="sxs-lookup"><span data-stu-id="cd458-134">For each separate _MethodName_**Async** method signature:</span></span>

1. <span data-ttu-id="cd458-135">Defina el siguiente evento en la misma clase que el método:</span><span class="sxs-lookup"><span data-stu-id="cd458-135">Define the following event in the same class as the method:</span></span>

    ```vb
    Public Event MethodNameCompleted As MethodNameCompletedEventHandler
    ```

    ```csharp
    public event MethodNameCompletedEventHandler MethodNameCompleted;
    ```

2. <span data-ttu-id="cd458-136">Defina el delegado siguiente y <xref:System.ComponentModel.AsyncCompletedEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="cd458-136">Define the following delegate and <xref:System.ComponentModel.AsyncCompletedEventArgs>.</span></span> <span data-ttu-id="cd458-137">Es probable que estos se definan fuera de la propia clase, pero en el mismo espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="cd458-137">These will likely be defined outside of the class itself, but in the same namespace.</span></span>

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

    - <span data-ttu-id="cd458-138">Asegúrese de que la clase _MethodName_**CompletedEventArgs** expone sus miembros como propiedades de solo lectura y no como campos, ya que estos impiden el enlace de datos.</span><span class="sxs-lookup"><span data-stu-id="cd458-138">Ensure that the _MethodName_**CompletedEventArgs** class exposes its members as read-only properties, and not fields, as fields prevent data binding.</span></span>

    - <span data-ttu-id="cd458-139">No defina ninguna clase derivada de <xref:System.ComponentModel.AsyncCompletedEventArgs> para métodos que no producen resultados.</span><span class="sxs-lookup"><span data-stu-id="cd458-139">Do not define any <xref:System.ComponentModel.AsyncCompletedEventArgs>-derived classes for methods that do not produce results.</span></span> <span data-ttu-id="cd458-140">Simplemente se usa una instancia de <xref:System.ComponentModel.AsyncCompletedEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="cd458-140">Simply use an instance of <xref:System.ComponentModel.AsyncCompletedEventArgs> itself.</span></span>

      > [!NOTE]
      > <span data-ttu-id="cd458-141">Es perfectamente aceptable, cuando sea posible y apropiado, para reutilizar el delegado y los tipos <xref:System.ComponentModel.AsyncCompletedEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="cd458-141">It is perfectly acceptable, when feasible and appropriate, to reuse delegate and <xref:System.ComponentModel.AsyncCompletedEventArgs> types.</span></span> <span data-ttu-id="cd458-142">En este caso, la nomenclatura no será tan coherente con el nombre del método, ya que ni un delegado especificado ni <xref:System.ComponentModel.AsyncCompletedEventArgs> se vincularán a un solo método.</span><span class="sxs-lookup"><span data-stu-id="cd458-142">In this case, the naming will not be as consistent with the method name, since a given delegate and <xref:System.ComponentModel.AsyncCompletedEventArgs> won't be tied to a single method.</span></span>

## <a name="optionally-support-cancellation"></a><span data-ttu-id="cd458-143">Opcionalmente, admiten la cancelación</span><span class="sxs-lookup"><span data-stu-id="cd458-143">Optionally Support Cancellation</span></span>

<span data-ttu-id="cd458-144">Si su clase admite la cancelación de operaciones asincrónicas, la cancelación debe exponerse al cliente como se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="cd458-144">If your class will support canceling asynchronous operations, cancellation should be exposed to the client as described below.</span></span> <span data-ttu-id="cd458-145">Tenga en cuenta que hay dos puntos de decisión que deben alcanzarse antes de definir la compatibilidad de cancelación:</span><span class="sxs-lookup"><span data-stu-id="cd458-145">Note that there are two decision points that need to be reached before defining your cancellation support:</span></span>

- <span data-ttu-id="cd458-146">¿Tiene su clase, incluidas las futuras adiciones a la misma previstas, solo una operación asincrónica que admita la cancelación?</span><span class="sxs-lookup"><span data-stu-id="cd458-146">Does your class, including future anticipated additions to it, have only one asynchronous operation that supports cancellation?</span></span>

- <span data-ttu-id="cd458-147">¿Pueden las operaciones asincrónicas que admiten la cancelación admitir varias operaciones pendientes?</span><span class="sxs-lookup"><span data-stu-id="cd458-147">Can the asynchronous operations that support cancellation support multiple pending operations?</span></span> <span data-ttu-id="cd458-148">Es decir, ¿toma el método _MethodName_**Async** un parámetro `userState` y permite varias invocaciones antes de esperar a que finalice alguna?</span><span class="sxs-lookup"><span data-stu-id="cd458-148">That is, does the _MethodName_**Async** method take a `userState` parameter, and does it allow multiple invocations before waiting for any to finish?</span></span>

<span data-ttu-id="cd458-149">Use las respuestas a estas dos preguntas en la siguiente tabla para determinar cuál debe ser la signatura para el método de cancelación.</span><span class="sxs-lookup"><span data-stu-id="cd458-149">Use the answers to these two questions in the table below to determine what the signature for your cancellation method should be.</span></span>

### <a name="visual-basic"></a><span data-ttu-id="cd458-150">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cd458-150">Visual Basic</span></span>

||<span data-ttu-id="cd458-151">Varias operaciones simultáneas compatibles</span><span class="sxs-lookup"><span data-stu-id="cd458-151">Multiple Simultaneous Operations Supported</span></span>|<span data-ttu-id="cd458-152">Solo una operación cada vez</span><span class="sxs-lookup"><span data-stu-id="cd458-152">Only One Operation at a Time</span></span>|
|------|------------------------------------------------|----------------------------------|
|<span data-ttu-id="cd458-153">Una operación asincrónica en toda la clase</span><span class="sxs-lookup"><span data-stu-id="cd458-153">One Async Operation in entire class</span></span>|`Sub MethodNameAsyncCancel(ByVal userState As Object)`|`Sub MethodNameAsyncCancel()`|
|<span data-ttu-id="cd458-154">Varias operaciones asincrónicas en la clase</span><span class="sxs-lookup"><span data-stu-id="cd458-154">Multiple Async Operations in class</span></span>|`Sub CancelAsync(ByVal userState As Object)`|`Sub CancelAsync()`|

### <a name="c"></a><span data-ttu-id="cd458-155">C\#</span><span class="sxs-lookup"><span data-stu-id="cd458-155">C\#</span></span>

||<span data-ttu-id="cd458-156">Varias operaciones simultáneas compatibles</span><span class="sxs-lookup"><span data-stu-id="cd458-156">Multiple Simultaneous Operations Supported</span></span>|<span data-ttu-id="cd458-157">Solo una operación cada vez</span><span class="sxs-lookup"><span data-stu-id="cd458-157">Only One Operation at a Time</span></span>|
|------|------------------------------------------------|----------------------------------|
|<span data-ttu-id="cd458-158">Una operación asincrónica en toda la clase</span><span class="sxs-lookup"><span data-stu-id="cd458-158">One Async Operation in entire class</span></span>|`void MethodNameAsyncCancel(object userState);`|`void MethodNameAsyncCancel();`|
|<span data-ttu-id="cd458-159">Varias operaciones asincrónicas en la clase</span><span class="sxs-lookup"><span data-stu-id="cd458-159">Multiple Async Operations in class</span></span>|`void CancelAsync(object userState);`|`void CancelAsync();`|

<span data-ttu-id="cd458-160">Si define el método `CancelAsync(object userState)`, los clientes deben ser cuidadosos al elegir su valor de estado para poder diferenciar entre todos los métodos asincrónicos invocados en el objeto y no solo entre todas las invocaciones de un solo método asincrónico.</span><span class="sxs-lookup"><span data-stu-id="cd458-160">If you define the `CancelAsync(object userState)` method, clients must be careful when choosing their state values to make them capable of distinguishing among all asynchronous methods invoked on the object, and not just between all invocations of a single asynchronous method.</span></span>

<span data-ttu-id="cd458-161">La decisión de asignar un nombre a la versión de operación asincrónica única _MethodName_**AsyncCancel** se basa en la capacidad de detectar más fácilmente el método en un entorno de diseño como IntelliSense de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="cd458-161">The decision to name the single-async-operation version _MethodName_**AsyncCancel** is based on being able to more easily discover the method in a design environment like Visual Studio's IntelliSense.</span></span> <span data-ttu-id="cd458-162">Esto agrupa a los miembros relacionados y los diferencia de otros miembros que no tienen nada que ver con la funcionalidad asincrónica.</span><span class="sxs-lookup"><span data-stu-id="cd458-162">This groups the related members and distinguishes them from other members that have nothing to do with asynchronous functionality.</span></span> <span data-ttu-id="cd458-163">Si espera que pueda haber agregadas operaciones asincrónicas adicionales en versiones posteriores, es mejor definir `CancelAsync`.</span><span class="sxs-lookup"><span data-stu-id="cd458-163">If you expect that there may be additional asynchronous operations added in subsequent versions, it is better to define `CancelAsync`.</span></span>

<span data-ttu-id="cd458-164">No defina varios métodos de la tabla anterior en la misma clase.</span><span class="sxs-lookup"><span data-stu-id="cd458-164">Do not define multiple methods from the table above in the same class.</span></span> <span data-ttu-id="cd458-165">No tendrá sentido o desordenará la interfaz de clase con una proliferación de métodos.</span><span class="sxs-lookup"><span data-stu-id="cd458-165">That will not make sense, or it will clutter the class interface with a proliferation of methods.</span></span>

<span data-ttu-id="cd458-166">Normalmente, estos métodos volverán de inmediato y la operación puede cancelarse, o bien puede no hacerlo en realidad.</span><span class="sxs-lookup"><span data-stu-id="cd458-166">These methods typically will return immediately, and the operation may or may not actually cancel.</span></span> <span data-ttu-id="cd458-167">En el controlador de eventos para el evento _MethodName_**Completed**, el objeto _MethodName_**CompletedEventArgs** contiene un campo `Cancelled` que los clientes pueden usar para determinar si se ha producido la cancelación.</span><span class="sxs-lookup"><span data-stu-id="cd458-167">In the event handler for the _MethodName_**Completed** event, the _MethodName_**CompletedEventArgs** object contains a `Cancelled` field, which clients can use to determine whether the cancellation occurred.</span></span>

<span data-ttu-id="cd458-168">Cumpla la semántica de cancelación descrita en [Procedimientos recomendados para implementar el modelo asincrónico basado en eventos](best-practices-for-implementing-the-event-based-asynchronous-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="cd458-168">Abide by the cancellation semantics described in [Best Practices for Implementing the Event-based Asynchronous Pattern](best-practices-for-implementing-the-event-based-asynchronous-pattern.md).</span></span>

## <a name="optionally-support-the-isbusy-property"></a><span data-ttu-id="cd458-169">Opcionalmente, admiten la propiedad IsBusy</span><span class="sxs-lookup"><span data-stu-id="cd458-169">Optionally Support the IsBusy Property</span></span>

<span data-ttu-id="cd458-170">Si la clase no admite varias invocaciones simultáneas, considere la posibilidad de exponer una propiedad `IsBusy`.</span><span class="sxs-lookup"><span data-stu-id="cd458-170">If your class does not support multiple concurrent invocations, consider exposing an `IsBusy` property.</span></span> <span data-ttu-id="cd458-171">Esto permite a los desarrolladores determinar si un método _MethodName_**Async** se ejecuta sin detectar una excepción desde el método _MethodName_**Async**.</span><span class="sxs-lookup"><span data-stu-id="cd458-171">This allows developers to determine whether a _MethodName_**Async** method is running without catching an exception from the _MethodName_**Async** method.</span></span>

<span data-ttu-id="cd458-172">Cumpla la semántica de `IsBusy` descrita en [Procedimientos recomendados para implementar el modelo asincrónico basado en eventos](best-practices-for-implementing-the-event-based-asynchronous-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="cd458-172">Abide by the `IsBusy` semantics described in [Best Practices for Implementing the Event-based Asynchronous Pattern](best-practices-for-implementing-the-event-based-asynchronous-pattern.md).</span></span>

## <a name="optionally-provide-support-for-progress-reporting"></a><span data-ttu-id="cd458-173">Opcionalmente, proporcionan compatibilidad para el informe de progreso</span><span class="sxs-lookup"><span data-stu-id="cd458-173">Optionally Provide Support for Progress Reporting</span></span>

<span data-ttu-id="cd458-174">Suele ser recomendable que una operación asincrónica informe sobre el progreso durante su funcionamiento.</span><span class="sxs-lookup"><span data-stu-id="cd458-174">It is frequently desirable for an asynchronous operation to report progress during its operation.</span></span> <span data-ttu-id="cd458-175">Para ello, el modelo asincrónico basado en eventos proporciona una directriz.</span><span class="sxs-lookup"><span data-stu-id="cd458-175">The Event-based Asynchronous Pattern provides a guideline for doing so.</span></span>

- <span data-ttu-id="cd458-176">Opcionalmente, defina un evento que la operación asincrónica va a generar y que se va a invocar en el subproceso adecuado.</span><span class="sxs-lookup"><span data-stu-id="cd458-176">Optionally define an event to be raised by the asynchronous operation and invoked on the appropriate thread.</span></span> <span data-ttu-id="cd458-177">El objeto <xref:System.ComponentModel.ProgressChangedEventArgs> lleva un indicador de progreso con valor entero que se espera que se sitúe entre 0 y 100.</span><span class="sxs-lookup"><span data-stu-id="cd458-177">The <xref:System.ComponentModel.ProgressChangedEventArgs> object carries an integer-valued progress indicator that is expected to be between 0 and 100.</span></span>

- <span data-ttu-id="cd458-178">Asigne un nombre a este evento como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="cd458-178">Name this event as follows:</span></span>

  - <span data-ttu-id="cd458-179">`ProgressChanged` si la clase tiene varias operaciones asincrónicas (o se espera que crezca para incluir varias operaciones asincrónicas en futuras versiones);</span><span class="sxs-lookup"><span data-stu-id="cd458-179">`ProgressChanged` if the class has multiple asynchronous operations (or is expected to grow to include multiple asynchronous operations in future versions);</span></span>

  - <span data-ttu-id="cd458-180">_MethodName_**ProgressChanged** si la clase tiene una sola operación asincrónica.</span><span class="sxs-lookup"><span data-stu-id="cd458-180">_MethodName_**ProgressChanged** if the class has a single asynchronous operation.</span></span>

  <span data-ttu-id="cd458-181">Esta opción de nomenclatura va paralela a aquella creada para el método de cancelación, como se describe en la sección Opcionalmente, admiten la cancelación.</span><span class="sxs-lookup"><span data-stu-id="cd458-181">This naming choice parallels that made for the cancellation method, as described in the Optionally Support Cancellation section.</span></span>

<span data-ttu-id="cd458-182">Este evento debería utilizar la firma de delegado <xref:System.ComponentModel.ProgressChangedEventHandler> y la clase <xref:System.ComponentModel.ProgressChangedEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="cd458-182">This event should use the <xref:System.ComponentModel.ProgressChangedEventHandler> delegate signature and the <xref:System.ComponentModel.ProgressChangedEventArgs> class.</span></span> <span data-ttu-id="cd458-183">De forma alternativa, si puede proporcionarse un indicador de progreso más específico de dominio (por ejemplo, bytes leídos y total de bytes para una operación de descarga), debe definir una clase derivada de <xref:System.ComponentModel.ProgressChangedEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="cd458-183">Alternatively, if a more domain-specific progress indicator can be provided (for instance, bytes read and total bytes for a download operation), then you should define a derived class of <xref:System.ComponentModel.ProgressChangedEventArgs>.</span></span>

<span data-ttu-id="cd458-184">Tenga en cuenta que solo hay un evento `ProgressChanged` o _MethodName_**ProgressChanged** para la clase, independientemente del número de métodos asincrónicos que admite.</span><span class="sxs-lookup"><span data-stu-id="cd458-184">Note that there is only one `ProgressChanged` or _MethodName_**ProgressChanged** event for the class, regardless of the number of asynchronous methods it supports.</span></span> <span data-ttu-id="cd458-185">Se espera que los clientes usen el objeto `userState` que se pasa a los métodos _MethodName_**Async** para diferenciar entre las actualizaciones de progreso en varias operaciones simultáneas.</span><span class="sxs-lookup"><span data-stu-id="cd458-185">Clients are expected to use the `userState` object that is passed to the _MethodName_**Async** methods to distinguish among progress updates on multiple concurrent operations.</span></span>

<span data-ttu-id="cd458-186">Puede haber situaciones en las que varias operaciones admitan el progreso y cada una devuelva un indicador para el progreso diferente.</span><span class="sxs-lookup"><span data-stu-id="cd458-186">There may be situations in which multiple operations support progress and each returns a different indicator for progress.</span></span> <span data-ttu-id="cd458-187">En este caso, un solo evento `ProgressChanged` no es adecuado, pudiendo considerar la posibilidad de admitir varios eventos `ProgressChanged`.</span><span class="sxs-lookup"><span data-stu-id="cd458-187">In this case, a single `ProgressChanged` event is not appropriate, and you may consider supporting multiple `ProgressChanged` events.</span></span> <span data-ttu-id="cd458-188">En este caso, use un patrón de nombres de _MethodName_**ProgressChanged** para cada método _MethodName_**Async**.</span><span class="sxs-lookup"><span data-stu-id="cd458-188">In this case use a naming pattern of _MethodName_**ProgressChanged** for each _MethodName_**Async** method.</span></span>

<span data-ttu-id="cd458-189">Cumpla la semántica de notificación sobre el progreso descrita en [Procedimientos recomendados para implementar el modelo asincrónico basado en eventos](best-practices-for-implementing-the-event-based-asynchronous-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="cd458-189">Abide by the progress-reporting semantics described [Best Practices for Implementing the Event-based Asynchronous Pattern](best-practices-for-implementing-the-event-based-asynchronous-pattern.md).</span></span>

## <a name="optionally-provide-support-for-returning-incremental-results"></a><span data-ttu-id="cd458-190">Opcionalmente, proporcionan compatibilidad para devolver resultados incrementales</span><span class="sxs-lookup"><span data-stu-id="cd458-190">Optionally Provide Support for Returning Incremental Results</span></span>

<span data-ttu-id="cd458-191">A veces, una operación asincrónica puede devolver resultados incrementales antes de finalizar.</span><span class="sxs-lookup"><span data-stu-id="cd458-191">Sometimes an asynchronous operation can return incremental results prior to completion.</span></span> <span data-ttu-id="cd458-192">Hay una serie de opciones que se pueden usar para admitir este escenario.</span><span class="sxs-lookup"><span data-stu-id="cd458-192">There are a number of options that can be used to support this scenario.</span></span> <span data-ttu-id="cd458-193">A continuación, se presentan algunos ejemplos.</span><span class="sxs-lookup"><span data-stu-id="cd458-193">Some examples follow.</span></span>

### <a name="single-operation-class"></a><span data-ttu-id="cd458-194">Clase de operación única</span><span class="sxs-lookup"><span data-stu-id="cd458-194">Single-operation Class</span></span>

<span data-ttu-id="cd458-195">Si la clase solo admite una sola operación asincrónica y dicha operación puede devolver resultados incrementales, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="cd458-195">If your class only supports a single asynchronous operation, and that operation is able to return incremental results, then:</span></span>

- <span data-ttu-id="cd458-196">Amplíe el tipo <xref:System.ComponentModel.ProgressChangedEventArgs> para llevar los datos del resultado incremental y defina un evento _MethodName_**ProgressChanged** con estos datos extendidos.</span><span class="sxs-lookup"><span data-stu-id="cd458-196">Extend the <xref:System.ComponentModel.ProgressChangedEventArgs> type to carry the incremental result data, and define a _MethodName_**ProgressChanged** event with this extended data.</span></span>

- <span data-ttu-id="cd458-197">Genere este evento _MethodName_**ProgressChanged** cuando haya un resultado incremental que notificar.</span><span class="sxs-lookup"><span data-stu-id="cd458-197">Raise this _MethodName_**ProgressChanged** event when there is an incremental result to report.</span></span>

<span data-ttu-id="cd458-198">Esta solución se aplica de forma específica a una clase de operación asincrónica única porque no hay ningún problema con que el mismo evento se produzca para devolver resultados incrementales en "todas las operaciones", como hace el evento _MethodName_**ProgressChanged**.</span><span class="sxs-lookup"><span data-stu-id="cd458-198">This solution applies specifically to a single-async-operation class because there is no problem with the same event occurring to return incremental results on "all operations", as the _MethodName_**ProgressChanged** event does.</span></span>

### <a name="multiple-operation-class-with-homogeneous-incremental-results"></a><span data-ttu-id="cd458-199">Clase de varias operaciones con resultados incrementales homogéneos</span><span class="sxs-lookup"><span data-stu-id="cd458-199">Multiple-operation Class with Homogeneous Incremental Results</span></span>

<span data-ttu-id="cd458-200">En este caso, la clase admite varios métodos asincrónicos, cada uno capaz de devolver resultados incrementales. Además, todos estos resultados incrementales tienen el mismo tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="cd458-200">In this case, your class supports multiple asynchronous methods, each capable of returning incremental results, and these incremental results all have the same type of data.</span></span>

<span data-ttu-id="cd458-201">Siga el modelo descrito anteriormente para las clases de operación única, ya que la misma estructura <xref:System.EventArgs> funcionará para todos los resultados incrementales.</span><span class="sxs-lookup"><span data-stu-id="cd458-201">Follow the model described above for single-operation classes, as the same <xref:System.EventArgs> structure will work for all incremental results.</span></span> <span data-ttu-id="cd458-202">Defina un evento `ProgressChanged` en lugar de un evento _MethodName_**ProgressChanged**, ya que se aplica a varios métodos asincrónicos.</span><span class="sxs-lookup"><span data-stu-id="cd458-202">Define a `ProgressChanged` event instead of a _MethodName_**ProgressChanged** event, since it applies to multiple asynchronous methods.</span></span>

### <a name="multiple-operation-class-with-heterogeneous-incremental-results"></a><span data-ttu-id="cd458-203">Clase de varias operaciones con resultados incrementales heterogéneos</span><span class="sxs-lookup"><span data-stu-id="cd458-203">Multiple-operation Class with Heterogeneous Incremental Results</span></span>

<span data-ttu-id="cd458-204">Si la clase admite varios métodos asincrónicos, devolviendo cada uno un tipo de datos diferente, debe hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="cd458-204">If your class supports multiple asynchronous methods, each returning a different type of data, you should:</span></span>

- <span data-ttu-id="cd458-205">Separe el informe de resultados del informe de progreso.</span><span class="sxs-lookup"><span data-stu-id="cd458-205">Separate your incremental result reporting from your progress reporting.</span></span>

- <span data-ttu-id="cd458-206">Defina un evento _MethodName_**ProgressChanged** independiente con el elemento <xref:System.EventArgs> adecuado para cada método asincrónico con el fin de controlar los datos del resultado incremental de ese método.</span><span class="sxs-lookup"><span data-stu-id="cd458-206">Define a separate _MethodName_**ProgressChanged** event with appropriate <xref:System.EventArgs> for each asynchronous method to handle that method's incremental result data.</span></span>

<span data-ttu-id="cd458-207">Invoque ese controlador de eventos en el subproceso adecuado como se describe en [Procedimientos recomendados para implementar el modelo asincrónico basado en eventos](best-practices-for-implementing-the-event-based-asynchronous-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="cd458-207">Invoke that event handler on the appropriate thread as described in [Best Practices for Implementing the Event-based Asynchronous Pattern](best-practices-for-implementing-the-event-based-asynchronous-pattern.md).</span></span>

## <a name="handling-out-and-ref-parameters-in-methods"></a><span data-ttu-id="cd458-208">Control de los parámetros Out y Ref en los métodos</span><span class="sxs-lookup"><span data-stu-id="cd458-208">Handling Out and Ref Parameters in Methods</span></span>

<span data-ttu-id="cd458-209">Aunque, en general, no se aconseja el uso de `out` y `ref` en .NET Framework, estas son las reglas que se deben seguir cuando estén presentes:</span><span class="sxs-lookup"><span data-stu-id="cd458-209">Although the use of `out` and `ref` is, in general, discouraged in the .NET Framework, here are the rules to follow when they are present:</span></span>

<span data-ttu-id="cd458-210">Dado un método sincrónico *MethodName*:</span><span class="sxs-lookup"><span data-stu-id="cd458-210">Given a synchronous method *MethodName*:</span></span>

- <span data-ttu-id="cd458-211">Los parámetros `out` de *MethodName* no deben formar parte de _MethodName_**Async**.</span><span class="sxs-lookup"><span data-stu-id="cd458-211">`out` parameters to *MethodName* should not be part of _MethodName_**Async**.</span></span> <span data-ttu-id="cd458-212">En su lugar, deben formar parte de _MethodName_**CompletedEventArgs** con el mismo nombre que su parámetro equivalente en *MethodName* (a menos que haya un nombre más adecuado).</span><span class="sxs-lookup"><span data-stu-id="cd458-212">Instead, they should be part of _MethodName_**CompletedEventArgs** with the same name as its parameter equivalent in *MethodName* (unless there is a more appropriate name).</span></span>

- <span data-ttu-id="cd458-213">Los parámetros `ref` de *MethodName* deben aparecer como parte de _MethodName_**Async** y como parte de _MethodName_**CompletedEventArgs** con el mismo nombre que su parámetro equivalente en *MethodName* (a menos que haya un nombre más adecuado).</span><span class="sxs-lookup"><span data-stu-id="cd458-213">`ref` parameters to *MethodName* should appear as part of _MethodName_**Async**, and as part of _MethodName_**CompletedEventArgs** with the same name as its parameter equivalent in *MethodName* (unless there is a more appropriate name).</span></span>

<span data-ttu-id="cd458-214">Por ejemplo, dado:</span><span class="sxs-lookup"><span data-stu-id="cd458-214">For example, given:</span></span>

```vb
Public Function MethodName(ByVal arg1 As String, ByRef arg2 As String, ByRef arg3 As String) As Integer
```

```csharp
public int MethodName(string arg1, ref string arg2, out string arg3);
```

<span data-ttu-id="cd458-215">El método asincrónico y su clase <xref:System.ComponentModel.AsyncCompletedEventArgs> tendrían un aspecto similar a este:</span><span class="sxs-lookup"><span data-stu-id="cd458-215">Your asynchronous method and its <xref:System.ComponentModel.AsyncCompletedEventArgs> class would look like this:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="cd458-216">Vea también</span><span class="sxs-lookup"><span data-stu-id="cd458-216">See also</span></span>

- <xref:System.ComponentModel.ProgressChangedEventArgs>
- <xref:System.ComponentModel.AsyncCompletedEventArgs>
- [<span data-ttu-id="cd458-217">Implementar un componente que admita el modelo asincrónico basado en eventos</span><span class="sxs-lookup"><span data-stu-id="cd458-217">How to: Implement a Component That Supports the Event-based Asynchronous Pattern</span></span>](component-that-supports-the-event-based-asynchronous-pattern.md)
- [<span data-ttu-id="cd458-218">Ejecutar una operación en segundo plano</span><span class="sxs-lookup"><span data-stu-id="cd458-218">How to: Run an Operation in the Background</span></span>](../../framework/winforms/controls/how-to-run-an-operation-in-the-background.md)
- [<span data-ttu-id="cd458-219">Cómo: Implementar un formulario que utiliza una operación en segundo plano</span><span class="sxs-lookup"><span data-stu-id="cd458-219">How to: Implement a Form That Uses a Background Operation</span></span>](../../framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)
- [<span data-ttu-id="cd458-220">Decisión de cuándo implementar el modelo asincrónico basado en eventos</span><span class="sxs-lookup"><span data-stu-id="cd458-220">Deciding When to Implement the Event-based Asynchronous Pattern</span></span>](deciding-when-to-implement-the-event-based-asynchronous-pattern.md)
- [<span data-ttu-id="cd458-221">Procedimientos recomendados para implementar el modelo asincrónico basado en eventos</span><span class="sxs-lookup"><span data-stu-id="cd458-221">Best Practices for Implementing the Event-based Asynchronous Pattern</span></span>](best-practices-for-implementing-the-event-based-asynchronous-pattern.md)
- [<span data-ttu-id="cd458-222">Modelo asincrónico basado en eventos (EAP)</span><span class="sxs-lookup"><span data-stu-id="cd458-222">Event-based Asynchronous Pattern (EAP)</span></span>](event-based-asynchronous-pattern-eap.md)
