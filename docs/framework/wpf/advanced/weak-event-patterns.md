---
title: Modelos de evento débil
ms.date: 03/30/2017
helpviewer_keywords:
- weak event pattern implementation [WPF]
- event handlers [WPF], weak event pattern
- IWeakEventListener interface [WPF]
ms.assetid: e7c62920-4812-4811-94d8-050a65c856f6
ms.openlocfilehash: e0cd6837de626fa6bcd560811c6a70f7f6604daa
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59316172"
---
# <a name="weak-event-patterns"></a><span data-ttu-id="826db-102">Modelos de evento débil</span><span class="sxs-lookup"><span data-stu-id="826db-102">Weak Event Patterns</span></span>
<span data-ttu-id="826db-103">En las aplicaciones, es posible que los controladores que están conectados a orígenes de eventos no se destruirán en coordinación con el objeto de agente de escucha que adjuntó el controlador para el origen.</span><span class="sxs-lookup"><span data-stu-id="826db-103">In applications, it is possible that handlers that are attached to event sources will not be destroyed in coordination with the listener object that attached the handler to the source.</span></span> <span data-ttu-id="826db-104">Esta situación puede provocar pérdidas de memoria.</span><span class="sxs-lookup"><span data-stu-id="826db-104">This situation can lead to memory leaks.</span></span> [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="826db-105">presenta un patrón de diseño que se puede usar para resolver este problema, que proporciona una clase de administrador dedicada para eventos concretos e implementando una interfaz en los agentes de escucha para ese evento.</span><span class="sxs-lookup"><span data-stu-id="826db-105">introduces a design pattern that can be used to address this issue, by providing a dedicated manager class for particular events and implementing an interface on listeners for that event.</span></span> <span data-ttu-id="826db-106">Este patrón de diseño se conoce como el *modelo de evento débil*.</span><span class="sxs-lookup"><span data-stu-id="826db-106">This design pattern is known as the *weak event pattern*.</span></span>  
  
## <a name="why-implement-the-weak-event-pattern"></a><span data-ttu-id="826db-107">¿Por qué implementar el modelo de evento débil?</span><span class="sxs-lookup"><span data-stu-id="826db-107">Why Implement the Weak Event Pattern?</span></span>  
 <span data-ttu-id="826db-108">Escucha de eventos puede dar lugar a pérdidas de memoria.</span><span class="sxs-lookup"><span data-stu-id="826db-108">Listening for events can lead to memory leaks.</span></span> <span data-ttu-id="826db-109">La técnica típica para realizar escuchas de eventos es usar la sintaxis específica del lenguaje que se adjunta un controlador a un evento en un origen.</span><span class="sxs-lookup"><span data-stu-id="826db-109">The typical technique for listening to an event is to use the language-specific syntax that attaches a handler to an event on a source.</span></span> <span data-ttu-id="826db-110">Por ejemplo, en C#, que la sintaxis es: `source.SomeEvent += new SomeEventHandler(MyEventHandler)`.</span><span class="sxs-lookup"><span data-stu-id="826db-110">For example, in C#, that syntax is: `source.SomeEvent += new SomeEventHandler(MyEventHandler)`.</span></span>  
  
 <span data-ttu-id="826db-111">Esta técnica crea una referencia segura desde el origen del evento a la escucha de eventos.</span><span class="sxs-lookup"><span data-stu-id="826db-111">This technique creates a strong reference from the event source to the event listener.</span></span> <span data-ttu-id="826db-112">Normalmente, adjuntar un controlador de eventos para un agente de escucha, hace que el agente de escucha tienen una duración de objeto que se ve afectada por la duración del objeto de origen (a menos que explícitamente se quita el controlador de eventos).</span><span class="sxs-lookup"><span data-stu-id="826db-112">Ordinarily, attaching an event handler for a listener causes the listener to have an object lifetime that is influenced by the object lifetime of the source (unless the event handler is explicitly removed).</span></span> <span data-ttu-id="826db-113">Pero en determinadas circunstancias, puede que desee la duración del objeto del agente de escucha que estén controladas por otros factores, como si lo actualmente pertenece al árbol visual de la aplicación y no por la duración de la fuente.</span><span class="sxs-lookup"><span data-stu-id="826db-113">But in certain circumstances, you might want the object lifetime of the listener to be controlled by other factors, such as whether it currently belongs to the visual tree of the application, and not by the lifetime of the source.</span></span> <span data-ttu-id="826db-114">Cada vez que la duración del objeto de origen se extiende más allá de la duración del objeto del agente de escucha, el patrón de eventos normales conduce a una pérdida de memoria: el agente de escucha se mantiene activo más tiempo del previsto.</span><span class="sxs-lookup"><span data-stu-id="826db-114">Whenever the source object lifetime extends beyond the object lifetime of the listener, the normal event pattern leads to a memory leak: the listener is kept alive longer than intended.</span></span>  
  
 <span data-ttu-id="826db-115">El modelo de evento débil está diseñado para resolver este problema de pérdida de memoria.</span><span class="sxs-lookup"><span data-stu-id="826db-115">The weak event pattern is designed to solve this memory leak problem.</span></span> <span data-ttu-id="826db-116">El modelo de evento débil puede usarse siempre que un agente de escucha necesita registrarse para un evento, pero el agente de escucha no conoce explícitamente cuándo se debe anular el registro.</span><span class="sxs-lookup"><span data-stu-id="826db-116">The weak event pattern can be used whenever a listener needs to register for an event, but the listener does not explicitly know when to unregister.</span></span> <span data-ttu-id="826db-117">También se puede usar el modelo de evento débil cada vez que la duración del objeto de origen supera la duración del objeto útiles del agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="826db-117">The weak event pattern can also be used whenever the object lifetime of the source exceeds the useful object lifetime of the listener.</span></span> <span data-ttu-id="826db-118">(En este caso, *útil* viene determinada por el usuario.) El modelo de evento débil permite que el agente de escucha para registrarse y recibir el evento sin que afecte a las características de la duración de objeto del agente de escucha de ninguna manera.</span><span class="sxs-lookup"><span data-stu-id="826db-118">(In this case, *useful* is determined by you.) The weak event pattern allows the listener to register for and receive the event without affecting the object lifetime characteristics of the listener in any way.</span></span> <span data-ttu-id="826db-119">De hecho, la referencia implícita desde el origen no determina si el agente de escucha es apto para la recolección de elementos.</span><span class="sxs-lookup"><span data-stu-id="826db-119">In effect, the implied reference from the source does not determine whether the listener is eligible for garbage collection.</span></span> <span data-ttu-id="826db-120">La referencia es una referencia débil, por lo tanto la denominación de modelo de evento débil y relacionado [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)].</span><span class="sxs-lookup"><span data-stu-id="826db-120">The reference is a weak reference, thus the naming of the weak event pattern and the related [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)].</span></span> <span data-ttu-id="826db-121">El agente de escucha puede ser elementos no utilizados o se destruye en caso contrario, y el origen puede continuar sin conservar las referencias de controlador no recopilables a un objeto que se ha destruido.</span><span class="sxs-lookup"><span data-stu-id="826db-121">The listener can be garbage collected or otherwise destroyed, and the source can continue without retaining noncollectible handler references to a now destroyed object.</span></span>  
  
