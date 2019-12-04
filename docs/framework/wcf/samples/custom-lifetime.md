---
title: Vigencia personalizada
ms.date: 08/20/2018
ms.assetid: 52806c07-b91c-48fe-b992-88a41924f51f
ms.openlocfilehash: 8625877d9b4d05d5cf06af2c9f8ef10f701e98db
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715477"
---
# <a name="custom-lifetime"></a><span data-ttu-id="672d9-102">Vigencia personalizada</span><span class="sxs-lookup"><span data-stu-id="672d9-102">Custom lifetime</span></span>

<span data-ttu-id="672d9-103">Este ejemplo muestra cómo escribir una extensión de Windows Communication Foundation (WCF) para proporcionar servicios de duración personalizados para las instancias de servicio WCF compartidas.</span><span class="sxs-lookup"><span data-stu-id="672d9-103">This sample demonstrates how to write a Windows Communication Foundation (WCF) extension to provide custom lifetime services for shared WCF service instances.</span></span>

> [!NOTE]
> <span data-ttu-id="672d9-104">El procedimiento de configuración y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="672d9-104">The setup procedure and build instructions for this sample are located at the end of this article.</span></span>

## <a name="shared-instancing"></a><span data-ttu-id="672d9-105">Instancias compartidas</span><span class="sxs-lookup"><span data-stu-id="672d9-105">Shared instancing</span></span>

<span data-ttu-id="672d9-106">WCF ofrece varios modos de creación de instancias para las instancias de servicio.</span><span class="sxs-lookup"><span data-stu-id="672d9-106">WCF offers several instancing modes for your service instances.</span></span> <span data-ttu-id="672d9-107">El modo de creación de instancias compartido que se trata en este artículo proporciona una manera de compartir una instancia de servicio entre varios canales.</span><span class="sxs-lookup"><span data-stu-id="672d9-107">The shared instancing mode covered in this article provides a way to share a service instance between multiple channels.</span></span> <span data-ttu-id="672d9-108">Los clientes pueden ponerse en contacto con un Factory Method del servicio y crear un nuevo canal para iniciar la comunicación.</span><span class="sxs-lookup"><span data-stu-id="672d9-108">Clients can contact a factory method in the service and create a new channel to start communication.</span></span> <span data-ttu-id="672d9-109">En el fragmento de código siguiente se muestra cómo una aplicación cliente crea un canal nuevo en una instancia de servicio existente:</span><span class="sxs-lookup"><span data-stu-id="672d9-109">The following code snippet shows how a client application creates a new channel to an existing service instance:</span></span>

```csharp
// Create a header for the shared instance id
MessageHeader shareableInstanceContextHeader = MessageHeader.CreateHeader(
        CustomHeader.HeaderName,
        CustomHeader.HeaderNamespace,
        Guid.NewGuid().ToString());

// Create the channel factory
ChannelFactory<IEchoService> channelFactory =
    new ChannelFactory<IEchoService>("echoservice");

// Create the first channel
IEchoService proxy = channelFactory.CreateChannel();

// Call an operation to create shared service instance
using (new OperationContextScope((IClientChannel)proxy))
{
    OperationContext.Current.OutgoingMessageHeaders.Add(shareableInstanceContextHeader);
    Console.WriteLine("Service returned: " + proxy.Echo("Apple"));
}

((IChannel)proxy).Close();

// Create the second channel
IEchoService proxy2 = channelFactory.CreateChannel();

// Call an operation using the same header that will reuse the shared service instance
using (new OperationContextScope((IClientChannel)proxy2))
{
    OperationContext.Current.OutgoingMessageHeaders.Add(shareableInstanceContextHeader);
    Console.WriteLine("Service returned: " + proxy2.Echo("Apple"));
}
```

