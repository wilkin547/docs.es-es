---
description: Más información acerca de la inicialización de instancias
title: Creación de instancias de inicialización
ms.date: 03/30/2017
ms.assetid: 154d049f-2140-4696-b494-c7e53f6775ef
ms.openlocfilehash: 056f867012667abaf046827a7c6295f83d4794f3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99726525"
---
# <a name="instancing-initialization"></a><span data-ttu-id="825e0-103">Creación de instancias de inicialización</span><span class="sxs-lookup"><span data-stu-id="825e0-103">Instancing Initialization</span></span>

<span data-ttu-id="825e0-104">Este ejemplo extiende el ejemplo de [agrupación](pooling.md) definiendo una interfaz, `IObjectControl` , que personaliza la inicialización de un objeto mediante su activación y desactivación.</span><span class="sxs-lookup"><span data-stu-id="825e0-104">This sample extends the [Pooling](pooling.md) sample by defining an interface, `IObjectControl`, which customizes the initialization of an object by activating and deactivating it.</span></span> <span data-ttu-id="825e0-105">El cliente invoca métodos que devuelven el objeto al grupo y que no devuelven el objeto al grupo.</span><span class="sxs-lookup"><span data-stu-id="825e0-105">The client invokes methods that return the object to the pool and that do not return the object to the pool.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="825e0-106">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="825e0-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
## <a name="extensibility-points"></a><span data-ttu-id="825e0-107">Puntos de extensibilidad</span><span class="sxs-lookup"><span data-stu-id="825e0-107">Extensibility Points</span></span>  

 <span data-ttu-id="825e0-108">El primer paso para crear una extensión de Windows Communication Foundation (WCF) es decidir el punto de extensibilidad que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="825e0-108">The first step in creating a Windows Communication Foundation (WCF) extension is to decide the extensibility point to use.</span></span> <span data-ttu-id="825e0-109">En WCF, el término *EndpointDispatcher* hace referencia a un componente de tiempo de ejecución responsable de convertir los mensajes entrantes en invocaciones de método en el servicio del usuario y de convertir los valores devueltos de ese método en un mensaje saliente.</span><span class="sxs-lookup"><span data-stu-id="825e0-109">In WCF, the term *EndpointDispatcher* refers to a run-time component responsible for converting incoming messages into method invocations on the user’s service and for converting return values from that method to an outgoing message.</span></span> <span data-ttu-id="825e0-110">Un servicio WCF crea un EndpointDispatcher para cada punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="825e0-110">A WCF service creates an EndpointDispatcher for each endpoint.</span></span>  
  
 <span data-ttu-id="825e0-111">EndpointDispatcher proporciona la extensibilidad (para todos los mensajes recibidos o enviados por el servicio) del ámbito del extremo mediante la clase <xref:System.ServiceModel.Dispatcher.EndpointDispatcher>.</span><span class="sxs-lookup"><span data-stu-id="825e0-111">The EndpointDispatcher offers endpoint scope (for all messages received or sent by the service) extensibility using the <xref:System.ServiceModel.Dispatcher.EndpointDispatcher> class.</span></span> <span data-ttu-id="825e0-112">Esta clase le permite personalizar varias propiedades que controlan el comportamiento de EndpointDispatcher.</span><span class="sxs-lookup"><span data-stu-id="825e0-112">This class allows you to customize various properties that control the behavior of the EndpointDispatcher.</span></span> <span data-ttu-id="825e0-113">Este ejemplo se centra en la propiedad <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceProvider%2A> que señala al objeto que proporciona las instancias de la clase de servicio.</span><span class="sxs-lookup"><span data-stu-id="825e0-113">This sample focuses on the <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceProvider%2A> property that points to the object that provides the instances of the service class.</span></span>  
  
