---
title: Modelos de evento débil
ms.date: 03/30/2017
helpviewer_keywords:
- weak event pattern implementation [WPF]
- event handlers [WPF], weak event pattern
- IWeakEventListener interface [WPF]
ms.assetid: e7c62920-4812-4811-94d8-050a65c856f6
ms.openlocfilehash: 9f61a5a60b2ba1305158d1ab570079fe6aac19ac
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76870745"
---
# <a name="weak-event-patterns"></a><span data-ttu-id="facc0-102">Modelos de evento débil</span><span class="sxs-lookup"><span data-stu-id="facc0-102">Weak Event Patterns</span></span>
<span data-ttu-id="facc0-103">En las aplicaciones, es posible que los controladores asociados a los orígenes de eventos no se destruyan en coordinación con el objeto de agente de escucha que adjuntó el controlador al origen.</span><span class="sxs-lookup"><span data-stu-id="facc0-103">In applications, it is possible that handlers that are attached to event sources will not be destroyed in coordination with the listener object that attached the handler to the source.</span></span> <span data-ttu-id="facc0-104">Esta situación puede provocar pérdidas de memoria.</span><span class="sxs-lookup"><span data-stu-id="facc0-104">This situation can lead to memory leaks.</span></span> [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="facc0-105">presenta un modelo de diseño que se puede usar para solucionar este problema, proporcionando una clase de administrador dedicada para eventos concretos e implementando una interfaz en agentes de escucha para ese evento.</span><span class="sxs-lookup"><span data-stu-id="facc0-105">introduces a design pattern that can be used to address this issue, by providing a dedicated manager class for particular events and implementing an interface on listeners for that event.</span></span> <span data-ttu-id="facc0-106">Este modelo de diseño se conoce como el *patrón de evento débil*.</span><span class="sxs-lookup"><span data-stu-id="facc0-106">This design pattern is known as the *weak event pattern*.</span></span>  
  
## <a name="why-implement-the-weak-event-pattern"></a><span data-ttu-id="facc0-107">¿Por qué implementar el patrón de evento débil?</span><span class="sxs-lookup"><span data-stu-id="facc0-107">Why Implement the Weak Event Pattern?</span></span>  
 <span data-ttu-id="facc0-108">La escucha de eventos puede dar lugar a pérdidas de memoria.</span><span class="sxs-lookup"><span data-stu-id="facc0-108">Listening for events can lead to memory leaks.</span></span> <span data-ttu-id="facc0-109">La técnica típica para escuchar un evento es usar la sintaxis específica del lenguaje que asocia un controlador a un evento en un origen.</span><span class="sxs-lookup"><span data-stu-id="facc0-109">The typical technique for listening to an event is to use the language-specific syntax that attaches a handler to an event on a source.</span></span> <span data-ttu-id="facc0-110">Por ejemplo, en C#, esa sintaxis es: `source.SomeEvent += new SomeEventHandler(MyEventHandler)`.</span><span class="sxs-lookup"><span data-stu-id="facc0-110">For example, in C#, that syntax is: `source.SomeEvent += new SomeEventHandler(MyEventHandler)`.</span></span>  
  
 <span data-ttu-id="facc0-111">Esta técnica crea una referencia segura desde el origen de eventos al agente de escucha de eventos.</span><span class="sxs-lookup"><span data-stu-id="facc0-111">This technique creates a strong reference from the event source to the event listener.</span></span> <span data-ttu-id="facc0-112">Normalmente, al adjuntar un controlador de eventos para un agente de escucha, el agente de escucha tiene una duración de objeto que se ve afectada por la duración del objeto del origen (a menos que se quite explícitamente el controlador de eventos).</span><span class="sxs-lookup"><span data-stu-id="facc0-112">Ordinarily, attaching an event handler for a listener causes the listener to have an object lifetime that is influenced by the object lifetime of the source (unless the event handler is explicitly removed).</span></span> <span data-ttu-id="facc0-113">Pero en determinadas circunstancias, puede que desee que la duración del objeto del agente de escucha se controle por otros factores, como si actualmente pertenece al árbol visual de la aplicación, y no por la duración del origen.</span><span class="sxs-lookup"><span data-stu-id="facc0-113">But in certain circumstances, you might want the object lifetime of the listener to be controlled by other factors, such as whether it currently belongs to the visual tree of the application, and not by the lifetime of the source.</span></span> <span data-ttu-id="facc0-114">Cuando la duración del objeto de origen se extiende más allá de la duración del objeto del agente de escucha, el patrón de evento normal conduce a una fuga de memoria: el agente de escucha se mantiene activo más tiempo del previsto.</span><span class="sxs-lookup"><span data-stu-id="facc0-114">Whenever the source object lifetime extends beyond the object lifetime of the listener, the normal event pattern leads to a memory leak: the listener is kept alive longer than intended.</span></span>  
  
 <span data-ttu-id="facc0-115">El patrón de evento débil está diseñado para resolver este problema de pérdida de memoria.</span><span class="sxs-lookup"><span data-stu-id="facc0-115">The weak event pattern is designed to solve this memory leak problem.</span></span> <span data-ttu-id="facc0-116">El patrón de evento débil se puede usar siempre que un agente de escucha debe registrarse para un evento, pero el agente de escucha no sabe explícitamente Cuándo se debe anular el registro.</span><span class="sxs-lookup"><span data-stu-id="facc0-116">The weak event pattern can be used whenever a listener needs to register for an event, but the listener does not explicitly know when to unregister.</span></span> <span data-ttu-id="facc0-117">El patrón de evento débil también se puede usar cuando la duración del objeto del origen supera la duración útil del objeto del agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="facc0-117">The weak event pattern can also be used whenever the object lifetime of the source exceeds the useful object lifetime of the listener.</span></span> <span data-ttu-id="facc0-118">(En este *caso, lo* determina el usuario). El modelo de evento débil permite al agente de escucha registrarse y recibir el evento sin afectar a las características de la duración de los objetos del agente de escucha de ninguna manera.</span><span class="sxs-lookup"><span data-stu-id="facc0-118">(In this case, *useful* is determined by you.) The weak event pattern allows the listener to register for and receive the event without affecting the object lifetime characteristics of the listener in any way.</span></span> <span data-ttu-id="facc0-119">En efecto, la referencia implícita del origen no determina si el agente de escucha es válido para la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="facc0-119">In effect, the implied reference from the source does not determine whether the listener is eligible for garbage collection.</span></span> <span data-ttu-id="facc0-120">La referencia es una referencia débil, por lo tanto, la denominación del modelo de evento débil y las API relacionadas.</span><span class="sxs-lookup"><span data-stu-id="facc0-120">The reference is a weak reference, thus the naming of the weak event pattern and the related APIs.</span></span> <span data-ttu-id="facc0-121">El agente de escucha se puede recolectar o destruir de otro modo, y el origen puede continuar sin conservar las referencias de controlador no recopilables a un objeto ya destruido.</span><span class="sxs-lookup"><span data-stu-id="facc0-121">The listener can be garbage collected or otherwise destroyed, and the source can continue without retaining noncollectible handler references to a now destroyed object.</span></span>  
  
## <a name="who-should-implement-the-weak-event-pattern"></a><span data-ttu-id="facc0-122">¿Quién debe implementar el patrón de evento débil?</span><span class="sxs-lookup"><span data-stu-id="facc0-122">Who Should Implement the Weak Event Pattern?</span></span>  
 <span data-ttu-id="facc0-123">Implementar el patrón de evento débil es interesante principalmente para los autores de controles.</span><span class="sxs-lookup"><span data-stu-id="facc0-123">Implementing the weak event pattern is interesting primarily for control authors.</span></span> <span data-ttu-id="facc0-124">Como autor de un control, es principalmente responsable del comportamiento y la contención del control y el impacto que tiene en las aplicaciones en las que se inserta.</span><span class="sxs-lookup"><span data-stu-id="facc0-124">As a control author, you are largely responsible for the behavior and containment of your control and the impact it has on applications in which it is inserted.</span></span> <span data-ttu-id="facc0-125">Esto incluye el comportamiento de duración del objeto de control, en particular el control del problema de pérdida de memoria que se describe.</span><span class="sxs-lookup"><span data-stu-id="facc0-125">This includes the control object lifetime behavior, in particular the handling of the described memory leak problem.</span></span>  
  
 <span data-ttu-id="facc0-126">Ciertos escenarios se prestan de forma inherente a la aplicación del modelo de evento débil.</span><span class="sxs-lookup"><span data-stu-id="facc0-126">Certain scenarios inherently lend themselves to the application of the weak event pattern.</span></span> <span data-ttu-id="facc0-127">Uno de estos escenarios es el enlace de datos.</span><span class="sxs-lookup"><span data-stu-id="facc0-127">One such scenario is data binding.</span></span> <span data-ttu-id="facc0-128">En el enlace de datos, es habitual que el objeto de origen sea completamente independiente del objeto de agente de escucha, que es un destino de un enlace.</span><span class="sxs-lookup"><span data-stu-id="facc0-128">In data binding, it is common for the source object to be completely independent of the listener object, which is a target of a binding.</span></span> <span data-ttu-id="facc0-129">Muchos aspectos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] enlace de datos ya tienen el patrón de evento débil aplicado en cómo se implementan los eventos.</span><span class="sxs-lookup"><span data-stu-id="facc0-129">Many aspects of [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] data binding already have the weak event pattern applied in how the events are implemented.</span></span>  
  
