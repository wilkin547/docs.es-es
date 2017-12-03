---
title: Vigencia personalizada
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 52806c07-b91c-48fe-b992-88a41924f51f
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2538a9c483b949dfef1c60bd2225f5daf4e01117
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="custom-lifetime"></a><span data-ttu-id="7056c-102">Vigencia personalizada</span><span class="sxs-lookup"><span data-stu-id="7056c-102">Custom Lifetime</span></span>
<span data-ttu-id="7056c-103">En este ejemplo se muestra cómo escribir una extensión de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] para proporcionar servicios de duración personalizados para las instancias de servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] compartidas.</span><span class="sxs-lookup"><span data-stu-id="7056c-103">This sample demonstrates how to write a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] extension to provide custom lifetime services for shared [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service instances.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7056c-104">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="7056c-104">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
## <a name="shared-instancing"></a><span data-ttu-id="7056c-105">Creación de instancias compartidas</span><span class="sxs-lookup"><span data-stu-id="7056c-105">Shared Instancing</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="7056c-106"> proporciona varios modos de creación de instancias para las instancias de servicio.</span><span class="sxs-lookup"><span data-stu-id="7056c-106"> offers several instancing modes for your service instances.</span></span> <span data-ttu-id="7056c-107">El modo Creación de instancias compartidas que se explica en este tema proporciona una manera de compartir una instancia de servicio entre varios canales.</span><span class="sxs-lookup"><span data-stu-id="7056c-107">The Shared Instancing mode covered in this topic provides a way to share a service instance between multiple channels.</span></span> <span data-ttu-id="7056c-108">Los clientes pueden resolver la dirección del extremo de la instancia de forma local o usar un método generador en el servicio para obtener la dirección del extremo de una instancia en ejecución.</span><span class="sxs-lookup"><span data-stu-id="7056c-108">Clients can either resolve the instance’s endpoint address locally or contact a factory method in the service to obtain the endpoint address of a running instance.</span></span> <span data-ttu-id="7056c-109">Cuando tenga la dirección del extremo, puede crear un nuevo canal e iniciar la comunicación.</span><span class="sxs-lookup"><span data-stu-id="7056c-109">Once it has the endpoint address, it can create a new channel and start communication.</span></span> <span data-ttu-id="7056c-110">El siguiente fragmento de código muestra el modo en que una aplicación cliente crea un canal nuevo para una instancia de servicio existente.</span><span class="sxs-lookup"><span data-stu-id="7056c-110">The following code snippet shows how a client application creates a new channel to an existing service instance.</span></span>  
  
```  
// Create the first channel.  
IEchoService proxy = channelFactory.CreateChannel();  
  
// Resolve the instance.  
EndpointAddress epa = ((IClientChannel)proxy).ResolveInstance();  
  
// Create new channel factory with the endpoint address resolved by   
// previous statement.  
ChannelFactory<IEchoService> channelFactory2 =  
                new ChannelFactory<IEchoService>("echoservice",  
                epa);  
  
// Create the second channel to the same instance.  
IEchoService proxy2 = channelFactory2.CreateChannel();  
```  
  
 <span data-ttu-id="7056c-111">A diferencia de los demás modos de creación de instancias, el modo de creación de instancias compartido tiene una sola manera de liberar las instancias de servicio.</span><span class="sxs-lookup"><span data-stu-id="7056c-111">Unlike other instancing modes, the shared instancing mode has a unique way of releasing the service instances.</span></span> <span data-ttu-id="7056c-112">Cuando todos los canales se cierran para una instancia, el tiempo de ejecución de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] del servicio inicia un temporizador.</span><span class="sxs-lookup"><span data-stu-id="7056c-112">When all the channels are closed for an instance, the service [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] runtime starts a timer.</span></span> <span data-ttu-id="7056c-113">Si nadie realiza una conexión antes de que el tiempo de espera expire, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] libera la instancia y reclama los recursos.</span><span class="sxs-lookup"><span data-stu-id="7056c-113">If nobody makes a connection before the timeout expires, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] releases the instance and claims the resources.</span></span> <span data-ttu-id="7056c-114">Como parte del procedimiento de destrucción, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] invoca el método <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> de todas las implementaciones de <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> antes de liberar la instancia.</span><span class="sxs-lookup"><span data-stu-id="7056c-114">As a part of the teardown procedure [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] invokes the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method of all <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementations before releasing the instance.</span></span> <span data-ttu-id="7056c-115">Si todas ellas devuelven `true`, la instancia se libera.</span><span class="sxs-lookup"><span data-stu-id="7056c-115">If all of them return `true` the instance is released.</span></span> <span data-ttu-id="7056c-116">De lo contrario, la implementación de <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> es responsable de notificar al `Dispatcher` el estado de inactividad utilizando un método de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="7056c-116">Otherwise the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementation is responsible for notifying the `Dispatcher` of the idle state by using a callback method.</span></span>  
  
 <span data-ttu-id="7056c-117">De forma predeterminada, el valor de tiempo de espera de inactividad de <xref:System.ServiceModel.InstanceContext> es de un minuto.</span><span class="sxs-lookup"><span data-stu-id="7056c-117">By default, the idle timeout value of <xref:System.ServiceModel.InstanceContext> is one minute.</span></span> <span data-ttu-id="7056c-118">Sin embargo, este ejemplo muestra cómo puede ampliarlo utilizando una extensión personalizada.</span><span class="sxs-lookup"><span data-stu-id="7056c-118">However this sample demonstrates how you can extend this using a custom extension.</span></span>  
  
