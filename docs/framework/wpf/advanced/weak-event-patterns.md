---
title: Modelos de evento débil
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- weak event pattern implementation [WPF]
- event handlers [WPF], weak event pattern
- IWeakEventListener interface [WPF]
ms.assetid: e7c62920-4812-4811-94d8-050a65c856f6
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f96327f8eaad36f3faebf48db083125816589821
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="weak-event-patterns"></a><span data-ttu-id="9406f-102">Modelos de evento débil</span><span class="sxs-lookup"><span data-stu-id="9406f-102">Weak Event Patterns</span></span>
<span data-ttu-id="9406f-103">En las aplicaciones, es posible que los controladores que están conectados a los orígenes de eventos no se destruirán en coordinación con el objeto de agente de escucha que se adjunta el controlador para el origen.</span><span class="sxs-lookup"><span data-stu-id="9406f-103">In applications, it is possible that handlers that are attached to event sources will not be destroyed in coordination with the listener object that attached the handler to the source.</span></span> <span data-ttu-id="9406f-104">Esta situación puede provocar pérdidas de memoria.</span><span class="sxs-lookup"><span data-stu-id="9406f-104">This situation can lead to memory leaks.</span></span> [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]<span data-ttu-id="9406f-105"> Introduce un modelo de diseño que puede utilizarse para solucionar este problema, debe proporcionar una clase de administrador dedicada para eventos concretos e implementando una interfaz en los agentes de escucha para ese evento.</span><span class="sxs-lookup"><span data-stu-id="9406f-105"> introduces a design pattern that can be used to address this issue, by providing a dedicated manager class for particular events and implementing an interface on listeners for that event.</span></span> <span data-ttu-id="9406f-106">Este patrón de diseño se conoce como el *modelo de evento débil*.</span><span class="sxs-lookup"><span data-stu-id="9406f-106">This design pattern is known as the *weak event pattern*.</span></span>  
  