## <a name="iinstanceprovider"></a><span data-ttu-id="825e0-114">IInstanceProvider</span><span class="sxs-lookup"><span data-stu-id="825e0-114">IInstanceProvider</span></span>  

 <span data-ttu-id="825e0-115">En WCF, EndpointDispatcher crea instancias de una clase de servicio mediante un proveedor de instancias que implementa la <xref:System.ServiceModel.Dispatcher.IInstanceProvider> interfaz.</span><span class="sxs-lookup"><span data-stu-id="825e0-115">In WCF, the EndpointDispatcher creates instances of a service class by using an instance provider that implements the <xref:System.ServiceModel.Dispatcher.IInstanceProvider> interface.</span></span> <span data-ttu-id="825e0-116">Esta interfaz tiene solo dos métodos:</span><span class="sxs-lookup"><span data-stu-id="825e0-116">This interface has only two methods:</span></span>  
  
- <span data-ttu-id="825e0-117"><xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A>: cuando un mensaje llega, el distribuidor llama al método <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A> para crear una instancia de la clase de servicio para procesar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="825e0-117"><xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A>: When a message arrives, the Dispatcher calls the <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A> method to create an instance of the service class to process the message.</span></span> <span data-ttu-id="825e0-118">La propiedad <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> determina la frecuencia de las llamadas a este método.</span><span class="sxs-lookup"><span data-stu-id="825e0-118">The frequency of the calls to this method is determined by the <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> property.</span></span> <span data-ttu-id="825e0-119">Por ejemplo, si la propiedad <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> está establecida en <xref:System.ServiceModel.InstanceContextMode.PerCall?displayProperty=nameWithType>, se crea una nueva instancia de la clase de servicio para procesar cada mensaje que llega, por lo que se llamará a <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A> siempre que llegue un mensaje.</span><span class="sxs-lookup"><span data-stu-id="825e0-119">For example if the <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> property is set to <xref:System.ServiceModel.InstanceContextMode.PerCall?displayProperty=nameWithType>, a new instance of service class is created to process each message that arrives, so <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A> is called whenever a message arrives.</span></span>  
  
- <span data-ttu-id="825e0-120"><xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A>: cuando la instancia del servicio termina de procesar el mensaje, EndpointDispatcher llama al método <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A>.</span><span class="sxs-lookup"><span data-stu-id="825e0-120"><xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A>: When the service instance finishes processing the message, the EndpointDispatcher calls the <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A> method.</span></span> <span data-ttu-id="825e0-121">Tal y como ocurre en el método <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A>, la frecuencia de las llamadas a este método está determinada por la propiedad <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="825e0-121">As in the <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A> method, the frequency of the calls to this method is determined by the <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> property.</span></span>  
  
## <a name="the-object-pool"></a><span data-ttu-id="825e0-122">Agrupación de objetos</span><span class="sxs-lookup"><span data-stu-id="825e0-122">The Object Pool</span></span>  

 <span data-ttu-id="825e0-123">La clase `ObjectPoolInstanceProvider` contiene la implementación para el grupo de objetos.</span><span class="sxs-lookup"><span data-stu-id="825e0-123">The `ObjectPoolInstanceProvider` class contains the implementation for the object pool.</span></span> <span data-ttu-id="825e0-124">Esta clase implementa la interfaz <xref:System.ServiceModel.Dispatcher.IInstanceProvider> para interactuar con el nivel de modelo de servicio.</span><span class="sxs-lookup"><span data-stu-id="825e0-124">This class implements the <xref:System.ServiceModel.Dispatcher.IInstanceProvider> interface to interact with the service model layer.</span></span> <span data-ttu-id="825e0-125">Cuando EndpointDispatcher llama al método <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A>, en lugar de crear una nueva instancia, la implementación personalizada busca un objeto existente en un grupo en memoria.</span><span class="sxs-lookup"><span data-stu-id="825e0-125">When the EndpointDispatcher calls the <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A> method, instead of creating a new instance, the custom implementation looks for an existing object in an in-memory pool.</span></span> <span data-ttu-id="825e0-126">Si hay uno disponible, se devuelve.</span><span class="sxs-lookup"><span data-stu-id="825e0-126">If one is available, it is returned.</span></span> <span data-ttu-id="825e0-127">De lo contrario, `ObjectPoolInstanceProvider` comprueba si la propiedad `ActiveObjectsCount` (número de objetos devueltos desde el grupo) ha alcanzado el tamaño máximo del grupo.</span><span class="sxs-lookup"><span data-stu-id="825e0-127">Otherwise, `ObjectPoolInstanceProvider` checks whether the `ActiveObjectsCount` property (number of objects returned from the pool) has reached the maximum pool size.</span></span> <span data-ttu-id="825e0-128">Si no, se crea una nueva instancia y se devuelve al autor de la llamada y, como consecuencia, se incrementa `ActiveObjectsCount`.</span><span class="sxs-lookup"><span data-stu-id="825e0-128">If not, a new instance is created and returned to the caller and `ActiveObjectsCount` is subsequently incremented.</span></span> <span data-ttu-id="825e0-129">De lo contrario, se pone en la cola una solicitud de creación de objetos para un período configurado de tiempo.</span><span class="sxs-lookup"><span data-stu-id="825e0-129">Otherwise an object creation request is queued for a configured period of time.</span></span> <span data-ttu-id="825e0-130">Se muestra la implementación para `GetObjectFromThePool` en el código de ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="825e0-130">The implementation for `GetObjectFromThePool` is shown in the following sample code.</span></span>  
  