## <a name="extending-the-instancecontext"></a><span data-ttu-id="7056c-119">Ampliar InstanceContext</span><span class="sxs-lookup"><span data-stu-id="7056c-119">Extending the InstanceContext</span></span>  
 <span data-ttu-id="7056c-120">En [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], <xref:System.ServiceModel.InstanceContext> es el vínculo entre la instancia de servicio y `Dispatcher`.</span><span class="sxs-lookup"><span data-stu-id="7056c-120">In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], <xref:System.ServiceModel.InstanceContext> is the link between the service instance and the `Dispatcher`.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="7056c-121"> le permite extender estoe componente de tiempo de ejecución al agregar un nuevo estado o comportamiento usando su patrón de objeto extensible.</span><span class="sxs-lookup"><span data-stu-id="7056c-121"> allows you to extend this runtime component by adding new state or behavior by using its extensible object pattern.</span></span> <span data-ttu-id="7056c-122">El patrón de objeto extensible se utiliza en [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] para extender clases de tiempo de ejecución existentes con nueva funcionalidad o agregar nuevas características del estado a un objeto.</span><span class="sxs-lookup"><span data-stu-id="7056c-122">The extensible object pattern is used in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] to either extend existing runtime classes with new functionality or to add new state features to an object.</span></span> <span data-ttu-id="7056c-123">Hay tres interfaces en el patrón de objeto extensible: `IExtensibleObject<T>`, `IExtension<T>`y `IExtensionCollection<T>`.</span><span class="sxs-lookup"><span data-stu-id="7056c-123">There are three interfaces in the extensible object pattern: `IExtensibleObject<T>`, `IExtension<T>`, and `IExtensionCollection<T>`.</span></span>  
  
 <span data-ttu-id="7056c-124">La interfaz `IExtensibleObject<T>` se implementa mediante objetos para permitir las extensiones que pueden personalizar su funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="7056c-124">The `IExtensibleObject<T>` interface is implemented by objects to allow extensions which customize their functionality.</span></span>  
  
 <span data-ttu-id="7056c-125">La interfaz `IExtension<T>` se implementa mediante objetos que pueden ser extensiones de clases de tipo `T`.</span><span class="sxs-lookup"><span data-stu-id="7056c-125">The `IExtension<T>` interface is implemented by objects that can be extensions of classes of type `T`.</span></span>  
  
 <span data-ttu-id="7056c-126">Y finalmente, la interfaz `IExtensionCollection<T>` es una colección de interfaces `IExtensions` que permite recuperar las interfaces `IExtensions` por su tipo.</span><span class="sxs-lookup"><span data-stu-id="7056c-126">And finally, the `IExtensionCollection<T>` interface is a collection of `IExtensions` that allows for retrieving `IExtensions` by their type.</span></span>  
  
 <span data-ttu-id="7056c-127">Por consiguiente, para extender el <xref:System.ServiceModel.InstanceContext> debe implementar la interfaz `IExtension`.</span><span class="sxs-lookup"><span data-stu-id="7056c-127">Therefore in order to extend the <xref:System.ServiceModel.InstanceContext> you must implement the `IExtension` interface.</span></span> <span data-ttu-id="7056c-128">En este proyecto de ejemplo, la clase `CustomLeaseExtension` contiene esta implementación.</span><span class="sxs-lookup"><span data-stu-id="7056c-128">In this sample project the `CustomLeaseExtension` class contains this implementation.</span></span>  
  
