---
title: Contexto de instancia duradera
ms.date: 03/30/2017
ms.assetid: 97bc2994-5a2c-47c7-927a-c4cd273153df
ms.openlocfilehash: 604a617dc03bf06b71fe3019b58b2161216ee3e0
ms.sourcegitcommit: 839777281a281684a7e2906dccb3acd7f6a32023
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/24/2020
ms.locfileid: "82141186"
---
# <a name="durable-instance-context"></a><span data-ttu-id="c184a-102">Contexto de instancia duradera</span><span class="sxs-lookup"><span data-stu-id="c184a-102">Durable Instance Context</span></span>

<span data-ttu-id="c184a-103">Este ejemplo muestra cómo personalizar el tiempo de ejecución de Windows Communication Foundation (WCF) para habilitar los contextos de instancia durable.</span><span class="sxs-lookup"><span data-stu-id="c184a-103">This sample demonstrates how to customize the Windows Communication Foundation (WCF) runtime to enable durable instance contexts.</span></span> <span data-ttu-id="c184a-104">Utiliza SQL Server 2005 como su memoria auxiliar (SQL Server 2005 Express en este caso).</span><span class="sxs-lookup"><span data-stu-id="c184a-104">It uses SQL Server 2005 as its backing store (SQL Server 2005 Express in this case).</span></span> <span data-ttu-id="c184a-105">Sin embargo, también proporciona una manera de tener acceso a los mecanismos de almacenamiento personalizados.</span><span class="sxs-lookup"><span data-stu-id="c184a-105">However, it also provides a way to access custom storage mechanisms.</span></span>

> [!NOTE]
> <span data-ttu-id="c184a-106">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="c184a-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

<span data-ttu-id="c184a-107">En este ejemplo se incluye la extensión de la capa de canal y la capa de modelo de servicio de WCF.</span><span class="sxs-lookup"><span data-stu-id="c184a-107">This sample involves extending both the channel layer and the service model layer of the WCF.</span></span> <span data-ttu-id="c184a-108">Por consiguiente, es necesario entender los conceptos subyacentes antes de entrar en los detalles de la implementación.</span><span class="sxs-lookup"><span data-stu-id="c184a-108">Therefore it is necessary to understand the underlying concepts before going into the implementation details.</span></span>

<span data-ttu-id="c184a-109">Los contextos de la instancia duraderos se pueden encontrar bastante a menudo en situaciones reales.</span><span class="sxs-lookup"><span data-stu-id="c184a-109">Durable instance contexts can be found in the real world scenarios quite often.</span></span> <span data-ttu-id="c184a-110">Una aplicación de carro de la compra, por ejemplo, tiene la capacidad de pausar la compra cuando ésta se encuentra a la mitad y continuarla otro día.</span><span class="sxs-lookup"><span data-stu-id="c184a-110">A shopping cart application for example, has the ability to pause shopping halfway through and continue it on another day.</span></span> <span data-ttu-id="c184a-111">Para que cuando visitemos el carro de la compra el día siguiente, se restaure nuestro contexto original.</span><span class="sxs-lookup"><span data-stu-id="c184a-111">So that when we visit the shopping cart the next day, our original context is restored.</span></span> <span data-ttu-id="c184a-112">Es importante tener en cuenta que la aplicación de carro de la compra (en el servidor) no mantiene la instancia del carro de la compra mientras estamos desconectados.</span><span class="sxs-lookup"><span data-stu-id="c184a-112">It is important to note that the shopping cart application (on the server) does not maintain the shopping cart instance while we are disconnected.</span></span> <span data-ttu-id="c184a-113">En su lugar, conserva su estado en medios de almacenamiento duraderos y lo utiliza cuando construye una nueva instancia para el contexto restaurado.</span><span class="sxs-lookup"><span data-stu-id="c184a-113">Instead, it persists its state into a durable storage media and uses it when constructing a new instance for the restored context.</span></span> <span data-ttu-id="c184a-114">Por consiguiente, la instancia del servicio que puede ser de utilidad para el mismo contexto no es igual que la instancia anterior (es decir, no tiene la misma dirección de memoria).</span><span class="sxs-lookup"><span data-stu-id="c184a-114">Therefore the service instance that may service for the same context is not the same as the previous instance (that is, it does not have the same memory address).</span></span>

<span data-ttu-id="c184a-115">Un protocolo pequeño que intercambia un id. de contexto entre el cliente y el servicio posibilita el contexto de la instancia duradera.</span><span class="sxs-lookup"><span data-stu-id="c184a-115">Durable instance context is made possible by a small protocol that exchanges a context ID between the client and service.</span></span> <span data-ttu-id="c184a-116">Este id. de contexto se crea en el cliente y se transmite al servicio.</span><span class="sxs-lookup"><span data-stu-id="c184a-116">This context ID is created on the client and transmitted to the service.</span></span> <span data-ttu-id="c184a-117">Cuando se crea la instancia del servicio, el tiempo de ejecución del servicio intenta cargar el estado conservado que corresponde a este id. de contexto desde un almacenamiento persistente (de forma predeterminada es una base de datos SQL Server 2005).</span><span class="sxs-lookup"><span data-stu-id="c184a-117">When the service instance is created, the service runtime tries to load the persisted state that corresponds to this context ID from a persistent storage (by default it is a SQL Server 2005 database).</span></span> <span data-ttu-id="c184a-118">Si no está disponible ningún estado, la nueva instancia tiene su estado predeterminado.</span><span class="sxs-lookup"><span data-stu-id="c184a-118">If no state is available the new instance has its default state.</span></span> <span data-ttu-id="c184a-119">La implementación del servicio utiliza un atributo personalizado para marcar operaciones que cambian el estado de la implementación del servicio para que el tiempo de ejecución pueda guardar la instancia del servicio después de invocarlos.</span><span class="sxs-lookup"><span data-stu-id="c184a-119">The service implementation uses a custom attribute to mark operations that change the state of the service implementation so that the runtime can save the service instance after invoking them.</span></span>

<span data-ttu-id="c184a-120">Por la descripción anterior, se pueden distinguir con facilidad dos pasos para lograr el objetivo:</span><span class="sxs-lookup"><span data-stu-id="c184a-120">By the previous description, two steps can easily be distinguished to achieve the goal:</span></span>

1. <span data-ttu-id="c184a-121">Cambiar el mensaje en la conexión para llevar el id. de contexto.</span><span class="sxs-lookup"><span data-stu-id="c184a-121">Change the message that goes on the wire to carry the context ID.</span></span>

2. <span data-ttu-id="c184a-122">Cambiar el comportamiento local del servicio para implementar la lógica de creación de instancias personalizada.</span><span class="sxs-lookup"><span data-stu-id="c184a-122">Change the service local behavior to implement custom instancing logic.</span></span>