```csharp
private object GetObjectFromThePool()  
{  
    bool didNotTimeout =
       availableCount.WaitOne(creationTimeout, true);  
    if(didNotTimeout)  
    {  
         object obj = null;  
         lock (poolLock)  
        {  
             if (pool.Count != 0)  
             {  
                   obj = pool.Pop();  
                   activeObjectsCount++;  
             }  
             else if (pool.Count == 0)  
             {  
                   if (activeObjectsCount < maxPoolSize)  
                   {  
                        obj = CreateNewPoolObject();  
                        activeObjectsCount++;  
  
                        #if (DEBUG)  
                        WritePoolMessage(  
                             ResourceHelper.GetString("MsgNewObject"));  
                       #endif  
                   }
            }  
           idleTimer.Stop();  
      }  
     // Call the Activate method if possible.  
    if (obj is IObjectControl)  
   {  
         ((IObjectControl)obj).Activate();  
   }  
   return obj;  
}  
throw new TimeoutException(  
ResourceHelper.GetString("ExObjectCreationTimeout"));  
}  
```  
  
 <span data-ttu-id="825e0-131">La implementación `ReleaseInstance` personalizada agrega la instancia liberada de nuevo al grupo y disminuye el valor de `ActiveObjectsCount`.</span><span class="sxs-lookup"><span data-stu-id="825e0-131">The custom `ReleaseInstance` implementation adds the released instance back to the pool and decrements the `ActiveObjectsCount` value.</span></span> <span data-ttu-id="825e0-132">EndpointDispatcher puede llamar a estos métodos desde subprocesos diferentes y, por consiguiente, se necesita tener acceso sincronizado a los miembros de nivel de clase en la clase `ObjectPoolInstanceProvider`.</span><span class="sxs-lookup"><span data-stu-id="825e0-132">The EndpointDispatcher can call these methods from different threads, and therefore synchronized access to the class level members in the `ObjectPoolInstanceProvider` class is required.</span></span>  
  