```  
class CustomLeaseExtension : IExtension<InstanceContext>  
{  
}  
```  
  
 <span data-ttu-id="7056c-129">La interfaz `IExtension` tiene dos métodos: `Attach` y `Detach`.</span><span class="sxs-lookup"><span data-stu-id="7056c-129">The `IExtension` interface has two methods `Attach` and `Detach`.</span></span> <span data-ttu-id="7056c-130">Como sus nombres indican, se llama a estos dos métodos cuando el tiempo de ejecución asocia y desasocia la extensión a una instancia de la clase <xref:System.ServiceModel.InstanceContext>.</span><span class="sxs-lookup"><span data-stu-id="7056c-130">As their names imply, these two methods are called when the runtime attaches and detaches the extension to an instance of the <xref:System.ServiceModel.InstanceContext> class.</span></span> <span data-ttu-id="7056c-131">En este ejemplo, el método `Attach` se usa para realizar un seguimiento del objeto <xref:System.ServiceModel.InstanceContext> que pertenece a la instancia actual de la extensión.</span><span class="sxs-lookup"><span data-stu-id="7056c-131">In this sample, the `Attach` method is used to keep track of the <xref:System.ServiceModel.InstanceContext> object that belongs to the current instance of the extension.</span></span>  
  
```  
InstanceContext owner;  
  
public void Attach(InstanceContext owner)  
{  
  this.owner = owner;   
}  
```  
  
 <span data-ttu-id="7056c-132">Además, debe agregar la implementación necesaria a la extensión para proporcionar compatibilidad con la duración extendida.</span><span class="sxs-lookup"><span data-stu-id="7056c-132">In addition, you must add the necessary implementation to the extension to provide the extended lifetime support.</span></span> <span data-ttu-id="7056c-133">Por consiguiente, la interfaz `ICustomLease` se declara con los métodos deseados y se implementa en la clase `CustomLeaseExtension`.</span><span class="sxs-lookup"><span data-stu-id="7056c-133">Therefore the `ICustomLease` interface is declared with the desired methods and is implemented in the `CustomLeaseExtension` class.</span></span>  
  
