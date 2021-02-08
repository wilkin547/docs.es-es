---
description: 'Más información acerca de: transporte: interoperabilidad de WSE 3,0 TCP'
title: 'Transporte: interoperabilidad de WSE 3.0 TCP'
ms.date: 03/30/2017
ms.assetid: 5f7c3708-acad-4eb3-acb9-d232c77d1486
ms.openlocfilehash: 2e0a5927b8f16116dc07910970268ff6ec35f396
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99798243"
---
# <a name="transport-wse-30-tcp-interoperability"></a><span data-ttu-id="79185-103">Transporte: interoperabilidad de WSE 3.0 TCP</span><span class="sxs-lookup"><span data-stu-id="79185-103">Transport: WSE 3.0 TCP Interoperability</span></span>

<span data-ttu-id="79185-104">El ejemplo de transporte de interoperabilidad de WSE 3,0 TCP muestra cómo implementar una sesión dúplex TCP como un transporte de Windows Communication Foundation personalizado (WCF).</span><span class="sxs-lookup"><span data-stu-id="79185-104">The WSE 3.0 TCP Interoperability Transport sample demonstrates how to implement a TCP duplex session as a custom Windows Communication Foundation (WCF) transport.</span></span> <span data-ttu-id="79185-105">También muestra cómo puede utilizar la extensibilidad de la capa del canal para comunicarse a través de la conexión con sistemas que ya estén implementados.</span><span class="sxs-lookup"><span data-stu-id="79185-105">It also demonstrates how you can use the extensibility of the channel layer to interface over the wire with existing deployed systems.</span></span> <span data-ttu-id="79185-106">En los pasos siguientes se muestra cómo crear este transporte WCF personalizado:</span><span class="sxs-lookup"><span data-stu-id="79185-106">The following steps show how to build this custom WCF transport:</span></span>  
  
1. <span data-ttu-id="79185-107">Comenzando con un socket de TCP, cree las implementaciones del cliente y el servidor de <xref:System.ServiceModel.Channels.IDuplexSessionChannel> que utilizan las tramas de DIME para delinear los límites del mensaje.</span><span class="sxs-lookup"><span data-stu-id="79185-107">Starting with a TCP socket, create client and server implementations of <xref:System.ServiceModel.Channels.IDuplexSessionChannel> that use DIME Framing to delineate message boundaries.</span></span>  
  
2. <span data-ttu-id="79185-108">Cree un generador de canales que conecta a un servicio de WSE TCP y envía los mensajes con tramas por el <xref:System.ServiceModel.Channels.IDuplexSessionChannel> del cliente.</span><span class="sxs-lookup"><span data-stu-id="79185-108">Create a channel factory that connects to a WSE TCP service and sends framed messages over the client <xref:System.ServiceModel.Channels.IDuplexSessionChannel>s.</span></span>  
  
3. <span data-ttu-id="79185-109">Cree un agente de escucha de canal para aceptar conexiones TCP entrantes y producir los canales correspondientes.</span><span class="sxs-lookup"><span data-stu-id="79185-109">Create a channel listener to accept incoming TCP connections and produce corresponding channels.</span></span>  
  
4. <span data-ttu-id="79185-110">Asegúrese de que se normalizan las excepciones específicas de red en la clase derivada adecuada de <xref:System.ServiceModel.CommunicationException>.</span><span class="sxs-lookup"><span data-stu-id="79185-110">Ensure that any network-specific exceptions are normalized to the appropriate derived class of <xref:System.ServiceModel.CommunicationException>.</span></span>  
  
5. <span data-ttu-id="79185-111">Agregue un elemento de enlace que agrega el transporte personalizado a una pila de canales.</span><span class="sxs-lookup"><span data-stu-id="79185-111">Add a binding element that adds the custom transport to a channel stack.</span></span> <span data-ttu-id="79185-112">Para obtener más información, vea [agregar un elemento de enlace].</span><span class="sxs-lookup"><span data-stu-id="79185-112">For more information, see [Adding a Binding Element].</span></span>  
  
