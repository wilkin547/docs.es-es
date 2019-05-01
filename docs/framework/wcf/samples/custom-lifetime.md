---
title: Vigencia personalizada
ms.date: 08/20/2018
ms.assetid: 52806c07-b91c-48fe-b992-88a41924f51f
ms.openlocfilehash: be6013d568e3625c5eac7e0c145db7df1c6917e3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62003170"
---
# <a name="custom-lifetime"></a><span data-ttu-id="f54e6-102">Vigencia personalizada</span><span class="sxs-lookup"><span data-stu-id="f54e6-102">Custom lifetime</span></span>

<span data-ttu-id="f54e6-103">Este ejemplo muestra cómo escribir una extensión de Windows Communication Foundation (WCF) para proporcionar servicios de duración personalizados para las instancias de servicio compartidas de WCF.</span><span class="sxs-lookup"><span data-stu-id="f54e6-103">This sample demonstrates how to write a Windows Communication Foundation (WCF) extension to provide custom lifetime services for shared WCF service instances.</span></span>

> [!NOTE]
> <span data-ttu-id="f54e6-104">El procedimiento de configuración y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="f54e6-104">The setup procedure and build instructions for this sample are located at the end of this article.</span></span>

## <a name="shared-instancing"></a><span data-ttu-id="f54e6-105">Creación de instancias compartidas</span><span class="sxs-lookup"><span data-stu-id="f54e6-105">Shared instancing</span></span>

<span data-ttu-id="f54e6-106">WCF ofrece varios modos de creación de instancias para las instancias de servicio.</span><span class="sxs-lookup"><span data-stu-id="f54e6-106">WCF offers several instancing modes for your service instances.</span></span> <span data-ttu-id="f54e6-107">El modo de creación de instancias compartido descrito en este artículo proporciona una manera de compartir una instancia de servicio entre varios canales.</span><span class="sxs-lookup"><span data-stu-id="f54e6-107">The shared instancing mode covered in this article provides a way to share a service instance between multiple channels.</span></span> <span data-ttu-id="f54e6-108">Los clientes pueden ponerse en contacto con un método de fábrica en el servicio y crear un nuevo canal para iniciar la comunicación.</span><span class="sxs-lookup"><span data-stu-id="f54e6-108">Clients can contact a factory method in the service and create a new channel to start communication.</span></span> <span data-ttu-id="f54e6-109">El fragmento de código siguiente muestra cómo una aplicación cliente crea un nuevo canal en una instancia de servicio existente:</span><span class="sxs-lookup"><span data-stu-id="f54e6-109">The following code snippet shows how a client application creates a new channel to an existing service instance:</span></span>

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

<span data-ttu-id="f54e6-110">A diferencia de los demás modos de creación de instancias, el modo de creación de instancias compartido tiene una sola manera de liberar las instancias de servicio.</span><span class="sxs-lookup"><span data-stu-id="f54e6-110">Unlike other instancing modes, the shared instancing mode has a unique way of releasing the service instances.</span></span> <span data-ttu-id="f54e6-111">De forma predeterminada, cuando se cierran todos los canales para un <xref:System.ServiceModel.InstanceContext>, el runtime del servicio WCF que se comprueba para ver si el servicio <xref:System.ServiceModel.InstanceContextMode> está configurado para <xref:System.ServiceModel.InstanceContextMode.PerCall> o <xref:System.ServiceModel.InstanceContextMode.PerSession>y si por lo que libera la instancia y reclama los recursos.</span><span class="sxs-lookup"><span data-stu-id="f54e6-111">By default, when all the channels are closed for an <xref:System.ServiceModel.InstanceContext>, the WCF service runtime checks to see if the service <xref:System.ServiceModel.InstanceContextMode> is configured to <xref:System.ServiceModel.InstanceContextMode.PerCall> or <xref:System.ServiceModel.InstanceContextMode.PerSession>, and if so releases the instance and claims the resources.</span></span> <span data-ttu-id="f54e6-112">Si un personalizado <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> es emplean, WCF invoca el <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> método de la implementación del proveedor antes de liberar la instancia.</span><span class="sxs-lookup"><span data-stu-id="f54e6-112">If a custom <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> is being used, WCF invokes the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method of the provider implementation before releasing the instance.</span></span> <span data-ttu-id="f54e6-113">Si <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> devuelve `true` , de lo contrario, se libera la instancia de la <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementación es responsable de notificar la `Dispatcher` del estado de inactividad mediante un método de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="f54e6-113">If <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> returns `true` the instance is released, otherwise the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementation is responsible for notifying the `Dispatcher` of the idle state by using a callback method.</span></span> <span data-ttu-id="f54e6-114">Esto se realiza mediante una llamada a la <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A> método del proveedor.</span><span class="sxs-lookup"><span data-stu-id="f54e6-114">This is done by calling the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A> method of the provider.</span></span>