<span data-ttu-id="c184a-123">Dado que la primera en la lista afecta a los mensajes en la conexión, se debería implementar como un canal personalizado y enlazarse hasta la capa del canal.</span><span class="sxs-lookup"><span data-stu-id="c184a-123">Because the first one in the list affects the messages on the wire it should be implemented as a custom channel and be hooked up to the channel layer.</span></span> <span data-ttu-id="c184a-124">El último solo afecta al comportamiento local del servicio y por consiguiente se puede implementar extendiendo varios puntos de extensibilidad de servicio.</span><span class="sxs-lookup"><span data-stu-id="c184a-124">The latter only affects the service local behavior and therefore can be implemented by extending several service extensibility points.</span></span> <span data-ttu-id="c184a-125">Cada una de estas extensiones se trata en las siguientes secciones.</span><span class="sxs-lookup"><span data-stu-id="c184a-125">In the next few sections, each of these extensions are discussed.</span></span>

## <a name="durable-instancecontext-channel"></a><span data-ttu-id="c184a-126">Canal de InstanceContext duradero</span><span class="sxs-lookup"><span data-stu-id="c184a-126">Durable InstanceContext Channel</span></span>

<span data-ttu-id="c184a-127">Lo primero que se ha de mirar es una extensión de capa de canal.</span><span class="sxs-lookup"><span data-stu-id="c184a-127">The first thing to look at is a channel layer extension.</span></span> <span data-ttu-id="c184a-128">El primer paso en escribir un canal personalizado es decidir la estructura de comunicación del canal.</span><span class="sxs-lookup"><span data-stu-id="c184a-128">The first step in writing a custom channel is to decide the communication structure of the channel.</span></span> <span data-ttu-id="c184a-129">Cuando se introduce un nuevo protocolo de conexión, el canal debería trabajar con casi cualquier otro canal en la pila de canales.</span><span class="sxs-lookup"><span data-stu-id="c184a-129">As a new wire protocol is being introduced the channel should work with almost any other channel in the channel stack.</span></span> <span data-ttu-id="c184a-130">Por consiguiente, debería admitir todos los patrones de intercambio de mensajes.</span><span class="sxs-lookup"><span data-stu-id="c184a-130">Therefore it should support all the message exchange patterns.</span></span> <span data-ttu-id="c184a-131">Sin embargo, la funcionalidad básica del canal es la misma, independientemente de su estructura de comunicación.</span><span class="sxs-lookup"><span data-stu-id="c184a-131">However, the core functionality of the channel is the same regardless of its communication structure.</span></span> <span data-ttu-id="c184a-132">Más específicamente, del cliente debería escribir el id. de contexto a los mensajes y del servicio debería leer este id. de contexto de los mensajes y pasarlo a los niveles superiores.</span><span class="sxs-lookup"><span data-stu-id="c184a-132">More specifically, from the client it should write the context ID to the messages and from the service it should read this context ID from the messages and pass it to the upper levels.</span></span> <span data-ttu-id="c184a-133">Debido a eso, se crea una clase `DurableInstanceContextChannelBase` que actúa como la clase base abstracta para todas las implementaciones de canal de contexto de instancia duraderas.</span><span class="sxs-lookup"><span data-stu-id="c184a-133">Because of that, a `DurableInstanceContextChannelBase` class is created that acts as the abstract base class for all durable instance context channel implementations.</span></span> <span data-ttu-id="c184a-134">Esta clase contiene las funciones de administración de máquina de estado común y dos miembros protegidos para aplicar y leer la información de contexto a y desde los mensajes.</span><span class="sxs-lookup"><span data-stu-id="c184a-134">This class contains the common state machine management functions and two protected members to apply and read the context information to and from messages.</span></span>

```csharp
class DurableInstanceContextChannelBase
{
  //…
  protected void ApplyContext(Message message)
  {
    //…
  }
  protected string ReadContextId(Message message)
  {
    //…
  }
}
```

<span data-ttu-id="c184a-135">Estos dos métodos utilizan implementaciones `IContextManager` para escribir y leer el id. de contexto a o del mensaje.</span><span class="sxs-lookup"><span data-stu-id="c184a-135">These two methods make use of `IContextManager` implementations to write and read the context ID to or from the message.</span></span> <span data-ttu-id="c184a-136">(`IContextManager` es una interfaz personalizada que se usa para definir el contrato para todos los administradores de contexto). El canal puede incluir el identificador de contexto en un encabezado SOAP personalizado o en un encabezado cookie HTTP.</span><span class="sxs-lookup"><span data-stu-id="c184a-136">(`IContextManager` is a custom interface used to define the contract for all context managers.) The channel can either include the context ID in a custom SOAP header or in a HTTP cookie header.</span></span> <span data-ttu-id="c184a-137">Cada implementación de administrador de contexto hereda de la clase `ContextManagerBase` que contiene la funcionalidad común para todos los administradores del contexto.</span><span class="sxs-lookup"><span data-stu-id="c184a-137">Each context manager implementation inherits from the `ContextManagerBase` class that contains the common functionality for all context managers.</span></span> <span data-ttu-id="c184a-138">El método `GetContextId` en esta clase se utiliza para originar el id. de contexto del cliente.</span><span class="sxs-lookup"><span data-stu-id="c184a-138">The `GetContextId` method in this class is used to originate the context ID from the client.</span></span> <span data-ttu-id="c184a-139">Cuando se origina un id. de contexto por primera vez, este método lo guarda en un archivo de texto cuyo nombre se construye a partir de la dirección remota del extremo (los caracteres del nombre de archivo no válidos en los URI típicos se reemplazan con caracteres @).</span><span class="sxs-lookup"><span data-stu-id="c184a-139">When a context ID is originated for the first time, this method saves it into a text file whose name is constructed by the remote endpoint address (the invalid file name characters in the typical URIs are replaced with @ characters).</span></span>

<span data-ttu-id="c184a-140">Después, cuando el id. de contexto se requiere para el mismo extremo remoto, comprueba si existe un archivo adecuado.</span><span class="sxs-lookup"><span data-stu-id="c184a-140">Later when the context ID is required for the same remote endpoint, it checks whether an appropriate file exists.</span></span> <span data-ttu-id="c184a-141">Si es así, lee el id. de contexto y lo devuelve.</span><span class="sxs-lookup"><span data-stu-id="c184a-141">If it does, it reads the context ID and returns.</span></span> <span data-ttu-id="c184a-142">De lo contrario devuelve un id. de contexto recientemente generado y lo guarda en un archivo.</span><span class="sxs-lookup"><span data-stu-id="c184a-142">Otherwise it returns a newly generated context ID and saves it to a file.</span></span> <span data-ttu-id="c184a-143">Con la configuración predeterminada, estos archivos se colocan en un directorio llamado ContextStore, que reside en el directorio temp del usuario actual.</span><span class="sxs-lookup"><span data-stu-id="c184a-143">With the default configuration, these files are placed in a directory called ContextStore, which resides in the current user’s temp directory.</span></span> <span data-ttu-id="c184a-144">No obstante, esta ubicación es configurable utilizando el elemento de enlace.</span><span class="sxs-lookup"><span data-stu-id="c184a-144">However this location is configurable using the binding element.</span></span>

