---
title: Canal de fragmentación
ms.date: 03/30/2017
ms.assetid: e4d53379-b37c-4b19-8726-9cc914d5d39f
ms.openlocfilehash: 3811f7e7229dec1a46585a558b96f94bb202902f
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716026"
---
# <a name="chunking-channel"></a>Canal de fragmentación

Al enviar mensajes de gran tamaño mediante Windows Communication Foundation (WCF), a menudo es conveniente limitar la cantidad de memoria usada para almacenar en búfer esos mensajes. Una posible solución es transmitir en secuencias el cuerpo del mensaje (suponiendo que la mayor parte de los datos se encuentra en el cuerpo). Sin embargo, algunos protocolos requieren almacenado en búfer del mensaje completo. La mensajería de confianza y la seguridad son dos ejemplos de lo anterior. Otra posible solución es dividir el mensaje grande en mensajes menores llamados fragmentos, enviar uno por uno esos fragmentos y reconstituir el mensaje entero en el lado receptor. La propia aplicación podría hacer esta fragmentación y desfragmentación, o podría utilizar un canal personalizado para hacerlo. El canal de fragmentación muestra cómo un protocolo personalizado o un canal en capas se pueden utilizar para la fragmentación y desfragmentación de mensajes arbitrariamente grandes.

Siempre se debería emplear la fragmentación solo una vez construido el mensaje completo que se va a enviar. Un canal de fragmentación siempre se debería disponer en niveles debajo de un canal de seguridad y un canal de sesión confiable.

> [!NOTE]
> El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.

> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos de Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)]. Este ejemplo se encuentra en el siguiente directorio.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\ChunkingChannel`

## <a name="chunking-channel-assumptions-and-limitations"></a>Supuestos y limitaciones del canal de fragmentación

### <a name="message-structure"></a>Estructura del mensaje

El canal de fragmentación supone la estructura de mensaje siguiente para que los mensajes estén fragmentados:

```xml
<soap:Envelope ...>
  <!-- headers -->
  <soap:Body>
    <operationElement>
      <paramElement>data to be chunked</paramElement>
    </operationElement>
  </soap:Body>
</soap:Envelope>
```

Al utilizar ServiceModel, las operaciones de contrato que tienen 1 parámetro de entrada cumplen con esta forma de mensaje para su mensaje de entrada. De manera similar, las operaciones de contrato que tienen 1 parámetro de salida o valor devuelto cumplen con esta forma de mensaje para su mensaje de salida. A continuación, se muestran ejemplos de tales operaciones:

```csharp
[ServiceContract]
interface ITestService
{
    [OperationContract]
    Stream EchoStream(Stream stream);

    [OperationContract]
    Stream DownloadStream();

    [OperationContract(IsOneWay = true)]
    void UploadStream(Stream stream);
}
```

### <a name="sessions"></a>Sesiones

El canal de fragmentación requiere que los mensajes se entreguen exactamente una vez, en entrega ordenada de mensajes (fragmentos). Esto significa que la pila del canal subyacente debe tener sesión. Las sesiones se pueden proporcionar por el transporte (por ejemplo, transporte TCP) o por un canal protocolar con sesión (por ejemplo, ReliableSession acanalan).

### <a name="asynchronous-send-and-receive"></a>Enviós y recepciones asincrónicos

Los métodos de envíos y recepciones asincrónicos no se implementan en esta versión de ejemplo del canal de fragmentación.

## <a name="chunking-protocol"></a>Protocolo de fragmentación

El canal de fragmentación define un protocolo que indica el inicio y fin de una serie de fragmentos, así como el número de secuencia de cada fragmento. Los tres mensajes del ejemplo siguientes muestran los mensajes de inicio, fragmento y fin con comentarios que describen los aspectos clave de cada uno.

### <a name="start-message"></a>Mensaje de comienzo

```xml
<s:Envelope xmlns:a="http://www.w3.org/2005/08/addressing"
            xmlns:s="http://www.w3.org/2003/05/soap-envelope">
  <s:Header>
<!--Original message action is replaced with a chunking-specific action. -->
    <a:Action s:mustUnderstand="1">http://samples.microsoft.com/chunkingAction</a:Action>