## <a name="why-implement-the-weak-event-pattern"></a><span data-ttu-id="9406f-107">¿Por qué implementar el modelo de evento débil?</span><span class="sxs-lookup"><span data-stu-id="9406f-107">Why Implement the Weak Event Pattern?</span></span>  
 <span data-ttu-id="9406f-108">Realizar escuchas de eventos pueden provocar pérdidas de memoria.</span><span class="sxs-lookup"><span data-stu-id="9406f-108">Listening for events can lead to memory leaks.</span></span> <span data-ttu-id="9406f-109">La técnica típica para realizar escuchas de eventos es utilizar la sintaxis específica del lenguaje que asocia un controlador a un evento en un origen.</span><span class="sxs-lookup"><span data-stu-id="9406f-109">The typical technique for listening to an event is to use the language-specific syntax that attaches a handler to an event on a source.</span></span> <span data-ttu-id="9406f-110">Por ejemplo, en C#, que la sintaxis es: `source.SomeEvent += new SomeEventHandler(MyEventHandler)`.</span><span class="sxs-lookup"><span data-stu-id="9406f-110">For example, in C#, that syntax is: `source.SomeEvent += new SomeEventHandler(MyEventHandler)`.</span></span>  
  
 <span data-ttu-id="9406f-111">Esta técnica crea una referencia segura desde el origen de eventos para el agente de escucha de eventos.</span><span class="sxs-lookup"><span data-stu-id="9406f-111">This technique creates a strong reference from the event source to the event listener.</span></span> <span data-ttu-id="9406f-112">Por lo general, asociar un controlador de eventos para un agente de escucha hace que el agente de escucha tienen una duración de los objetos que se ven afectada por la duración del objeto de origen (a menos que explícitamente se quita el controlador de eventos).</span><span class="sxs-lookup"><span data-stu-id="9406f-112">Ordinarily, attaching an event handler for a listener causes the listener to have an object lifetime that is influenced by the object lifetime of the source (unless the event handler is explicitly removed).</span></span> <span data-ttu-id="9406f-113">Sin embargo, en ciertas circunstancias, podrían desear la duración de los objetos del agente de escucha esté controlada por otros factores, como si actualmente pertenece al árbol visual de la aplicación y no por la duración del origen.</span><span class="sxs-lookup"><span data-stu-id="9406f-113">But in certain circumstances, you might want the object lifetime of the listener to be controlled by other factors, such as whether it currently belongs to the visual tree of the application, and not by the lifetime of the source.</span></span> <span data-ttu-id="9406f-114">Cada vez que la duración del objeto de origen se extiende más allá de la duración de los objetos del agente de escucha, el patrón de eventos normales conduce a una pérdida de memoria: el agente de escucha se mantiene activo más tiempo del previsto.</span><span class="sxs-lookup"><span data-stu-id="9406f-114">Whenever the source object lifetime extends beyond the object lifetime of the listener, the normal event pattern leads to a memory leak: the listener is kept alive longer than intended.</span></span>  
  
 <span data-ttu-id="9406f-115">El modelo de evento débil está diseñado para resolver este problema de pérdida de memoria.</span><span class="sxs-lookup"><span data-stu-id="9406f-115">The weak event pattern is designed to solve this memory leak problem.</span></span> <span data-ttu-id="9406f-116">El modelo de evento débil se pueden usar cuando un agente de escucha debe suscribirse a un evento, pero el agente de escucha no sabe explícitamente cuándo se debe anular el registro.</span><span class="sxs-lookup"><span data-stu-id="9406f-116">The weak event pattern can be used whenever a listener needs to register for an event, but the listener does not explicitly know when to unregister.</span></span> <span data-ttu-id="9406f-117">También se puede utilizar el modelo de evento débil siempre que la duración de los objetos del origen supera la duración de los objetos útiles del agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="9406f-117">The weak event pattern can also be used whenever the object lifetime of the source exceeds the useful object lifetime of the listener.</span></span> <span data-ttu-id="9406f-118">(En este caso, *útil* se determina por el usuario.) El modelo de evento débil permite que el agente de escucha registrar y reciban el evento sin que afecte a las características de duración de objeto del agente de escucha de ninguna manera.</span><span class="sxs-lookup"><span data-stu-id="9406f-118">(In this case, *useful* is determined by you.) The weak event pattern allows the listener to register for and receive the event without affecting the object lifetime characteristics of the listener in any way.</span></span> <span data-ttu-id="9406f-119">De hecho, la referencia implícita del origen no determina si el agente de escucha es apto para la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="9406f-119">In effect, the implied reference from the source does not determine whether the listener is eligible for garbage collection.</span></span> <span data-ttu-id="9406f-120">La referencia es una referencia débil, por lo tanto la denominación de modelo de evento débil y relacionado [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9406f-120">The reference is a weak reference, thus the naming of the weak event pattern and the related [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)].</span></span> <span data-ttu-id="9406f-121">El agente de escucha puede ser elementos no utilizados o en caso contrario, se destruye y el origen puede continuar sin conservar las referencias de controlador no recopilables a un objeto que se ha destruido.</span><span class="sxs-lookup"><span data-stu-id="9406f-121">The listener can be garbage collected or otherwise destroyed, and the source can continue without retaining noncollectible handler references to a now destroyed object.</span></span>  
  
## <a name="who-should-implement-the-weak-event-pattern"></a><span data-ttu-id="9406f-122">¿Que deben implementar el modelo de evento débil?</span><span class="sxs-lookup"><span data-stu-id="9406f-122">Who Should Implement the Weak Event Pattern?</span></span>  
 <span data-ttu-id="9406f-123">Implementar el patrón de eventos débiles es interesante principalmente para los autores de controles.</span><span class="sxs-lookup"><span data-stu-id="9406f-123">Implementing the weak event pattern is interesting primarily for control authors.</span></span> <span data-ttu-id="9406f-124">Como autor de un control, es responsable en gran medida el comportamiento y la contención de su control y el impacto en las aplicaciones en el que se inserta.</span><span class="sxs-lookup"><span data-stu-id="9406f-124">As a control author, you are largely responsible for the behavior and containment of your control and the impact it has on applications in which it is inserted.</span></span> <span data-ttu-id="9406f-125">Esto incluye el comportamiento de duración de objetos de control, en particular el tratamiento del problema de pérdida de memoria descrito.</span><span class="sxs-lookup"><span data-stu-id="9406f-125">This includes the control object lifetime behavior, in particular the handling of the described memory leak problem.</span></span>  
  
 <span data-ttu-id="9406f-126">Algunos escenarios se prestan de forma inherente a la aplicación del modelo de evento débil.</span><span class="sxs-lookup"><span data-stu-id="9406f-126">Certain scenarios inherently lend themselves to the application of the weak event pattern.</span></span> <span data-ttu-id="9406f-127">Uno de estos escenarios es el enlace de datos.</span><span class="sxs-lookup"><span data-stu-id="9406f-127">One such scenario is data binding.</span></span> <span data-ttu-id="9406f-128">En el enlace de datos, es común para el objeto de origen que sean completamente independientes del objeto de agente de escucha, que es un destino de un enlace.</span><span class="sxs-lookup"><span data-stu-id="9406f-128">In data binding, it is common for the source object to be completely independent of the listener object, which is a target of a binding.</span></span> <span data-ttu-id="9406f-129">Muchos aspectos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] enlace de datos ya tiene el modelo de evento débil aplicado en cómo se implementan los eventos.</span><span class="sxs-lookup"><span data-stu-id="9406f-129">Many aspects of [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] data binding already have the weak event pattern applied in how the events are implemented.</span></span>  
  