<span data-ttu-id="672d9-110">A diferencia de los demás modos de creación de instancias, el modo de creación de instancias compartido tiene una sola manera de liberar las instancias de servicio.</span><span class="sxs-lookup"><span data-stu-id="672d9-110">Unlike other instancing modes, the shared instancing mode has a unique way of releasing the service instances.</span></span> <span data-ttu-id="672d9-111">De forma predeterminada, cuando se cierran todos los canales para un <xref:System.ServiceModel.InstanceContext>, el tiempo de ejecución del servicio WCF comprueba si el servicio <xref:System.ServiceModel.InstanceContextMode> está configurado para <xref:System.ServiceModel.InstanceContextMode.PerCall> o <xref:System.ServiceModel.InstanceContextMode.PerSession>y, en ese caso, libera la instancia y notifica los recursos.</span><span class="sxs-lookup"><span data-stu-id="672d9-111">By default, when all the channels are closed for an <xref:System.ServiceModel.InstanceContext>, the WCF service runtime checks to see if the service <xref:System.ServiceModel.InstanceContextMode> is configured to <xref:System.ServiceModel.InstanceContextMode.PerCall> or <xref:System.ServiceModel.InstanceContextMode.PerSession>, and if so releases the instance and claims the resources.</span></span> <span data-ttu-id="672d9-112">Si se utiliza un <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> personalizado, WCF invoca el método <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> de la implementación del proveedor antes de liberar la instancia.</span><span class="sxs-lookup"><span data-stu-id="672d9-112">If a custom <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> is being used, WCF invokes the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method of the provider implementation before releasing the instance.</span></span> <span data-ttu-id="672d9-113">Si <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> devuelve `true` se libera la instancia de, en caso contrario, la implementación de <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> es responsable de notificar al `Dispatcher` del estado de inactividad mediante un método de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="672d9-113">If <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> returns `true` the instance is released, otherwise the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementation is responsible for notifying the `Dispatcher` of the idle state by using a callback method.</span></span> <span data-ttu-id="672d9-114">Esto se hace llamando al método <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A> del proveedor.</span><span class="sxs-lookup"><span data-stu-id="672d9-114">This is done by calling the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A> method of the provider.</span></span>

<span data-ttu-id="672d9-115">Este ejemplo muestra cómo se puede retrasar la liberación del <xref:System.ServiceModel.InstanceContext> con un tiempo de espera de inactividad de 20 segundos.</span><span class="sxs-lookup"><span data-stu-id="672d9-115">This sample demonstrates how you can delay releasing the <xref:System.ServiceModel.InstanceContext> with an idle timeout of 20 seconds.</span></span>

## <a name="extending-the-instancecontext"></a><span data-ttu-id="672d9-116">Ampliar InstanceContext</span><span class="sxs-lookup"><span data-stu-id="672d9-116">Extending the InstanceContext</span></span>

<span data-ttu-id="672d9-117">En WCF, <xref:System.ServiceModel.InstanceContext> es el vínculo entre la instancia de servicio y el `Dispatcher`.</span><span class="sxs-lookup"><span data-stu-id="672d9-117">In WCF, <xref:System.ServiceModel.InstanceContext> is the link between the service instance and the `Dispatcher`.</span></span> <span data-ttu-id="672d9-118">WCF le permite ampliar este componente en tiempo de ejecución agregando nuevo estado o comportamiento mediante su patrón de objeto extensible.</span><span class="sxs-lookup"><span data-stu-id="672d9-118">WCF allows you to extend this runtime component by adding new state or behavior by using its extensible object pattern.</span></span> <span data-ttu-id="672d9-119">El patrón de objeto extensible se utiliza en WCF para ampliar las clases en tiempo de ejecución existentes con nueva funcionalidad o agregar nuevas características de estado a un objeto.</span><span class="sxs-lookup"><span data-stu-id="672d9-119">The extensible object pattern is used in WCF to either extend existing runtime classes with new functionality or to add new state features to an object.</span></span> <span data-ttu-id="672d9-120">Hay tres interfaces en el patrón de objeto extensible: <xref:System.ServiceModel.IExtensibleObject%601>, <xref:System.ServiceModel.IExtension%601>y <xref:System.ServiceModel.IExtensionCollection%601>.</span><span class="sxs-lookup"><span data-stu-id="672d9-120">There are three interfaces in the extensible object pattern: <xref:System.ServiceModel.IExtensibleObject%601>, <xref:System.ServiceModel.IExtension%601>, and <xref:System.ServiceModel.IExtensionCollection%601>.</span></span>

<span data-ttu-id="672d9-121">Los objetos implementan la interfaz <xref:System.ServiceModel.IExtensibleObject%601> para permitir extensiones que personalizan su funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="672d9-121">The <xref:System.ServiceModel.IExtensibleObject%601> interface is implemented by objects to allow extensions that customize their functionality.</span></span>

<span data-ttu-id="672d9-122">La interfaz <xref:System.ServiceModel.IExtension%601> se implementa mediante objetos que pueden ser extensiones de clases de tipo `T`.</span><span class="sxs-lookup"><span data-stu-id="672d9-122">The <xref:System.ServiceModel.IExtension%601> interface is implemented by objects that can be extensions of classes of type `T`.</span></span>