<!--
Original message is assigned a unique id that is transmitted
in a MessageId header. Note that this is different from the WS-Addressing MessageId header.
-->
    <MessageId s:mustUnderstand="1" xmlns="http://samples.microsoft.com/chunking">
53f183ee-04aa-44a0-b8d3-e45224563109
</MessageId>
<!--
ChunkingStart header signals the start of a chunked message.
-->
    <ChunkingStart s:mustUnderstand="1" i:nil="true" xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://samples.microsoft.com/chunking" />
<!--
Original message action is transmitted in OriginalAction.
This is required to re-create the original message on the other side.
-->
    <OriginalAction xmlns="http://samples.microsoft.com/chunking">
http://tempuri.org/ITestService/EchoStream
    </OriginalAction>
   <!--
    All original message headers are included here.
   -->
  </s:Header>
  <s:Body>
<!--
Chunking assumes this structure of Body content:
<element>
  <childelement>large data to be chunked<childelement>
</element>
The start message contains just <element> and <childelement> without
the data to be chunked.
-->
    <EchoStream xmlns="http://tempuri.org/">
      <stream />
    </EchoStream>
  </s:Body>
</s:Envelope>
```

### <a name="chunk-message"></a>Mensaje fragmento

```xml
<s:Envelope
  xmlns:a="http://www.w3.org/2005/08/addressing"
  xmlns:s="http://www.w3.org/2003/05/soap-envelope">
  <s:Header>
   <!--
    All chunking protocol messages have this action.
   -->
    <a:Action s:mustUnderstand="1">
      http://samples.microsoft.com/chunkingAction
    </a:Action>
<!--
Same as MessageId in the start message. The GUID indicates which original message this chunk belongs to.
-->
    <MessageId s:mustUnderstand="1"
               xmlns="http://samples.microsoft.com/chunking">
      53f183ee-04aa-44a0-b8d3-e45224563109
    </MessageId>
<!--
The sequence number of the chunk.
This number restarts at 1 with each new sequence of chunks.
-->
    <ChunkNumber s:mustUnderstand="1"
                 xmlns="http://samples.microsoft.com/chunking">
      1096
    </ChunkNumber>
  </s:Header>
  <s:Body>
<!--
The chunked data is wrapped in a chunk element.
The encoding of this data (and the entire message)
depends on the encoder used. The chunking channel does not mandate an encoding.
-->
    <chunk xmlns="http://samples.microsoft.com/chunking">
kfSr2QcBlkHTvQ==
    </chunk>
  </s:Body>
</s:Envelope>
```

### <a name="end-message"></a>Mensaje final

```xml
<s:Envelope xmlns:a="http://www.w3.org/2005/08/addressing"
            xmlns:s="http://www.w3.org/2003/05/soap-envelope">
  <s:Header>
    <a:Action s:mustUnderstand="1">
      http://samples.microsoft.com/chunkingAction
    </a:Action>
<!--
Same as MessageId in the start message. The GUID indicates which original message this chunk belongs to.
-->
    <MessageId s:mustUnderstand="1"
               xmlns="http://samples.microsoft.com/chunking">
      53f183ee-04aa-44a0-b8d3-e45224563109
    </MessageId>
<!--
ChunkingEnd header signals the end of a chunk sequence.
-->
    <ChunkingEnd s:mustUnderstand="1" i:nil="true"
                 xmlns:i="http://www.w3.org/2001/XMLSchema-instance"
                 xmlns="http://samples.microsoft.com/chunking" />
<!--
ChunkingEnd messages have a sequence number.
-->
    <ChunkNumber s:mustUnderstand="1"
                 xmlns="http://samples.microsoft.com/chunking">
      79
    </ChunkNumber>
  </s:Header>
  <s:Body>
<!--
The ChunkingEnd message has the same <element><childelement> structure
as the ChunkingStart message.
-->
    <EchoStream xmlns="http://tempuri.org/">
      <stream />
    </EchoStream>
  </s:Body>