## <a name="who-should-implement-the-weak-event-pattern"></a><span data-ttu-id="826db-122">¿Quién debe implementar el modelo de evento débil?</span><span class="sxs-lookup"><span data-stu-id="826db-122">Who Should Implement the Weak Event Pattern?</span></span>  
 <span data-ttu-id="826db-123">Implementar el patrón de evento débil es interesante, principalmente para los autores de controles.</span><span class="sxs-lookup"><span data-stu-id="826db-123">Implementing the weak event pattern is interesting primarily for control authors.</span></span> <span data-ttu-id="826db-124">Como autor del control, es responsable en gran medida el comportamiento y la contención de su control y el impacto que tiene en las aplicaciones en la que se inserta.</span><span class="sxs-lookup"><span data-stu-id="826db-124">As a control author, you are largely responsible for the behavior and containment of your control and the impact it has on applications in which it is inserted.</span></span> <span data-ttu-id="826db-125">Esto incluye el comportamiento de duración de objetos de control, en particular la administración del problema de pérdida de memoria descrito.</span><span class="sxs-lookup"><span data-stu-id="826db-125">This includes the control object lifetime behavior, in particular the handling of the described memory leak problem.</span></span>  
  
 <span data-ttu-id="826db-126">Ciertos escenarios intrínsecamente se prestan a la aplicación del modelo de evento débil.</span><span class="sxs-lookup"><span data-stu-id="826db-126">Certain scenarios inherently lend themselves to the application of the weak event pattern.</span></span> <span data-ttu-id="826db-127">Uno de estos escenarios es el enlace de datos.</span><span class="sxs-lookup"><span data-stu-id="826db-127">One such scenario is data binding.</span></span> <span data-ttu-id="826db-128">En el enlace de datos, es común para el objeto de origen que sean completamente independientes del objeto de agente de escucha, que es un destino de un enlace.</span><span class="sxs-lookup"><span data-stu-id="826db-128">In data binding, it is common for the source object to be completely independent of the listener object, which is a target of a binding.</span></span> <span data-ttu-id="826db-129">Muchos aspectos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] enlace de datos ya tiene el modelo de evento débil aplicado en cómo se implementan los eventos.</span><span class="sxs-lookup"><span data-stu-id="826db-129">Many aspects of [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] data binding already have the weak event pattern applied in how the events are implemented.</span></span>  
  