## <a name="how-to-implement-the-weak-event-pattern"></a><span data-ttu-id="facc0-130">Cómo implementar el patrón de evento débil</span><span class="sxs-lookup"><span data-stu-id="facc0-130">How to Implement the Weak Event Pattern</span></span>  
 <span data-ttu-id="facc0-131">Hay tres maneras de implementar el patrón de evento débil.</span><span class="sxs-lookup"><span data-stu-id="facc0-131">There are three ways to implement weak event pattern.</span></span> <span data-ttu-id="facc0-132">En la tabla siguiente se enumeran los tres enfoques y se proporcionan instrucciones sobre cuándo se debe utilizar cada uno de ellos.</span><span class="sxs-lookup"><span data-stu-id="facc0-132">The following table lists the three approaches and provides some guidance for when you should use each.</span></span>  
  
|<span data-ttu-id="facc0-133">Método</span><span class="sxs-lookup"><span data-stu-id="facc0-133">Approach</span></span>|<span data-ttu-id="facc0-134">Cuándo implementar</span><span class="sxs-lookup"><span data-stu-id="facc0-134">When to Implement</span></span>|  
|--------------|-----------------------|  
|<span data-ttu-id="facc0-135">Usar una clase de administrador de eventos débiles existente</span><span class="sxs-lookup"><span data-stu-id="facc0-135">Use an existing weak event manager class</span></span>|<span data-ttu-id="facc0-136">Si el evento al que desea suscribirse tiene un <xref:System.Windows.WeakEventManager>correspondiente, use el administrador de eventos débiles existente.</span><span class="sxs-lookup"><span data-stu-id="facc0-136">If the event you want to subscribe to has a corresponding <xref:System.Windows.WeakEventManager>, use the existing weak event manager.</span></span> <span data-ttu-id="facc0-137">Para obtener una lista de los administradores de eventos débiles que se incluyen con WPF, vea la jerarquía de herencia en la clase <xref:System.Windows.WeakEventManager>.</span><span class="sxs-lookup"><span data-stu-id="facc0-137">For a list of weak event managers that are included with WPF, see the inheritance hierarchy in the <xref:System.Windows.WeakEventManager> class.</span></span> <span data-ttu-id="facc0-138">Dado que los administradores de eventos débiles incluidos están limitados, probablemente tendrá que elegir uno de los otros enfoques.</span><span class="sxs-lookup"><span data-stu-id="facc0-138">Because the included weak event managers are limited, you will probably need to choose one of the other approaches.</span></span>|  
|<span data-ttu-id="facc0-139">Usar una clase genérica de administrador de eventos débiles</span><span class="sxs-lookup"><span data-stu-id="facc0-139">Use a generic weak event manager class</span></span>|<span data-ttu-id="facc0-140">Usar una <xref:System.Windows.WeakEventManager%602> genérica cuando una <xref:System.Windows.WeakEventManager> existente no está disponible, desea una manera fácil de implementar y no le preocupa la eficacia.</span><span class="sxs-lookup"><span data-stu-id="facc0-140">Use a generic <xref:System.Windows.WeakEventManager%602> when an existing <xref:System.Windows.WeakEventManager> is not available, you want an easy way to implement, and you are not concerned about efficiency.</span></span> <span data-ttu-id="facc0-141">El <xref:System.Windows.WeakEventManager%602> genérico es menos eficaz que un administrador de eventos débil existente o personalizado.</span><span class="sxs-lookup"><span data-stu-id="facc0-141">The generic <xref:System.Windows.WeakEventManager%602> is less efficient than an existing or custom weak event manager.</span></span> <span data-ttu-id="facc0-142">Por ejemplo, la clase genérica realiza más reflexión para detectar el evento dado el nombre del evento.</span><span class="sxs-lookup"><span data-stu-id="facc0-142">For example, the generic class does more reflection to discover the event given the event's name.</span></span> <span data-ttu-id="facc0-143">Además, el código para registrar el evento mediante el <xref:System.Windows.WeakEventManager%602> genérico es más detallado que el uso de un <xref:System.Windows.WeakEventManager>existente o personalizado.</span><span class="sxs-lookup"><span data-stu-id="facc0-143">Also, the code to register the event by using the generic <xref:System.Windows.WeakEventManager%602> is more verbose than using an existing or custom <xref:System.Windows.WeakEventManager>.</span></span>|  
|<span data-ttu-id="facc0-144">Creación de una clase de administrador de eventos débiles personalizada</span><span class="sxs-lookup"><span data-stu-id="facc0-144">Create a custom weak event manager class</span></span>|<span data-ttu-id="facc0-145">Cree un <xref:System.Windows.WeakEventManager> personalizado cuando un <xref:System.Windows.WeakEventManager> existente no esté disponible y desee obtener la máxima eficacia.</span><span class="sxs-lookup"><span data-stu-id="facc0-145">Create a custom <xref:System.Windows.WeakEventManager> when an existing <xref:System.Windows.WeakEventManager> is not available and you want the best efficiency.</span></span> <span data-ttu-id="facc0-146">El uso de un <xref:System.Windows.WeakEventManager> personalizado para suscribirse a un evento será más eficaz, pero incurrirá en el costo de escribir más código al principio.</span><span class="sxs-lookup"><span data-stu-id="facc0-146">Using a custom <xref:System.Windows.WeakEventManager> to subscribe to an event will be more efficient, but you do incur the cost of writing more code at the beginning.</span></span>|  
|<span data-ttu-id="facc0-147">Usar un administrador de eventos débil de terceros</span><span class="sxs-lookup"><span data-stu-id="facc0-147">Use a third-party weak event manager</span></span>|<span data-ttu-id="facc0-148">NuGet tiene [varios administradores de eventos débiles](https://www.nuget.org/packages?q=weak+event+manager&prerel=false) y muchos marcos de WPF también admiten el patrón (por ejemplo, consulte la [documentación de Prism sobre la suscripción a eventos de acoplamiento flexible](https://github.com/PrismLibrary/Prism-Documentation/blob/master/docs/wpf/legacy/Communication.md#subscribing-to-events)).</span><span class="sxs-lookup"><span data-stu-id="facc0-148">NuGet has [several weak event managers](https://www.nuget.org/packages?q=weak+event+manager&prerel=false) and many WPF frameworks also support the pattern (for instance, see [Prism's documentation on loosely coupled event subscription](https://github.com/PrismLibrary/Prism-Documentation/blob/master/docs/wpf/legacy/Communication.md#subscribing-to-events)).</span></span>|

 <span data-ttu-id="facc0-149">En las secciones siguientes se describe cómo implementar el patrón de evento débil.</span><span class="sxs-lookup"><span data-stu-id="facc0-149">The following sections describe how to implement the weak event pattern.</span></span>  <span data-ttu-id="facc0-150">Para los fines de este debate, el evento al que se va a suscribir tiene las siguientes características.</span><span class="sxs-lookup"><span data-stu-id="facc0-150">For purposes of this discussion, the event to subscribe to has the following characteristics.</span></span>  
  
- <span data-ttu-id="facc0-151">El nombre del evento es `SomeEvent`.</span><span class="sxs-lookup"><span data-stu-id="facc0-151">The event name is `SomeEvent`.</span></span>  
  
- <span data-ttu-id="facc0-152">La clase `EventSource` genera el evento.</span><span class="sxs-lookup"><span data-stu-id="facc0-152">The event is raised by the `EventSource` class.</span></span>  
  
- <span data-ttu-id="facc0-153">El controlador de eventos tiene el tipo: `SomeEventEventHandler` (o `EventHandler<SomeEventEventArgs>`).</span><span class="sxs-lookup"><span data-stu-id="facc0-153">The event handler has type: `SomeEventEventHandler` (or `EventHandler<SomeEventEventArgs>`).</span></span>  
  
- <span data-ttu-id="facc0-154">El evento pasa un parámetro de tipo `SomeEventEventArgs` a los controladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="facc0-154">The event passes a parameter of type `SomeEventEventArgs` to the event handlers.</span></span>  
  
### <a name="using-an-existing-weak-event-manager-class"></a><span data-ttu-id="facc0-155">Usar una clase de administrador de eventos débiles existente</span><span class="sxs-lookup"><span data-stu-id="facc0-155">Using an Existing Weak Event Manager Class</span></span>  
  
1. <span data-ttu-id="facc0-156">Busque un administrador de eventos débil existente.</span><span class="sxs-lookup"><span data-stu-id="facc0-156">Find an existing weak event manager.</span></span>  
  
     <span data-ttu-id="facc0-157">Para obtener una lista de los administradores de eventos débiles que se incluyen con WPF, vea la jerarquía de herencia en la clase <xref:System.Windows.WeakEventManager>.</span><span class="sxs-lookup"><span data-stu-id="facc0-157">For a list of weak event managers that are included with WPF, see the inheritance hierarchy in the <xref:System.Windows.WeakEventManager> class.</span></span>  
  
2. <span data-ttu-id="facc0-158">Use el nuevo administrador de eventos débiles en lugar del enlace de eventos normal.</span><span class="sxs-lookup"><span data-stu-id="facc0-158">Use the new weak event manager instead of the normal event hookup.</span></span>  
  
     <span data-ttu-id="facc0-159">Por ejemplo, si el código usa el siguiente patrón para suscribirse a un evento:</span><span class="sxs-lookup"><span data-stu-id="facc0-159">For example, if your code uses the following pattern to subscribe to an event:</span></span>  
  
    ```csharp  
    source.SomeEvent += new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     <span data-ttu-id="facc0-160">Cámbielo al siguiente patrón:</span><span class="sxs-lookup"><span data-stu-id="facc0-160">Change it to the following pattern:</span></span>  
  
    ```csharp  
    SomeEventWeakEventManager.AddHandler(source, OnSomeEvent);  
    ```  
  
     <span data-ttu-id="facc0-161">Del mismo modo, si el código usa el siguiente patrón para cancelar la suscripción a un evento:</span><span class="sxs-lookup"><span data-stu-id="facc0-161">Similarly, if your code uses the following pattern to unsubscribe from an event:</span></span>  
  
    ```csharp  
    source.SomeEvent -= new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     <span data-ttu-id="facc0-162">Cámbielo al siguiente patrón:</span><span class="sxs-lookup"><span data-stu-id="facc0-162">Change it to the following pattern:</span></span>  
  
    ```csharp  
    SomeEventWeakEventManager.RemoveHandler(source, OnSomeEvent);  
    ```  
  
### <a name="using-the-generic-weak-event-manager-class"></a><span data-ttu-id="facc0-163">Usar la clase Generic Event Manager débil</span><span class="sxs-lookup"><span data-stu-id="facc0-163">Using the Generic Weak Event Manager Class</span></span>  
  
1. <span data-ttu-id="facc0-164">Use la clase <xref:System.Windows.WeakEventManager%602> genérica en lugar del enlace de eventos normal.</span><span class="sxs-lookup"><span data-stu-id="facc0-164">Use the generic <xref:System.Windows.WeakEventManager%602> class instead of the normal event hookup.</span></span>  
  
     <span data-ttu-id="facc0-165">Cuando use <xref:System.Windows.WeakEventManager%602> para registrar agentes de escucha de eventos, suministre el origen del evento y <xref:System.EventArgs> tipo como parámetros de tipo a la clase y llame a <xref:System.Windows.WeakEventManager%602.AddHandler%2A> como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="facc0-165">When you use <xref:System.Windows.WeakEventManager%602> to register event listeners, you supply the event source and <xref:System.EventArgs> type as the type parameters to the class and call <xref:System.Windows.WeakEventManager%602.AddHandler%2A> as shown in the following code:</span></span>  
  
    ```csharp  
    WeakEventManager<EventSource, SomeEventEventArgs>.AddHandler(source, "SomeEvent", source_SomeEvent);  
    ```  
  
### <a name="creating-a-custom-weak-event-manager-class"></a><span data-ttu-id="facc0-166">Creación de una clase personalizada de administrador de eventos débiles</span><span class="sxs-lookup"><span data-stu-id="facc0-166">Creating a Custom Weak Event Manager Class</span></span>  
  
1. <span data-ttu-id="facc0-167">Copie la siguiente plantilla de clase en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="facc0-167">Copy the following class template to your project.</span></span>  
  
     <span data-ttu-id="facc0-168">Esta clase hereda de la clase <xref:System.Windows.WeakEventManager>.</span><span class="sxs-lookup"><span data-stu-id="facc0-168">This class inherits from the <xref:System.Windows.WeakEventManager> class.</span></span>  
  
     [!code-csharp[WeakEvents#WeakEventManagerTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/WeakEvents/CSharp/WeakEventManagerTemplate.cs#weakeventmanagertemplate)]  
  
2. <span data-ttu-id="facc0-169">Reemplace el nombre del `SomeEventWeakEventManager` por su propio nombre.</span><span class="sxs-lookup"><span data-stu-id="facc0-169">Replace the `SomeEventWeakEventManager` name with your own name.</span></span>  
  
3. <span data-ttu-id="facc0-170">Reemplace los tres nombres descritos anteriormente con los nombres correspondientes del evento.</span><span class="sxs-lookup"><span data-stu-id="facc0-170">Replace the three names described previously with the corresponding names for your event.</span></span> <span data-ttu-id="facc0-171">(`SomeEvent`, `EventSource`y `SomeEventEventArgs`)</span><span class="sxs-lookup"><span data-stu-id="facc0-171">(`SomeEvent`, `EventSource`, and `SomeEventEventArgs`)</span></span>  
  
4. <span data-ttu-id="facc0-172">Establezca la visibilidad (pública/interna/privada) de la clase débil de Event Manager en la misma visibilidad que el evento que administra.</span><span class="sxs-lookup"><span data-stu-id="facc0-172">Set the visibility (public / internal / private) of the weak event manager class to the same visibility as event it manages.</span></span>  
  
5. <span data-ttu-id="facc0-173">Use el nuevo administrador de eventos débiles en lugar del enlace de eventos normal.</span><span class="sxs-lookup"><span data-stu-id="facc0-173">Use the new weak event manager instead of the normal event hookup.</span></span>  
  
     <span data-ttu-id="facc0-174">Por ejemplo, si el código usa el siguiente patrón para suscribirse a un evento:</span><span class="sxs-lookup"><span data-stu-id="facc0-174">For example, if your code uses the following pattern to subscribe to an event:</span></span>  
  
    ```csharp  
    source.SomeEvent += new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     <span data-ttu-id="facc0-175">Cámbielo al siguiente patrón:</span><span class="sxs-lookup"><span data-stu-id="facc0-175">Change it to the following pattern:</span></span>  
  
    ```csharp  
    SomeEventWeakEventManager.AddHandler(source, OnSomeEvent);  
    ```  
  
     <span data-ttu-id="facc0-176">Del mismo modo, si el código usa el siguiente patrón para cancelar la suscripción a un evento:</span><span class="sxs-lookup"><span data-stu-id="facc0-176">Similarly, if your code uses the following pattern to unsubscribe to an event:</span></span>  
  
    ```csharp  
    source.SomeEvent -= new SomeEventEventHandler(OnSome);  
    ```  
  
     <span data-ttu-id="facc0-177">Cámbielo al siguiente patrón:</span><span class="sxs-lookup"><span data-stu-id="facc0-177">Change it to the following pattern:</span></span>  
  
    ```csharp  
    SomeEventWeakEventManager.RemoveHandler(source, OnSomeEvent);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="facc0-178">Vea también</span><span class="sxs-lookup"><span data-stu-id="facc0-178">See also</span></span>

- <xref:System.Windows.WeakEventManager>
- <xref:System.Windows.IWeakEventListener>
- [<span data-ttu-id="facc0-179">Información general sobre eventos enrutados</span><span class="sxs-lookup"><span data-stu-id="facc0-179">Routed Events Overview</span></span>](routed-events-overview.md)
- [<span data-ttu-id="facc0-180">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="facc0-180">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