</s:Envelope>
```

## <a name="chunking-channel-architecture"></a>Arquitectura del canal de fragmentación

El canal de fragmentación es un `IDuplexSessionChannel` que, a un nivel alto, sigue la arquitectura de canal típica. Hay un `ChunkingBindingElement` que puede generar un `ChunkingChannelFactory` y un `ChunkingChannelListener`. `ChunkingChannelFactory` crea instancias de `ChunkingChannel` cuando se le pide. `ChunkingChannelListener` crea instancias de `ChunkingChannel` cuando se acepta un nuevo canal interno. El propio `ChunkingChannel` es responsable de enviar y recibir los mensajes.

En el siguiente nivel inferior, `ChunkingChannel` confia en varios componentes para implementar el protocolo de fragmentación. En el lado emisor, el canal usa un <xref:System.Xml.XmlDictionaryWriter> personalizado denominado `ChunkingWriter` que realiza la fragmentación real. `ChunkingWriter` usa el canal interno directamente para enviar fragmentos. Utilizar un `XmlDictionaryWriter` personalizado nos permite mandar fragmentos mientras se escribe el cuerpo grande del mensaje original. Esto significa que no almacenamos en búfer el mensaje original completo.

![Diagrama que muestra la arquitectura de envío del canal de fragmentación.](./media/chunking-channel/chunking-channel-send.gif)

En el lado receptor, `ChunkingChannel` extrae mensajes del canal interno y los ofrece a un <xref:System.Xml.XmlDictionaryReader> personalizado denominado `ChunkingReader`, que reconstituye el mensaje original a partir de los fragmentos de entrada. `ChunkingChannel` ajusta este `ChunkingReader` en una implementación de `Message``ChunkingMessage` personalizada y devuelve este mensaje al nivel anterior. Esta combinación de `ChunkingReader` y `ChunkingMessage` nos permite al anular la fragmentación del cuerpo del mensaje original mientras la lee el nivel anterior en lugar de tener que almacenar en búfer todo el cuerpo del mensaje original. `ChunkingReader` tiene una cola donde almacena en búfer fragmentos de entrada hasta un número máximo configurable de fragmentos almacenados en búfer. Cuando se alcanza este límite máximo, el lector espera que la capa superior recoja los mensajes de la cola (es decir, simplemente leyendo el cuerpo del mensaje original) o hasta que se alcance el tiempo de espera máximo de recepción.

![Diagrama que muestra la arquitectura de recepción del canal de fragmentación.](./media/chunking-channel/chunking-channel-receive.gif)

## <a name="chunking-programming-model"></a>Modelo de programación de fragmentación

Los programadores del servicio pueden especificar qué mensajes deben ser fragmentados, aplicando el atributo `ChunkingBehavior` a las operaciones dentro del contrato. El atributo expone una propiedad `AppliesTo` que permite al desarrollador especificar si la desfragmentación se aplica al mensaje de entrada, el mensaje de salida o ambos. En el ejemplo siguiente se muestra el uso del atributo `ChunkingBehavior`:

```csharp
[ServiceContract]
interface ITestService
{
    [OperationContract]
    [ChunkingBehavior(ChunkingAppliesTo.Both)]
    Stream EchoStream(Stream stream);

    [OperationContract]
    [ChunkingBehavior(ChunkingAppliesTo.OutMessage)]
    Stream DownloadStream();

