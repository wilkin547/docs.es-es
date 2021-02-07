---
description: 'Más información acerca de: vigencia personalizada'
title: Vigencia personalizada
ms.date: 08/20/2018
ms.assetid: 52806c07-b91c-48fe-b992-88a41924f51f
ms.openlocfilehash: 24845aaa20e60f92e2add568c81ab3d6502ebedf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99732480"
---
# <a name="custom-lifetime"></a><span data-ttu-id="1d4e3-103">Vigencia personalizada</span><span class="sxs-lookup"><span data-stu-id="1d4e3-103">Custom lifetime</span></span>

<span data-ttu-id="1d4e3-104">Este ejemplo muestra cómo escribir una extensión de Windows Communication Foundation (WCF) para proporcionar servicios de duración personalizados para las instancias de servicio WCF compartidas.</span><span class="sxs-lookup"><span data-stu-id="1d4e3-104">This sample demonstrates how to write a Windows Communication Foundation (WCF) extension to provide custom lifetime services for shared WCF service instances.</span></span>

> [!NOTE]
> <span data-ttu-id="1d4e3-105">El procedimiento de configuración y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="1d4e3-105">The setup procedure and build instructions for this sample are located at the end of this article.</span></span>

## <a name="shared-instancing"></a><span data-ttu-id="1d4e3-106">Instancias compartidas</span><span class="sxs-lookup"><span data-stu-id="1d4e3-106">Shared instancing</span></span>

<span data-ttu-id="1d4e3-107">WCF ofrece varios modos de creación de instancias para las instancias de servicio.</span><span class="sxs-lookup"><span data-stu-id="1d4e3-107">WCF offers several instancing modes for your service instances.</span></span> <span data-ttu-id="1d4e3-108">El modo de creación de instancias compartido que se trata en este artículo proporciona una manera de compartir una instancia de servicio entre varios canales.</span><span class="sxs-lookup"><span data-stu-id="1d4e3-108">The shared instancing mode covered in this article provides a way to share a service instance between multiple channels.</span></span> <span data-ttu-id="1d4e3-109">Los clientes pueden ponerse en contacto con un Factory Method del servicio y crear un nuevo canal para iniciar la comunicación.</span><span class="sxs-lookup"><span data-stu-id="1d4e3-109">Clients can contact a factory method in the service and create a new channel to start communication.</span></span> <span data-ttu-id="1d4e3-110">En el fragmento de código siguiente se muestra cómo una aplicación cliente crea un canal nuevo en una instancia de servicio existente:</span><span class="sxs-lookup"><span data-stu-id="1d4e3-110">The following code snippet shows how a client application creates a new channel to an existing service instance:</span></span>

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

<span data-ttu-id="1d4e3-111">A diferencia de los demás modos de creación de instancias, el modo de creación de instancias compartido tiene una sola manera de liberar las instancias de servicio.</span><span class="sxs-lookup"><span data-stu-id="1d4e3-111">Unlike other instancing modes, the shared instancing mode has a unique way of releasing the service instances.</span></span> <span data-ttu-id="1d4e3-112">De forma predeterminada, cuando todos los canales están cerrados para un <xref:System.ServiceModel.InstanceContext> , el tiempo de ejecución del servicio WCF comprueba si el servicio <xref:System.ServiceModel.InstanceContextMode> está configurado para <xref:System.ServiceModel.InstanceContextMode.PerCall> o <xref:System.ServiceModel.InstanceContextMode.PerSession> , y si es así, libera la instancia y notifica los recursos.</span><span class="sxs-lookup"><span data-stu-id="1d4e3-112">By default, when all the channels are closed for an <xref:System.ServiceModel.InstanceContext>, the WCF service runtime checks to see if the service <xref:System.ServiceModel.InstanceContextMode> is configured to <xref:System.ServiceModel.InstanceContextMode.PerCall> or <xref:System.ServiceModel.InstanceContextMode.PerSession>, and if so releases the instance and claims the resources.</span></span> <span data-ttu-id="1d4e3-113">Si <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> se utiliza un personalizado, WCF invoca el <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> método de la implementación del proveedor antes de liberar la instancia.</span><span class="sxs-lookup"><span data-stu-id="1d4e3-113">If a custom <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> is being used, WCF invokes the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method of the provider implementation before releasing the instance.</span></span> <span data-ttu-id="1d4e3-114">Si <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> devuelve `true` , se libera la instancia de; en caso contrario, la <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementación es responsable de notificar el `Dispatcher` del estado de inactividad mediante un método de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="1d4e3-114">If <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> returns `true` the instance is released, otherwise the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementation is responsible for notifying the `Dispatcher` of the idle state by using a callback method.</span></span> <span data-ttu-id="1d4e3-115">Esto se hace llamando al <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A> método del proveedor.</span><span class="sxs-lookup"><span data-stu-id="1d4e3-115">This is done by calling the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A> method of the provider.</span></span>