## <a name="how-to-implement-the-weak-event-pattern"></a><span data-ttu-id="9406f-130">Cómo implementar el modelo de evento débil</span><span class="sxs-lookup"><span data-stu-id="9406f-130">How to Implement the Weak Event Pattern</span></span>  
 <span data-ttu-id="9406f-131">Hay tres maneras de implementar el modelo de evento débil.</span><span class="sxs-lookup"><span data-stu-id="9406f-131">There are three ways to implement weak event pattern.</span></span> <span data-ttu-id="9406f-132">En la tabla siguiente se enumera los tres enfoques y proporciona cierta orientación acerca de cuándo se debe utilizar cada una.</span><span class="sxs-lookup"><span data-stu-id="9406f-132">The following table lists the three approaches and provides some guidance for when you should use each.</span></span>  
  
|<span data-ttu-id="9406f-133">Enfoque</span><span class="sxs-lookup"><span data-stu-id="9406f-133">Approach</span></span>|<span data-ttu-id="9406f-134">Cuándo implementar</span><span class="sxs-lookup"><span data-stu-id="9406f-134">When to Implement</span></span>|  
|--------------|-----------------------|  
|<span data-ttu-id="9406f-135">Utilizar una clase de administrador de eventos débiles existente</span><span class="sxs-lookup"><span data-stu-id="9406f-135">Use an existing weak event manager class</span></span>|<span data-ttu-id="9406f-136">Si el evento que desea suscribirse a tiene su correspondiente <xref:System.Windows.WeakEventManager>, use el Administrador de eventos débiles existentes.</span><span class="sxs-lookup"><span data-stu-id="9406f-136">If the event you want to subscribe to has a corresponding <xref:System.Windows.WeakEventManager>, use the existing weak event manager.</span></span> <span data-ttu-id="9406f-137">Para obtener una lista de administradores de eventos débiles que se incluyen con WPF, vea la jerarquía de herencia en la <xref:System.Windows.WeakEventManager> clase.</span><span class="sxs-lookup"><span data-stu-id="9406f-137">For a list of weak event managers that are included with WPF, see the inheritance hierarchy in the <xref:System.Windows.WeakEventManager> class.</span></span> <span data-ttu-id="9406f-138">Sin embargo, tenga en cuenta que hay relativamente pocos administradores de eventos débiles que se incluyen con WPF, por lo que probablemente tendrá que elegir uno de los otros métodos.</span><span class="sxs-lookup"><span data-stu-id="9406f-138">Note, however, that there are relatively few weak event managers that are included with WPF, so you will probably need to choose one of the other approaches.</span></span>|  
|<span data-ttu-id="9406f-139">Use una clase de administrador de eventos débiles genérico</span><span class="sxs-lookup"><span data-stu-id="9406f-139">Use a generic weak event manager class</span></span>|<span data-ttu-id="9406f-140">Usar un tipo genérico <xref:System.Windows.WeakEventManager%602> cuando existente <xref:System.Windows.WeakEventManager> es no disponible, desea una manera fácil de implementar, y no están preocupada con eficacia.</span><span class="sxs-lookup"><span data-stu-id="9406f-140">Use a generic <xref:System.Windows.WeakEventManager%602> when an existing <xref:System.Windows.WeakEventManager> is not available, you want an easy way to implement, and you are not concerned about efficiency.</span></span> <span data-ttu-id="9406f-141">La interfaz genérica <xref:System.Windows.WeakEventManager%602> resulta menos eficaz que un administrador de eventos débiles existentes o personalizadas.</span><span class="sxs-lookup"><span data-stu-id="9406f-141">The generic <xref:System.Windows.WeakEventManager%602> is less efficient than an existing or custom weak event manager.</span></span> <span data-ttu-id="9406f-142">Por ejemplo, la clase genérica hace más de reflexión para detectar el evento que tiene el nombre del evento.</span><span class="sxs-lookup"><span data-stu-id="9406f-142">For example, the generic class does more reflection to discover the event given the event's name.</span></span> <span data-ttu-id="9406f-143">Además, el código para registrar el evento mediante la interfaz genérica <xref:System.Windows.WeakEventManager%602> es más detallado que el uso de una existente o personalizado <xref:System.Windows.WeakEventManager>.</span><span class="sxs-lookup"><span data-stu-id="9406f-143">Also, the code to register the event by using the generic <xref:System.Windows.WeakEventManager%602> is more verbose than using an existing or custom <xref:System.Windows.WeakEventManager>.</span></span>|  
|<span data-ttu-id="9406f-144">Crear una clase de administrador de eventos débiles personalizado</span><span class="sxs-lookup"><span data-stu-id="9406f-144">Create a custom weak event manager class</span></span>|<span data-ttu-id="9406f-145">Crear una personalizada <xref:System.Windows.WeakEventManager> cuando existente <xref:System.Windows.WeakEventManager> no está disponible y desea que la mejor eficacia.</span><span class="sxs-lookup"><span data-stu-id="9406f-145">Create a custom <xref:System.Windows.WeakEventManager> when an existing <xref:System.Windows.WeakEventManager> is not available and you want the best efficiency.</span></span> <span data-ttu-id="9406f-146">Usando un comparador <xref:System.Windows.WeakEventManager> para suscribirse a un evento será más eficaz, pero se incurre en el costo de escribir más código al principio.</span><span class="sxs-lookup"><span data-stu-id="9406f-146">Using a custom <xref:System.Windows.WeakEventManager> to subscribe to an event will be more efficient, but you do incur the cost of writing more code at the beginning.</span></span>|  
  
 <span data-ttu-id="9406f-147">Las secciones siguientes describen cómo implementar el patrón de eventos débiles.</span><span class="sxs-lookup"><span data-stu-id="9406f-147">The following sections describe how to implement the weak event pattern.</span></span>  <span data-ttu-id="9406f-148">Para fines de este análisis, el evento para suscribirse a tiene las siguientes características.</span><span class="sxs-lookup"><span data-stu-id="9406f-148">For purposes of this discussion, the event to subscribe to has the following characteristics.</span></span>  
  