<span data-ttu-id="f54e6-115">Este ejemplo muestra cómo se puede retrasar la liberación de la <xref:System.ServiceModel.InstanceContext> con un tiempo de inactividad de 20 segundos.</span><span class="sxs-lookup"><span data-stu-id="f54e6-115">This sample demonstrates how you can delay releasing the <xref:System.ServiceModel.InstanceContext> with an idle timeout of 20 seconds.</span></span>

## <a name="extending-the-instancecontext"></a><span data-ttu-id="f54e6-116">Ampliar InstanceContext</span><span class="sxs-lookup"><span data-stu-id="f54e6-116">Extending the InstanceContext</span></span>

<span data-ttu-id="f54e6-117">En WCF, <xref:System.ServiceModel.InstanceContext> es el vínculo entre la instancia de servicio y el `Dispatcher`.</span><span class="sxs-lookup"><span data-stu-id="f54e6-117">In WCF, <xref:System.ServiceModel.InstanceContext> is the link between the service instance and the `Dispatcher`.</span></span> <span data-ttu-id="f54e6-118">WCF permite ampliar este componente en tiempo de ejecución al agregar el nuevo estado o comportamiento usando su patrón de objeto extensible.</span><span class="sxs-lookup"><span data-stu-id="f54e6-118">WCF allows you to extend this runtime component by adding new state or behavior by using its extensible object pattern.</span></span> <span data-ttu-id="f54e6-119">El patrón de objeto extensible se utiliza en WCF para extender las clases en tiempo de ejecución existentes con nueva funcionalidad o agregar nuevas características del estado a un objeto.</span><span class="sxs-lookup"><span data-stu-id="f54e6-119">The extensible object pattern is used in WCF to either extend existing runtime classes with new functionality or to add new state features to an object.</span></span> <span data-ttu-id="f54e6-120">Hay tres interfaces en el patrón de objeto extensible: <xref:System.ServiceModel.IExtensibleObject%601>, <xref:System.ServiceModel.IExtension%601>y <xref:System.ServiceModel.IExtensionCollection%601>.</span><span class="sxs-lookup"><span data-stu-id="f54e6-120">There are three interfaces in the extensible object pattern: <xref:System.ServiceModel.IExtensibleObject%601>, <xref:System.ServiceModel.IExtension%601>, and <xref:System.ServiceModel.IExtensionCollection%601>.</span></span>

<span data-ttu-id="f54e6-121">El <xref:System.ServiceModel.IExtensibleObject%601> objetos para permitir las extensiones que personalicen su funcionalidad implementan la interfaz.</span><span class="sxs-lookup"><span data-stu-id="f54e6-121">The <xref:System.ServiceModel.IExtensibleObject%601> interface is implemented by objects to allow extensions that customize their functionality.</span></span>

<span data-ttu-id="f54e6-122">La interfaz <xref:System.ServiceModel.IExtension%601> se implementa mediante objetos que pueden ser extensiones de clases de tipo `T`.</span><span class="sxs-lookup"><span data-stu-id="f54e6-122">The <xref:System.ServiceModel.IExtension%601> interface is implemented by objects that can be extensions of classes of type `T`.</span></span>