<span data-ttu-id="1d4e3-116">Este ejemplo muestra cómo se puede retrasar la liberación del <xref:System.ServiceModel.InstanceContext> con un tiempo de espera de inactividad de 20 segundos.</span><span class="sxs-lookup"><span data-stu-id="1d4e3-116">This sample demonstrates how you can delay releasing the <xref:System.ServiceModel.InstanceContext> with an idle timeout of 20 seconds.</span></span>

## <a name="extending-the-instancecontext"></a><span data-ttu-id="1d4e3-117">Ampliar InstanceContext</span><span class="sxs-lookup"><span data-stu-id="1d4e3-117">Extending the InstanceContext</span></span>

<span data-ttu-id="1d4e3-118">En WCF, <xref:System.ServiceModel.InstanceContext> es el vínculo entre la instancia de servicio y el `Dispatcher` .</span><span class="sxs-lookup"><span data-stu-id="1d4e3-118">In WCF, <xref:System.ServiceModel.InstanceContext> is the link between the service instance and the `Dispatcher`.</span></span> <span data-ttu-id="1d4e3-119">WCF le permite ampliar este componente en tiempo de ejecución agregando nuevo estado o comportamiento mediante su patrón de objeto extensible.</span><span class="sxs-lookup"><span data-stu-id="1d4e3-119">WCF allows you to extend this runtime component by adding new state or behavior by using its extensible object pattern.</span></span> <span data-ttu-id="1d4e3-120">El patrón de objeto extensible se utiliza en WCF para ampliar las clases en tiempo de ejecución existentes con nueva funcionalidad o agregar nuevas características de estado a un objeto.</span><span class="sxs-lookup"><span data-stu-id="1d4e3-120">The extensible object pattern is used in WCF to either extend existing runtime classes with new functionality or to add new state features to an object.</span></span> <span data-ttu-id="1d4e3-121">Hay tres interfaces en el patrón de objeto extensible: <xref:System.ServiceModel.IExtensibleObject%601>, <xref:System.ServiceModel.IExtension%601>y <xref:System.ServiceModel.IExtensionCollection%601>.</span><span class="sxs-lookup"><span data-stu-id="1d4e3-121">There are three interfaces in the extensible object pattern: <xref:System.ServiceModel.IExtensibleObject%601>, <xref:System.ServiceModel.IExtension%601>, and <xref:System.ServiceModel.IExtensionCollection%601>.</span></span>

<span data-ttu-id="1d4e3-122">La <xref:System.ServiceModel.IExtensibleObject%601> interfaz se implementa mediante objetos para permitir extensiones que personalizan su funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="1d4e3-122">The <xref:System.ServiceModel.IExtensibleObject%601> interface is implemented by objects to allow extensions that customize their functionality.</span></span>

<span data-ttu-id="1d4e3-123">La interfaz <xref:System.ServiceModel.IExtension%601> se implementa mediante objetos que pueden ser extensiones de clases de tipo `T`.</span><span class="sxs-lookup"><span data-stu-id="1d4e3-123">The <xref:System.ServiceModel.IExtension%601> interface is implemented by objects that can be extensions of classes of type `T`.</span></span>