<span data-ttu-id="c184a-145">El mecanismo utilizado para transportar el id. de contexto es configurable.</span><span class="sxs-lookup"><span data-stu-id="c184a-145">The mechanism used to transport the context ID is configurable.</span></span> <span data-ttu-id="c184a-146">Se pudría escribir en el encabezado cookie HTTP o en un encabezado SOAP personalizado.</span><span class="sxs-lookup"><span data-stu-id="c184a-146">It could be either written to the HTTP cookie header or to a custom SOAP header.</span></span> <span data-ttu-id="c184a-147">El enfoque del encabezado SOAP personalizado permite utilizar este protocolo con protocolos que no son HTTP (por ejemplo, TCP o canalizaciones con nombre).</span><span class="sxs-lookup"><span data-stu-id="c184a-147">The custom SOAP header approach makes it possible to use this protocol with non-HTTP protocols (for example, TCP or Named Pipes).</span></span> <span data-ttu-id="c184a-148">Hay dos clases, a saber `MessageHeaderContextManager` y `HttpCookieContextManager`, que implementan estas dos opciones.</span><span class="sxs-lookup"><span data-stu-id="c184a-148">There are two classes, namely `MessageHeaderContextManager` and `HttpCookieContextManager`, which implement these two options.</span></span>

<span data-ttu-id="c184a-149">Ambos escriben apropiadamente el id. de contexto en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="c184a-149">Both of them write the context ID to the message appropriately.</span></span> <span data-ttu-id="c184a-150">Por ejemplo, la clase `MessageHeaderContextManager` lo escribe en un encabezado SOAP en el método `WriteContext`.</span><span class="sxs-lookup"><span data-stu-id="c184a-150">For example, the `MessageHeaderContextManager` class writes it to a SOAP header in the `WriteContext` method.</span></span>

```csharp
public override void WriteContext(Message message)
{
  string contextId = this.GetContextId();

  MessageHeader contextHeader =
    MessageHeader.CreateHeader(DurableInstanceContextUtility.HeaderName,
      DurableInstanceContextUtility.HeaderNamespace,
      contextId,
      true);

  message.Headers.Add(contextHeader);
}
```

<span data-ttu-id="c184a-151">Ambos métodos, `ApplyContext` y `ReadContextId` en la clase `DurableInstanceContextChannelBase` invocan el `IContextManager.ReadContext` y `IContextManager.WriteContext`, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="c184a-151">Both the `ApplyContext` and `ReadContextId` methods in the `DurableInstanceContextChannelBase` class invoke the `IContextManager.ReadContext` and `IContextManager.WriteContext`, respectively.</span></span> <span data-ttu-id="c184a-152">Sin embargo, la clase `DurableInstanceContextChannelBase` no crea directamente estos administradores del contexto.</span><span class="sxs-lookup"><span data-stu-id="c184a-152">However, these context managers are not directly created by the `DurableInstanceContextChannelBase` class.</span></span> <span data-ttu-id="c184a-153">En su lugar utiliza la clase `ContextManagerFactory` para hacer ese trabajo.</span><span class="sxs-lookup"><span data-stu-id="c184a-153">Instead it uses the `ContextManagerFactory` class to do that job.</span></span>

```csharp
IContextManager contextManager =
                ContextManagerFactory.CreateContextManager(contextType,
                this.contextStoreLocation,
                this.endpointAddress);
```

<span data-ttu-id="c184a-154">Los canales de envío invocan el método `ApplyContext`.</span><span class="sxs-lookup"><span data-stu-id="c184a-154">The `ApplyContext` method is invoked by the sending channels.</span></span> <span data-ttu-id="c184a-155">Éste inserta el id. de contexto a los mensajes salientes.</span><span class="sxs-lookup"><span data-stu-id="c184a-155">It injects the context ID to the outgoing messages.</span></span> <span data-ttu-id="c184a-156">Los canales de recepción invocan el método `ReadContextId`.</span><span class="sxs-lookup"><span data-stu-id="c184a-156">The `ReadContextId` method is invoked by the receiving channels.</span></span> <span data-ttu-id="c184a-157">Este método garantiza que el id. de contexto esté disponible en los mensajes entrantes y lo agrega a la colección `Properties` de la clase `Message`.</span><span class="sxs-lookup"><span data-stu-id="c184a-157">This method ensures that the context ID is available in the incoming messages and adds it to the `Properties` collection of the `Message` class.</span></span> <span data-ttu-id="c184a-158">También produce un `CommunicationException` en caso de un error al leer el id. de contexto y así hace que se anule el canal.</span><span class="sxs-lookup"><span data-stu-id="c184a-158">It also throws a `CommunicationException` in case of a failure to read the context ID and thus causes the channel to be aborted.</span></span>

```csharp
message.Properties.Add(DurableInstanceContextUtility.ContextIdProperty, contextId);
```

<span data-ttu-id="c184a-159">Antes de continuar, es importante entender el uso de la colección `Properties` en la clase `Message`.</span><span class="sxs-lookup"><span data-stu-id="c184a-159">Before proceeding, it is important to understand the usage of the `Properties` collection in the `Message` class.</span></span> <span data-ttu-id="c184a-160">Normalmente, esta colección se utiliza `Properties` al pasar los datos de niveles bajos a superiores desde la capa del canal.</span><span class="sxs-lookup"><span data-stu-id="c184a-160">Typically, this `Properties` collection is used when passing data from lower to the upper levels from the channel layer.</span></span> <span data-ttu-id="c184a-161">De este modo los datos deseados se pueden proporcionar a los niveles superiores de una manera coherente sin tener en cuenta los detalles protocolares.</span><span class="sxs-lookup"><span data-stu-id="c184a-161">This way the desired data can be provided to the upper levels in a consistent manner regardless of the protocol details.</span></span> <span data-ttu-id="c184a-162">En otras palabras, la capa del canal puede enviar y recibir el id. de contexto como un encabezado SOAP o un encabezado cookie HTTP.</span><span class="sxs-lookup"><span data-stu-id="c184a-162">In other words, the channel layer can send and receive the context ID either as a SOAP header or a HTTP cookie header.</span></span> <span data-ttu-id="c184a-163">Pero no es necesario que los niveles superiores conozcan estos detalles, porque la capa del canal hace que esta información esté disponible en la colección `Properties`.</span><span class="sxs-lookup"><span data-stu-id="c184a-163">But it is not necessary for the upper levels to know about these details because the channel layer makes this information available in the `Properties` collection.</span></span>

<span data-ttu-id="c184a-164">Ahora, con la clase `DurableInstanceContextChannelBase` en su lugar, se deben implementar los diez interfaces necesarios (IOutputChannel, IInputChannel, IOutputSessionChannel, IInputSessionChannel, IRequestChannel, IReplyChannel, IRequestSessionChannel, IReplySessionChannel, IDuplexChannel, IDuplexSessionChannel).</span><span class="sxs-lookup"><span data-stu-id="c184a-164">Now with the `DurableInstanceContextChannelBase` class in place all ten of the necessary interfaces (IOutputChannel, IInputChannel, IOutputSessionChannel, IInputSessionChannel, IRequestChannel, IReplyChannel, IRequestSessionChannel, IReplySessionChannel, IDuplexChannel, IDuplexSessionChannel) must be implemented.</span></span> <span data-ttu-id="c184a-165">Se parecen a cualquier patrón de intercambio de mensajes disponible (datagrama, simplex, duplex y sus variantes con sesión).</span><span class="sxs-lookup"><span data-stu-id="c184a-165">They resemble every available message exchange pattern (datagram, simplex, duplex and their sessionful variants).</span></span> <span data-ttu-id="c184a-166">Cada una de estas implementaciones hereda previamente la clase base descrita y llama apropiadamente a `ApplyContext` y a `ReadContextId`.</span><span class="sxs-lookup"><span data-stu-id="c184a-166">Each of these implementations inherit the base class previously described and calls `ApplyContext` and `ReadContextId` appropriately.</span></span> <span data-ttu-id="c184a-167">Por ejemplo, `DurableInstanceContextOutputChannel`- que implementa la interfaz IOutputChannel - llama al método `ApplyContext` desde cada método que envía los mensajes.</span><span class="sxs-lookup"><span data-stu-id="c184a-167">For example, `DurableInstanceContextOutputChannel` - which implements the IOutputChannel interface - calls the `ApplyContext` method from each method that sends the messages.</span></span>