-   <span data-ttu-id="9406f-149">Es el nombre del evento `SomeEvent`.</span><span class="sxs-lookup"><span data-stu-id="9406f-149">The event name is `SomeEvent`.</span></span>  
  
-   <span data-ttu-id="9406f-150">El evento es desencadenado por la `EventSource` clase.</span><span class="sxs-lookup"><span data-stu-id="9406f-150">The event is raised by the `EventSource` class.</span></span>  
  
-   <span data-ttu-id="9406f-151">El controlador de eventos tiene el tipo: `SomeEventEventHandler` (o `EventHandler<SomeEventEventArgs>`).</span><span class="sxs-lookup"><span data-stu-id="9406f-151">The event handler has type: `SomeEventEventHandler` (or `EventHandler<SomeEventEventArgs>`).</span></span>  
  
-   <span data-ttu-id="9406f-152">El evento pasa un parámetro de tipo `SomeEventEventArgs` a los controladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="9406f-152">The event passes a parameter of type `SomeEventEventArgs` to the event handlers.</span></span>  
  
### <a name="using-an-existing-weak-event-manager-class"></a><span data-ttu-id="9406f-153">Usar una clase de evento Manager débil existente</span><span class="sxs-lookup"><span data-stu-id="9406f-153">Using an Existing Weak Event Manager Class</span></span>  
  