```  
interface ICustomLease  
{  
    bool IsIdle { get; }          
    InstanceContextIdleCallback Callback { get; set; }  
}  
  
class CustomLeaseExtension : IExtension<InstanceContext>, ICustomLease  
{  
}  
```  
  
 <span data-ttu-id="7056c-134">Cuando [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] invoca el método <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> en la implementación de <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider>, esta llamada se enruta al método <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> de `CustomLeaseExtension`.</span><span class="sxs-lookup"><span data-stu-id="7056c-134">When [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] invokes the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method in the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementation this call is routed to the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method of the `CustomLeaseExtension`.</span></span> <span data-ttu-id="7056c-135">A continuación, `CustomLeaseExtension` comprueba su estado privado para ver si el <xref:System.ServiceModel.InstanceContext> está inactivo.</span><span class="sxs-lookup"><span data-stu-id="7056c-135">Then the `CustomLeaseExtension` checks its private state to see whether the <xref:System.ServiceModel.InstanceContext> is idle.</span></span> <span data-ttu-id="7056c-136">Si lo está, devuelve `true`.</span><span class="sxs-lookup"><span data-stu-id="7056c-136">If it is idle it returns `true`.</span></span> <span data-ttu-id="7056c-137">De lo contrario, inicia un temporizador con la duración extendida especificada.</span><span class="sxs-lookup"><span data-stu-id="7056c-137">Otherwise, it starts a timer for a specified amount of extended lifetime.</span></span>  
  
```  
public bool IsIdle  
{  
  get  
  {  
    lock (thisLock)  
    {  
      if (isIdle)  
      {  
        return true;  
      }  
      else  
      {  
        StartTimer();  
        return false;  
      }  
    }  
  }  
}  
```  
  
 <span data-ttu-id="7056c-138">En el evento `Elapsed` del temporizador, se llama a la función de devolución de llamada en el Distribuidor para iniciar otro ciclo de limpieza.</span><span class="sxs-lookup"><span data-stu-id="7056c-138">In the timer’s `Elapsed` event the callback function in the Dispatcher is called in order to start another clean up cycle.</span></span>  
  
```  
void idleTimer_Elapsed(object sender, ElapsedEventArgs args)  
{  
    idleTimer.Stop();  
    isIdle = true;    
    callback(owner);  
}  
```  
  
 <span data-ttu-id="7056c-139">No hay ninguna manera de renovar el temporizador en ejecución cuando llega un mensaje nuevo para la instancia que se va a pasar al estado inactivo.</span><span class="sxs-lookup"><span data-stu-id="7056c-139">There is no way to renew the running timer when a new message arrives for the instance being moved to the idle state.</span></span>  
  
 <span data-ttu-id="7056c-140">En el ejemplo se implementa <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> para interceptar las llamadas al método <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> y enrutarlas a `CustomLeaseExtension`.</span><span class="sxs-lookup"><span data-stu-id="7056c-140">The sample implements <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> to intercept the calls to the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method and route them to the `CustomLeaseExtension`.</span></span> <span data-ttu-id="7056c-141">La implementación de <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> está contenida en la clase `CustomLifetimeLease`.</span><span class="sxs-lookup"><span data-stu-id="7056c-141">The <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementation is contained in `CustomLifetimeLease` class.</span></span> <span data-ttu-id="7056c-142">Se invoca al método <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> cuando [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] está a punto de liberar la instancia de servicio.</span><span class="sxs-lookup"><span data-stu-id="7056c-142">The <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method is invoked when [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] is about to release the service instance.</span></span> <span data-ttu-id="7056c-143">Sin embargo, solo hay una instancia de una implementación de `ISharedSessionInstance` determinada en la colección de propiedades <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> de ServiceBehavior.</span><span class="sxs-lookup"><span data-stu-id="7056c-143">However, there is only one instance of a particular `ISharedSessionInstance` implementation in the ServiceBehavior’s <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> collection.</span></span> <span data-ttu-id="7056c-144">Esto significa que no hay ninguna manera de saber que el <xref:System.ServiceModel.InstanceContext> se está cerrando en el momento en que [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] comprueba el método <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A>.</span><span class="sxs-lookup"><span data-stu-id="7056c-144">This means there is no way of knowing the <xref:System.ServiceModel.InstanceContext> being closed at the time [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] checks the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method.</span></span> <span data-ttu-id="7056c-145">Por consiguiente, este ejemplo utiliza el bloqueo de subprocesos para serializar las solicitudes al método <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A>.</span><span class="sxs-lookup"><span data-stu-id="7056c-145">Therefore this sample uses thread locking to serialize requests to the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7056c-146">El uso del bloqueo de subprocesos no es una solución recomendada porque la serialización puede afectar de forma grave al rendimiento de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7056c-146">Using thread locking is not a recommended approach because serialization can severely affect the performance of your application.</span></span>  
  
 <span data-ttu-id="7056c-147">Una variable de miembro privado se utiliza en la clase `CustomLeaseExtension` para realizar el seguimiento del valor `IsIdle`.</span><span class="sxs-lookup"><span data-stu-id="7056c-147">A private member variable is used in the `CustomLeaseExtension` class to track the `IsIdle` value.</span></span> <span data-ttu-id="7056c-148">Cada vez que se recupera el valor de <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider>, se devuelve el miembro privado `IsIdle` y se restablece en `false`.</span><span class="sxs-lookup"><span data-stu-id="7056c-148">Each time the value of <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> is retrieved the `IsIdle` private member is returned and reset to `false`.</span></span> <span data-ttu-id="7056c-149">Es esencial establecer este valor en `false` para asegurarse de que el Distribuidor llama al método <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A>.</span><span class="sxs-lookup"><span data-stu-id="7056c-149">It is essential to set this value to `false` in order to make sure the Dispatcher calls the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A> method.</span></span>  
  