```csharp
public void Send(Message message, TimeSpan timeout)
{
    // Apply the context information before sending the message.
    this.ApplyContext(message);
    //…
}
```

<span data-ttu-id="c184a-168">Por otro lado, `DurableInstanceContextInputChannel`- qué implementa la interfaz `IInputChannel`- llama al método `ReadContextId` en cada método que recibe los mensajes.</span><span class="sxs-lookup"><span data-stu-id="c184a-168">On the other hand, `DurableInstanceContextInputChannel` - which implements the `IInputChannel` interface - calls the `ReadContextId` method in each method which receives the messages.</span></span>

```csharp
public Message Receive(TimeSpan timeout)
{
    //…
      ReadContextId(message);
      return message;
}
```

<span data-ttu-id="c184a-169">Aparte de esto, estas implementaciones de canal delegan las invocaciones de método al canal debajo de ellos en la pila del canal.</span><span class="sxs-lookup"><span data-stu-id="c184a-169">Apart from this, these channel implementations delegate the method invocations to the channel below them in the channel stack.</span></span> <span data-ttu-id="c184a-170">Sin embargo, las variantes con sesión tienen una lógica básica para asegurarse de que el id. de contexto se envía y se lee solo para el primer mensaje que provoca que la sesión se cree.</span><span class="sxs-lookup"><span data-stu-id="c184a-170">However, sessionful variants have a basic logic to make sure that the context ID is sent and is read only for the first message that causes the session to be created.</span></span>

```csharp
if (isFirstMessage)
{
//…
    this.ApplyContext(message);
    isFirstMessage = false;
}
```

<span data-ttu-id="c184a-171">Estas implementaciones de canal se agregan a continuación al tiempo de ejecución `DurableInstanceContextBindingElement` del canal `DurableInstanceContextBindingElementSection` de WCF mediante la clase y la clase adecuadamente.</span><span class="sxs-lookup"><span data-stu-id="c184a-171">These channel implementations are then added to the WCF channel runtime by the `DurableInstanceContextBindingElement` class and `DurableInstanceContextBindingElementSection` class appropriately.</span></span> <span data-ttu-id="c184a-172">Consulte la documentación del ejemplo de canal de [HttpCookieSession](../../../../docs/framework/wcf/samples/httpcookiesession.md) para obtener más información sobre los elementos de enlace y las secciones del elemento de enlace.</span><span class="sxs-lookup"><span data-stu-id="c184a-172">See the [HttpCookieSession](../../../../docs/framework/wcf/samples/httpcookiesession.md) channel sample documentation for more details about binding elements and binding element sections.</span></span>

## <a name="service-model-layer-extensions"></a><span data-ttu-id="c184a-173">Extensiones de la capa de modelo de servicio</span><span class="sxs-lookup"><span data-stu-id="c184a-173">Service Model Layer Extensions</span></span>

<span data-ttu-id="c184a-174">Ahora que el id. de contexto ha viajado a través de la capa del canal, el comportamiento del servicio se puede implementar para personalizar la creación de instancias.</span><span class="sxs-lookup"><span data-stu-id="c184a-174">Now that the context ID has traveled through the channel layer, the service behavior can be implemented to customize the instantiation.</span></span> <span data-ttu-id="c184a-175">En este ejemplo, se utiliza un administrador de almacenamiento para cargar y guardar el estado desde o al almacén persistente.</span><span class="sxs-lookup"><span data-stu-id="c184a-175">In this sample, a storage manager is used to load and save state from or to the persistent store.</span></span> <span data-ttu-id="c184a-176">Tal y como se explicó con anterioridad, este ejemplo proporciona un administrador de almacenamiento que utiliza SQL Server 2005 como su memoria auxiliar.</span><span class="sxs-lookup"><span data-stu-id="c184a-176">As explained previously, this sample provides a storage manager that uses SQL Server 2005 as its backing store.</span></span> <span data-ttu-id="c184a-177">Sin embargo, también es posible agregar mecanismos de almacenamiento personalizados a esta extensión.</span><span class="sxs-lookup"><span data-stu-id="c184a-177">However, it is also possible to add custom storage mechanisms to this extension.</span></span> <span data-ttu-id="c184a-178">Para hacer eso se declara una interfaz pública, la cual debe ser implementada por todos los administradores de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="c184a-178">To do that a public interface is declared, which must be implemented by all storage managers.</span></span>

```csharp
public interface IStorageManager
{
    object GetInstance(string contextId, Type type);
    void SaveInstance(string contextId, object state);
}
```

<span data-ttu-id="c184a-179">La clase `SqlServerStorageManager`contiene la implementación `IStorageManager` predeterminada.</span><span class="sxs-lookup"><span data-stu-id="c184a-179">The `SqlServerStorageManager` class contains the default `IStorageManager` implementation.</span></span> <span data-ttu-id="c184a-180">En su método `SaveInstance`, el objeto determinado se serializa utilizando XmlSerializer y se guarda en la base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c184a-180">In its `SaveInstance` method the given object is serialized using the XmlSerializer and is saved to the SQL Server database.</span></span>

```csharp
XmlSerializer serializer = new XmlSerializer(state.GetType());
string data;

using (StringWriter writer = new StringWriter(CultureInfo.InvariantCulture))
{
    serializer.Serialize(writer, state);
    data = writer.ToString();
}

using (SqlConnection connection = new SqlConnection(GetConnectionString()))
{
    connection.Open();

    string update = @"UPDATE Instances SET Instance = @instance WHERE ContextId = @contextId";

    using (SqlCommand command = new SqlCommand(update, connection))
    {
        command.Parameters.Add("@instance", SqlDbType.VarChar, 2147483647).Value = data;
        command.Parameters.Add("@contextId", SqlDbType.VarChar, 256).Value = contextId;

        int rows = command.ExecuteNonQuery();

        if (rows == 0)
        {
            string insert = @"INSERT INTO Instances(ContextId, Instance) VALUES(@contextId, @instance)";
            command.CommandText = insert;
            command.ExecuteNonQuery();
        }
    }
}
```

<span data-ttu-id="c184a-181">En el método `GetInstance` los datos serializados se leen para un id. de contexto determinado y el objeto construido a partir de él se devuelve al llamador.</span><span class="sxs-lookup"><span data-stu-id="c184a-181">In the `GetInstance` method the serialized data is read for a given context ID and the object constructed from it is returned to the caller.</span></span>

