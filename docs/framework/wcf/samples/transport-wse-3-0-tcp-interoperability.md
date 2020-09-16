---
title: 'Transporte: interoperabilidad de WSE 3.0 TCP'
ms.date: 03/30/2017
ms.assetid: 5f7c3708-acad-4eb3-acb9-d232c77d1486
ms.openlocfilehash: f61d5037af0be6579d5110152ca070bec586fe87
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90558971"
---
# <a name="transport-wse-30-tcp-interoperability"></a>Transporte: interoperabilidad de WSE 3.0 TCP
El ejemplo de transporte de interoperabilidad de WSE 3,0 TCP muestra cómo implementar una sesión dúplex TCP como un transporte de Windows Communication Foundation personalizado (WCF). También muestra cómo puede utilizar la extensibilidad de la capa del canal para comunicarse a través de la conexión con sistemas que ya estén implementados. En los pasos siguientes se muestra cómo crear este transporte WCF personalizado:  
  
1. Comenzando con un socket de TCP, cree las implementaciones del cliente y el servidor de <xref:System.ServiceModel.Channels.IDuplexSessionChannel> que utilizan las tramas de DIME para delinear los límites del mensaje.  
  
2. Cree un generador de canales que conecta a un servicio de WSE TCP y envía los mensajes con tramas por el <xref:System.ServiceModel.Channels.IDuplexSessionChannel> del cliente.  
  
3. Cree un agente de escucha de canal para aceptar conexiones TCP entrantes y producir los canales correspondientes.  
  
4. Asegúrese de que se normalizan las excepciones específicas de red en la clase derivada adecuada de <xref:System.ServiceModel.CommunicationException>.  
  
5. Agregue un elemento de enlace que agrega el transporte personalizado a una pila de canales. Para obtener más información, vea [agregar un elemento de enlace].  
  
## <a name="creating-iduplexsessionchannel"></a>Creación de IDuplexSessionChannel  
 El primer paso a la hora de escribir el transporte de interoperabilidad de WSE 3.0 TCP es crear una implementación de <xref:System.ServiceModel.Channels.IDuplexSessionChannel> encima de <xref:System.Net.Sockets.Socket>. `WseTcpDuplexSessionChannel` se deriva de <xref:System.ServiceModel.Channels.ChannelBase>. La lógica para enviar un mensaje consta de dos elementos principales: (1) codificar el mensaje en bytes y (2) hacer tramas de esos bytes y enviarlos en la conexión.  
  
 `ArraySegment<byte> encodedBytes = EncodeMessage(message);`  
  
 `WriteData(encodedBytes);`  
  
 Además, se establece un bloqueo de manera que las llamadas de Send() mantienen la garantía en orden de IduplexSessionChannel y las llamadas al socket subyacente se sincronizan correctamente.  
  
 `WseTcpDuplexSessionChannel` utiliza <xref:System.ServiceModel.Channels.MessageEncoder> para traducir un <xref:System.ServiceModel.Channels.Message> a y desde el byte []. Como es un transporte, `WseTcpDuplexSessionChannel` también es responsable de aplicar la dirección remota con la que se configuró el canal. `EncodeMessage` encapsula la lógica para esta conversión.  
  
 `this.RemoteAddress.ApplyTo(message);`  
  
 `return encoder.WriteMessage(message, maxBufferSize, bufferManager);`  
  
 Una vez que <xref:System.ServiceModel.Channels.Message> se codifica en bytes, se debe transmitir en la conexión. Esto requiere un sistema para definir los límites del mensaje. WSE 3,0 utiliza una versión de [dime](/archive/msdn-magazine/2002/december/sending-files-attachments-and-soap-messages-via-dime) como protocolo de tramas. `WriteData` encapsula la lógica con tramas para ajustar un byte[] en un conjunto de registros de DIME.  
  
 La lógica para recibir mensajes es similar. La complejidad principal es controlar el hecho de que una lectura de socket puede devolver menos bytes de los solicitados. Para recibir un mensaje, `WseTcpDuplexSessionChannel` lee los bytes fuera de la conexión, descodifica las tramas de DIME y después utiliza <xref:System.ServiceModel.Channels.MessageEncoder> para convertir el byte[] en <xref:System.ServiceModel.Channels.Message>.  
  
 El `WseTcpDuplexSessionChannel` base supone que recibe un socket conectado. La clase base administra el cierre del socket. Hay tres lugares que actúan de interfaz con el cierre del socket:  
  