<span data-ttu-id="672d9-123">Y, por último, la interfaz de <xref:System.ServiceModel.IExtensionCollection%601> es una colección de implementaciones de <xref:System.ServiceModel.IExtension%601> que permite recuperar una implementación de <xref:System.ServiceModel.IExtension%601> por su tipo.</span><span class="sxs-lookup"><span data-stu-id="672d9-123">And finally, the <xref:System.ServiceModel.IExtensionCollection%601> interface is a collection of <xref:System.ServiceModel.IExtension%601> implementations that allows for retrieving an implementation of <xref:System.ServiceModel.IExtension%601> by their type.</span></span>

<span data-ttu-id="672d9-124">Por lo tanto, para extender el <xref:System.ServiceModel.InstanceContext>, debe implementar la interfaz <xref:System.ServiceModel.IExtension%601>.</span><span class="sxs-lookup"><span data-stu-id="672d9-124">Therefore, in order to extend the <xref:System.ServiceModel.InstanceContext>, you must implement the <xref:System.ServiceModel.IExtension%601> interface.</span></span> <span data-ttu-id="672d9-125">En este proyecto de ejemplo, la clase `CustomLeaseExtension` contiene esta implementación.</span><span class="sxs-lookup"><span data-stu-id="672d9-125">In this sample project, the `CustomLeaseExtension` class contains this implementation.</span></span>

```csharp
class CustomLeaseExtension : IExtension<InstanceContext>
{
}
```

<span data-ttu-id="672d9-126">La interfaz <xref:System.ServiceModel.IExtension%601> tiene dos métodos: <xref:System.ServiceModel.IExtension%601.Attach%2A> y <xref:System.ServiceModel.IExtension%601.Detach%2A>.</span><span class="sxs-lookup"><span data-stu-id="672d9-126">The <xref:System.ServiceModel.IExtension%601> interface has two methods <xref:System.ServiceModel.IExtension%601.Attach%2A> and <xref:System.ServiceModel.IExtension%601.Detach%2A>.</span></span> <span data-ttu-id="672d9-127">Como sus nombres indican, se llama a estos dos métodos cuando el tiempo de ejecución asocia y desasocia la extensión a una instancia de la clase <xref:System.ServiceModel.InstanceContext>.</span><span class="sxs-lookup"><span data-stu-id="672d9-127">As their names imply, these two methods are called when the runtime attaches and detaches the extension to an instance of the <xref:System.ServiceModel.InstanceContext> class.</span></span> <span data-ttu-id="672d9-128">En este ejemplo, el método `Attach` se usa para realizar un seguimiento del objeto <xref:System.ServiceModel.InstanceContext> que pertenece a la instancia actual de la extensión.</span><span class="sxs-lookup"><span data-stu-id="672d9-128">In this sample, the `Attach` method is used to keep track of the <xref:System.ServiceModel.InstanceContext> object that belongs to the current instance of the extension.</span></span>

```csharp
InstanceContext owner;

public void Attach(InstanceContext owner)
{
    this.owner = owner;
}
```

<span data-ttu-id="672d9-129">Además, debe agregar la implementación necesaria a la extensión para proporcionar compatibilidad con la duración extendida.</span><span class="sxs-lookup"><span data-stu-id="672d9-129">In addition, you must add the necessary implementation to the extension to provide the extended lifetime support.</span></span> <span data-ttu-id="672d9-130">Por lo tanto, la interfaz de `ICustomLease` se declara con los métodos deseados y se implementa en la clase `CustomLeaseExtension`.</span><span class="sxs-lookup"><span data-stu-id="672d9-130">Therefore, the `ICustomLease` interface is declared with the desired methods and is implemented in the `CustomLeaseExtension` class.</span></span>

```csharp
interface ICustomLease
{
    bool IsIdle { get; }
    InstanceContextIdleCallback Callback { get; set; }
}

class CustomLeaseExtension : IExtension<InstanceContext>, ICustomLease
{
}
```