<span data-ttu-id="f54e6-123">Y, finalmente, el <xref:System.ServiceModel.IExtensionCollection%601> interfaz es una colección de <xref:System.ServiceModel.IExtension%601> implementaciones que permite la recuperación de una implementación de <xref:System.ServiceModel.IExtension%601> por su tipo.</span><span class="sxs-lookup"><span data-stu-id="f54e6-123">And finally, the <xref:System.ServiceModel.IExtensionCollection%601> interface is a collection of <xref:System.ServiceModel.IExtension%601> implementations that allows for retrieving an implementation of <xref:System.ServiceModel.IExtension%601> by their type.</span></span>

<span data-ttu-id="f54e6-124">Por lo tanto, con el fin de ampliar la <xref:System.ServiceModel.InstanceContext>, debe implementar la <xref:System.ServiceModel.IExtension%601> interfaz.</span><span class="sxs-lookup"><span data-stu-id="f54e6-124">Therefore, in order to extend the <xref:System.ServiceModel.InstanceContext>, you must implement the <xref:System.ServiceModel.IExtension%601> interface.</span></span> <span data-ttu-id="f54e6-125">En este proyecto de ejemplo, el `CustomLeaseExtension` clase contiene esta implementación.</span><span class="sxs-lookup"><span data-stu-id="f54e6-125">In this sample project, the `CustomLeaseExtension` class contains this implementation.</span></span>

```csharp
class CustomLeaseExtension : IExtension<InstanceContext>
{
}
```

<span data-ttu-id="f54e6-126">La interfaz <xref:System.ServiceModel.IExtension%601> tiene dos métodos: <xref:System.ServiceModel.IExtension%601.Attach%2A> y <xref:System.ServiceModel.IExtension%601.Detach%2A>.</span><span class="sxs-lookup"><span data-stu-id="f54e6-126">The <xref:System.ServiceModel.IExtension%601> interface has two methods <xref:System.ServiceModel.IExtension%601.Attach%2A> and <xref:System.ServiceModel.IExtension%601.Detach%2A>.</span></span> <span data-ttu-id="f54e6-127">Como sus nombres indican, se llama a estos dos métodos cuando el tiempo de ejecución asocia y desasocia la extensión a una instancia de la clase <xref:System.ServiceModel.InstanceContext>.</span><span class="sxs-lookup"><span data-stu-id="f54e6-127">As their names imply, these two methods are called when the runtime attaches and detaches the extension to an instance of the <xref:System.ServiceModel.InstanceContext> class.</span></span> <span data-ttu-id="f54e6-128">En este ejemplo, el método `Attach` se usa para realizar un seguimiento del objeto <xref:System.ServiceModel.InstanceContext> que pertenece a la instancia actual de la extensión.</span><span class="sxs-lookup"><span data-stu-id="f54e6-128">In this sample, the `Attach` method is used to keep track of the <xref:System.ServiceModel.InstanceContext> object that belongs to the current instance of the extension.</span></span>

```csharp
InstanceContext owner;

public void Attach(InstanceContext owner)
{
    this.owner = owner;
}
```

<span data-ttu-id="f54e6-129">Además, debe agregar la implementación necesaria a la extensión para proporcionar compatibilidad con la duración extendida.</span><span class="sxs-lookup"><span data-stu-id="f54e6-129">In addition, you must add the necessary implementation to the extension to provide the extended lifetime support.</span></span> <span data-ttu-id="f54e6-130">Por lo tanto, el `ICustomLease` interfaz se declara con los métodos deseados y se implementa en el `CustomLeaseExtension` clase.</span><span class="sxs-lookup"><span data-stu-id="f54e6-130">Therefore, the `ICustomLease` interface is declared with the desired methods and is implemented in the `CustomLeaseExtension` class.</span></span>

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