## <a name="creating-iduplexsessionchannel"></a><span data-ttu-id="79185-113">Creación de IDuplexSessionChannel</span><span class="sxs-lookup"><span data-stu-id="79185-113">Creating IDuplexSessionChannel</span></span>  

 <span data-ttu-id="79185-114">El primer paso a la hora de escribir el transporte de interoperabilidad de WSE 3.0 TCP es crear una implementación de <xref:System.ServiceModel.Channels.IDuplexSessionChannel> encima de <xref:System.Net.Sockets.Socket>.</span><span class="sxs-lookup"><span data-stu-id="79185-114">The first step in writing the WSE 3.0 TCP Interoperability Transport is to create an implementation of <xref:System.ServiceModel.Channels.IDuplexSessionChannel> on top of a <xref:System.Net.Sockets.Socket>.</span></span> <span data-ttu-id="79185-115">`WseTcpDuplexSessionChannel` se deriva de <xref:System.ServiceModel.Channels.ChannelBase>.</span><span class="sxs-lookup"><span data-stu-id="79185-115">`WseTcpDuplexSessionChannel` derives from <xref:System.ServiceModel.Channels.ChannelBase>.</span></span> <span data-ttu-id="79185-116">La lógica para enviar un mensaje consta de dos elementos principales: (1) codificar el mensaje en bytes y (2) hacer tramas de esos bytes y enviarlos en la conexión.</span><span class="sxs-lookup"><span data-stu-id="79185-116">The logic of sending a message consists of two main pieces: (1) Encoding the message into bytes, and (2) framing those bytes and sending them on the wire.</span></span>  
  
 `ArraySegment<byte> encodedBytes = EncodeMessage(message);`  
  
 `WriteData(encodedBytes);`  
  
 <span data-ttu-id="79185-117">Además, se establece un bloqueo de manera que las llamadas de Send() mantienen la garantía en orden de IduplexSessionChannel y las llamadas al socket subyacente se sincronizan correctamente.</span><span class="sxs-lookup"><span data-stu-id="79185-117">In addition, a lock is taken so that the Send() calls preserve the IDuplexSessionChannel in-order guarantee, and so that calls to the underlying socket are synchronized correctly.</span></span>  
  
 <span data-ttu-id="79185-118">`WseTcpDuplexSessionChannel` utiliza <xref:System.ServiceModel.Channels.MessageEncoder> para traducir un <xref:System.ServiceModel.Channels.Message> a y desde el byte [].</span><span class="sxs-lookup"><span data-stu-id="79185-118">`WseTcpDuplexSessionChannel` uses a <xref:System.ServiceModel.Channels.MessageEncoder> for translating a <xref:System.ServiceModel.Channels.Message> to and from byte[].</span></span> <span data-ttu-id="79185-119">Como es un transporte, `WseTcpDuplexSessionChannel` también es responsable de aplicar la dirección remota con la que se configuró el canal.</span><span class="sxs-lookup"><span data-stu-id="79185-119">Because it is a transport, `WseTcpDuplexSessionChannel` is also responsible for applying the remote address that the channel was configured with.</span></span> <span data-ttu-id="79185-120">`EncodeMessage` encapsula la lógica para esta conversión.</span><span class="sxs-lookup"><span data-stu-id="79185-120">`EncodeMessage` encapsulates the logic for this conversion.</span></span>  
  
 `this.RemoteAddress.ApplyTo(message);`  
  
 `return encoder.WriteMessage(message, maxBufferSize, bufferManager);`  
  
 <span data-ttu-id="79185-121">Una vez que <xref:System.ServiceModel.Channels.Message> se codifica en bytes, se debe transmitir en la conexión.</span><span class="sxs-lookup"><span data-stu-id="79185-121">Once the <xref:System.ServiceModel.Channels.Message> is encoded into bytes, it must be transmitted on the wire.</span></span> <span data-ttu-id="79185-122">Esto requiere un sistema para definir los límites del mensaje.</span><span class="sxs-lookup"><span data-stu-id="79185-122">This requires a system for defining message boundaries.</span></span> <span data-ttu-id="79185-123">WSE 3,0 utiliza una versión de [dime](/archive/msdn-magazine/2002/december/sending-files-attachments-and-soap-messages-via-dime) como protocolo de tramas.</span><span class="sxs-lookup"><span data-stu-id="79185-123">WSE 3.0 uses a version of [DIME](/archive/msdn-magazine/2002/december/sending-files-attachments-and-soap-messages-via-dime) as its framing protocol.</span></span> <span data-ttu-id="79185-124">`WriteData` encapsula la lógica con tramas para ajustar un byte[] en un conjunto de registros de DIME.</span><span class="sxs-lookup"><span data-stu-id="79185-124">`WriteData` encapsulates the framing logic to wrap a byte[] into a set of DIME records.</span></span>  
  
 <span data-ttu-id="79185-125">La lógica para recibir mensajes es similar.</span><span class="sxs-lookup"><span data-stu-id="79185-125">The logic for receiving messages is similar.</span></span> <span data-ttu-id="79185-126">La complejidad principal es controlar el hecho de que una lectura de socket puede devolver menos bytes de los solicitados.</span><span class="sxs-lookup"><span data-stu-id="79185-126">The main complexity is handling the fact that a socket read can return fewer bytes than were requested.</span></span> <span data-ttu-id="79185-127">Para recibir un mensaje, `WseTcpDuplexSessionChannel` lee los bytes fuera de la conexión, descodifica las tramas de DIME y después utiliza <xref:System.ServiceModel.Channels.MessageEncoder> para convertir el byte[] en <xref:System.ServiceModel.Channels.Message>.</span><span class="sxs-lookup"><span data-stu-id="79185-127">To receive a message, `WseTcpDuplexSessionChannel` reads bytes off the wire, decodes the DIME framing, and then uses the <xref:System.ServiceModel.Channels.MessageEncoder> for turning the byte[] into a <xref:System.ServiceModel.Channels.Message>.</span></span>  
  
 <span data-ttu-id="79185-128">El `WseTcpDuplexSessionChannel` base supone que recibe un socket conectado.</span><span class="sxs-lookup"><span data-stu-id="79185-128">The base `WseTcpDuplexSessionChannel` assumes that it receives a connected socket.</span></span> <span data-ttu-id="79185-129">La clase base administra el cierre del socket.</span><span class="sxs-lookup"><span data-stu-id="79185-129">The base class handles socket shutdown.</span></span> <span data-ttu-id="79185-130">Hay tres lugares que actúan de interfaz con el cierre del socket:</span><span class="sxs-lookup"><span data-stu-id="79185-130">There are three places that interface with socket closure:</span></span>  
  