<span data-ttu-id="1d4e3-124">Y, por último, la <xref:System.ServiceModel.IExtensionCollection%601> interfaz es una colección de <xref:System.ServiceModel.IExtension%601> implementaciones que permite recuperar una implementación de <xref:System.ServiceModel.IExtension%601> por su tipo.</span><span class="sxs-lookup"><span data-stu-id="1d4e3-124">And finally, the <xref:System.ServiceModel.IExtensionCollection%601> interface is a collection of <xref:System.ServiceModel.IExtension%601> implementations that allows for retrieving an implementation of <xref:System.ServiceModel.IExtension%601> by their type.</span></span>

<span data-ttu-id="1d4e3-125">Por lo tanto, para extender el <xref:System.ServiceModel.InstanceContext> , debe implementar la <xref:System.ServiceModel.IExtension%601> interfaz.</span><span class="sxs-lookup"><span data-stu-id="1d4e3-125">Therefore, in order to extend the <xref:System.ServiceModel.InstanceContext>, you must implement the <xref:System.ServiceModel.IExtension%601> interface.</span></span> <span data-ttu-id="1d4e3-126">En este proyecto de ejemplo, la `CustomLeaseExtension` clase contiene esta implementación.</span><span class="sxs-lookup"><span data-stu-id="1d4e3-126">In this sample project, the `CustomLeaseExtension` class contains this implementation.</span></span>

```csharp
class CustomLeaseExtension : IExtension<InstanceContext>
{
}
```

<span data-ttu-id="1d4e3-127">La interfaz <xref:System.ServiceModel.IExtension%601> tiene dos métodos: <xref:System.ServiceModel.IExtension%601.Attach%2A> y <xref:System.ServiceModel.IExtension%601.Detach%2A>.</span><span class="sxs-lookup"><span data-stu-id="1d4e3-127">The <xref:System.ServiceModel.IExtension%601> interface has two methods <xref:System.ServiceModel.IExtension%601.Attach%2A> and <xref:System.ServiceModel.IExtension%601.Detach%2A>.</span></span> <span data-ttu-id="1d4e3-128">Como sus nombres indican, se llama a estos dos métodos cuando el tiempo de ejecución asocia y desasocia la extensión a una instancia de la clase <xref:System.ServiceModel.InstanceContext>.</span><span class="sxs-lookup"><span data-stu-id="1d4e3-128">As their names imply, these two methods are called when the runtime attaches and detaches the extension to an instance of the <xref:System.ServiceModel.InstanceContext> class.</span></span> <span data-ttu-id="1d4e3-129">En este ejemplo, el método `Attach` se usa para realizar un seguimiento del objeto <xref:System.ServiceModel.InstanceContext> que pertenece a la instancia actual de la extensión.</span><span class="sxs-lookup"><span data-stu-id="1d4e3-129">In this sample, the `Attach` method is used to keep track of the <xref:System.ServiceModel.InstanceContext> object that belongs to the current instance of the extension.</span></span>

```csharp
InstanceContext owner;

public void Attach(InstanceContext owner)
{
    this.owner = owner;
}
```

<span data-ttu-id="1d4e3-130">Además, debe agregar la implementación necesaria a la extensión para proporcionar compatibilidad con la duración extendida.</span><span class="sxs-lookup"><span data-stu-id="1d4e3-130">In addition, you must add the necessary implementation to the extension to provide the extended lifetime support.</span></span> <span data-ttu-id="1d4e3-131">Por consiguiente, la `ICustomLease` interfaz se declara con los métodos deseados y se implementa en la `CustomLeaseExtension` clase.</span><span class="sxs-lookup"><span data-stu-id="1d4e3-131">Therefore, the `ICustomLease` interface is declared with the desired methods and is implemented in the `CustomLeaseExtension` class.</span></span>

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