<span data-ttu-id="672d9-131">Cuando WCF invoca el método <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> en la implementación de <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider>, esta llamada se enruta al método <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> del `CustomLeaseExtension`.</span><span class="sxs-lookup"><span data-stu-id="672d9-131">When WCF invokes the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method in the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementation, this call is routed to the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method of the `CustomLeaseExtension`.</span></span> <span data-ttu-id="672d9-132">A continuación, el `CustomLeaseExtension` comprueba su estado privado para ver si el <xref:System.ServiceModel.InstanceContext> está inactivo.</span><span class="sxs-lookup"><span data-stu-id="672d9-132">Then, the `CustomLeaseExtension` checks its private state to see whether the <xref:System.ServiceModel.InstanceContext> is idle.</span></span> <span data-ttu-id="672d9-133">Si está inactivo, devuelve `true`.</span><span class="sxs-lookup"><span data-stu-id="672d9-133">If it is idle, it returns `true`.</span></span> <span data-ttu-id="672d9-134">De lo contrario, inicia un temporizador con la duración extendida especificada.</span><span class="sxs-lookup"><span data-stu-id="672d9-134">Otherwise, it starts a timer for a specified amount of extended lifetime.</span></span>

```csharp
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

<span data-ttu-id="672d9-135">En el evento `Elapsed` del temporizador, se llama a la función de devolución de llamada del distribuidor para iniciar otro ciclo de limpieza.</span><span class="sxs-lookup"><span data-stu-id="672d9-135">In the timer’s `Elapsed` event, the callback function in the Dispatcher is called in order to start another clean-up cycle.</span></span>

```csharp
void idleTimer_Elapsed(object sender, ElapsedEventArgs args)
{
    lock (thisLock)
    {
        StopTimer();
        isIdle = true;
        Utility.WriteMessageToConsole(
            ResourceHelper.GetString("MsgLeaseExpired"));
        callback(owner);
    }
}
```

<span data-ttu-id="672d9-136">No hay ninguna manera de renovar el temporizador en ejecución cuando llega un mensaje nuevo para que la instancia se mueva al estado inactivo.</span><span class="sxs-lookup"><span data-stu-id="672d9-136">There's no way to renew the running timer when a new message arrives for the instance being moved to the idle state.</span></span>

<span data-ttu-id="672d9-137">En el ejemplo se implementa <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> para interceptar las llamadas al método <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> y enrutarlas a `CustomLeaseExtension`.</span><span class="sxs-lookup"><span data-stu-id="672d9-137">The sample implements <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> to intercept the calls to the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method and route them to the `CustomLeaseExtension`.</span></span> <span data-ttu-id="672d9-138">La implementación de <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> está contenida en la clase `CustomLifetimeLease`.</span><span class="sxs-lookup"><span data-stu-id="672d9-138">The <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementation is contained in `CustomLifetimeLease` class.</span></span> <span data-ttu-id="672d9-139">Se invoca al método <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> cuando WCF está a punto de liberar la instancia de servicio.</span><span class="sxs-lookup"><span data-stu-id="672d9-139">The <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method is invoked when WCF is about to release the service instance.</span></span> <span data-ttu-id="672d9-140">Sin embargo, solo hay una instancia de una implementación de `ISharedSessionInstance` determinada en la colección de propiedades <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> de ServiceBehavior.</span><span class="sxs-lookup"><span data-stu-id="672d9-140">However, there is only one instance of a particular `ISharedSessionInstance` implementation in the ServiceBehavior’s <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> collection.</span></span> <span data-ttu-id="672d9-141">Esto significa que no hay ninguna manera de saber si el <xref:System.ServiceModel.InstanceContext> está cerrado en el momento en que WCF comprueba el método <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A>.</span><span class="sxs-lookup"><span data-stu-id="672d9-141">This means there's no way of knowing if the <xref:System.ServiceModel.InstanceContext> is closed at the time WCF checks the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method.</span></span> <span data-ttu-id="672d9-142">Por consiguiente, este ejemplo usa el bloqueo de subprocesos para serializar las solicitudes al método <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A>.</span><span class="sxs-lookup"><span data-stu-id="672d9-142">Therefore, this sample uses thread locking to serialize requests to the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="672d9-143">El uso del bloqueo de subprocesos no es una solución recomendada porque la serialización puede afectar de forma grave al rendimiento de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="672d9-143">Using thread locking is not a recommended approach because serialization can severely affect the performance of your application.</span></span>

<span data-ttu-id="672d9-144">Se utiliza un campo de miembro privado en la clase `CustomLifetimeLease` para realizar un seguimiento del estado de inactividad y lo devuelve el método <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A>.</span><span class="sxs-lookup"><span data-stu-id="672d9-144">A private member field is used in the `CustomLifetimeLease` class to track the idle state and is returned by the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method.</span></span> <span data-ttu-id="672d9-145">Cada vez que se llama al método <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A>, se devuelve el `isIdle` campo y se restablece en `false`.</span><span class="sxs-lookup"><span data-stu-id="672d9-145">Each time the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method is called, the `isIdle` field is returned and reset to `false`.</span></span>  <span data-ttu-id="672d9-146">Es esencial establecer este valor en `false` para asegurarse de que el Distribuidor llama al método <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A>.</span><span class="sxs-lookup"><span data-stu-id="672d9-146">It is essential to set this value to `false` in order to make sure the Dispatcher calls the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A> method.</span></span>

```csharp
public bool IsIdle(InstanceContext instanceContext)
{
    get
    {
        lock (thisLock)
        {
            //...
            bool idleCopy = isIdle;
            isIdle = false;
            return idleCopy;
        }
    }
}
```

<span data-ttu-id="672d9-147">Si el método <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A?displayProperty=nameWithType> devuelve `false`, el distribuidor registra una función de devolución de llamada mediante el método <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A>.</span><span class="sxs-lookup"><span data-stu-id="672d9-147">If the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A?displayProperty=nameWithType> method returns `false`, the Dispatcher registers a callback function by using the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A> method.</span></span> <span data-ttu-id="672d9-148">Este método recibe una referencia al <xref:System.ServiceModel.InstanceContext> que se va a liberar.</span><span class="sxs-lookup"><span data-stu-id="672d9-148">This method receives a reference to the <xref:System.ServiceModel.InstanceContext> being released.</span></span> <span data-ttu-id="672d9-149">Por lo tanto, el código de ejemplo puede consultar la extensión de tipo `ICustomLease` y comprobar la propiedad `ICustomLease.IsIdle` en el estado extendido.</span><span class="sxs-lookup"><span data-stu-id="672d9-149">Therefore, the sample code can query the `ICustomLease` type extension and check the `ICustomLease.IsIdle` property in the extended state.</span></span>

```csharp
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