- <span data-ttu-id="79185-131">OnAbort: cierra el socket de manera inadecuada (cierre repentino).</span><span class="sxs-lookup"><span data-stu-id="79185-131">OnAbort -- close the socket ungracefully (hard close).</span></span>  
  
- <span data-ttu-id="79185-132">On[Begin]Close: cierra el socket de manera correcta (cierre suave).</span><span class="sxs-lookup"><span data-stu-id="79185-132">On[Begin]Close -- close the socket gracefully (soft close).</span></span>  
  
- <span data-ttu-id="79185-133">sesión. CloseOutputSession: cierra el flujo de datos de salida (medio cierre).</span><span class="sxs-lookup"><span data-stu-id="79185-133">session.CloseOutputSession -- shut down the outbound data stream (half close).</span></span>  
  
## <a name="channel-factory"></a><span data-ttu-id="79185-134">Generador de canales</span><span class="sxs-lookup"><span data-stu-id="79185-134">Channel Factory</span></span>  

 <span data-ttu-id="79185-135">El paso siguiente para escribir el transporte de TCP es crear una implementación de <xref:System.ServiceModel.Channels.IChannelFactory> para los canales de cliente.</span><span class="sxs-lookup"><span data-stu-id="79185-135">The next step in writing the TCP transport is to create an implementation of <xref:System.ServiceModel.Channels.IChannelFactory> for client channels.</span></span>  
  