```csharp
public void ReleaseInstance(InstanceContext instanceContext, object instance)  
{  
    lock (poolLock)  
    {  
        // Check whether the object can be pooled.
        // Call the Deactivate method if possible.  
        if (instance is IObjectControl)  
        {  
            IObjectControl objectControl = (IObjectControl)instance;  
            objectControl.Deactivate();  
  
            if (objectControl.CanBePooled)  
            {  
                pool.Push(instance);  
  
                #if(DEBUG)  
                WritePoolMessage(  
                    ResourceHelper.GetString("MsgObjectPooled"));  
                #endif
            }  
            else  
            {  
                #if(DEBUG)  
                WritePoolMessage(  
                    ResourceHelper.GetString("MsgObjectWasNotPooled"));  
                #endif  
            }  
        }  
        else  
        {  
            pool.Push(instance);  
  
            #if(DEBUG)  
            WritePoolMessage(  
                ResourceHelper.GetString("MsgObjectPooled"));  
            #endif
        }  
  
        activeObjectsCount--;  
  
        if (activeObjectsCount == 0)  
        {  
            idleTimer.Start();
        }  
    }  
  
    availableCount.Release(1);  
}  
```  
  
 <span data-ttu-id="825e0-133">El `ReleaseInstance` método proporciona una característica de *inicialización de limpieza* .</span><span class="sxs-lookup"><span data-stu-id="825e0-133">The `ReleaseInstance` method provides a *clean up initialization* feature.</span></span> <span data-ttu-id="825e0-134">Normalmente el grupo mantiene un número mínimo de objetos para la duración del grupo.</span><span class="sxs-lookup"><span data-stu-id="825e0-134">Normally the pool maintains a minimum number of objects for the lifetime of the pool.</span></span> <span data-ttu-id="825e0-135">Sin embargo, puede haber períodos de uso excesivo que requieren la creación de objetos adicionales en el grupo para alcanzar el límite máximo especificado en la configuración.</span><span class="sxs-lookup"><span data-stu-id="825e0-135">However, there can be periods of excessive usage that require creating additional objects in the pool to reach the maximum limit specified in the configuration.</span></span> <span data-ttu-id="825e0-136">Finalmente, cuando el grupo se vuelve menos activo, esos objetos adicionales pueden suponer una sobrecarga adicional.</span><span class="sxs-lookup"><span data-stu-id="825e0-136">Eventually when the pool becomes less active those surplus objects can become an extra overhead.</span></span> <span data-ttu-id="825e0-137">Por consiguiente, cuando `activeObjectsCount` llega a cero, se inicia un temporizador inactivo que activa y realiza un ciclo de limpieza.</span><span class="sxs-lookup"><span data-stu-id="825e0-137">Therefore when the `activeObjectsCount` reaches zero an idle timer is started that triggers and performs a clean-up cycle.</span></span>  
  
```csharp  
if (activeObjectsCount == 0)  
{  
    idleTimer.Start();
}  
```  
  
 <span data-ttu-id="825e0-138">Las extensiones de nivel de ServiceModel se enlazan utilizando los comportamientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="825e0-138">ServiceModel layer extensions are hooked up using the following behaviors:</span></span>  
  
- <span data-ttu-id="825e0-139">Comportamientos del servicio: permiten la personalización del tiempo de ejecución completo del servicio.</span><span class="sxs-lookup"><span data-stu-id="825e0-139">Service Behaviors: These allow for the customization of the entire service runtime.</span></span>  
  
- <span data-ttu-id="825e0-140">Comportamientos del punto de conexión: permiten la personalización de un punto de conexión de servicio determinado, incluido EndpointDispatcher.</span><span class="sxs-lookup"><span data-stu-id="825e0-140">Endpoint Behaviors: These allow for the customization of a particular service endpoint, including the EndpointDispatcher.</span></span>  
  
- <span data-ttu-id="825e0-141">Comportamientos del contrato: permiten la personalización de las clases <xref:System.ServiceModel.Dispatcher.ClientRuntime> o <xref:System.ServiceModel.Dispatcher.DispatchRuntime> en el cliente o el servicio respectivamente.</span><span class="sxs-lookup"><span data-stu-id="825e0-141">Contract Behaviors: These allow for the customization of either <xref:System.ServiceModel.Dispatcher.ClientRuntime> or <xref:System.ServiceModel.Dispatcher.DispatchRuntime> classes on the client or the service respectively.</span></span>  
  
- <span data-ttu-id="825e0-142">Comportamientos de la operación: permiten la personalización de las clases <xref:System.ServiceModel.Dispatcher.ClientOperation> o <xref:System.ServiceModel.Dispatcher.DispatchOperation> en el cliente o el servicio respectivamente.</span><span class="sxs-lookup"><span data-stu-id="825e0-142">Operation Behaviors: These allow for the customization of either <xref:System.ServiceModel.Dispatcher.ClientOperation> or <xref:System.ServiceModel.Dispatcher.DispatchOperation> classes on the client or the service respectively.</span></span>  
  
 <span data-ttu-id="825e0-143">Con el objetivo de una extensión de agrupación de objetos, se puede crear un comportamiento de punto de conexión o de servicio.</span><span class="sxs-lookup"><span data-stu-id="825e0-143">For the purpose of an object pooling extension, either an endpoint behavior or a service behavior can be created.</span></span> <span data-ttu-id="825e0-144">En este ejemplo, utilizamos un comportamiento de servicio, que aplica la capacidad de agrupación de objetos a cada punto de conexión del servicio.</span><span class="sxs-lookup"><span data-stu-id="825e0-144">In this example, we use a service behavior, which applies object pooling ability to every endpoint of the service.</span></span> <span data-ttu-id="825e0-145">Los comportamientos de servicio se crean implementando la interfaz <xref:System.ServiceModel.Description.IServiceBehavior>.</span><span class="sxs-lookup"><span data-stu-id="825e0-145">Service behaviors are created by implementing the <xref:System.ServiceModel.Description.IServiceBehavior> interface.</span></span> <span data-ttu-id="825e0-146">Hay varias maneras de hacer que ServiceModel sea consciente de los comportamientos personalizados:</span><span class="sxs-lookup"><span data-stu-id="825e0-146">There are several ways to make the ServiceModel aware of the custom behaviors:</span></span>  
  