<span data-ttu-id="f54e6-131">Cuando se invoca WCF la <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> método en el <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementación, esta llamada se enruta a la <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> método de la `CustomLeaseExtension`.</span><span class="sxs-lookup"><span data-stu-id="f54e6-131">When WCF invokes the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method in the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementation, this call is routed to the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method of the `CustomLeaseExtension`.</span></span> <span data-ttu-id="f54e6-132">A continuación, la `CustomLeaseExtension` comprueba su estado privado para ver si el <xref:System.ServiceModel.InstanceContext> está inactivo.</span><span class="sxs-lookup"><span data-stu-id="f54e6-132">Then, the `CustomLeaseExtension` checks its private state to see whether the <xref:System.ServiceModel.InstanceContext> is idle.</span></span> <span data-ttu-id="f54e6-133">Si está inactiva, devuelve `true`.</span><span class="sxs-lookup"><span data-stu-id="f54e6-133">If it is idle, it returns `true`.</span></span> <span data-ttu-id="f54e6-134">De lo contrario, inicia un temporizador con la duración extendida especificada.</span><span class="sxs-lookup"><span data-stu-id="f54e6-134">Otherwise, it starts a timer for a specified amount of extended lifetime.</span></span>

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

<span data-ttu-id="f54e6-135">En el temporizador `Elapsed` evento, se llama a la función de devolución de llamada en el distribuidor para iniciar otro ciclo de limpieza.</span><span class="sxs-lookup"><span data-stu-id="f54e6-135">In the timer’s `Elapsed` event, the callback function in the Dispatcher is called in order to start another clean-up cycle.</span></span>

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

<span data-ttu-id="f54e6-136">No hay ninguna manera de renovar el temporizador en ejecución cuando llega un mensaje nuevo para la instancia que se mueven al estado inactivo.</span><span class="sxs-lookup"><span data-stu-id="f54e6-136">There's no way to renew the running timer when a new message arrives for the instance being moved to the idle state.</span></span>

<span data-ttu-id="f54e6-137">En el ejemplo se implementa <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> para interceptar las llamadas al método <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> y enrutarlas a `CustomLeaseExtension`.</span><span class="sxs-lookup"><span data-stu-id="f54e6-137">The sample implements <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> to intercept the calls to the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method and route them to the `CustomLeaseExtension`.</span></span> <span data-ttu-id="f54e6-138">La implementación de <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> está contenida en la clase `CustomLifetimeLease`.</span><span class="sxs-lookup"><span data-stu-id="f54e6-138">The <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementation is contained in `CustomLifetimeLease` class.</span></span> <span data-ttu-id="f54e6-139">El <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> método se invoca cuando WCF está a punto de liberar la instancia de servicio.</span><span class="sxs-lookup"><span data-stu-id="f54e6-139">The <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method is invoked when WCF is about to release the service instance.</span></span> <span data-ttu-id="f54e6-140">Sin embargo, solo hay una instancia de una implementación de `ISharedSessionInstance` determinada en la colección de propiedades <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> de ServiceBehavior.</span><span class="sxs-lookup"><span data-stu-id="f54e6-140">However, there is only one instance of a particular `ISharedSessionInstance` implementation in the ServiceBehavior’s <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> collection.</span></span> <span data-ttu-id="f54e6-141">Esto significa que no hay ninguna manera de saber si el <xref:System.ServiceModel.InstanceContext> está cerrado en el momento en que WCF comprueba el <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> método.</span><span class="sxs-lookup"><span data-stu-id="f54e6-141">This means there's no way of knowing if the <xref:System.ServiceModel.InstanceContext> is closed at the time WCF checks the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method.</span></span> <span data-ttu-id="f54e6-142">Por lo tanto, este ejemplo utiliza el bloqueo de subprocesos para serializar las solicitudes a la <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> método.</span><span class="sxs-lookup"><span data-stu-id="f54e6-142">Therefore, this sample uses thread locking to serialize requests to the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f54e6-143">El uso del bloqueo de subprocesos no es una solución recomendada porque la serialización puede afectar de forma grave al rendimiento de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f54e6-143">Using thread locking is not a recommended approach because serialization can severely affect the performance of your application.</span></span>