- <span data-ttu-id="79185-136">`WseTcpChannelFactory`deriva de <xref:System.ServiceModel.Channels.ChannelFactoryBase> \<IDuplexSessionChannel> .</span><span class="sxs-lookup"><span data-stu-id="79185-136">`WseTcpChannelFactory` derives from <xref:System.ServiceModel.Channels.ChannelFactoryBase>\<IDuplexSessionChannel>.</span></span> <span data-ttu-id="79185-137">Es un generador que invalida `OnCreateChannel` para generar canales de cliente.</span><span class="sxs-lookup"><span data-stu-id="79185-137">It is a factory that overrides `OnCreateChannel` to produce client channels.</span></span>  
  
 `protected override IDuplexSessionChannel OnCreateChannel(EndpointAddress remoteAddress, Uri via)`  
  
 `{`  
  
 `return new ClientWseTcpDuplexSessionChannel(encoderFactory, bufferManager, remoteAddress, via, this);`  
  
 `}`  
  
- <span data-ttu-id="79185-138">`ClientWseTcpDuplexSessionChannel` agrega lógica a la base `WseTcpDuplexSessionChannel` para conectarse a un servidor TCP a la `channel.Open` vez.</span><span class="sxs-lookup"><span data-stu-id="79185-138">`ClientWseTcpDuplexSessionChannel` adds logic to the base `WseTcpDuplexSessionChannel` to connect to a TCP server at `channel.Open` time.</span></span> <span data-ttu-id="79185-139">Primero el nombre de host se resuelve como una dirección IP, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="79185-139">First the hostname is resolved to an IP address, as shown in the following code.</span></span>  
  
 `hostEntry = Dns.GetHostEntry(Via.Host);`  
  
- <span data-ttu-id="79185-140">A continuación, el nombre de host conecta a la primera dirección IP disponible en un bucle, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="79185-140">Then the hostname is connected to the first available IP address in a loop, as shown in the following code.</span></span>  
  
 `IPAddress address = hostEntry.AddressList[i];`  
  
 `socket = new Socket(address.AddressFamily, SocketType.Stream, ProtocolType.Tcp);`  
  
 `socket.Connect(new IPEndPoint(address, port));`  
  
- <span data-ttu-id="79185-141">Como parte del contrato del canal, se ajustan todas las excepciones específicas del dominio, como `SocketException` en <xref:System.ServiceModel.CommunicationException>.</span><span class="sxs-lookup"><span data-stu-id="79185-141">As part of the channel contract, any domain-specific exceptions are wrapped, such as `SocketException` in <xref:System.ServiceModel.CommunicationException>.</span></span>  
  
## <a name="channel-listener"></a><span data-ttu-id="79185-142">Agente de escucha del canal</span><span class="sxs-lookup"><span data-stu-id="79185-142">Channel Listener</span></span>  

 <span data-ttu-id="79185-143">El paso siguiente al escribir el transporte de TCP es crear una implementación de <xref:System.ServiceModel.Channels.IChannelListener> para aceptar los canales del servidor.</span><span class="sxs-lookup"><span data-stu-id="79185-143">The next step in writing the TCP transport is to create an implementation of <xref:System.ServiceModel.Channels.IChannelListener> for accepting server channels.</span></span>  
  