```csharp
object data;
using (SqlConnection connection = new SqlConnection(GetConnectionString()))
{
    connection.Open();

    string select = "SELECT Instance FROM Instances WHERE ContextId = @contextId";
    using (SqlCommand command = new SqlCommand(select, connection))
    {
        command.Parameters.Add("@contextId", SqlDbType.VarChar, 256).Value = contextId;
        data = command.ExecuteScalar();
    }
}

if (data != null)
{
    XmlSerializer serializer = new XmlSerializer(type);
    using (StringReader reader = new StringReader((string)data))
    {
        object instance = serializer.Deserialize(reader);
        return instance;
    }
}
```

<span data-ttu-id="c184a-182">No se supone que los usuarios de estos administradores de almacenamiento creen directamente instancias de ellos.</span><span class="sxs-lookup"><span data-stu-id="c184a-182">Users of these storage managers are not supposed to instantiate them directly.</span></span> <span data-ttu-id="c184a-183">Utilizan la clase `StorageManagerFactory`, que resume detalles de creación en el administrador de almacenamiento .</span><span class="sxs-lookup"><span data-stu-id="c184a-183">They use the `StorageManagerFactory` class, which abstracts from the storage manager creation details.</span></span> <span data-ttu-id="c184a-184">Esta clase tiene un miembro estático, `GetStorageManager`, que crea una instancia de un tipo de administrador de almacenamiento determinado.</span><span class="sxs-lookup"><span data-stu-id="c184a-184">This class has one static member, `GetStorageManager`, which creates an instance of a given storage manager type.</span></span> <span data-ttu-id="c184a-185">Si el parámetro de tipo es `null`, este método crea una instancia de la clase `SqlServerStorageManager` predeterminada y lo devuelve.</span><span class="sxs-lookup"><span data-stu-id="c184a-185">If the type parameter is `null`, this method creates an instance of the default `SqlServerStorageManager` class and returns it.</span></span> <span data-ttu-id="c184a-186">También valida el tipo determinado para asegurarse de que implementa la interfaz `IStorageManager`.</span><span class="sxs-lookup"><span data-stu-id="c184a-186">It also validates the given type to make sure that it implements the `IStorageManager` interface.</span></span>

```csharp
public static IStorageManager GetStorageManager(Type storageManagerType)
{
IStorageManager storageManager = null;

if (storageManagerType == null)
{
    return new SqlServerStorageManager();
}
else
{
    object obj = Activator.CreateInstance(storageManagerType);

    // Throw if the specified storage manager type does not
    // implement IStorageManager.
    if (obj is IStorageManager)
    {
        storageManager = (IStorageManager)obj;
    }
    else
    {
        throw new InvalidOperationException(
                  ResourceHelper.GetString("ExInvalidStorageManager"));
    }

    return storageManager;
}
}
```

<span data-ttu-id="c184a-187">Se implementa la infraestructura necesaria para leer y escribir instancias del almacenamiento persistente.</span><span class="sxs-lookup"><span data-stu-id="c184a-187">The necessary infrastructure to read and write instances from the persistent storage is implemented.</span></span> <span data-ttu-id="c184a-188">Ahora tienen que tomarse los pasos necesarios para cambiar el comportamiento del servicio.</span><span class="sxs-lookup"><span data-stu-id="c184a-188">Now the necessary steps to change the service behavior have to be taken.</span></span>

<span data-ttu-id="c184a-189">Como primer paso de este proceso tenemos que guardar el id. de contexto, que pasó por la capa del canal al InstanceContext actual.</span><span class="sxs-lookup"><span data-stu-id="c184a-189">As the first step of this process we have to save the context ID, which came through the channel layer to the current InstanceContext.</span></span> <span data-ttu-id="c184a-190">InstanceContext es un componente de tiempo de ejecución que actúa como el vínculo entre el distribuidor de WCF y la instancia de servicio.</span><span class="sxs-lookup"><span data-stu-id="c184a-190">InstanceContext is a runtime component that acts as the link between the WCF dispatcher and the service instance.</span></span> <span data-ttu-id="c184a-191">Se puede utilizar para proporcionar estado y comportamiento adicionales a la instancia del servicio.</span><span class="sxs-lookup"><span data-stu-id="c184a-191">It can be used to provide additional state and behavior to the service instance.</span></span> <span data-ttu-id="c184a-192">Esto es esencial porque en comunicación con sesión el id. de contexto solo se envía con el primer mensaje.</span><span class="sxs-lookup"><span data-stu-id="c184a-192">This is essential because in sessionful communication the context ID is sent only with the first message.</span></span>

<span data-ttu-id="c184a-193">WCF permite extender su componente de tiempo de ejecución InstanceContext agregando un nuevo estado y comportamiento mediante su patrón de objeto extensible.</span><span class="sxs-lookup"><span data-stu-id="c184a-193">WCF allows extending its InstanceContext runtime component by adding a new state and behavior using its extensible object pattern.</span></span> <span data-ttu-id="c184a-194">El patrón de objeto extensible se utiliza en WCF para ampliar las clases en tiempo de ejecución existentes con nueva funcionalidad o agregar nuevas características de estado a un objeto.</span><span class="sxs-lookup"><span data-stu-id="c184a-194">The extensible object pattern is used in WCF to either extend existing runtime classes with new functionality or to add new state features to an object.</span></span> <span data-ttu-id="c184a-195">Hay tres interfaces en el patrón de objeto extensible: IExtensibleObject\<t>, IExtension\<t> y IExtensionCollection\<T>:</span><span class="sxs-lookup"><span data-stu-id="c184a-195">There are three interfaces in the extensible object pattern - IExtensibleObject\<T>, IExtension\<T>, and IExtensionCollection\<T>:</span></span>

- <span data-ttu-id="c184a-196">La interfaz\<IExtensibleObject T> se implementa mediante objetos que permiten extensiones que personalizan su funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="c184a-196">The IExtensibleObject\<T> interface is implemented by objects that allow extensions that customize their functionality.</span></span>

- <span data-ttu-id="c184a-197">La interfaz\<IExtension T> se implementa mediante objetos que son extensiones de clases de tipo T.</span><span class="sxs-lookup"><span data-stu-id="c184a-197">The IExtension\<T> interface is implemented by objects that are extensions of classes of type T.</span></span>

- <span data-ttu-id="c184a-198">La interfaz\<de> IExtensionCollection T es una colección de IExtensions que permite recuperar IExtensions por su tipo.</span><span class="sxs-lookup"><span data-stu-id="c184a-198">The IExtensionCollection\<T> interface is a collection of IExtensions that allows for retrieving IExtensions by their type.</span></span>

<span data-ttu-id="c184a-199">Por consiguiente una clase InstanceContextExtension se debería crear de tal manera que implementase la interfaz IExtension y definiese el estado necesario para guardar el id. de contexto.</span><span class="sxs-lookup"><span data-stu-id="c184a-199">Therefore an InstanceContextExtension class should be created that implements the IExtension interface and defines the required state to save the context ID.</span></span> <span data-ttu-id="c184a-200">Esta clase también proporciona el estado para mantener al administrador de almacenamiento en uso.</span><span class="sxs-lookup"><span data-stu-id="c184a-200">This class also provides the state to hold the storage manager being used.</span></span> <span data-ttu-id="c184a-201">Una vez guardado el nuevo estado, no debería ser posible modificarlo.</span><span class="sxs-lookup"><span data-stu-id="c184a-201">Once the new state is saved, it should not be possible to modify it.</span></span> <span data-ttu-id="c184a-202">Por consiguiente, el estado se proporciona y guarda a la instancia en el momento en que se construye; en ese momento solo se puede tener acceso a él utilizando las propiedades de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="c184a-202">Therefore the state is provided and saved to the instance at the time it is being constructed and then only accessible using read-only properties.</span></span>