```  
public bool IsIdle  
{  
    get   
    {  
       lock (thisLock)  
       {  
           bool idleCopy = isIdle;  
           isIdle = false;  
           return idleCopy;  
       }  
    }  
}  
```  
  
 <span data-ttu-id="7056c-150">Si la propiedad `ISharedSessionLifetime.IsIdle` devuelve `false`, el Distribuidor registra una función de devolución de llamada utilizando el método `NotifyIdle`.</span><span class="sxs-lookup"><span data-stu-id="7056c-150">If the `ISharedSessionLifetime.IsIdle` property returns `false` the Dispatcher registers a callback function by using the `NotifyIdle` method.</span></span> <span data-ttu-id="7056c-151">Este método recibe una referencia al <xref:System.ServiceModel.InstanceContext> que se va a liberar.</span><span class="sxs-lookup"><span data-stu-id="7056c-151">This method receives a reference to the <xref:System.ServiceModel.InstanceContext> being released.</span></span> <span data-ttu-id="7056c-152">Por consiguiente, el código de muestra puede consultar la extensión de tipo de `ICustomLease` y comprobar la propiedad `ICustomLease.IsIdle` en el estado extendido.</span><span class="sxs-lookup"><span data-stu-id="7056c-152">Therefore the sample code can query the `ICustomLease` type extension and check the `ICustomLease.IsIdle` property in the extended state.</span></span>  
  