## <a name="how-to-implement-the-weak-event-pattern"></a><span data-ttu-id="826db-130">Cómo implementar el modelo de evento débil</span><span class="sxs-lookup"><span data-stu-id="826db-130">How to Implement the Weak Event Pattern</span></span>  
 <span data-ttu-id="826db-131">Hay tres maneras de implementar el modelo de evento débil.</span><span class="sxs-lookup"><span data-stu-id="826db-131">There are three ways to implement weak event pattern.</span></span> <span data-ttu-id="826db-132">En la tabla siguiente se enumera los tres enfoques y ofrece algunas indicaciones sobre cuándo deben usar cada uno.</span><span class="sxs-lookup"><span data-stu-id="826db-132">The following table lists the three approaches and provides some guidance for when you should use each.</span></span>  
  
|<span data-ttu-id="826db-133">Enfoque</span><span class="sxs-lookup"><span data-stu-id="826db-133">Approach</span></span>|<span data-ttu-id="826db-134">Cuándo implementar</span><span class="sxs-lookup"><span data-stu-id="826db-134">When to Implement</span></span>|  
|--------------|-----------------------|  
|<span data-ttu-id="826db-135">Usar una clase de administrador existente de evento débil</span><span class="sxs-lookup"><span data-stu-id="826db-135">Use an existing weak event manager class</span></span>|<span data-ttu-id="826db-136">Si el evento que desea suscribirse a le corresponde una <xref:System.Windows.WeakEventManager>, utilice el Administrador de evento débil existente.</span><span class="sxs-lookup"><span data-stu-id="826db-136">If the event you want to subscribe to has a corresponding <xref:System.Windows.WeakEventManager>, use the existing weak event manager.</span></span> <span data-ttu-id="826db-137">Para obtener una lista de administradores de evento débil que se incluyen con WPF, vea la jerarquía de herencia en el <xref:System.Windows.WeakEventManager> clase.</span><span class="sxs-lookup"><span data-stu-id="826db-137">For a list of weak event managers that are included with WPF, see the inheritance hierarchy in the <xref:System.Windows.WeakEventManager> class.</span></span> <span data-ttu-id="826db-138">Dado que los administradores de evento débil incluye son limitados, probablemente tendrá que elegir uno de los otros enfoques.</span><span class="sxs-lookup"><span data-stu-id="826db-138">Because the included weak event managers are limited, you will probably need to choose one of the other approaches.</span></span>|  
|<span data-ttu-id="826db-139">Usar una clase de evento débil genérico manager</span><span class="sxs-lookup"><span data-stu-id="826db-139">Use a generic weak event manager class</span></span>|<span data-ttu-id="826db-140">Usar un tipo genérico <xref:System.Windows.WeakEventManager%602> cuando existente <xref:System.Windows.WeakEventManager> es en cuestión no está disponible, desea una manera fácil de implementar, y no sobre la eficacia.</span><span class="sxs-lookup"><span data-stu-id="826db-140">Use a generic <xref:System.Windows.WeakEventManager%602> when an existing <xref:System.Windows.WeakEventManager> is not available, you want an easy way to implement, and you are not concerned about efficiency.</span></span> <span data-ttu-id="826db-141">La interfaz genérica <xref:System.Windows.WeakEventManager%602> es menos eficaz que un administrador de evento débil existentes o personalizadas.</span><span class="sxs-lookup"><span data-stu-id="826db-141">The generic <xref:System.Windows.WeakEventManager%602> is less efficient than an existing or custom weak event manager.</span></span> <span data-ttu-id="826db-142">Por ejemplo, la clase genérica hace más de reflexión para detectar el evento que tiene el nombre del evento.</span><span class="sxs-lookup"><span data-stu-id="826db-142">For example, the generic class does more reflection to discover the event given the event's name.</span></span> <span data-ttu-id="826db-143">Además, el código para registrar el evento mediante el modelo genérico <xref:System.Windows.WeakEventManager%602> es más detallado que el uso de una existente o personalizado <xref:System.Windows.WeakEventManager>.</span><span class="sxs-lookup"><span data-stu-id="826db-143">Also, the code to register the event by using the generic <xref:System.Windows.WeakEventManager%602> is more verbose than using an existing or custom <xref:System.Windows.WeakEventManager>.</span></span>|  
|<span data-ttu-id="826db-144">Crear una clase de administrador personalizado de evento débil</span><span class="sxs-lookup"><span data-stu-id="826db-144">Create a custom weak event manager class</span></span>|<span data-ttu-id="826db-145">Crear un personalizado <xref:System.Windows.WeakEventManager> cuando existente <xref:System.Windows.WeakEventManager> no está disponible y desea que la mejor eficacia.</span><span class="sxs-lookup"><span data-stu-id="826db-145">Create a custom <xref:System.Windows.WeakEventManager> when an existing <xref:System.Windows.WeakEventManager> is not available and you want the best efficiency.</span></span> <span data-ttu-id="826db-146">Utiliza una <xref:System.Windows.WeakEventManager> para suscribirse a un evento será más eficaz, pero se incurre en el costo de escribir más código al principio.</span><span class="sxs-lookup"><span data-stu-id="826db-146">Using a custom <xref:System.Windows.WeakEventManager> to subscribe to an event will be more efficient, but you do incur the cost of writing more code at the beginning.</span></span>|  
|<span data-ttu-id="826db-147">Usar un administrador de evento débil de terceros</span><span class="sxs-lookup"><span data-stu-id="826db-147">Use a third-party weak event manager</span></span>|<span data-ttu-id="826db-148">NuGet tiene [varios administradores de evento débil](https://www.nuget.org/packages?q=weak+event+manager&prerel=false) y muchos marcos WPF también admiten el patrón (por ejemplo, ver [documentación de Prism en la suscripción de eventos de correspondencia imprecisa](https://github.com/PrismLibrary/Prism-Documentation/blob/master/docs/wpf/Communication.md#subscribing-to-events)).</span><span class="sxs-lookup"><span data-stu-id="826db-148">NuGet has [several weak event managers](https://www.nuget.org/packages?q=weak+event+manager&prerel=false) and many WPF frameworks also support the pattern (for instance, see [Prism's documentation on loosely coupled event subscription](https://github.com/PrismLibrary/Prism-Documentation/blob/master/docs/wpf/Communication.md#subscribing-to-events)).</span></span>|

 <span data-ttu-id="826db-149">Las secciones siguientes describen cómo implementar el modelo de evento débil.</span><span class="sxs-lookup"><span data-stu-id="826db-149">The following sections describe how to implement the weak event pattern.</span></span>  <span data-ttu-id="826db-150">Para propósitos de este tutorial, el evento para la suscripción tiene las siguientes características.</span><span class="sxs-lookup"><span data-stu-id="826db-150">For purposes of this discussion, the event to subscribe to has the following characteristics.</span></span>  
  
-   <span data-ttu-id="826db-151">Es el nombre del evento `SomeEvent`.</span><span class="sxs-lookup"><span data-stu-id="826db-151">The event name is `SomeEvent`.</span></span>  
  
-   <span data-ttu-id="826db-152">El evento es desencadenado por la `EventSource` clase.</span><span class="sxs-lookup"><span data-stu-id="826db-152">The event is raised by the `EventSource` class.</span></span>  
  
-   <span data-ttu-id="826db-153">El controlador de eventos tiene el tipo: `SomeEventEventHandler` (o `EventHandler<SomeEventEventArgs>`).</span><span class="sxs-lookup"><span data-stu-id="826db-153">The event handler has type: `SomeEventEventHandler` (or `EventHandler<SomeEventEventArgs>`).</span></span>  
  
-   <span data-ttu-id="826db-154">El evento pasa un parámetro de tipo `SomeEventEventArgs` a los controladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="826db-154">The event passes a parameter of type `SomeEventEventArgs` to the event handlers.</span></span>  
  
### <a name="using-an-existing-weak-event-manager-class"></a><span data-ttu-id="826db-155">Uso de una clase de administrador de eventos débiles existente</span><span class="sxs-lookup"><span data-stu-id="826db-155">Using an Existing Weak Event Manager Class</span></span>  
  
1. <span data-ttu-id="826db-156">Encuentre un evento existente débil manager.</span><span class="sxs-lookup"><span data-stu-id="826db-156">Find an existing weak event manager.</span></span>  
  
     <span data-ttu-id="826db-157">Para obtener una lista de administradores de evento débil que se incluyen con WPF, vea la jerarquía de herencia en el <xref:System.Windows.WeakEventManager> clase.</span><span class="sxs-lookup"><span data-stu-id="826db-157">For a list of weak event managers that are included with WPF, see the inheritance hierarchy in the <xref:System.Windows.WeakEventManager> class.</span></span>  
  
2. <span data-ttu-id="826db-158">Use el nuevo administrador de evento débil en lugar de los enlaces de eventos normales.</span><span class="sxs-lookup"><span data-stu-id="826db-158">Use the new weak event manager instead of the normal event hookup.</span></span>  
  
     <span data-ttu-id="826db-159">Por ejemplo, si el código usa el patrón siguiente para suscribirse a un evento:</span><span class="sxs-lookup"><span data-stu-id="826db-159">For example, if your code uses the following pattern to subscribe to an event:</span></span>  
  
    ```  
    source.SomeEvent += new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     <span data-ttu-id="826db-160">Puede cambiarlo en el siguiente patrón:</span><span class="sxs-lookup"><span data-stu-id="826db-160">Change it to the following pattern:</span></span>  
  
    ```  
    SomeEventWeakEventManager.AddHandler(source, OnSomeEvent);  
    ```  
  
     <span data-ttu-id="826db-161">De forma similar, si el código usa el patrón siguiente para cancelar la suscripción a un evento:</span><span class="sxs-lookup"><span data-stu-id="826db-161">Similarly, if your code uses the following pattern to unsubscribe from an event:</span></span>  
  
    ```  
    source.SomeEvent -= new SomeEventEventHandler(OnSome);  
    ```  
  
     <span data-ttu-id="826db-162">Puede cambiarlo en el siguiente patrón:</span><span class="sxs-lookup"><span data-stu-id="826db-162">Change it to the following pattern:</span></span>  
  
    ```  
    SomeEventWeakEventManager.RemoveHandler(source, OnSomeEvent);  
    ```  
  
### <a name="using-the-generic-weak-event-manager-class"></a><span data-ttu-id="826db-163">Uso de la clase de administrador de eventos genéricos débil</span><span class="sxs-lookup"><span data-stu-id="826db-163">Using the Generic Weak Event Manager Class</span></span>  
  
1. <span data-ttu-id="826db-164">Utilice el tipo genérico <xref:System.Windows.WeakEventManager%602> clase en lugar de los enlaces de eventos normales.</span><span class="sxs-lookup"><span data-stu-id="826db-164">Use the generic <xref:System.Windows.WeakEventManager%602> class instead of the normal event hookup.</span></span>  
  
     <span data-ttu-id="826db-165">Cuando usas <xref:System.Windows.WeakEventManager%602> para registrar los agentes de escucha de eventos, proporciona el origen del evento y <xref:System.EventArgs> tipo como parámetros de tipo para la clase y llamar a <xref:System.Windows.WeakEventManager%602.AddHandler%2A> tal como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="826db-165">When you use <xref:System.Windows.WeakEventManager%602> to register event listeners, you supply the event source and <xref:System.EventArgs> type as the type parameters to the class and call <xref:System.Windows.WeakEventManager%602.AddHandler%2A> as shown in the following code:</span></span>  
  
    ```  
    WeakEventManager<EventSource, SomeEventEventArgs>.AddHandler(source, "SomeEvent", source_SomeEvent);  
    ```  
  
### <a name="creating-a-custom-weak-event-manager-class"></a><span data-ttu-id="826db-166">Creación de una clase personalizada de administrador de evento débil</span><span class="sxs-lookup"><span data-stu-id="826db-166">Creating a Custom Weak Event Manager Class</span></span>  
  
1. <span data-ttu-id="826db-167">Copie la siguiente plantilla de clase al proyecto.</span><span class="sxs-lookup"><span data-stu-id="826db-167">Copy the following class template to your project.</span></span>  
  
     <span data-ttu-id="826db-168">Esta clase hereda de la <xref:System.Windows.WeakEventManager> clase.</span><span class="sxs-lookup"><span data-stu-id="826db-168">This class inherits from the <xref:System.Windows.WeakEventManager> class.</span></span>  
  
     [!code-csharp[WeakEvents#WeakEventManagerTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/WeakEvents/CSharp/WeakEventManagerTemplate.cs#weakeventmanagertemplate)]  
  
2. <span data-ttu-id="826db-169">Reemplace el `SomeEventWeakEventManager` nombre con su propio nombre.</span><span class="sxs-lookup"><span data-stu-id="826db-169">Replace the `SomeEventWeakEventManager` name with your own name.</span></span>  
  
3. <span data-ttu-id="826db-170">Reemplace los tres nombres que se ha descrito anteriormente con los nombres correspondientes para el evento.</span><span class="sxs-lookup"><span data-stu-id="826db-170">Replace the three names described previously with the corresponding names for your event.</span></span> <span data-ttu-id="826db-171">(`SomeEvent`, `EventSource`, y `SomeEventEventArgs`)</span><span class="sxs-lookup"><span data-stu-id="826db-171">(`SomeEvent`, `EventSource`, and `SomeEventEventArgs`)</span></span>  
  
4. <span data-ttu-id="826db-172">Establecer la visibilidad (pública o interna o privada) de la clase de evento débil manager en la misma visibilidad que administra el evento.</span><span class="sxs-lookup"><span data-stu-id="826db-172">Set the visibility (public / internal / private) of the weak event manager class to the same visibility as event it manages.</span></span>  
  
5. <span data-ttu-id="826db-173">Use el nuevo administrador de evento débil en lugar de los enlaces de eventos normales.</span><span class="sxs-lookup"><span data-stu-id="826db-173">Use the new weak event manager instead of the normal event hookup.</span></span>  
  
     <span data-ttu-id="826db-174">Por ejemplo, si el código usa el patrón siguiente para suscribirse a un evento:</span><span class="sxs-lookup"><span data-stu-id="826db-174">For example, if your code uses the following pattern to subscribe to an event:</span></span>  
  
    ```  
    source.SomeEvent += new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     <span data-ttu-id="826db-175">Puede cambiarlo en el siguiente patrón:</span><span class="sxs-lookup"><span data-stu-id="826db-175">Change it to the following pattern:</span></span>  
  
    ```  
    SomeEventWeakEventManager.AddHandler(source, OnSomeEvent);  
    ```  
  
     <span data-ttu-id="826db-176">De forma similar, si el código usa el patrón siguiente para cancelar la suscripción a un evento:</span><span class="sxs-lookup"><span data-stu-id="826db-176">Similarly, if your code uses the following pattern to unsubscribe to an event:</span></span>  
  
    ```  
    source.SomeEvent -= new SomeEventEventHandler(OnSome);  
    ```  
  
     <span data-ttu-id="826db-177">Puede cambiarlo en el siguiente patrón:</span><span class="sxs-lookup"><span data-stu-id="826db-177">Change it to the following pattern:</span></span>  
  
    ```  
    SomeEventWeakEventManager.RemoveHandler(source, OnSomeEvent);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="826db-178">Vea también</span><span class="sxs-lookup"><span data-stu-id="826db-178">See also</span></span>

- <xref:System.Windows.WeakEventManager>
- <xref:System.Windows.IWeakEventListener>
- [<span data-ttu-id="826db-179">Información general sobre eventos enrutados</span><span class="sxs-lookup"><span data-stu-id="826db-179">Routed Events Overview</span></span>](routed-events-overview.md)
- [<span data-ttu-id="826db-180">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="826db-180">Data Binding Overview</span></span>](../data/data-binding-overview.md)