- <span data-ttu-id="825e0-147">Utilizar un atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="825e0-147">Using a custom attribute.</span></span>  
  
- <span data-ttu-id="825e0-148">Agregarlo de manera imperativa a la colección de comportamientos de la descripción del servicio.</span><span class="sxs-lookup"><span data-stu-id="825e0-148">Imperatively adding it to the service description’s behaviors collection.</span></span>  
  
- <span data-ttu-id="825e0-149">Extender el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="825e0-149">Extending the configuration file.</span></span>  
  
 <span data-ttu-id="825e0-150">Este ejemplo utiliza un atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="825e0-150">This sample uses a custom attribute.</span></span> <span data-ttu-id="825e0-151">Cuando se construye <xref:System.ServiceModel.ServiceHost>, examina los atributos utilizados en la definición de tipo del servicio y agrega los comportamientos disponibles a la colección de comportamientos de la descripción del servicio.</span><span class="sxs-lookup"><span data-stu-id="825e0-151">When the <xref:System.ServiceModel.ServiceHost> is constructed, it examines the attributes used in the service’s type definition and adds the available behaviors to the service description’s behaviors collection.</span></span>  
  
 <span data-ttu-id="825e0-152">La <xref:System.ServiceModel.Description.IServiceBehavior> interfaz tiene tres métodos: <xref:System.ServiceModel.Description.IServiceBehavior.Validate%2A> `,` <xref:System.ServiceModel.Description.IServiceBehavior.AddBindingParameters%2A> `,` y <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A> .</span><span class="sxs-lookup"><span data-stu-id="825e0-152">The <xref:System.ServiceModel.Description.IServiceBehavior> interface has three methods: <xref:System.ServiceModel.Description.IServiceBehavior.Validate%2A>`,` <xref:System.ServiceModel.Description.IServiceBehavior.AddBindingParameters%2A>`,` and <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A>.</span></span> <span data-ttu-id="825e0-153">WCF llama a estos métodos cuando <xref:System.ServiceModel.ServiceHost> se inicializa.</span><span class="sxs-lookup"><span data-stu-id="825e0-153">These methods are called by WCF when the <xref:System.ServiceModel.ServiceHost> is being initialized.</span></span> <span data-ttu-id="825e0-154">Primero se llama a <xref:System.ServiceModel.Description.IServiceBehavior.Validate%2A?displayProperty=nameWithType>; permite inspeccionar el servicio para ver si hay incoherencias.</span><span class="sxs-lookup"><span data-stu-id="825e0-154"><xref:System.ServiceModel.Description.IServiceBehavior.Validate%2A?displayProperty=nameWithType> is called first; it allows the service to be inspected for inconsistencies.</span></span> <span data-ttu-id="825e0-155">Después se llama a <xref:System.ServiceModel.Description.IServiceBehavior.AddBindingParameters%2A?displayProperty=nameWithType>; este método solo se necesita en escenarios muy avanzados.</span><span class="sxs-lookup"><span data-stu-id="825e0-155"><xref:System.ServiceModel.Description.IServiceBehavior.AddBindingParameters%2A?displayProperty=nameWithType> is called next; this method is only required in very advanced scenarios.</span></span> <span data-ttu-id="825e0-156">En último lugar se llama a <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A?displayProperty=nameWithType>, que es responsable de configurar el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="825e0-156"><xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A?displayProperty=nameWithType> is called last and is responsible for configuring the runtime.</span></span> <span data-ttu-id="825e0-157">Los parámetros siguientes se pasan a <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="825e0-157">The following parameters are passed into <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A?displayProperty=nameWithType>:</span></span>  
  