<span data-ttu-id="1d4e3-132">Cuando WCF invoca el <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> método en la <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementación, esta llamada se enruta al <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> método de `CustomLeaseExtension` .</span><span class="sxs-lookup"><span data-stu-id="1d4e3-132">When WCF invokes the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method in the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementation, this call is routed to the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method of the `CustomLeaseExtension`.</span></span> <span data-ttu-id="1d4e3-133">A continuación, `CustomLeaseExtension` comprueba su estado privado para ver si <xref:System.ServiceModel.InstanceContext> está inactivo.</span><span class="sxs-lookup"><span data-stu-id="1d4e3-133">Then, the `CustomLeaseExtension` checks its private state to see whether the <xref:System.ServiceModel.InstanceContext> is idle.</span></span> <span data-ttu-id="1d4e3-134">Si está inactivo, devuelve `true` .</span><span class="sxs-lookup"><span data-stu-id="1d4e3-134">If it is idle, it returns `true`.</span></span> <span data-ttu-id="1d4e3-135">De lo contrario, inicia un temporizador con la duración extendida especificada.</span><span class="sxs-lookup"><span data-stu-id="1d4e3-135">Otherwise, it starts a timer for a specified amount of extended lifetime.</span></span>

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

<span data-ttu-id="1d4e3-136">En el evento del temporizador `Elapsed` , se llama a la función de devolución de llamada en el distribuidor para iniciar otro ciclo de limpieza.</span><span class="sxs-lookup"><span data-stu-id="1d4e3-136">In the timer’s `Elapsed` event, the callback function in the Dispatcher is called in order to start another clean-up cycle.</span></span>

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

<span data-ttu-id="1d4e3-137">No hay ninguna manera de renovar el temporizador en ejecución cuando llega un mensaje nuevo para que la instancia se mueva al estado inactivo.</span><span class="sxs-lookup"><span data-stu-id="1d4e3-137">There's no way to renew the running timer when a new message arrives for the instance being moved to the idle state.</span></span>

<span data-ttu-id="1d4e3-138">En el ejemplo se implementa <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> para interceptar las llamadas al método <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> y enrutarlas a `CustomLeaseExtension`.</span><span class="sxs-lookup"><span data-stu-id="1d4e3-138">The sample implements <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> to intercept the calls to the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method and route them to the `CustomLeaseExtension`.</span></span> <span data-ttu-id="1d4e3-139">La implementación de <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> está contenida en la clase `CustomLifetimeLease`.</span><span class="sxs-lookup"><span data-stu-id="1d4e3-139">The <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementation is contained in `CustomLifetimeLease` class.</span></span> <span data-ttu-id="1d4e3-140">El <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> método se invoca cuando WCF está a punto de liberar la instancia de servicio.</span><span class="sxs-lookup"><span data-stu-id="1d4e3-140">The <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method is invoked when WCF is about to release the service instance.</span></span> <span data-ttu-id="1d4e3-141">Sin embargo, solo hay una instancia de una implementación de `ISharedSessionInstance` determinada en la colección de propiedades <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> de ServiceBehavior.</span><span class="sxs-lookup"><span data-stu-id="1d4e3-141">However, there is only one instance of a particular `ISharedSessionInstance` implementation in the ServiceBehavior’s <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> collection.</span></span> <span data-ttu-id="1d4e3-142">Esto significa que no hay ninguna manera de saber si el <xref:System.ServiceModel.InstanceContext> está cerrado en el momento en que WCF comprueba el <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> método.</span><span class="sxs-lookup"><span data-stu-id="1d4e3-142">This means there's no way of knowing if the <xref:System.ServiceModel.InstanceContext> is closed at the time WCF checks the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method.</span></span> <span data-ttu-id="1d4e3-143">Por consiguiente, este ejemplo usa el bloqueo de subprocesos para serializar las solicitudes al <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> método.</span><span class="sxs-lookup"><span data-stu-id="1d4e3-143">Therefore, this sample uses thread locking to serialize requests to the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1d4e3-144">El uso del bloqueo de subprocesos no es una solución recomendada porque la serialización puede afectar de forma grave al rendimiento de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1d4e3-144">Using thread locking is not a recommended approach because serialization can severely affect the performance of your application.</span></span>