- OnAbort: cierra el socket de manera inadecuada (cierre repentino).  
  
- On[Begin]Close: cierra el socket de manera correcta (cierre suave).  
  
- sesión. CloseOutputSession: cierra el flujo de datos de salida (medio cierre).  
  
## <a name="channel-factory"></a>Generador de canales  
 El paso siguiente para escribir el transporte de TCP es crear una implementación de <xref:System.ServiceModel.Channels.IChannelFactory> para los canales de cliente.  
  
- `WseTcpChannelFactory`deriva de <xref:System.ServiceModel.Channels.ChannelFactoryBase> \<IDuplexSessionChannel> . Es un generador que invalida `OnCreateChannel` para generar canales de cliente.  
  
 `protected override IDuplexSessionChannel OnCreateChannel(EndpointAddress remoteAddress, Uri via)`  
  
 `{`  
  
 `return new ClientWseTcpDuplexSessionChannel(encoderFactory, bufferManager, remoteAddress, via, this);`  
  
 `}`  
  
- `ClientWseTcpDuplexSessionChannel` agrega lógica a la base `WseTcpDuplexSessionChannel` para conectarse a un servidor TCP a la `channel.Open` vez. Primero el nombre de host se resuelve como una dirección IP, como se muestra en el código siguiente.  
  
 `hostEntry = Dns.GetHostEntry(Via.Host);`  
  
- A continuación, el nombre de host conecta a la primera dirección IP disponible en un bucle, como se muestra en el código siguiente.  
  
 `IPAddress address = hostEntry.AddressList[i];`  
  
 `socket = new Socket(address.AddressFamily, SocketType.Stream, ProtocolType.Tcp);`  
  
 `socket.Connect(new IPEndPoint(address, port));`  
  
- Como parte del contrato del canal, se ajustan todas las excepciones específicas del dominio, como `SocketException` en <xref:System.ServiceModel.CommunicationException>.  
  
## <a name="channel-listener"></a>Agente de escucha del canal  
 El paso siguiente al escribir el transporte de TCP es crear una implementación de <xref:System.ServiceModel.Channels.IChannelListener> para aceptar los canales del servidor.  
  
- `WseTcpChannelListener`deriva de <xref:System.ServiceModel.Channels.ChannelListenerBase> \<IDuplexSessionChannel> e invalida en [begin] Open y on [begin] CLOSE para controlar la duración de su socket de escucha. En OnOpen, se crea un socket para realizar escuchas en IP_ANY. Las implementaciones más avanzadas pueden crear un segundo socket para realizar escuchas también en IPv6. También pueden permitir que la dirección IP se especifique en el nombre de host.  
  
 `IPEndPoint localEndpoint = new IPEndPoint(IPAddress.Any, uri.Port);`  
  
 `this.listenSocket = new Socket(localEndpoint.AddressFamily, SocketType.Stream, ProtocolType.Tcp);`  
  
 `this.listenSocket.Bind(localEndpoint);`  
  
 `this.listenSocket.Listen(10);`  
  
 Cuando se acepta un nuevo socket, se inicializa un canal de servidor con este socket. Ya se ha implementado toda la entrada y salida en la clase base de manera que este canal es el responsable de inicializar el socket.  
  