- <span data-ttu-id="825e0-158">`Description`: este parámetro proporciona la descripción del servicio para todo el servicio.</span><span class="sxs-lookup"><span data-stu-id="825e0-158">`Description`: This parameter provides the service description for the entire service.</span></span> <span data-ttu-id="825e0-159">Esto se puede utilizar para inspeccionar los datos de la descripción sobre los extremos del servicio, los contratos, enlaces y otros datos asociados al servicio.</span><span class="sxs-lookup"><span data-stu-id="825e0-159">This can be used to inspect description data about the service’s endpoints, contracts, bindings, and other data associated with the service.</span></span>  
  
- <span data-ttu-id="825e0-160">`ServiceHostBase`: este parámetro proporciona <xref:System.ServiceModel.ServiceHostBase> que se inicializa actualmente.</span><span class="sxs-lookup"><span data-stu-id="825e0-160">`ServiceHostBase`: This parameter provides the <xref:System.ServiceModel.ServiceHostBase> that is currently being initialized.</span></span>  
  
 <span data-ttu-id="825e0-161">En la implementación <xref:System.ServiceModel.Description.IServiceBehavior> personalizada, se crea una nueva instancia de `ObjectPoolInstanceProvider` y se asigna a la propiedad <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceProvider%2A> en cada <xref:System.ServiceModel.Dispatcher.EndpointDispatcher> que está adjuntada a <xref:System.ServiceModel.ServiceHostBase>.</span><span class="sxs-lookup"><span data-stu-id="825e0-161">In the custom <xref:System.ServiceModel.Description.IServiceBehavior> implementation, a new instance of `ObjectPoolInstanceProvider` is instantiated and assigned to the <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceProvider%2A> property in each <xref:System.ServiceModel.Dispatcher.EndpointDispatcher> that is attached to the <xref:System.ServiceModel.ServiceHostBase>.</span></span>  
  
```csharp
public void ApplyDispatchBehavior(ServiceDescription description, ServiceHostBase serviceHostBase)  
{  
    if (enabled)  
    {  
        // Create an instance of the ObjectPoolInstanceProvider.  
        instanceProvider = new ObjectPoolInstanceProvider(description.ServiceType,  
        maxPoolSize, minPoolSize, creationTimeout);  
  
        // Assign our instance provider to Dispatch behavior in each
        // endpoint.  
        foreach (ChannelDispatcherBase cdb in serviceHostBase.ChannelDispatchers)  
        {  
             ChannelDispatcher cd = cdb as ChannelDispatcher;  
             if (cd != null)  
             {  
                 foreach (EndpointDispatcher ed in cd.Endpoints)  
                 {  
                        ed.DispatchRuntime.InstanceProvider = instanceProvider;  
                 }  
             }  
         }  
     }  
}
```  
  
 <span data-ttu-id="825e0-162">Además de una implementación <xref:System.ServiceModel.Description.IServiceBehavior>, la clase `ObjectPoolingAttribute` cuenta con varios miembros para personalizar el grupo de objetos mediante los argumentos de atributo.</span><span class="sxs-lookup"><span data-stu-id="825e0-162">In addition to an <xref:System.ServiceModel.Description.IServiceBehavior> implementation the `ObjectPoolingAttribute` class has several members to customize the object pool using the attribute arguments.</span></span> <span data-ttu-id="825e0-163">Estos miembros incluyen `MaxSize`, `MinSize`, `Enabled` y `CreationTimeout`, para que coincida con el conjunto de características de agrupación de objetos proporcionada por .NET Enterprise Services.</span><span class="sxs-lookup"><span data-stu-id="825e0-163">These members include `MaxSize`, `MinSize`, `Enabled` and `CreationTimeout`, to match the object pooling feature set provided by .NET Enterprise Services.</span></span>  
  
 <span data-ttu-id="825e0-164">El comportamiento de la agrupación de objetos se puede Agregar ahora a un servicio WCF mediante la anotación de la implementación del servicio con el atributo personalizado que se acaba de crear `ObjectPooling` .</span><span class="sxs-lookup"><span data-stu-id="825e0-164">The object pooling behavior can now be added to a WCF service by annotating the service implementation with the newly created custom `ObjectPooling` attribute.</span></span>  
  