- <span data-ttu-id="79185-144">`WseTcpChannelListener`deriva de <xref:System.ServiceModel.Channels.ChannelListenerBase> \<IDuplexSessionChannel> e invalida en [begin] Open y on [begin] CLOSE para controlar la duración de su socket de escucha.</span><span class="sxs-lookup"><span data-stu-id="79185-144">`WseTcpChannelListener` derives from <xref:System.ServiceModel.Channels.ChannelListenerBase>\<IDuplexSessionChannel> and overrides On[Begin]Open and On[Begin]Close to control the lifetime of its listen socket.</span></span> <span data-ttu-id="79185-145">En OnOpen, se crea un socket para realizar escuchas en IP_ANY.</span><span class="sxs-lookup"><span data-stu-id="79185-145">In OnOpen, a socket is created to listen on IP_ANY.</span></span> <span data-ttu-id="79185-146">Las implementaciones más avanzadas pueden crear un segundo socket para realizar escuchas también en IPv6.</span><span class="sxs-lookup"><span data-stu-id="79185-146">More advanced implementations can create a second socket to listen on IPv6 as well.</span></span> <span data-ttu-id="79185-147">También pueden permitir que la dirección IP se especifique en el nombre de host.</span><span class="sxs-lookup"><span data-stu-id="79185-147">They can also allow the IP address to be specified in the hostname.</span></span>  
  
 `IPEndPoint localEndpoint = new IPEndPoint(IPAddress.Any, uri.Port);`  
  
 `this.listenSocket = new Socket(localEndpoint.AddressFamily, SocketType.Stream, ProtocolType.Tcp);`  
  
 `this.listenSocket.Bind(localEndpoint);`  
  
 `this.listenSocket.Listen(10);`  
  
 <span data-ttu-id="79185-148">Cuando se acepta un nuevo socket, se inicializa un canal de servidor con este socket.</span><span class="sxs-lookup"><span data-stu-id="79185-148">When a new socket is accepted, a server channel is initialized with this socket.</span></span> <span data-ttu-id="79185-149">Ya se ha implementado toda la entrada y salida en la clase base de manera que este canal es el responsable de inicializar el socket.</span><span class="sxs-lookup"><span data-stu-id="79185-149">All the input and output is already implemented in the base class, so this channel is responsible for initializing the socket.</span></span>  
  
## <a name="adding-a-binding-element"></a><span data-ttu-id="79185-150">Adición de un elemento de enlace</span><span class="sxs-lookup"><span data-stu-id="79185-150">Adding a Binding Element</span></span>  

 <span data-ttu-id="79185-151">Ahora que se han creado los generadores y canales, se deben exponer en el tiempo de ejecución de ServiceModel mediante un enlace.</span><span class="sxs-lookup"><span data-stu-id="79185-151">Now that the factories and channels are built, they must be exposed to the ServiceModel runtime through a binding.</span></span> <span data-ttu-id="79185-152">Un enlace es una colección de elementos de enlace que representa la pila de comunicación asociada con una dirección de servicio.</span><span class="sxs-lookup"><span data-stu-id="79185-152">A binding is a collection of binding elements that represents the communication stack associated with a service address.</span></span> <span data-ttu-id="79185-153">Un elemento de enlace está representado por un elemento en la pila.</span><span class="sxs-lookup"><span data-stu-id="79185-153">Each element in the stack is represented by a binding element.</span></span>  
  
 <span data-ttu-id="79185-154">En el ejemplo, el elemento de enlace es `WseTcpTransportBindingElement`, que deriva de <xref:System.ServiceModel.Channels.TransportBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="79185-154">In the sample, the binding element is `WseTcpTransportBindingElement`, which derives from <xref:System.ServiceModel.Channels.TransportBindingElement>.</span></span> <span data-ttu-id="79185-155">Admite <xref:System.ServiceModel.Channels.IDuplexSessionChannel> e invalida los métodos siguientes para crear los generadores asociados con nuestro enlace.</span><span class="sxs-lookup"><span data-stu-id="79185-155">It supports <xref:System.ServiceModel.Channels.IDuplexSessionChannel> and overrides the following methods to build the factories associated with our binding.</span></span>  
  
 `public IChannelFactory<TChannel> BuildChannelFactory<TChannel>(BindingContext context)`  
  
 `{`  
  
 `return (IChannelFactory<TChannel>)(object)new WseTcpChannelFactory(this, context);`  
  
 `}`  
  
 `public IChannelListener<TChannel> BuildChannelListener<TChannel>(BindingContext context)`  
  
 `{`  
  
 `return (IChannelListener<TChannel>)(object)new WseTcpChannelListener(this, context);`  
  
 `}`  
  
 <span data-ttu-id="79185-156">También contiene los miembros para clonar `BindingElement` y devolver nuestro esquema (wse.tcp).</span><span class="sxs-lookup"><span data-stu-id="79185-156">It also contains members for cloning the `BindingElement` and returning our scheme (wse.tcp).</span></span>  
  