```  
public void NotifyIdle(InstanceContextIdleCallback callback,   
            InstanceContext instanceContext)  
{  
    lock (thisLock)  
    {  
       ICustomLease customLease =  
           instanceContext.Extensions.Find<ICustomLease>();  
       customLease.Callback = callback;   
       isIdle = customLease.IsIdle;  
       if (isIdle)  
       {  
             callback(instanceContext);  
       }  
    }   
}  
```  
  
 <span data-ttu-id="7056c-153">Antes de que se compruebe la propiedad `ICustomLease.IsIdle`, tiene que establecerse la propiedad Callback porque es esencial para que `CustomLeaseExtension` notifique al Distribuidor cuando pase a estar inactivo.</span><span class="sxs-lookup"><span data-stu-id="7056c-153">Before the `ICustomLease.IsIdle` property is checked the Callback property needs to be set as this is essential for `CustomLeaseExtension` to notify the Dispatcher when it becomes idle.</span></span> <span data-ttu-id="7056c-154">Si `ICustomLease.IsIdle` devuelve `true`, el miembro privado `isIdle` simplemente se establece en `CustomLifetimeLease` como `true` y llama al método de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="7056c-154">If `ICustomLease.IsIdle` returns `true`, the `isIdle` private member is simply set in `CustomLifetimeLease` to `true` and calls the callback method.</span></span> <span data-ttu-id="7056c-155">Dado que el código contiene un bloqueo, otros subprocesos no pueden cambiar el valor de este miembro privado.</span><span class="sxs-lookup"><span data-stu-id="7056c-155">Because the code holds a lock, other threads cannot change the value of this private member.</span></span> <span data-ttu-id="7056c-156">Y la siguiente vez que el Distribuidor compruebe la interfaz `ISharedSessionLifetime.IsIdle`, devuelve `true` y permite que el Distribuidor libere la instancia.</span><span class="sxs-lookup"><span data-stu-id="7056c-156">And the next time Dispatcher checks the `ISharedSessionLifetime.IsIdle`, it returns `true` and lets Dispatcher release the instance.</span></span>  
  
 <span data-ttu-id="7056c-157">Ahora que el fundamento de la extensión personalizada está completado, tiene que enlazarse con el modelo de servicio.</span><span class="sxs-lookup"><span data-stu-id="7056c-157">Now that the groundwork for the custom extension is completed, it has to be hooked up to the service model.</span></span> <span data-ttu-id="7056c-158">Para enlazar la implementación de `CustomLeaseExtension` en el <xref:System.ServiceModel.InstanceContext>, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] proporciona la interfaz de <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer> para realizar la secuencia de arranque de <xref:System.ServiceModel.InstanceContext>.</span><span class="sxs-lookup"><span data-stu-id="7056c-158">To hook up the `CustomLeaseExtension` implementation to the <xref:System.ServiceModel.InstanceContext>, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] provides the <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer> interface to perform the bootstrapping of <xref:System.ServiceModel.InstanceContext>.</span></span> <span data-ttu-id="7056c-159">En el ejemplo, la clase `CustomLeaseInitializer` implementa esta interfaz y agrega una instancia de `CustomLeaseExtension` a la colección de la propiedad <xref:System.ServiceModel.InstanceContext.Extensions%2A> desde la única inicialización del método.</span><span class="sxs-lookup"><span data-stu-id="7056c-159">In the sample, the `CustomLeaseInitializer` class implements this interface and adds an instance of `CustomLeaseExtension` to the <xref:System.ServiceModel.InstanceContext.Extensions%2A> collection from the only method initialization.</span></span> <span data-ttu-id="7056c-160">El Distribuidor llama a este método inicializando la instancia de <xref:System.ServiceModel.InstanceContext>.</span><span class="sxs-lookup"><span data-stu-id="7056c-160">This method is called by Dispatcher while initializing the <xref:System.ServiceModel.InstanceContext>.</span></span>  
  