<span data-ttu-id="1d4e3-145">Se usa un campo de miembro privado en la `CustomLifetimeLease` clase para realizar un seguimiento del estado de inactividad y lo devuelve el <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> método.</span><span class="sxs-lookup"><span data-stu-id="1d4e3-145">A private member field is used in the `CustomLifetimeLease` class to track the idle state and is returned by the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method.</span></span> <span data-ttu-id="1d4e3-146">Cada vez que <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> se llama al método, `isIdle` se devuelve el campo y se restablece en `false` .</span><span class="sxs-lookup"><span data-stu-id="1d4e3-146">Each time the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method is called, the `isIdle` field is returned and reset to `false`.</span></span>  <span data-ttu-id="1d4e3-147">Es esencial establecer este valor en `false` para asegurarse de que el Distribuidor llama al método <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A>.</span><span class="sxs-lookup"><span data-stu-id="1d4e3-147">It is essential to set this value to `false` in order to make sure the Dispatcher calls the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A> method.</span></span>

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

<span data-ttu-id="1d4e3-148">Si el <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A?displayProperty=nameWithType> método devuelve `false` , el distribuidor registra una función de devolución de llamada mediante el <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A> método.</span><span class="sxs-lookup"><span data-stu-id="1d4e3-148">If the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A?displayProperty=nameWithType> method returns `false`, the Dispatcher registers a callback function by using the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A> method.</span></span> <span data-ttu-id="1d4e3-149">Este método recibe una referencia al <xref:System.ServiceModel.InstanceContext> que se va a liberar.</span><span class="sxs-lookup"><span data-stu-id="1d4e3-149">This method receives a reference to the <xref:System.ServiceModel.InstanceContext> being released.</span></span> <span data-ttu-id="1d4e3-150">Por lo tanto, el código de ejemplo puede consultar la `ICustomLease` extensión de tipo y comprobar la `ICustomLease.IsIdle` propiedad en el estado extendido.</span><span class="sxs-lookup"><span data-stu-id="1d4e3-150">Therefore, the sample code can query the `ICustomLease` type extension and check the `ICustomLease.IsIdle` property in the extended state.</span></span>

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

<span data-ttu-id="1d4e3-151">Antes de que `ICustomLease.IsIdle` se Compruebe la propiedad, debe establecerse la propiedad de devolución de llamada, ya que es esencial para `CustomLeaseExtension` que notifique al distribuidor cuando se vuelve inactiva.</span><span class="sxs-lookup"><span data-stu-id="1d4e3-151">Before the `ICustomLease.IsIdle` property is checked, the Callback property needs to be set as this is essential for `CustomLeaseExtension` to notify the Dispatcher when it becomes idle.</span></span> <span data-ttu-id="1d4e3-152">Si `ICustomLease.IsIdle` devuelve `true`, el miembro privado `isIdle` simplemente se establece en `CustomLifetimeLease` como `true` y llama al método de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="1d4e3-152">If `ICustomLease.IsIdle` returns `true`, the `isIdle` private member is simply set in `CustomLifetimeLease` to `true` and calls the callback method.</span></span> <span data-ttu-id="1d4e3-153">Dado que el código contiene un bloqueo, otros subprocesos no pueden cambiar el valor de este miembro privado.</span><span class="sxs-lookup"><span data-stu-id="1d4e3-153">Because the code holds a lock, other threads can't change the value of this private member.</span></span> <span data-ttu-id="1d4e3-154">Y la próxima vez que el distribuidor llama a <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A?displayProperty=nameWithType> , devuelve `true` y permite que el distribuidor libere la instancia.</span><span class="sxs-lookup"><span data-stu-id="1d4e3-154">And the next time Dispatcher calls the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A?displayProperty=nameWithType>, it returns `true` and lets Dispatcher release the instance.</span></span>