## <a name="the-wse-tcp-test-console"></a><span data-ttu-id="79185-157">La consola de prueba de WSE TCP</span><span class="sxs-lookup"><span data-stu-id="79185-157">The WSE TCP Test Console</span></span>  

 <span data-ttu-id="79185-158">El código de prueba que usar para este transporte de ejemplo está disponible en TestCode.cs.</span><span class="sxs-lookup"><span data-stu-id="79185-158">Test code for using this sample transport is available in TestCode.cs.</span></span> <span data-ttu-id="79185-159">Las instrucciones siguientes muestran cómo preparar el ejemplo de WSE `TcpSyncStockService`.</span><span class="sxs-lookup"><span data-stu-id="79185-159">The following instructions show how to set up the WSE `TcpSyncStockService` sample.</span></span>  
  
 <span data-ttu-id="79185-160">El código de prueba crea un enlace personalizado que utiliza MTOM como la codificación y `WseTcpTransport` como el transporte.</span><span class="sxs-lookup"><span data-stu-id="79185-160">The test code creates a custom binding that uses MTOM as the encoding and `WseTcpTransport` as the transport.</span></span> <span data-ttu-id="79185-161">También se configura AddressingVersion para que sea compatible con WSE 3.0, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="79185-161">It also sets up the AddressingVersion to be conformant with WSE 3.0, as shown in the following code.</span></span>  
  
 `CustomBinding binding = new CustomBinding();`  
  
 `MtomMessageEncodingBindingElement mtomBindingElement = new MtomMessageEncodingBindingElement();`  
  
 `mtomBindingElement.MessageVersion = MessageVersion.Soap11WSAddressingAugust2004;`  
  
 `binding.Elements.Add(mtomBindingElement);`  
  
 `binding.Elements.Add(new WseTcpTransportBindingElement());`  
  
 <span data-ttu-id="79185-162">Está compuesto de dos pruebas: una configura un cliente con tipo usando el código generado a partir de WSDL de WSE 3.0.</span><span class="sxs-lookup"><span data-stu-id="79185-162">It consists of two tests—one test sets up a typed client using code generated from the WSE 3.0 WSDL.</span></span> <span data-ttu-id="79185-163">La segunda prueba usa WCF como el cliente y el servidor mediante el envío de mensajes directamente sobre las API del canal.</span><span class="sxs-lookup"><span data-stu-id="79185-163">The second test uses WCF as both the client and the server by sending messages directly on top of the channel APIs.</span></span>  
  
 <span data-ttu-id="79185-164">Al ejecutar el ejemplo, se espera el resultado siguiente.</span><span class="sxs-lookup"><span data-stu-id="79185-164">When running the sample, the following output is expected.</span></span>  
  
 <span data-ttu-id="79185-165">Cliente:</span><span class="sxs-lookup"><span data-stu-id="79185-165">Client:</span></span>  
  
```console  
Calling soap://stockservice.contoso.com/wse/samples/2003/06/TcpSyncStockService  
  
Symbol: FABRIKAM  
        Name: Fabrikam, Inc.  
        Last Price: 120  
  
Symbol: CONTOSO  
        Name: Contoso Corp.  
        Last Price: 50.07  
Press enter.  
  
Received Action: http://SayHello  
Received Body: to you.  
Hello to you.  
Press enter.  
  
Received Action: http://NotHello  
Received Body: to me.  
Press enter.  
```  
  
 <span data-ttu-id="79185-166">Servidor: </span><span class="sxs-lookup"><span data-stu-id="79185-166">Server:</span></span>  
  
```console  
Listening for messages at soap://stockservice.contoso.com/wse/samples/2003/06/TcpSyncStockService  
  
Press any key to exit when done...  
  
Request received.  
Symbols:  
        FABRIKAM  
        CONTOSO  
```  
  
## <a name="set-up-build-and-run-the-sample"></a><span data-ttu-id="79185-167">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="79185-167">Set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="79185-168">Para ejecutar este ejemplo, debe tener [mejoras de servicios web (WSE) 3,0 para Microsoft .net](https://www.microsoft.com/download/details.aspx?id=14089) y el ejemplo de WSE `TcpSyncStockService` instalado.</span><span class="sxs-lookup"><span data-stu-id="79185-168">To run this sample, you must have [Web Services Enhancements (WSE) 3.0 for Microsoft .NET](https://www.microsoft.com/download/details.aspx?id=14089) and the WSE `TcpSyncStockService` sample installed.</span></span>
  