```csharp  
[ObjectPooling(MaxSize=1024, MinSize=10, CreationTimeout=30000]
public class PoolService : IPoolService  
{  
  // …  
}  
```  
  
## <a name="hooking-activation-and-deactivation"></a><span data-ttu-id="825e0-165">Activación y desactivación de enlace</span><span class="sxs-lookup"><span data-stu-id="825e0-165">Hooking Activation and Deactivation</span></span>  

 <span data-ttu-id="825e0-166">El objetivo principal de la agrupación de objetos es optimizar los objetos de corta duración con una creación e inicialización relativamente cara.</span><span class="sxs-lookup"><span data-stu-id="825e0-166">The primary objective of object pooling is to optimize short-lived objects with relatively expensive creation and initialization.</span></span> <span data-ttu-id="825e0-167">Por consiguiente, puede aumentar considerablemente el rendimiento de una aplicación si se utiliza correctamente.</span><span class="sxs-lookup"><span data-stu-id="825e0-167">Therefore it can give a dramatic performance boost to an application if properly used.</span></span> <span data-ttu-id="825e0-168">Dado que el objeto se devuelve desde el grupo, al constructor se llama solo una vez.</span><span class="sxs-lookup"><span data-stu-id="825e0-168">Because the object is returned from the pool, the constructor is called only once.</span></span> <span data-ttu-id="825e0-169">Sin embargo, algunas aplicaciones requieren cierto nivel de control para que puedan inicializar y limpiar los recursos utilizados durante un contexto único.</span><span class="sxs-lookup"><span data-stu-id="825e0-169">However, some applications require some level of control so that they can initialize and clean-up the resources used during a single context.</span></span> <span data-ttu-id="825e0-170">Por ejemplo, un objeto que está siendo utilizado por un conjunto de cálculos puede restablecer los campos privados antes de procesar el cálculo siguiente.</span><span class="sxs-lookup"><span data-stu-id="825e0-170">For example, an object being used for a set of calculations can reset its private fields before processing the next calculation.</span></span> <span data-ttu-id="825e0-171">Enterprise Services habilitó este tipo de inicialización específica del contexto permitiendo al desarrollador de objetos invalidar los métodos `Activate` y `Deactivate` de la clase base <xref:System.EnterpriseServices.ServicedComponent>.</span><span class="sxs-lookup"><span data-stu-id="825e0-171">Enterprise Services enabled this kind of context-specific initialization by letting the object developer override `Activate` and `Deactivate` methods from the <xref:System.EnterpriseServices.ServicedComponent> base class.</span></span>  
  
 <span data-ttu-id="825e0-172">El conjunto de objetos llama al método `Activate` justo antes de devolver el objeto.</span><span class="sxs-lookup"><span data-stu-id="825e0-172">The object pool calls the `Activate` method just before returning the object from the pool.</span></span> <span data-ttu-id="825e0-173">Se llama a `Deactivate` cuando el objeto vuelve al conjunto.</span><span class="sxs-lookup"><span data-stu-id="825e0-173">`Deactivate` is called when the object returns back to the pool.</span></span> <span data-ttu-id="825e0-174">La clase base <xref:System.EnterpriseServices.ServicedComponent> también tiene una propiedad `boolean` llamada `CanBePooled`, que se puede utilizar para notificar al grupo si el objeto puede agruparse más adelante.</span><span class="sxs-lookup"><span data-stu-id="825e0-174">The <xref:System.EnterpriseServices.ServicedComponent> base class also has a `boolean` property called `CanBePooled`, which can be used to notify the pool whether the object can be pooled further.</span></span>  
  
 <span data-ttu-id="825e0-175">Para imitar esta funcionalidad, el ejemplo declara una interfaz pública (`IObjectControl`) que tiene los miembros mencionados anteriormente.</span><span class="sxs-lookup"><span data-stu-id="825e0-175">To mimic this functionality, the sample declares a public interface (`IObjectControl`) that has the aforementioned members.</span></span> <span data-ttu-id="825e0-176">Las clases de servicio implementan esta interfaz con objeto de proporcionar inicialización específica de contexto.</span><span class="sxs-lookup"><span data-stu-id="825e0-176">This interface is then implemented by service classes intended to provide context specific initialization.</span></span> <span data-ttu-id="825e0-177">Se debe modificar la implementación <xref:System.ServiceModel.Dispatcher.IInstanceProvider> para cumplir estos requisitos.</span><span class="sxs-lookup"><span data-stu-id="825e0-177">The <xref:System.ServiceModel.Dispatcher.IInstanceProvider> implementation must be modified to meet these requirements.</span></span> <span data-ttu-id="825e0-178">Ahora, cada vez que obtenga un objeto llamando al `GetInstance` método, debe comprobar si el objeto implementa `IObjectControl.` si lo hace, debe llamar al `Activate` método adecuadamente.</span><span class="sxs-lookup"><span data-stu-id="825e0-178">Now, each time you get an object by calling the `GetInstance` method, you must check whether the object implements `IObjectControl.` If it does, you must call the `Activate` method appropriately.</span></span>  
  