<span data-ttu-id="672d9-150">Antes de que se Compruebe la propiedad `ICustomLease.IsIdle`, es necesario establecer la propiedad de devolución de llamada, ya que es esencial para que `CustomLeaseExtension` notifique al distribuidor cuando se vuelva inactiva.</span><span class="sxs-lookup"><span data-stu-id="672d9-150">Before the `ICustomLease.IsIdle` property is checked, the Callback property needs to be set as this is essential for `CustomLeaseExtension` to notify the Dispatcher when it becomes idle.</span></span> <span data-ttu-id="672d9-151">Si `ICustomLease.IsIdle` devuelve `true`, el miembro privado `isIdle` simplemente se establece en `CustomLifetimeLease` como `true` y llama al método de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="672d9-151">If `ICustomLease.IsIdle` returns `true`, the `isIdle` private member is simply set in `CustomLifetimeLease` to `true` and calls the callback method.</span></span> <span data-ttu-id="672d9-152">Dado que el código contiene un bloqueo, otros subprocesos no pueden cambiar el valor de este miembro privado.</span><span class="sxs-lookup"><span data-stu-id="672d9-152">Because the code holds a lock, other threads can't change the value of this private member.</span></span> <span data-ttu-id="672d9-153">Y la próxima vez que el distribuidor llama al <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A?displayProperty=nameWithType>, devuelve `true` y permite que el distribuidor libere la instancia.</span><span class="sxs-lookup"><span data-stu-id="672d9-153">And the next time Dispatcher calls the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A?displayProperty=nameWithType>, it returns `true` and lets Dispatcher release the instance.</span></span>