## <a name="adding-a-binding-element"></a>Adición de un elemento de enlace  
 Ahora que se han creado los generadores y canales, se deben exponer en el tiempo de ejecución de ServiceModel mediante un enlace. Un enlace es una colección de elementos de enlace que representa la pila de comunicación asociada con una dirección de servicio. Un elemento de enlace está representado por un elemento en la pila.  
  
 En el ejemplo, el elemento de enlace es `WseTcpTransportBindingElement`, que deriva de <xref:System.ServiceModel.Channels.TransportBindingElement>. Admite <xref:System.ServiceModel.Channels.IDuplexSessionChannel> e invalida los métodos siguientes para crear los generadores asociados con nuestro enlace.  
  
 `public IChannelFactory<TChannel> BuildChannelFactory<TChannel>(BindingContext context)`  
  
 `{`  
  
 `return (IChannelFactory<TChannel>)(object)new WseTcpChannelFactory(this, context);`  
  
 `}`  
  
 `public IChannelListener<TChannel> BuildChannelListener<TChannel>(BindingContext context)`  
  
 `{`  
  
 `return (IChannelListener<TChannel>)(object)new WseTcpChannelListener(this, context);`  
  
 `}`  
  
 También contiene los miembros para clonar `BindingElement` y devolver nuestro esquema (wse.tcp).  
  
## <a name="the-wse-tcp-test-console"></a>La consola de prueba de WSE TCP  
 El código de prueba que usar para este transporte de ejemplo está disponible en TestCode.cs. Las instrucciones siguientes muestran cómo preparar el ejemplo de WSE `TcpSyncStockService`.  
  
 El código de prueba crea un enlace personalizado que utiliza MTOM como la codificación y `WseTcpTransport` como el transporte. También se configura AddressingVersion para que sea compatible con WSE 3.0, como se muestra en el código siguiente.  
  
 `CustomBinding binding = new CustomBinding();`  
  
 `MtomMessageEncodingBindingElement mtomBindingElement = new MtomMessageEncodingBindingElement();`  
  
 `mtomBindingElement.MessageVersion = MessageVersion.Soap11WSAddressingAugust2004;`  
  
 `binding.Elements.Add(mtomBindingElement);`  
  
 `binding.Elements.Add(new WseTcpTransportBindingElement());`  
  
 Está compuesto de dos pruebas: una configura un cliente con tipo usando el código generado a partir de WSDL de WSE 3.0. La segunda prueba usa WCF como el cliente y el servidor mediante el envío de mensajes directamente sobre las API del canal.  
  
 Al ejecutar el ejemplo, se espera el resultado siguiente.  
  
 Cliente:  
  
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
  
 Servidor:   
  
```console  
Listening for messages at soap://stockservice.contoso.com/wse/samples/2003/06/TcpSyncStockService  
  
Press any key to exit when done...  
  
Request received.  
Symbols:  
        FABRIKAM  
        CONTOSO  
```  
  
## <a name="set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1. Para ejecutar este ejemplo, debe tener [mejoras de servicios web (WSE) 3,0 para Microsoft .net](https://www.microsoft.com/download/details.aspx?id=14089) y el ejemplo de WSE `TcpSyncStockService` instalado.
  
> [!NOTE]
> Dado que WSE 3,0 no se admite en Windows Server 2008, no puede instalar o ejecutar el `TcpSyncStockService` ejemplo en ese sistema operativo.  
  
1. Una vez instalado el ejemplo de `TcpSyncStockService`, haga lo siguiente:  
  
    1. Abra el `TcpSyncStockService` en Visual Studio. (El ejemplo TcpSyncStockService se instala con WSE 3,0. No forma parte del código de este ejemplo).  
  
    2. Establezca el proyecto StockService como el proyecto de inicio.  
  
    3. Abra StockService.cs en el proyecto StockService y marque como comentario el atributo [Policy] en la clase `StockService`. Esto deshabilita la seguridad del ejemplo. Aunque WCF puede interoperar con los puntos de conexión seguros de WSE 3,0, se deshabilita la seguridad para mantener este ejemplo centrado en el transporte TCP personalizado.  
  
    4. Presione F5 para iniciar la solución `TcpSyncStockService`. El servicio se inicia en una nueva ventana de la consola.  
  
    5. Abra este ejemplo de transporte de TCP en Visual Studio.  
  
    6. Actualice la variable de "nombre del host" en TestCode.cs para que coincida con el nombre de equipo que ejecuta `TcpSyncStockService`.  
  
    7. Presione F5 para iniciar el ejemplo de transporte de TCP.  
  
    8. El cliente de prueba de transporte de TCP se inicia en una nueva consola. El cliente solicita las cotizaciones bursátiles desde el servicio y después muestra los resultados en la ventana de la consola.