> [!NOTE]
> <span data-ttu-id="79185-169">Dado que WSE 3,0 no se admite en Windows Server 2008, no puede instalar o ejecutar el `TcpSyncStockService` ejemplo en ese sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="79185-169">Because WSE 3.0 is not supported on Windows Server 2008, you cannot install or run the `TcpSyncStockService` sample on that operating system.</span></span>  
  
1. <span data-ttu-id="79185-170">Una vez instalado el ejemplo de `TcpSyncStockService`, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="79185-170">Once you install the `TcpSyncStockService` sample, do the following:</span></span>  
  
    1. <span data-ttu-id="79185-171">Abra el `TcpSyncStockService` en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="79185-171">Open the `TcpSyncStockService` in Visual Studio.</span></span> <span data-ttu-id="79185-172">(El ejemplo TcpSyncStockService se instala con WSE 3,0.</span><span class="sxs-lookup"><span data-stu-id="79185-172">(The TcpSyncStockService sample is installed with WSE 3.0.</span></span> <span data-ttu-id="79185-173">No forma parte del código de este ejemplo).</span><span class="sxs-lookup"><span data-stu-id="79185-173">It is not part of this sample's code.)</span></span>  
  
    2. <span data-ttu-id="79185-174">Establezca el proyecto StockService como el proyecto de inicio.</span><span class="sxs-lookup"><span data-stu-id="79185-174">Set the StockService project as the start-up project.</span></span>  
  
    3. <span data-ttu-id="79185-175">Abra StockService.cs en el proyecto StockService y marque como comentario el atributo [Policy] en la clase `StockService`.</span><span class="sxs-lookup"><span data-stu-id="79185-175">Open StockService.cs in the StockService project and comment out the [Policy] attribute on the `StockService` class.</span></span> <span data-ttu-id="79185-176">Esto deshabilita la seguridad del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="79185-176">This disables security from the sample.</span></span> <span data-ttu-id="79185-177">Aunque WCF puede interoperar con los puntos de conexión seguros de WSE 3,0, se deshabilita la seguridad para mantener este ejemplo centrado en el transporte TCP personalizado.</span><span class="sxs-lookup"><span data-stu-id="79185-177">While WCF can interoperate with WSE 3.0 secure endpoints, security is disabled to keep this sample focused on the custom TCP transport.</span></span>  
  
    4. <span data-ttu-id="79185-178">Presione F5 para iniciar la solución `TcpSyncStockService`.</span><span class="sxs-lookup"><span data-stu-id="79185-178">Press F5 to start the `TcpSyncStockService`.</span></span> <span data-ttu-id="79185-179">El servicio se inicia en una nueva ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="79185-179">The service starts in a new console window.</span></span>  
  
    5. <span data-ttu-id="79185-180">Abra este ejemplo de transporte de TCP en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="79185-180">Open this TCP transport sample in Visual Studio.</span></span>  
  
    6. <span data-ttu-id="79185-181">Actualice la variable de "nombre del host" en TestCode.cs para que coincida con el nombre de equipo que ejecuta `TcpSyncStockService`.</span><span class="sxs-lookup"><span data-stu-id="79185-181">Update the "hostname" variable in TestCode.cs to match the machine name running the `TcpSyncStockService`.</span></span>  
  
    7. <span data-ttu-id="79185-182">Presione F5 para iniciar el ejemplo de transporte de TCP.</span><span class="sxs-lookup"><span data-stu-id="79185-182">Press F5 to start the TCP transport sample.</span></span>  
  
    8. <span data-ttu-id="79185-183">El cliente de prueba de transporte de TCP se inicia en una nueva consola.</span><span class="sxs-lookup"><span data-stu-id="79185-183">The TCP transport test client starts in a new console.</span></span> <span data-ttu-id="79185-184">El cliente solicita las cotizaciones bursátiles desde el servicio y después muestra los resultados en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="79185-184">The client requests stock quotes from the service and then displays the results in its console window.</span></span>