<span data-ttu-id="f54e6-144">Se usa un campo de miembro privado en la `CustomLifetimeLease` clase para realizar un seguimiento del estado de inactividad y es devuelto por la <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> método.</span><span class="sxs-lookup"><span data-stu-id="f54e6-144">A private member field is used in the `CustomLifetimeLease` class to track the idle state and is returned by the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method.</span></span> <span data-ttu-id="f54e6-145">Cada vez que el <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> se invoca el `isIdle` campo se devuelve y se restablece a `false`.</span><span class="sxs-lookup"><span data-stu-id="f54e6-145">Each time the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method is called, the `isIdle` field is returned and reset to `false`.</span></span>  <span data-ttu-id="f54e6-146">Es esencial establecer este valor en `false` para asegurarse de que el Distribuidor llama al método <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A>.</span><span class="sxs-lookup"><span data-stu-id="f54e6-146">It is essential to set this value to `false` in order to make sure the Dispatcher calls the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A> method.</span></span>

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

<span data-ttu-id="f54e6-147">Si el <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A?displayProperty=nameWithType> devuelve del método `false`, el distribuidor registra una función de devolución de llamada utilizando el <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A> método.</span><span class="sxs-lookup"><span data-stu-id="f54e6-147">If the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A?displayProperty=nameWithType> method returns `false`, the Dispatcher registers a callback function by using the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A> method.</span></span> <span data-ttu-id="f54e6-148">Este método recibe una referencia al <xref:System.ServiceModel.InstanceContext> que se va a liberar.</span><span class="sxs-lookup"><span data-stu-id="f54e6-148">This method receives a reference to the <xref:System.ServiceModel.InstanceContext> being released.</span></span> <span data-ttu-id="f54e6-149">Por lo tanto, puede consultar el código de ejemplo la `ICustomLease` escribir extensión y comprobar la `ICustomLease.IsIdle` propiedad en el estado extendido.</span><span class="sxs-lookup"><span data-stu-id="f54e6-149">Therefore, the sample code can query the `ICustomLease` type extension and check the `ICustomLease.IsIdle` property in the extended state.</span></span>

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

<span data-ttu-id="f54e6-150">Antes de la `ICustomLease.IsIdle` propiedad está activada, la propiedad de devolución de llamada debe establecerse como esto es esencial para `CustomLeaseExtension` notifique al distribuidor cuando esté inactivo.</span><span class="sxs-lookup"><span data-stu-id="f54e6-150">Before the `ICustomLease.IsIdle` property is checked, the Callback property needs to be set as this is essential for `CustomLeaseExtension` to notify the Dispatcher when it becomes idle.</span></span> <span data-ttu-id="f54e6-151">Si `ICustomLease.IsIdle` devuelve `true`, el miembro privado `isIdle` simplemente se establece en `CustomLifetimeLease` como `true` y llama al método de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="f54e6-151">If `ICustomLease.IsIdle` returns `true`, the `isIdle` private member is simply set in `CustomLifetimeLease` to `true` and calls the callback method.</span></span> <span data-ttu-id="f54e6-152">Dado que el código contiene un bloqueo, otros subprocesos no pueden cambiar el valor de este miembro privado.</span><span class="sxs-lookup"><span data-stu-id="f54e6-152">Because the code holds a lock, other threads can't change the value of this private member.</span></span> <span data-ttu-id="f54e6-153">Y la próxima vez que se llama al distribuidor la <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A?displayProperty=nameWithType>, devuelve `true` y permite que el distribuidor libere la instancia.</span><span class="sxs-lookup"><span data-stu-id="f54e6-153">And the next time Dispatcher calls the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A?displayProperty=nameWithType>, it returns `true` and lets Dispatcher release the instance.</span></span>