<span data-ttu-id="1d4e3-155">Ahora que el fundamento de la extensión personalizada está completado, tiene que enlazarse con el modelo de servicio.</span><span class="sxs-lookup"><span data-stu-id="1d4e3-155">Now that the groundwork for the custom extension is completed, it has to be hooked up to the service model.</span></span> <span data-ttu-id="1d4e3-156">Para enlazar la `CustomLeaseExtension` implementación a <xref:System.ServiceModel.InstanceContext> , WCF proporciona la <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer> interfaz para realizar el arranque de <xref:System.ServiceModel.InstanceContext> .</span><span class="sxs-lookup"><span data-stu-id="1d4e3-156">To hook up the `CustomLeaseExtension` implementation to the <xref:System.ServiceModel.InstanceContext>, WCF provides the <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer> interface to perform the bootstrapping of <xref:System.ServiceModel.InstanceContext>.</span></span> <span data-ttu-id="1d4e3-157">En el ejemplo, la clase `CustomLeaseInitializer` implementa esta interfaz y agrega una instancia de `CustomLeaseExtension` a la colección de la propiedad <xref:System.ServiceModel.InstanceContext.Extensions%2A> desde la única inicialización del método.</span><span class="sxs-lookup"><span data-stu-id="1d4e3-157">In the sample, the `CustomLeaseInitializer` class implements this interface and adds an instance of `CustomLeaseExtension` to the <xref:System.ServiceModel.InstanceContext.Extensions%2A> collection from the only method initialization.</span></span> <span data-ttu-id="1d4e3-158">El Distribuidor llama a este método inicializando la instancia de <xref:System.ServiceModel.InstanceContext>.</span><span class="sxs-lookup"><span data-stu-id="1d4e3-158">This method is called by Dispatcher while initializing the <xref:System.ServiceModel.InstanceContext>.</span></span>

```csharp
public void InitializeInstanceContext(InstanceContext instanceContext,
    System.ServiceModel.Channels.Message message, IContextChannel channel)

    //...

    IExtension<InstanceContext> customLeaseExtension =
        new CustomLeaseExtension(timeout, headerId);
    instanceContext.Extensions.Add(customLeaseExtension);
}
```

 <span data-ttu-id="1d4e3-159">Por último, la <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementación se enlaza al modelo de servicio mediante la <xref:System.ServiceModel.Description.IServiceBehavior> implementación de.</span><span class="sxs-lookup"><span data-stu-id="1d4e3-159">Finally the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementation is hooked up to the service model by using the <xref:System.ServiceModel.Description.IServiceBehavior> implementation.</span></span> <span data-ttu-id="1d4e3-160">Esta implementación se coloca en la clase `CustomLeaseTimeAttribute` y también deriva de la clase base <xref:System.Attribute> para exponer este comportamiento como un atributo.</span><span class="sxs-lookup"><span data-stu-id="1d4e3-160">This implementation is placed in the `CustomLeaseTimeAttribute` class and it also derives from the <xref:System.Attribute> base class to expose this behavior as an attribute.</span></span>

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

<span data-ttu-id="1d4e3-161">Este comportamiento se puede agregar a una clase de servicio de ejemplo agregándolo con el atributo `CustomLeaseTime`.</span><span class="sxs-lookup"><span data-stu-id="1d4e3-161">This behavior can be added to a sample service class by annotating it with the `CustomLeaseTime` attribute.</span></span>

```csharp
[CustomLeaseTime(Timeout = 20000)]
public class EchoService : IEchoService
{
  //…
}
```

<span data-ttu-id="1d4e3-162">Al ejecutar el ejemplo, las solicitudes y las respuestas de operación se muestran tanto en la ventanas de la consola del cliente como del servicio.</span><span class="sxs-lookup"><span data-stu-id="1d4e3-162">When you run the sample, the operation requests and responses are displayed in both the service and client console windows.</span></span> <span data-ttu-id="1d4e3-163">Presione Entrar en cada ventana de la consola para cerrar el servicio y el cliente.</span><span class="sxs-lookup"><span data-stu-id="1d4e3-163">Press ENTER in each console window to shut down the service and client.</span></span>

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="1d4e3-164">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="1d4e3-164">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="1d4e3-165">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="1d4e3-165">Ensure that you've performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="1d4e3-166">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="1d4e3-166">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

3. <span data-ttu-id="1d4e3-167">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="1d4e3-167">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1d4e3-168">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="1d4e3-168">The samples may already be installed on your machine.</span></span> <span data-ttu-id="1d4e3-169">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="1d4e3-169">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="1d4e3-170">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="1d4e3-170">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="1d4e3-171">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="1d4e3-171">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Instancing\Lifetime`