```  
public void Initialize(InstanceContext instanceContext, Message message)  
{  
  IExtension<InstanceContext> customLeaseExtension =  
    new CustomLeaseExtension(timeout);  
  instanceContext.Extensions.Add(customLeaseExtension);  
}  
```  
  
 <span data-ttu-id="7056c-161">Por último, el `System.ServiceModel.Dispatcher.IShareableInstanceContextLifetime` y <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer> las implementaciones son es ángulo hasta el modelo de servicio mediante el uso de la <xref:System.ServiceModel.Description.IServiceBehavior> implementación.</span><span class="sxs-lookup"><span data-stu-id="7056c-161">Finally the `System.ServiceModel.Dispatcher.IShareableInstanceContextLifetime` and <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer> implementations are is hooked up to the service model by using the <xref:System.ServiceModel.Description.IServiceBehavior> implementation.</span></span> <span data-ttu-id="7056c-162">Esta implementación se coloca en la clase `CustomLeaseTimeAttribute` y también deriva de la clase base `Attribute` para exponer este comportamiento como un atributo.</span><span class="sxs-lookup"><span data-stu-id="7056c-162">This implementation is placed in the `CustomLeaseTimeAttribute` class and it also derives from the `Attribute` base class to expose this behavior as an attribute.</span></span> <span data-ttu-id="7056c-163">En el método `IServiceBehavior.ApplyBehavior`, las instancias de las implementaciones de <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer> y `System.ServiceModel.Dispatcher.IShareableInstanceContextLifetime` se agregan respectivamente a las colecciones de propiedades `System.ServiceModel.Dispatcher.DispatchRuntime.InstanceContextLifetimes` y <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceContextInitializers%2A> del espacio de nombres <xref:System.ServiceModel.Dispatcher.IShareableInstanceContextLifetime>.</span><span class="sxs-lookup"><span data-stu-id="7056c-163">In the `IServiceBehavior.ApplyBehavior` method, instances of <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer> and `System.ServiceModel.Dispatcher.IShareableInstanceContextLifetime` implementations are added to the `System.ServiceModel.Dispatcher.DispatchRuntime.InstanceContextLifetimes` and <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceContextInitializers%2A> collections of the <xref:System.ServiceModel.Dispatcher.IShareableInstanceContextLifetime> respectively.</span></span>  
  
```  
public void ApplyBehavior(ServiceDescription description,   
           ServiceHostBase serviceHostBase,   
           Collection<DispatchBehavior> behaviors,  
           Collection<BindingParameterCollection> parameters)  
{  
    CustomLifetimeLease customLease = new CustomLifetimeLease();  
    CustomLeaseInitializer initializer =   
                new CustomLeaseInitializer(timeout);  
  
    foreach (DispatchBehavior dispatchBehavior in behaviors)  
    {  
        dispatchBehavior.InstanceContextLifetimes.Add(customLease);  
        dispatchBehavior.InstanceContextInitializers.Add(initializer);  
    }  
}  
```  
  
 <span data-ttu-id="7056c-164">Este comportamiento se puede agregar a una clase de servicio de ejemplo agregándolo con el atributo `CustomLeaseTime`.</span><span class="sxs-lookup"><span data-stu-id="7056c-164">This behavior can be added to a sample service class by annotating it with the `CustomLeaseTime` attribute.</span></span>  
  
```  
[ServiceBehavior(InstanceContextMode=InstanceContextMode.Shareable)]  
[CustomLeaseTime(Timeout = 20000)]  
public class EchoService : IEchoService  
{  
  //…  
}  
```  
  
 <span data-ttu-id="7056c-165">Al ejecutar el ejemplo, las solicitudes y las respuestas de operación se muestran tanto en la ventanas de la consola del cliente como del servicio.</span><span class="sxs-lookup"><span data-stu-id="7056c-165">When you run the sample, the operation requests and responses are displayed in both the service and client console windows.</span></span> <span data-ttu-id="7056c-166">Presione Entrar en cada ventana de la consola para cerrar el servicio y el cliente.</span><span class="sxs-lookup"><span data-stu-id="7056c-166">Press ENTER in each console window to shut down the service and client.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="7056c-167">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="7056c-167">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="7056c-168">Asegúrese de que ha llevado a cabo la [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="7056c-168">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="7056c-169">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="7056c-169">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="7056c-170">Para ejecutar el ejemplo en una configuración de equipo único o de varios, siga las instrucciones de [ejecutando los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="7056c-170">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7056c-171">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="7056c-171">The samples may already be installed on your machine.</span></span> <span data-ttu-id="7056c-172">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="7056c-172">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="7056c-173">Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7056c-173">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="7056c-174">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="7056c-174">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Instancing\Lifetime`  
  
## <a name="see-also"></a><span data-ttu-id="7056c-175">Vea también</span><span class="sxs-lookup"><span data-stu-id="7056c-175">See Also</span></span>