<span data-ttu-id="672d9-154">Ahora que el fundamento de la extensión personalizada está completado, tiene que enlazarse con el modelo de servicio.</span><span class="sxs-lookup"><span data-stu-id="672d9-154">Now that the groundwork for the custom extension is completed, it has to be hooked up to the service model.</span></span> <span data-ttu-id="672d9-155">Para enlazar la implementación de `CustomLeaseExtension` al <xref:System.ServiceModel.InstanceContext>, WCF proporciona la interfaz <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer> para realizar el arranque de <xref:System.ServiceModel.InstanceContext>.</span><span class="sxs-lookup"><span data-stu-id="672d9-155">To hook up the `CustomLeaseExtension` implementation to the <xref:System.ServiceModel.InstanceContext>, WCF provides the <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer> interface to perform the bootstrapping of <xref:System.ServiceModel.InstanceContext>.</span></span> <span data-ttu-id="672d9-156">En el ejemplo, la clase `CustomLeaseInitializer` implementa esta interfaz y agrega una instancia de `CustomLeaseExtension` a la colección de la propiedad <xref:System.ServiceModel.InstanceContext.Extensions%2A> desde la única inicialización del método.</span><span class="sxs-lookup"><span data-stu-id="672d9-156">In the sample, the `CustomLeaseInitializer` class implements this interface and adds an instance of `CustomLeaseExtension` to the <xref:System.ServiceModel.InstanceContext.Extensions%2A> collection from the only method initialization.</span></span> <span data-ttu-id="672d9-157">El Distribuidor llama a este método inicializando la instancia de <xref:System.ServiceModel.InstanceContext>.</span><span class="sxs-lookup"><span data-stu-id="672d9-157">This method is called by Dispatcher while initializing the <xref:System.ServiceModel.InstanceContext>.</span></span>

```csharp
public void InitializeInstanceContext(InstanceContext instanceContext,
    System.ServiceModel.Channels.Message message, IContextChannel channel)

    //...

    IExtension<InstanceContext> customLeaseExtension =
        new CustomLeaseExtension(timeout, headerId);
    instanceContext.Extensions.Add(customLeaseExtension);
}
```

 <span data-ttu-id="672d9-158">Por último, la implementación de <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> se enlaza al modelo de servicio mediante el uso de la implementación de <xref:System.ServiceModel.Description.IServiceBehavior>.</span><span class="sxs-lookup"><span data-stu-id="672d9-158">Finally the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementation is hooked up to the service model by using the <xref:System.ServiceModel.Description.IServiceBehavior> implementation.</span></span> <span data-ttu-id="672d9-159">Esta implementación se coloca en la clase `CustomLeaseTimeAttribute` y también deriva de la clase base <xref:System.Attribute> para exponer este comportamiento como un atributo.</span><span class="sxs-lookup"><span data-stu-id="672d9-159">This implementation is placed in the `CustomLeaseTimeAttribute` class and it also derives from the <xref:System.Attribute> base class to expose this behavior as an attribute.</span></span>

```csharp
public void ApplyDispatchBehavior(ServiceDescription description,
           ServiceHostBase serviceHostBase)
{
    CustomLifetimeLease customLease = new CustomLifetimeLease(timeout);

    foreach (ChannelDispatcherBase cdb in serviceHostBase.ChannelDispatchers)
    {
        ChannelDispatcher cd = cdb as ChannelDispatcher;

        if (cd != null)
        {
            foreach (EndpointDispatcher ed in cd.Endpoints)
            {
                ed.DispatchRuntime.InstanceContextProvider = customLease;
            }
        }
    }
}
```

<span data-ttu-id="672d9-160">Este comportamiento se puede agregar a una clase de servicio de ejemplo agregándolo con el atributo `CustomLeaseTime`.</span><span class="sxs-lookup"><span data-stu-id="672d9-160">This behavior can be added to a sample service class by annotating it with the `CustomLeaseTime` attribute.</span></span>

```csharp
[CustomLeaseTime(Timeout = 20000)]
public class EchoService : IEchoService
{
  //…
}
```

<span data-ttu-id="672d9-161">Al ejecutar el ejemplo, las solicitudes y las respuestas de operación se muestran tanto en la ventanas de la consola del cliente como del servicio.</span><span class="sxs-lookup"><span data-stu-id="672d9-161">When you run the sample, the operation requests and responses are displayed in both the service and client console windows.</span></span> <span data-ttu-id="672d9-162">Presione Entrar en cada ventana de la consola para cerrar el servicio y el cliente.</span><span class="sxs-lookup"><span data-stu-id="672d9-162">Press ENTER in each console window to shut down the service and client.</span></span>

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="672d9-163">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="672d9-163">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="672d9-164">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="672d9-164">Ensure that you've performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="672d9-165">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="672d9-165">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

3. <span data-ttu-id="672d9-166">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="672d9-166">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="672d9-167">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="672d9-167">The samples may already be installed on your machine.</span></span> <span data-ttu-id="672d9-168">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="672d9-168">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="672d9-169">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos de Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="672d9-169">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="672d9-170">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="672d9-170">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Instancing\Lifetime`