1.  <span data-ttu-id="9406f-154">Encuentra el Administrador de un evento débil existente.</span><span class="sxs-lookup"><span data-stu-id="9406f-154">Find an existing weak event manager.</span></span>  
  
     <span data-ttu-id="9406f-155">Para obtener una lista de administradores de eventos débiles que se incluyen con WPF, vea la jerarquía de herencia en la <xref:System.Windows.WeakEventManager> clase.</span><span class="sxs-lookup"><span data-stu-id="9406f-155">For a list of weak event managers that are included with WPF, see the inheritance hierarchy in the <xref:System.Windows.WeakEventManager> class.</span></span>  
  
2.  <span data-ttu-id="9406f-156">Use el nuevo administrador de eventos débiles en lugar de los enlaces de eventos normales.</span><span class="sxs-lookup"><span data-stu-id="9406f-156">Use the new weak event manager instead of the normal event hookup.</span></span>  
  
     <span data-ttu-id="9406f-157">Por ejemplo, si el código usa el modelo siguiente para suscribirse a un evento:</span><span class="sxs-lookup"><span data-stu-id="9406f-157">For example, if your code uses the following pattern to subscribe to an event:</span></span>  
  
    ```  
    source.SomeEvent += new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     <span data-ttu-id="9406f-158">Cambia al siguiente patrón:</span><span class="sxs-lookup"><span data-stu-id="9406f-158">Change it to the following pattern:</span></span>  
  
    ```  
    SomeEventWeakEventManager.AddHandler(source, OnSomeEvent);  
    ```  
  
     <span data-ttu-id="9406f-159">De forma similar, si el código usa el modelo siguiente para cancelar la suscripción a un evento:</span><span class="sxs-lookup"><span data-stu-id="9406f-159">Similarly, if your code uses the following pattern to unsubscribe to an event:</span></span>  
  
    ```  
    source.SomeEvent -= new SomeEventEventHandler(OnSome);  
    ```  
  
     <span data-ttu-id="9406f-160">Cambia al siguiente patrón:</span><span class="sxs-lookup"><span data-stu-id="9406f-160">Change it to the following pattern:</span></span>  
  
    ```  
    SomeEventWeakEventManager.RemoveHandler(source, OnSomeEvent);  
    ```  
  
### <a name="using-the-generic-weak-event-manager-class"></a><span data-ttu-id="9406f-161">Uso de la clase de administrador de eventos débiles genérico</span><span class="sxs-lookup"><span data-stu-id="9406f-161">Using the Generic Weak Event Manager Class</span></span>  
  
1.  <span data-ttu-id="9406f-162">Usar la interfaz genérica <xref:System.Windows.WeakEventManager%602> clase en lugar de los enlaces de eventos normales.</span><span class="sxs-lookup"><span data-stu-id="9406f-162">Use the generic <xref:System.Windows.WeakEventManager%602> class instead of the normal event hookup.</span></span>  
  
     <span data-ttu-id="9406f-163">Cuando usas <xref:System.Windows.WeakEventManager%602> para registrar los agentes de escucha de eventos, se proporciona el origen del evento y <xref:System.EventArgs> tipo como parámetros de tipo para la clase y llamar a <xref:System.Windows.WeakEventManager%602.AddHandler%2A> tal como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="9406f-163">When you use <xref:System.Windows.WeakEventManager%602> to register event listeners, you supply the event source and <xref:System.EventArgs> type as the type parameters to the class and call <xref:System.Windows.WeakEventManager%602.AddHandler%2A> as shown in the following code:</span></span>  
  
    ```  
    WeakEventManager<EventSource, SomeEventEventArgs>.AddHandler(source, "SomeEvent", source_SomeEvent);  
    ```  
  
### <a name="creating-a-custom-weak-event-manager-class"></a><span data-ttu-id="9406f-164">Crear una clase de evento Manager débil personalizada</span><span class="sxs-lookup"><span data-stu-id="9406f-164">Creating a Custom Weak Event Manager Class</span></span>  
  
1.  <span data-ttu-id="9406f-165">Copie la siguiente plantilla de clase al proyecto.</span><span class="sxs-lookup"><span data-stu-id="9406f-165">Copy the following class template to your project.</span></span>  
  
     <span data-ttu-id="9406f-166">Esta clase hereda de la <xref:System.Windows.WeakEventManager> clase.</span><span class="sxs-lookup"><span data-stu-id="9406f-166">This class inherits from the <xref:System.Windows.WeakEventManager> class.</span></span>  
  
     [!code-csharp[WeakEvents#WeakEventManagerTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WeakEvents/CSharp/WeakEventManagerTemplate.cs#weakeventmanagertemplate)]  
  
2.  <span data-ttu-id="9406f-167">Reemplace el `SomeEventWeakEventManager` nombre con su propio nombre.</span><span class="sxs-lookup"><span data-stu-id="9406f-167">Replace the `SomeEventWeakEventManager` name with your own name.</span></span>  
  
3.  <span data-ttu-id="9406f-168">Reemplace los nombres de tres descritos previamente con los nombres correspondientes para el evento.</span><span class="sxs-lookup"><span data-stu-id="9406f-168">Replace the three names described previously with the corresponding names for your event.</span></span> <span data-ttu-id="9406f-169">(`SomeEvent`, `EventSource`, y `SomeEventEventArgs`)</span><span class="sxs-lookup"><span data-stu-id="9406f-169">(`SomeEvent`, `EventSource`, and `SomeEventEventArgs`)</span></span>  
  
4.  <span data-ttu-id="9406f-170">Establecer la visibilidad (pública / interna / privada) de la clase de eventos débiles manager a la misma visibilidad que administra el evento.</span><span class="sxs-lookup"><span data-stu-id="9406f-170">Set the visibility (public / internal / private) of the weak event manager class to the same visibility as event it manages.</span></span>  
  
5.  <span data-ttu-id="9406f-171">Use el nuevo administrador de eventos débiles en lugar de los enlaces de eventos normales.</span><span class="sxs-lookup"><span data-stu-id="9406f-171">Use the new weak event manager instead of the normal event hookup.</span></span>  
  
     <span data-ttu-id="9406f-172">Por ejemplo, si el código usa el modelo siguiente para suscribirse a un evento:</span><span class="sxs-lookup"><span data-stu-id="9406f-172">For example, if your code uses the following pattern to subscribe to an event:</span></span>  
  
    ```  
    source.SomeEvent += new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     <span data-ttu-id="9406f-173">Cambia al siguiente patrón:</span><span class="sxs-lookup"><span data-stu-id="9406f-173">Change it to the following pattern:</span></span>  
  
    ```  
    SomeEventWeakEventManager.AddHandler(source, OnSomeEvent);  
    ```  
  
     <span data-ttu-id="9406f-174">De forma similar, si el código usa el modelo siguiente para cancelar la suscripción a un evento:</span><span class="sxs-lookup"><span data-stu-id="9406f-174">Similarly, if your code uses the following pattern to unsubscribe to an event:</span></span>  
  
    ```  
    source.SomeEvent -= new SomeEventEventHandler(OnSome);  
    ```  
  
     <span data-ttu-id="9406f-175">Cambia al siguiente patrón:</span><span class="sxs-lookup"><span data-stu-id="9406f-175">Change it to the following pattern:</span></span>  
  
    ```  
    SomeEventWeakEventManager.RemoveHandler(source, OnSomeEvent);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="9406f-176">Vea también</span><span class="sxs-lookup"><span data-stu-id="9406f-176">See Also</span></span>  
 <xref:System.Windows.WeakEventManager>  
 <xref:System.Windows.IWeakEventListener>  
 [<span data-ttu-id="9406f-177">Información general sobre eventos enrutados</span><span class="sxs-lookup"><span data-stu-id="9406f-177">Routed Events Overview</span></span>](../../../../docs/framework/wpf/advanced/routed-events-overview.md)  
 [<span data-ttu-id="9406f-178">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="9406f-178">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)