```csharp  
if (obj is IObjectControl)  
{  
    ((IObjectControl)obj).Activate();  
}  
```  
  
 <span data-ttu-id="825e0-179">Al devolver un objeto al grupo, se requiere una comprobación para la propiedad `CanBePooled` antes de volver a agregar el objeto al grupo.</span><span class="sxs-lookup"><span data-stu-id="825e0-179">When returning an object to the pool, a check is required for the `CanBePooled` property before adding the object back to the pool.</span></span>  
  
```csharp  
if (instance is IObjectControl)  
{  
    IObjectControl objectControl = (IObjectControl)instance;  
    objectControl.Deactivate();  
    if (objectControl.CanBePooled)  
    {  
       pool.Push(instance);  
    }  
}  
```  
  
 <span data-ttu-id="825e0-180">Dado que el programador del servicio puede decidir si se puede agrupar un objeto, el recuento de objetos en el grupo a una hora determinada puede estar por debajo del tamaño mínimo.</span><span class="sxs-lookup"><span data-stu-id="825e0-180">Because the service developer can decide whether an object can be pooled, the object count in the pool at a given time can go below the minimum size.</span></span> <span data-ttu-id="825e0-181">Por consiguiente, debe comprobar si el recuento de objetos ha caído por debajo del nivel mínimo y realizar la inicialización necesaria en el procedimiento de limpieza.</span><span class="sxs-lookup"><span data-stu-id="825e0-181">Therefore you must check whether the object count has gone below the minimum level and perform the necessary initialization in the clean-up procedure.</span></span>  
  
```csharp  
// Remove the surplus objects.  
if (pool.Count > minPoolSize)  
{  
  // Clean the surplus objects.  
}
else if (pool.Count < minPoolSize)  
{  
  // Reinitialize the missing objects.  
  while(pool.Count != minPoolSize)  
  {  
    pool.Push(CreateNewPoolObject());  
  }  
}  
```  
  
 <span data-ttu-id="825e0-182">Al ejecutar el ejemplo, las solicitudes y las respuestas de operación se muestran tanto en la ventanas de la consola del cliente como del servicio.</span><span class="sxs-lookup"><span data-stu-id="825e0-182">When you run the sample, the operation requests and responses are displayed in both the service and client console windows.</span></span> <span data-ttu-id="825e0-183">Presione ENTRAR en cada ventana de la consola para cerrar el servicio y el cliente.</span><span class="sxs-lookup"><span data-stu-id="825e0-183">Press Enter in each console window to shut down the service and client.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="825e0-184">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="825e0-184">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="825e0-185">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="825e0-185">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="825e0-186">Para compilar la solución, siga las instrucciones de [creación de los ejemplos de Windows Communication Foundation](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="825e0-186">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="825e0-187">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="825e0-187">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="825e0-188">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="825e0-188">The samples may already be installed on your machine.</span></span> <span data-ttu-id="825e0-189">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="825e0-189">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="825e0-190">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="825e0-190">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="825e0-191">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="825e0-191">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Instancing\Initialization`  