```csharp
// Constructor
public DurableInstanceContextExtension(string contextId,
            IStorageManager storageManager)
{
    this.contextId = contextId;
    this.storageManager = storageManager;
}

// Read only properties
public string ContextId
{
    get { return this.contextId; }
}

public IStorageManager StorageManager
{
    get { return this.storageManager; }
}
```

<span data-ttu-id="c184a-203">La clase InstanceContextInitializer implementa la interfaz IInstanceContextInitializer y agrega la extensión de contexto de instancia a la colección Extensions del InstanceContext construyéndose.</span><span class="sxs-lookup"><span data-stu-id="c184a-203">The InstanceContextInitializer class implements the IInstanceContextInitializer interface and adds the instance context extension to the Extensions collection of the InstanceContext being constructed.</span></span>

```csharp
public void Initialize(InstanceContext instanceContext, Message message)
{
    string contextId =
  (string)message.Properties[DurableInstanceContextUtility.ContextIdProperty];

    DurableInstanceContextExtension extension =
                new DurableInstanceContextExtension(contextId,
                     storageManager);
    instanceContext.Extensions.Add(extension);
}
```

<span data-ttu-id="c184a-204">Tal y como se describió con anterioridad, el id. de contexto se lee de la colección `Properties` de la clase `Message` y pasa al constructor de la clase de extensión.</span><span class="sxs-lookup"><span data-stu-id="c184a-204">As described earlier the context ID is read from the `Properties` collection of the `Message` class and passed to the constructor of the extension class.</span></span> <span data-ttu-id="c184a-205">Esto muestra cómo la información se puede intercambiar entre las capas de una manera coherente.</span><span class="sxs-lookup"><span data-stu-id="c184a-205">This demonstrates how information can be exchanged between the layers in a consistent manner.</span></span>

<span data-ttu-id="c184a-206">El paso importante siguiente es invalidar el proceso de creación de la instancia de servicio.</span><span class="sxs-lookup"><span data-stu-id="c184a-206">The next important step is overriding the service instance creation process.</span></span> <span data-ttu-id="c184a-207">WCF permite implementar comportamientos de creación de instancias personalizadas y enlazarlos al tiempo de ejecución mediante la interfaz IInstanceProvider.</span><span class="sxs-lookup"><span data-stu-id="c184a-207">WCF allows implementing custom instantiation behaviors and hooking them up to the runtime using the IInstanceProvider interface.</span></span> <span data-ttu-id="c184a-208">La nueva clase `InstanceProvider` se implementa para hacer ese trabajo.</span><span class="sxs-lookup"><span data-stu-id="c184a-208">The new `InstanceProvider` class is implemented to do that job.</span></span> <span data-ttu-id="c184a-209">En el constructor se acepta el tipo de servicio esperado del proveedor de instancias.</span><span class="sxs-lookup"><span data-stu-id="c184a-209">In the constructor the service type expected from the instance provider is accepted.</span></span> <span data-ttu-id="c184a-210">Después se utiliza para crear nuevas instancias.</span><span class="sxs-lookup"><span data-stu-id="c184a-210">Later this is used to create new instances.</span></span> <span data-ttu-id="c184a-211">En la implementación `GetInstance` una instancia de un administrador de almacenamiento se crea buscando una instancia conservada.</span><span class="sxs-lookup"><span data-stu-id="c184a-211">In the `GetInstance` implementation an instance of a storage manager is created looking for a persisted instance.</span></span> <span data-ttu-id="c184a-212">Si devuelve a continuación `null` entonces una nueva instancia del tipo de servicio se crea y se devuelve al llamador.</span><span class="sxs-lookup"><span data-stu-id="c184a-212">If it returns `null` then a new instance of the service type is instantiated and returned to the caller.</span></span>

```csharp
public object GetInstance(InstanceContext instanceContext, Message message)
{
    object instance = null;

    DurableInstanceContextExtension extension =
    instanceContext.Extensions.Find<DurableInstanceContextExtension>();

    string contextId = extension.ContextId;
    IStorageManager storageManager = extension.StorageManager;

    instance = storageManager.GetInstance(contextId, serviceType);

    instance ??= Activator.CreateInstance(serviceType);
    return instance;
}
```

<span data-ttu-id="c184a-213">El siguiente paso importante es instalar el `InstanceContextExtension`, `InstanceContextInitializer` y las clases `InstanceProvider` en el tiempo de ejecución del modelo de servicio.</span><span class="sxs-lookup"><span data-stu-id="c184a-213">The next important step is to install the `InstanceContextExtension`, `InstanceContextInitializer` and `InstanceProvider` classes into the service model runtime.</span></span> <span data-ttu-id="c184a-214">Podría utilizarse un atributo personalizado para marcar las clases de implementación de servicio para instalar el comportamiento.</span><span class="sxs-lookup"><span data-stu-id="c184a-214">A custom attribute could be used to mark the service implementation classes to install the behavior.</span></span> <span data-ttu-id="c184a-215">`DurableInstanceContextAttribute` contiene la implementación para este atributo e implementa la interfaz `IServiceBehavior` para extender el tiempo de ejecución del servicio por completo.</span><span class="sxs-lookup"><span data-stu-id="c184a-215">The `DurableInstanceContextAttribute` contains the implementation for this attribute and it implements the `IServiceBehavior` interface to extend the entire service runtime.</span></span>

<span data-ttu-id="c184a-216">Esta clase tiene una propiedad que acepta el tipo del administrador de almacenamiento que se va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="c184a-216">This class has a property that accepts the type of the storage manager to be used.</span></span> <span data-ttu-id="c184a-217">De esta manera la implementación les permite a los usuarios especificar su propia implementación `IStorageManager` como parámetro de este atributo.</span><span class="sxs-lookup"><span data-stu-id="c184a-217">In this way the implementation enables the users to specify their own `IStorageManager` implementation as parameter of this attribute.</span></span>

<span data-ttu-id="c184a-218">En la implementación `ApplyDispatchBehavior`el `InstanceContextMode` del atributo `ServiceBehavior` actual se comprueba.</span><span class="sxs-lookup"><span data-stu-id="c184a-218">In the `ApplyDispatchBehavior` implementation the `InstanceContextMode` of the current `ServiceBehavior` attribute is being verified.</span></span> <span data-ttu-id="c184a-219">Si esta propiedad está establecida en Singleton, no es posible habilitar la creación de instancias duraderas y se inicia un `InvalidOperationException` para notificar al host.</span><span class="sxs-lookup"><span data-stu-id="c184a-219">If this property is set to Singleton, enabling durable instancing is not possible and an `InvalidOperationException` is thrown to notify the host.</span></span>