    [OperationContract(IsOneWay=true)]
    [ChunkingBehavior(ChunkingAppliesTo.InMessage)]
    void UploadStream(Stream stream);

}
```

De este modelo de programación, `ChunkingBindingElement` compila una lista de URI de acción que identifica los mensajes que se deben fragmentar. La acción de cada mensaje saliente se compara contra esta lista para determinar si el mensaje se debería fragmentar o enviar directamente.

## <a name="implementing-the-send-operation"></a>Implementar la operación Send

A un nivel alto, la operación Send comprueba primero si el mensaje saliente debe fragmentarse y, si no, envía el mensaje directamente mediante el canal interno.

Si el mensaje debe fragmentarse, Send crea un nuevo `ChunkingWriter` y llama `WriteBodyContents` en el mensaje saliente pasándole este `ChunkingWriter`. `ChunkingWriter` realiza a continuación la fragmentación del mensaje (incluyendo copiar los encabezados originales del mensaje al fragmento inicial del mensaje) y envía fragmentos mediante el canal interno.

Detalles que se han de tener en cuenta:

- Send primero llama a `ThrowIfDisposedOrNotOpened` para asegurar que se abre `CommunicationState`.

- El envío se sincroniza, para que solo un mensaje se pueda enviar a la vez para cada sesión. Hay un `ManualResetEvent` denominado `sendingDone` que se restablece cuando se envía un mensaje fragmentado. Una vez enviado el fragmento del mensaje final, se establece este evento. El método Send espera a que este evento esté establecido antes de intentar enviar el mensaje saliente.

- Send bloquea el `CommunicationObject.ThisLock` para evitar cambios de estado sincronizados mientras se realiza el envío. Consulte la documentación <xref:System.ServiceModel.Channels.CommunicationObject> para obtener más información sobre los estados y el equipo de estado <xref:System.ServiceModel.Channels.CommunicationObject>.

- El tiempo de espera pasado a Send se utiliza como tiempo de espera para la operación de envío al completo, la cual incluye el envío de todos los fragmentos.

- El diseño <xref:System.Xml.XmlDictionaryWriter> personalizado fue elegido para evitar almacenar en búfer el cuerpo del mensaje original completo. Si deseáramos obtener un <xref:System.Xml.XmlDictionaryReader> en el cuerpo utilizando `message.GetReaderAtBodyContents` el cuerpo completo se almacenaría en búfer. En su lugar, tenemos una <xref:System.Xml.XmlDictionaryWriter> personalizada que se pasa a `message.WriteBodyContents`. Mientras el mensaje llama a WriteBase64 en el sistema de escritura, el sistema de escritura empaqueta los fragmentos en los mensajes y los envía utilizando el canal interno. WriteBase64 se bloquea hasta que se envía el fragmento.

## <a name="implementing-the-receive-operation"></a>Implementar la operación Receive

A un nivel alto, la operación Receive comprueba primero que el mensaje entrante no es `null` y que su acción es `ChunkingAction`. Si no cumple ambos criterios, el mensaje se devuelve sin modificar desde Receive. De lo contrario, Receive crea un nuevo `ChunkingReader` y un nuevo `ChunkingMessage` ajustado alrededor de él (llamando a `GetNewChunkingMessage`). Antes de devolver ese nuevo `ChunkingMessage`, Receive utiliza un subproceso de un conjunto de subprocesos para ejecutar `ReceiveChunkLoop`, que llama `innerChannel.Receive` en un bucle y entrega fragmentos a `ChunkingReader` hasta que se reciba el fragmento de mensaje final o se alcance el tiempo de espera de recepción.

Detalles que se han de tener en cuenta:

- Al igual que Send, Receive primero llama `ThrowIfDisposedOrNotOepned` para asegurar que se abre `CommunicationState`.

- Receive también se sincroniza para que solo se pueda recibir un mensaje de la sesión al mismo tiempo. Esto es especialmente importante porque una vez se recibe un fragmento de mensaje de inicio, se espera que todos los mensajes siguientes recibidos sean fragmentos de esta nueva secuencia de fragmentos hasta que se reciba un fragmento de mensaje final. Receive no puede incorporar los cambios de los mensajes del canal interno hasta que no se reciban todos los fragmentos que pertenecen al mensaje que se está desfragmentando. Para lograr esto, Receive utiliza un `ManualResetEvent` denominado `currentMessageCompleted`, que se establece cuando el fragmento de mensaje final se recibe y se restablece cuando se recibe un nuevo fragmento de mensaje de inicio.

- A diferencia de Send, Receive no evita las transiciones de estado sincronizadas mientras recibe. Por ejemplo, se puede llamar a Close mientras se recibe y se espera hasta que las recepciones pendientes del mensaje original se completen o se alcance el valor de tiempo de espera especificado.

- El tiempo de espera pasado a Receive se utiliza como tiempo de espera para la operación de recepción completa, que incluye la recepción todos los fragmentos.

- Si la capa que consume el mensaje está consumiendo el cuerpo del mensaje a una tasa menor que la tasa de llegadas de fragmentos de mensajes, el `ChunkingReader` almacena en búfer esos fragmentos de entrada hasta el límite especificado por `ChunkingBindingElement.MaxBufferedChunks`. Una vez alcanzado ese límite, ningún fragmento más se extrae de la capa inferior hasta que un fragmento almacenado en búfer se utiliza o se alcanza el tiempo de espera para la recepción.

## <a name="communicationobject-overrides"></a>Invalidaciones de CommunicationObject

### <a name="onopen"></a>OnOpen

`OnOpen` llama `innerChannel.Open` para abrir el canal interno.

### <a name="onclose"></a>OnClose

`OnClose` establece primero `stopReceive` a `true` para señalar el `ReceiveChunkLoop` pendiente para detenerse. Después espera el <xref:System.Threading.ManualResetEvent>de `receiveStopped`, que se establece cuando `ReceiveChunkLoop` se detiene. Suponiendo las pausas `ReceiveChunkLoop` dentro del tiempo de espera especificado, `OnClose` llama `innerChannel.Close` con el tiempo de espera restante.

### <a name="onabort"></a>OnAbort

`OnAbort` llama `innerChannel.Abort` para anular el canal interno. Si hay un `ReceiveChunkLoop` pendiente, recibe a una excepción de la llamada `innerChannel.Receive` pendiente.

### <a name="onfaulted"></a>OnFaulted

`ChunkingChannel` no requiere comportamiento especial cuando el canal tiene errores, por lo que no se invalida `OnFaulted`.

## <a name="implementing-channel-factory"></a>Implementar el generador de canales

`ChunkingChannelFactory` es responsable de crear instancias de `ChunkingDuplexSessionChannel` y de colocar en cascada las transiciones de estado al generador de canales interno.

`OnCreateChannel` utiliza el generador de canales interno para crear un canal interno `IDuplexSessionChannel`. Crea a continuación un nuevo `ChunkingDuplexSessionChannel` que le pasa este canal interno junto con la lista de acciones de mensaje para ser fragmentada y el número máximo de fragmentos para almacenar en búfer cuando se produce la recepción. La lista de acciones de mensaje para ser fragmentada y el número máximo de fragmentos para almacenar en búfer son dos parámetros pasados a `ChunkingChannelFactory` en su constructor. La sección en `ChunkingBindingElement` describe de dónde proceden estos valores.

`OnOpen`, `OnClose`, `OnAbort` y sus equivalentes asincrónicos llaman al método de transición de estado correspondiente en el generador de canales interno.

## <a name="implementing-channel-listener"></a>Implementar el escuchado del canal

`ChunkingChannelListener` es un contenedor alrededor de una escucha de canal interno. Su función principal, además de delegar llamadas a esa escucha del canal interno, es ajustar nuevo `ChunkingDuplexSessionChannels` alrededor de los canales aceptados por la escucha del canal interno. Esto se hace en `OnAcceptChannel` y `OnEndAcceptChannel`. El `ChunkingDuplexSessionChannel` recientemente creado se pasa al canal interno junto con los otros parámetros descritos previamente.

## <a name="implementing-binding-element-and-binding"></a>Implementar elemento de enlace y enlace

`ChunkingBindingElement` es el responsable de crear el `ChunkingChannelFactory` y `ChunkingChannelListener`. El `ChunkingBindingElement` comprueba si T en `CanBuildChannelFactory`\<T > y `CanBuildChannelListener`\<T > es de tipo `IDuplexSessionChannel` (el único canal que admite el canal de fragmentación) y que los otros elementos de enlace del enlace admiten este tipo de canal.

`BuildChannelFactory`\<T > primero comprueba que el tipo de canal solicitado se puede compilar y, a continuación, obtiene una lista de acciones de mensaje que se van a fragmentar. Para obtener más información, vea la siguiente sección: Crea a continuación un nuevo `ChunkingChannelFactory` que le pasa el generador de canales interno (tal y como se devolvió desde `context.BuildInnerChannelFactory<IDuplexSessionChannel>`), la lista de acciones de mensaje, y el número máximo de fragmentos para almacenar en búfer. El número máximo de fragmentos procede de una propiedad llamada `MaxBufferedChunks` expuesta por el `ChunkingBindingElement`.

`BuildChannelListener<T>` tiene una implementación similar para crear `ChunkingChannelListener` y pasarle el agente de escucha de canal interno.

Hay un enlace de ejemplo incluido en este ejemplo denominado `TcpChunkingBinding`. Este enlace está compuesto de dos elementos de enlace: `TcpTransportBindingElement` y `ChunkingBindingElement`. Además de exponer la propiedad `MaxBufferedChunks`, el enlace también establece algunas de las propiedades `TcpTransportBindingElement` como `MaxReceivedMessageSize` (lo establece a `ChunkingUtils.ChunkSize` + 100KB bytes para los encabezados).

`TcpChunkingBinding` también implementa `IBindingRuntimePreferences` y devuelve true desde el método `ReceiveSynchronously` que indica que solo las llamadas sincrónicas Receive se implementan.

### <a name="determining-which-messages-to-chunk"></a>Determinar qué mensajes se fragmentan

El canal de fragmentación solo fragmenta los mensajes identificados a través del atributo `ChunkingBehavior`. La clase `ChunkingBehavior` implementa `IOperationBehavior` y se implementa llamando al método `AddBindingParameter`. En este método,el `ChunkingBehavior` examina el valor de su propiedad (`AppliesTo`, `InMessage` o ambos) `OutMessage` para determinar qué mensajes deberían fragmentarse. Obtiene a continuación la acción de cada uno de esos mensajes (de la colección Messages en `OperationDescription`) y lo agrega a una colección de cadenas contenida dentro de una instancia de `ChunkingBindingParameter`. Agrega a continuación `ChunkingBindingParameter` al `BindingParameterCollection`proporcionado.

Esta `BindingParameterCollection` se pasa dentro del `BindingContext` a cada elemento de enlace en el enlace cuando ese elemento de enlace compila el generador de canales o la escucha del canal. La implementación del `ChunkingBindingElement`de `BuildChannelFactory<T>` y `BuildChannelListener<T>` extraer este `ChunkingBindingParameter` del `BindingContext’``BindingParameterCollection`s. La colección de acciones contenida dentro de `ChunkingBindingParameter` se pasa a continuación al `ChunkingChannelFactory` o `ChunkingChannelListener`, que a su vez lo pasa al `ChunkingDuplexSessionChannel`.

## <a name="running-the-sample"></a>Ejecutar el ejemplo

#### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo

1. Instale ASP.NET 4,0 con el siguiente comando.

    ```console
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable
    ```

2. Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).

3. Para compilar la solución, siga las instrucciones de [creación de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).

4. Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).

5. Ejecute primero Service.exe, a continuación, ejecute Client.exe e inspeccione ambas ventanas de la consola para ver el resultado.

Al ejecutar el ejemplo, se espera el resultado siguiente.

Cliente:

```console
Press enter when service is available

 > Sent chunk 1 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 > Sent chunk 2 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 > Sent chunk 3 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 > Sent chunk 4 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 > Sent chunk 5 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 > Sent chunk 6 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 > Sent chunk 7 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 > Sent chunk 8 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 > Sent chunk 9 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 > Sent chunk 10 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 < Received chunk 1 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 < Received chunk 2 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 < Received chunk 3 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 < Received chunk 4 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 < Received chunk 5 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 < Received chunk 6 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 < Received chunk 7 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 < Received chunk 8 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 < Received chunk 9 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 < Received chunk 10 of message 5b226ad5-c088-4988-b737-6a565e0563dd
```

Servidor:

```console
Service started, press enter to exit
 < Received chunk 1 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 < Received chunk 2 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 < Received chunk 3 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 < Received chunk 4 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 < Received chunk 5 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 < Received chunk 6 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 < Received chunk 7 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 < Received chunk 8 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 < Received chunk 9 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 < Received chunk 10 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 > Sent chunk 1 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 > Sent chunk 2 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 > Sent chunk 3 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 > Sent chunk 4 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 > Sent chunk 5 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 > Sent chunk 6 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 > Sent chunk 7 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 > Sent chunk 8 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 > Sent chunk 9 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 > Sent chunk 10 of message 5b226ad5-c088-4988-b737-6a565e0563dd
```