<span data-ttu-id="f54e6-154">Ahora que el fundamento de la extensión personalizada está completado, tiene que enlazarse con el modelo de servicio.</span><span class="sxs-lookup"><span data-stu-id="f54e6-154">Now that the groundwork for the custom extension is completed, it has to be hooked up to the service model.</span></span> <span data-ttu-id="f54e6-155">Para enlazar el `CustomLeaseExtension` implementación para el <xref:System.ServiceModel.InstanceContext>, WCF proporciona el <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer> interfaz para realizar el arranque de <xref:System.ServiceModel.InstanceContext>.</span><span class="sxs-lookup"><span data-stu-id="f54e6-155">To hook up the `CustomLeaseExtension` implementation to the <xref:System.ServiceModel.InstanceContext>, WCF provides the <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer> interface to perform the bootstrapping of <xref:System.ServiceModel.InstanceContext>.</span></span> <span data-ttu-id="f54e6-156">En el ejemplo, la clase `CustomLeaseInitializer` implementa esta interfaz y agrega una instancia de `CustomLeaseExtension` a la colección de la propiedad <xref:System.ServiceModel.InstanceContext.Extensions%2A> desde la única inicialización del método.</span><span class="sxs-lookup"><span data-stu-id="f54e6-156">In the sample, the `CustomLeaseInitializer` class implements this interface and adds an instance of `CustomLeaseExtension` to the <xref:System.ServiceModel.InstanceContext.Extensions%2A> collection from the only method initialization.</span></span> <span data-ttu-id="f54e6-157">El Distribuidor llama a este método inicializando la instancia de <xref:System.ServiceModel.InstanceContext>.</span><span class="sxs-lookup"><span data-stu-id="f54e6-157">This method is called by Dispatcher while initializing the <xref:System.ServiceModel.InstanceContext>.</span></span>

```csharp
public void InitializeInstanceContext(InstanceContext instanceContext,
    System.ServiceModel.Channels.Message message, IContextChannel channel)

    //...

    IExtension<InstanceContext> customLeaseExtension =
        new CustomLeaseExtension(timeout, headerId);
    instanceContext.Extensions.Add(customLeaseExtension);
}
```

 <span data-ttu-id="f54e6-158">Por último el <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementación está enlazada al modelo de servicio mediante el uso de la <xref:System.ServiceModel.Description.IServiceBehavior> implementación.</span><span class="sxs-lookup"><span data-stu-id="f54e6-158">Finally the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementation is hooked up to the service model by using the <xref:System.ServiceModel.Description.IServiceBehavior> implementation.</span></span> <span data-ttu-id="f54e6-159">Esta implementación se coloca en la clase `CustomLeaseTimeAttribute` y también deriva de la clase base <xref:System.Attribute> para exponer este comportamiento como un atributo.</span><span class="sxs-lookup"><span data-stu-id="f54e6-159">This implementation is placed in the `CustomLeaseTimeAttribute` class and it also derives from the <xref:System.Attribute> base class to expose this behavior as an attribute.</span></span>

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

<span data-ttu-id="f54e6-160">Este comportamiento se puede agregar a una clase de servicio de ejemplo agregándolo con el atributo `CustomLeaseTime`.</span><span class="sxs-lookup"><span data-stu-id="f54e6-160">This behavior can be added to a sample service class by annotating it with the `CustomLeaseTime` attribute.</span></span>

```csharp
[CustomLeaseTime(Timeout = 20000)]
public class EchoService : IEchoService
{
  //…
}
```

<span data-ttu-id="f54e6-161">Al ejecutar el ejemplo, las solicitudes y las respuestas de operación se muestran tanto en la ventanas de la consola del cliente como del servicio.</span><span class="sxs-lookup"><span data-stu-id="f54e6-161">When you run the sample, the operation requests and responses are displayed in both the service and client console windows.</span></span> <span data-ttu-id="f54e6-162">Presione Entrar en cada ventana de la consola para cerrar el servicio y el cliente.</span><span class="sxs-lookup"><span data-stu-id="f54e6-162">Press ENTER in each console window to shut down the service and client.</span></span>

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="f54e6-163">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="f54e6-163">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="f54e6-164">Asegúrese de que ha realizado la [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="f54e6-164">Ensure that you've performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="f54e6-165">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="f54e6-165">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

3. <span data-ttu-id="f54e6-166">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecutando los ejemplos de Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="f54e6-166">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f54e6-167">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="f54e6-167">The samples may already be installed on your machine.</span></span> <span data-ttu-id="f54e6-168">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="f54e6-168">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="f54e6-169">Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="f54e6-169">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f54e6-170">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="f54e6-170">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Instancing\Lifetime`