```csharp
ServiceBehaviorAttribute serviceBehavior =
    serviceDescription.Behaviors.Find<ServiceBehaviorAttribute>();

if (serviceBehavior != null &&
     serviceBehavior.InstanceContextMode == InstanceContextMode.Single)
{
    throw new InvalidOperationException(
       ResourceHelper.GetString("ExSingletonInstancingNotSupported"));
}
```

<span data-ttu-id="c184a-220">Después de esto se crean las instancias del administrador de almacenamiento, el inicializador de contexto de instancias y el proveedor de instancias, y se instalan en `DispatchRuntime` creado para cada punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="c184a-220">After this the instances of the storage manager, instance context initializer, and the instance provider are created and installed in the `DispatchRuntime` created for every endpoint.</span></span>

```csharp
IStorageManager storageManager =
    StorageManagerFactory.GetStorageManager(storageManagerType);

InstanceContextInitializer contextInitializer =
    new InstanceContextInitializer(storageManager);

InstanceProvider instanceProvider =
    new InstanceProvider(description.ServiceType);

foreach (ChannelDispatcherBase cdb in serviceHostBase.ChannelDispatchers)
{
    ChannelDispatcher cd = cdb as ChannelDispatcher;

    if (cd != null)
    {
        foreach (EndpointDispatcher ed in cd.Endpoints)
        {
            ed.DispatchRuntime.InstanceContextInitializers.Add(contextInitializer);
            ed.DispatchRuntime.InstanceProvider = instanceProvider;
        }
    }
}
```

<span data-ttu-id="c184a-221">Resumiendo hasta ahora, este ejemplo ha generado un canal que habilita el protocolo de conexión personalizado para el intercambio de id. de contexto personalizado y también sobrescribe el comportamiento de la creación de instancias predeterminado para cargar las instancias desde el almacenamiento persistente.</span><span class="sxs-lookup"><span data-stu-id="c184a-221">In summary so far, this sample has produced a channel that enabled the custom wire protocol for custom context ID exchange and it also overwrites the default instancing behavior to load the instances from the persistent storage.</span></span>

<span data-ttu-id="c184a-222">Lo que queda es un modo de guardar la instancia del servicio en el almacenamiento persistente.</span><span class="sxs-lookup"><span data-stu-id="c184a-222">What is left is a way to save the service instance to the persistent storage.</span></span> <span data-ttu-id="c184a-223">Como se dijo con anterioridad, ya existe la funcionalidad necesaria para guardar el estado en una implementación `IStorageManager`.</span><span class="sxs-lookup"><span data-stu-id="c184a-223">As discussed previously, there is already the required functionality to save the state in an `IStorageManager` implementation.</span></span> <span data-ttu-id="c184a-224">Ahora debemos integrarlo con el tiempo de ejecución de WCF.</span><span class="sxs-lookup"><span data-stu-id="c184a-224">We now must integrate this with the WCF runtime.</span></span> <span data-ttu-id="c184a-225">Se requiere otro atributo, que es aplicable a los métodos en la clase de implementación de servicio.</span><span class="sxs-lookup"><span data-stu-id="c184a-225">Another attribute is required that is applicable to the methods in the service implementation class.</span></span> <span data-ttu-id="c184a-226">Se supone que este atributo se aplica a los métodos que cambian el estado de la instancia del servicio.</span><span class="sxs-lookup"><span data-stu-id="c184a-226">This attribute is supposed to be applied to the methods that change the state of the service instance.</span></span>

<span data-ttu-id="c184a-227">La clase `SaveStateAttribute` implementa esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="c184a-227">The `SaveStateAttribute` class implements this functionality.</span></span> <span data-ttu-id="c184a-228">También implementa la `IOperationBehavior` clase para modificar el tiempo de ejecución de WCF para cada operación.</span><span class="sxs-lookup"><span data-stu-id="c184a-228">It also implements `IOperationBehavior` class to modify the WCF runtime for each operation.</span></span> <span data-ttu-id="c184a-229">Cuando un método se marca con este atributo, el tiempo de ejecución de WCF `ApplyBehavior` invoca el método mientras `DispatchOperation` se construye el adecuado.</span><span class="sxs-lookup"><span data-stu-id="c184a-229">When a method is marked with this attribute, the WCF runtime invokes the `ApplyBehavior` method while the appropriate `DispatchOperation` is being constructed.</span></span> <span data-ttu-id="c184a-230">En esta implementación de método hay línea única de código:</span><span class="sxs-lookup"><span data-stu-id="c184a-230">In this method implementation there is single line of code:</span></span>

```csharp
dispatch.Invoker = new OperationInvoker(dispatch.Invoker);
```

<span data-ttu-id="c184a-231">Esta instrucción crea una instancia del tipo `OperationInvoker` y lo asigna a la propiedad `Invoker` de `DispatchOperation` construyéndose.</span><span class="sxs-lookup"><span data-stu-id="c184a-231">This instruction creates an instance of `OperationInvoker` type and assigns it to the `Invoker` property of the `DispatchOperation` being constructed.</span></span> <span data-ttu-id="c184a-232">La clase `OperationInvoker` es un contenedor para el invocador de la operación predeterminado creado para `DispatchOperation`.</span><span class="sxs-lookup"><span data-stu-id="c184a-232">The `OperationInvoker` class is a wrapper for the default operation invoker created for the `DispatchOperation`.</span></span> <span data-ttu-id="c184a-233">Esta clase implementa la interfaz `IOperationInvoker`.</span><span class="sxs-lookup"><span data-stu-id="c184a-233">This class implements the `IOperationInvoker` interface.</span></span> <span data-ttu-id="c184a-234">En la implementación del método `Invoke` la invocación de método real se delega al invocador de operación interno.</span><span class="sxs-lookup"><span data-stu-id="c184a-234">In the `Invoke` method implementation the actual method invocation is delegated to the inner operation invoker.</span></span> <span data-ttu-id="c184a-235">Sin embargo, antes de devolver los resultados el administrador de almacenamiento en `InstanceContext` se utiliza para guardar la instancia del servicio.</span><span class="sxs-lookup"><span data-stu-id="c184a-235">However, before returning the results the storage manager in the `InstanceContext` is used to save the service instance.</span></span>

```csharp
object result = innerOperationInvoker.Invoke(instance,
    inputs, out outputs);

// Save the instance using the storage manager saved in the
// current InstanceContext.
InstanceContextExtension extension =
    OperationContext.Current.InstanceContext.Extensions.Find<InstanceContextExtension>();

extension.StorageManager.SaveInstance(extension.ContextId, instance);
return result;
```

## <a name="using-the-extension"></a><span data-ttu-id="c184a-236">Utilizar la extensión</span><span class="sxs-lookup"><span data-stu-id="c184a-236">Using the Extension</span></span>

<span data-ttu-id="c184a-237">Tanto la capa de canal como las extensiones de nivel de modelo de servicio se realizan y ahora se pueden usar en aplicaciones WCF.</span><span class="sxs-lookup"><span data-stu-id="c184a-237">Both the channel layer and service model layer extensions are done and they can now be used in WCF applications.</span></span> <span data-ttu-id="c184a-238">Los servicios tienen que agregar el canal en la pila del canal utilizando un enlace personalizado y a continuación marcar las clases de implementación de servicio con los atributos adecuados.</span><span class="sxs-lookup"><span data-stu-id="c184a-238">Services have to add the channel into the channel stack using a custom binding and then mark the service implementation classes with the appropriate attributes.</span></span>

```csharp
[DurableInstanceContext]
[ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)]
public class ShoppingCart : IShoppingCart
{
//…
     [SaveState]
     public int AddItem(string item)
     {
         //…
     }
//…
 }
```

<span data-ttu-id="c184a-239">Las aplicaciones Cliente deben agregar DurableInstanceContextChannel en la pila de canal utilizando un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="c184a-239">Client applications must add the DurableInstanceContextChannel into the channel stack using a custom binding.</span></span> <span data-ttu-id="c184a-240">Para configurar mediante declaración el canal en el archivo de configuración, la sección de elemento de enlace tiene que ser agregada a la colección de extensiones de elemento de enlace.</span><span class="sxs-lookup"><span data-stu-id="c184a-240">To configure the channel declaratively in the configuration file, the binding element section has to be added to the binding element extensions collection.</span></span>

```xml
<system.serviceModel>
 <extensions>
   <bindingElementExtensions>
     <add name="durableInstanceContext"
type="Microsoft.ServiceModel.Samples.DurableInstanceContextBindingElementSection, DurableInstanceContextExtension, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null"/>
   </bindingElementExtensions>
 </extensions>
</system.serviceModel>
```

<span data-ttu-id="c184a-241">Ahora el elemento de enlace se puede utilizar con un enlace personalizado, del mismo modo que otros elementos de enlace estándar:</span><span class="sxs-lookup"><span data-stu-id="c184a-241">Now the binding element can be used with a custom binding just like other standard binding elements:</span></span>

```xml
<bindings>
 <customBinding>
   <binding name="TextOverHttp">
     <durableInstanceContext contextType="HttpCookie"/>
     <reliableSession />
     <textMessageEncoding />
     <httpTransport />
   </binding>
 </customBinding>
</bindings>
```

## <a name="conclusion"></a><span data-ttu-id="c184a-242">Conclusión</span><span class="sxs-lookup"><span data-stu-id="c184a-242">Conclusion</span></span>

<span data-ttu-id="c184a-243">Este ejemplo mostró cómo crear un canal protocolar personalizado y cómo personalizar el comportamiento del servicio para habilitarlo.</span><span class="sxs-lookup"><span data-stu-id="c184a-243">This sample showed how to create a custom protocol channel and how to customize the service behavior to enable it.</span></span>

<span data-ttu-id="c184a-244">La extensión se puede mejorar más, permitiendo a los usuarios especificar la implementación `IStorageManager` mediante una sección de configuración.</span><span class="sxs-lookup"><span data-stu-id="c184a-244">The extension can be further improved by letting users specify the `IStorageManager` implementation using a configuration section.</span></span> <span data-ttu-id="c184a-245">Esto permite modificar la memoria auxiliar sin recompilar el código de servicio.</span><span class="sxs-lookup"><span data-stu-id="c184a-245">This makes it possible to modify the backing store without recompiling the service code.</span></span>

<span data-ttu-id="c184a-246">Además, puede intentar implementar una clase (por ejemplo, `StateBag`), que encapsula el estado de la instancia.</span><span class="sxs-lookup"><span data-stu-id="c184a-246">Furthermore you could try to implement a class (for example, `StateBag`), which encapsulates the state of the instance.</span></span> <span data-ttu-id="c184a-247">Esa clase es responsable por haber conservado el estado cada vez que cambia.</span><span class="sxs-lookup"><span data-stu-id="c184a-247">That class is responsible for persisting the state whenever it changes.</span></span> <span data-ttu-id="c184a-248">De esta manera puede evitar utilizar el atributo `SaveState` y realizar el trabajo persistente con más precisión (por ejemplo, podría conservar el estado cuando se cambia realmente el estado, en lugar de guardarlo cada vez que se llama a un método con el atributo `SaveState` ).</span><span class="sxs-lookup"><span data-stu-id="c184a-248">This way you can avoid using the `SaveState` attribute and perform the persisting work more accurately (for example, you could persist the state when the state is actually changed rather than saving it each time when a method with the `SaveState` attribute is called).</span></span>

<span data-ttu-id="c184a-249">Al ejecutar el ejemplo, se muestra el resultado siguiente.</span><span class="sxs-lookup"><span data-stu-id="c184a-249">When you run the sample, the following output is displayed.</span></span> <span data-ttu-id="c184a-250">El cliente agrega dos elementos a su carro de la compra y, a continuación, recibe la lista de elementos en su carro de la compra desde el servicio.</span><span class="sxs-lookup"><span data-stu-id="c184a-250">The client adds two items to its shopping cart and then gets the list of items in its shopping cart from the service.</span></span> <span data-ttu-id="c184a-251">Presione Entrar en cada ventana de la consola para cerrar el servicio y el cliente.</span><span class="sxs-lookup"><span data-stu-id="c184a-251">Press ENTER in each console window to shut down the service and client.</span></span>

```console
Enter the name of the product: apples
Enter the name of the product: bananas

Shopping cart currently contains the following items.
apples
bananas
Press ENTER to shut down client
```

> [!NOTE]
> <span data-ttu-id="c184a-252">Al recompilar el servicio, se sobrescribe el archivo de base de datos.</span><span class="sxs-lookup"><span data-stu-id="c184a-252">Rebuilding the service overwrites the database file.</span></span> <span data-ttu-id="c184a-253">Para observar el estado conservado durante varias ejecuciones del ejemplo, asegúrese de no recompilar el ejemplo entre las distintas ejecuciones.</span><span class="sxs-lookup"><span data-stu-id="c184a-253">To observe state preserved across multiple runs of the sample, be sure not to rebuild the sample between runs.</span></span>

#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="c184a-254">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="c184a-254">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="c184a-255">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="c184a-255">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="c184a-256">Para compilar la solución, siga las instrucciones de [creación de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="c184a-256">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

3. <span data-ttu-id="c184a-257">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="c184a-257">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>

> [!NOTE]
> <span data-ttu-id="c184a-258">Debe estar ejecutando SQL Server 2005 o SQL Express 2005 para ejecutar este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="c184a-258">You must be running SQL Server 2005 or SQL Express 2005 to run this sample.</span></span> <span data-ttu-id="c184a-259">Si está ejecutando SQL Server 2005, debe modificar la configuración de la cadena de conexión del servicio.</span><span class="sxs-lookup"><span data-stu-id="c184a-259">If you are running SQL Server 2005, you must modify the configuration of the service's connection string.</span></span> <span data-ttu-id="c184a-260">Al ejecutar un equipo cruzado, SQL Server sólo se requiere en el equipo del servidor.</span><span class="sxs-lookup"><span data-stu-id="c184a-260">When running cross-machine, SQL Server is only required on the server machine.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c184a-261">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="c184a-261">The samples may already be installed on your machine.</span></span> <span data-ttu-id="c184a-262">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="c184a-262">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="c184a-263">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y ejemplos.</span><span class="sxs-lookup"><span data-stu-id="c184a-263">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="c184a-264">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="c184a-264">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Instancing\Durable`
