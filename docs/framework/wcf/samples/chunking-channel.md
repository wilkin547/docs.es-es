---
description: 'Más información acerca de: canal de fragmentación'
title: Canal de fragmentación
ms.date: 03/30/2017
ms.assetid: e4d53379-b37c-4b19-8726-9cc914d5d39f
ms.openlocfilehash: 826db33186aa8e01ade9123d6b0d8b696b7e77ce
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99778781"
---
# <a name="chunking-channel"></a><span data-ttu-id="cd0dd-103">Canal de fragmentación</span><span class="sxs-lookup"><span data-stu-id="cd0dd-103">Chunking Channel</span></span>

<span data-ttu-id="cd0dd-104">Al enviar mensajes de gran tamaño mediante Windows Communication Foundation (WCF), a menudo es conveniente limitar la cantidad de memoria usada para almacenar en búfer esos mensajes.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-104">When sending large messages using Windows Communication Foundation (WCF), it is often desirable to limit the amount of memory used to buffer those messages.</span></span> <span data-ttu-id="cd0dd-105">Una posible solución es transmitir en secuencias el cuerpo del mensaje (suponiendo que la mayor parte de los datos se encuentra en el cuerpo).</span><span class="sxs-lookup"><span data-stu-id="cd0dd-105">One possible solution is to stream the message body (assuming the bulk of the data is in the body).</span></span> <span data-ttu-id="cd0dd-106">Sin embargo, algunos protocolos requieren almacenado en búfer del mensaje completo.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-106">However some protocols require buffering of the entire message.</span></span> <span data-ttu-id="cd0dd-107">La mensajería de confianza y la seguridad son dos ejemplos de lo anterior.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-107">Reliable messaging and security are two such examples.</span></span> <span data-ttu-id="cd0dd-108">Otra posible solución es dividir el mensaje grande en mensajes menores llamados fragmentos, enviar uno por uno esos fragmentos y reconstituir el mensaje entero en el lado receptor.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-108">Another possible solution is to divide up the large message into smaller messages called chunks, send those chunks one chunk at a time, and reconstitute the large message on the receiving side.</span></span> <span data-ttu-id="cd0dd-109">La propia aplicación podría hacer esta fragmentación y desfragmentación, o podría utilizar un canal personalizado para hacerlo.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-109">The application itself could do this chunking and de-chunking or it could use a custom channel to do it.</span></span> <span data-ttu-id="cd0dd-110">El canal de fragmentación muestra cómo un protocolo personalizado o un canal en capas se pueden utilizar para la fragmentación y desfragmentación de mensajes arbitrariamente grandes.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-110">The chunking channel sample shows how a custom protocol or layered channel can be used to do chunking and de-chunking of arbitrarily large messages.</span></span>

<span data-ttu-id="cd0dd-111">Siempre se debería emplear la fragmentación solo una vez construido el mensaje completo que se va a enviar.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-111">Chunking should always be employed only after the entire message to be sent has been constructed.</span></span> <span data-ttu-id="cd0dd-112">Un canal de fragmentación siempre se debería disponer en niveles debajo de un canal de seguridad y un canal de sesión confiable.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-112">A chunking channel should always be layered below a security channel and a reliable session channel.</span></span>

> [!NOTE]
> <span data-ttu-id="cd0dd-113">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-113">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cd0dd-114">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-114">The samples may already be installed on your machine.</span></span> <span data-ttu-id="cd0dd-115">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-115">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="cd0dd-116">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-116">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="cd0dd-117">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-117">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\ChunkingChannel`

## <a name="chunking-channel-assumptions-and-limitations"></a><span data-ttu-id="cd0dd-118">Supuestos y limitaciones del canal de fragmentación</span><span class="sxs-lookup"><span data-stu-id="cd0dd-118">Chunking Channel Assumptions and Limitations</span></span>

### <a name="message-structure"></a><span data-ttu-id="cd0dd-119">Estructura de mensaje</span><span class="sxs-lookup"><span data-stu-id="cd0dd-119">Message Structure</span></span>

<span data-ttu-id="cd0dd-120">El canal de fragmentación supone la estructura de mensaje siguiente para que los mensajes estén fragmentados:</span><span class="sxs-lookup"><span data-stu-id="cd0dd-120">The chunking channel assumes the following message structure for messages to be chunked:</span></span>

```xml
<soap:Envelope>
  <!-- headers -->
  <soap:Body>
    <operationElement>
      <paramElement>data to be chunked</paramElement>
    </operationElement>
  </soap:Body>
</soap:Envelope>
```

<span data-ttu-id="cd0dd-121">Al utilizar ServiceModel, las operaciones de contrato que tienen 1 parámetro de entrada cumplen con esta forma de mensaje para su mensaje de entrada.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-121">When using the ServiceModel, contract operations that have 1 input parameter comply with this shape of message for their input message.</span></span> <span data-ttu-id="cd0dd-122">De manera similar, las operaciones de contrato que tienen 1 parámetro de salida o valor devuelto cumplen con esta forma de mensaje para su mensaje de salida.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-122">Similarly, contract operations that have 1 output parameter or return value comply with this shape of message for their output message.</span></span> <span data-ttu-id="cd0dd-123">A continuación, se muestran ejemplos de tales operaciones:</span><span class="sxs-lookup"><span data-stu-id="cd0dd-123">The following are examples of such operations:</span></span>

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

### <a name="sessions"></a><span data-ttu-id="cd0dd-124">Sesiones</span><span class="sxs-lookup"><span data-stu-id="cd0dd-124">Sessions</span></span>

<span data-ttu-id="cd0dd-125">El canal de fragmentación requiere que los mensajes se entreguen exactamente una vez, en entrega ordenada de mensajes (fragmentos).</span><span class="sxs-lookup"><span data-stu-id="cd0dd-125">The chunking channel requires messages to be delivered exactly once, in ordered delivery of messages (chunks).</span></span> <span data-ttu-id="cd0dd-126">Esto significa que la pila del canal subyacente debe tener sesión.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-126">This means the underlying channel stack must be sessionful.</span></span> <span data-ttu-id="cd0dd-127">Las sesiones se pueden proporcionar por el transporte (por ejemplo, transporte TCP) o por un canal protocolar con sesión (por ejemplo, ReliableSession acanalan).</span><span class="sxs-lookup"><span data-stu-id="cd0dd-127">Sessions can be provided by the transport (for example, TCP transport) or by a sessionful protocol channel (for example, ReliableSession channel).</span></span>

### <a name="asynchronous-send-and-receive"></a><span data-ttu-id="cd0dd-128">Enviós y recepciones asincrónicos</span><span class="sxs-lookup"><span data-stu-id="cd0dd-128">Asynchronous Send and Receive</span></span>

<span data-ttu-id="cd0dd-129">Los métodos de envíos y recepciones asincrónicos no se implementan en esta versión de ejemplo del canal de fragmentación.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-129">Asynchronous send and receive methods are not implemented in this version of the chunking channel sample.</span></span>

## <a name="chunking-protocol"></a><span data-ttu-id="cd0dd-130">Protocolo de fragmentación</span><span class="sxs-lookup"><span data-stu-id="cd0dd-130">Chunking Protocol</span></span>

<span data-ttu-id="cd0dd-131">El canal de fragmentación define un protocolo que indica el inicio y fin de una serie de fragmentos, así como el número de secuencia de cada fragmento.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-131">The chunking channel defines a protocol that indicates the start and end of a series of chunks as well as the sequence number of each chunk.</span></span> <span data-ttu-id="cd0dd-132">Los tres mensajes del ejemplo siguientes muestran los mensajes de inicio, fragmento y fin con comentarios que describen los aspectos clave de cada uno.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-132">The following three example messages demonstrate the start, chunk and end messages with comments that describe the key aspects of each.</span></span>

### <a name="start-message"></a><span data-ttu-id="cd0dd-133">Mensaje de comienzo</span><span class="sxs-lookup"><span data-stu-id="cd0dd-133">Start Message</span></span>

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

### <a name="chunk-message"></a><span data-ttu-id="cd0dd-134">Mensaje fragmento</span><span class="sxs-lookup"><span data-stu-id="cd0dd-134">Chunk Message</span></span>

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

### <a name="end-message"></a><span data-ttu-id="cd0dd-135">Mensaje final</span><span class="sxs-lookup"><span data-stu-id="cd0dd-135">End Message</span></span>

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

## <a name="chunking-channel-architecture"></a><span data-ttu-id="cd0dd-136">Arquitectura del canal de fragmentación</span><span class="sxs-lookup"><span data-stu-id="cd0dd-136">Chunking Channel Architecture</span></span>

<span data-ttu-id="cd0dd-137">El canal de fragmentación es un `IDuplexSessionChannel` que, a un nivel alto, sigue la arquitectura de canal típica.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-137">The chunking channel is an `IDuplexSessionChannel` that, at a high level, follows the typical channel architecture.</span></span> <span data-ttu-id="cd0dd-138">Hay un `ChunkingBindingElement` que puede generar un `ChunkingChannelFactory` y un `ChunkingChannelListener`.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-138">There is a `ChunkingBindingElement` that can build a `ChunkingChannelFactory` and a `ChunkingChannelListener`.</span></span> <span data-ttu-id="cd0dd-139">`ChunkingChannelFactory` crea instancias de `ChunkingChannel` cuando se le pide.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-139">The `ChunkingChannelFactory` creates instances of `ChunkingChannel` when it is asked to.</span></span> <span data-ttu-id="cd0dd-140">`ChunkingChannelListener` crea instancias de `ChunkingChannel` cuando se acepta un nuevo canal interno.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-140">The `ChunkingChannelListener` creates instances of `ChunkingChannel` when a new inner channel is accepted.</span></span> <span data-ttu-id="cd0dd-141">El propio `ChunkingChannel` es responsable de enviar y recibir los mensajes.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-141">The `ChunkingChannel` itself is responsible for sending and receiving messages.</span></span>

<span data-ttu-id="cd0dd-142">En el siguiente nivel inferior, `ChunkingChannel` confia en varios componentes para implementar el protocolo de fragmentación.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-142">At the next level down, `ChunkingChannel` relies on several components to implement the chunking protocol.</span></span> <span data-ttu-id="cd0dd-143">En el lado emisor, el canal usa un <xref:System.Xml.XmlDictionaryWriter> personalizado denominado `ChunkingWriter` que realiza la fragmentación real.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-143">On the send side, the channel uses a custom <xref:System.Xml.XmlDictionaryWriter> called `ChunkingWriter` that does the actual chunking.</span></span> <span data-ttu-id="cd0dd-144">`ChunkingWriter` usa el canal interno directamente para enviar fragmentos.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-144">`ChunkingWriter` uses the inner channel directly to send chunks.</span></span> <span data-ttu-id="cd0dd-145">Utilizar un `XmlDictionaryWriter` personalizado nos permite mandar fragmentos mientras se escribe el cuerpo grande del mensaje original.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-145">Using a custom `XmlDictionaryWriter` allows us to send out chunks as the large body of the original message is being written.</span></span> <span data-ttu-id="cd0dd-146">Esto significa que no almacenamos en búfer el mensaje original completo.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-146">This means we do not buffer the entire original message.</span></span>

![Diagrama que muestra la arquitectura de envío del canal de fragmentación.](./media/chunking-channel/chunking-channel-send.gif)

<span data-ttu-id="cd0dd-148">En el lado receptor, `ChunkingChannel` extrae mensajes del canal interno y los ofrece a un <xref:System.Xml.XmlDictionaryReader> personalizado denominado `ChunkingReader`, que reconstituye el mensaje original a partir de los fragmentos de entrada.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-148">On the receive side, `ChunkingChannel` pulls messages from the inner channel and hands them to a custom <xref:System.Xml.XmlDictionaryReader> called `ChunkingReader`, which reconstitutes the original message from the incoming chunks.</span></span> <span data-ttu-id="cd0dd-149">`ChunkingChannel` ajusta este `ChunkingReader` en una implementación de `Message``ChunkingMessage` personalizada y devuelve este mensaje al nivel anterior.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-149">`ChunkingChannel` wraps this `ChunkingReader` in a custom `Message` implementation called `ChunkingMessage` and returns this message to the layer above.</span></span> <span data-ttu-id="cd0dd-150">Esta combinación de `ChunkingReader` y `ChunkingMessage` nos permite al anular la fragmentación del cuerpo del mensaje original mientras la lee el nivel anterior en lugar de tener que almacenar en búfer todo el cuerpo del mensaje original.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-150">This combination of `ChunkingReader` and `ChunkingMessage` allows us to de-chunk the original message body as it is being read by the layer above instead of having to buffer the entire original message body.</span></span> <span data-ttu-id="cd0dd-151">`ChunkingReader` tiene una cola donde almacena en búfer fragmentos de entrada hasta un número máximo configurable de fragmentos almacenados en búfer.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-151">`ChunkingReader` has a queue where it buffers incoming chunks up to a maximum configurable number of buffered chunks.</span></span> <span data-ttu-id="cd0dd-152">Cuando se alcanza este límite máximo, el lector espera que la capa superior recoja los mensajes de la cola (es decir, simplemente leyendo el cuerpo del mensaje original) o hasta que se alcance el tiempo de espera máximo de recepción.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-152">When this maximum limit is reached, the reader waits for messages to be drained from the queue by the layer above (that is, by just reading from the original message body) or until the maximum receive timeout is reached.</span></span>

![Diagrama que muestra la arquitectura de recepción del canal de fragmentación.](./media/chunking-channel/chunking-channel-receive.gif)

## <a name="chunking-programming-model"></a><span data-ttu-id="cd0dd-154">Modelo de programación de fragmentación</span><span class="sxs-lookup"><span data-stu-id="cd0dd-154">Chunking Programming Model</span></span>

<span data-ttu-id="cd0dd-155">Los programadores del servicio pueden especificar qué mensajes deben ser fragmentados, aplicando el atributo `ChunkingBehavior` a las operaciones dentro del contrato.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-155">Service developers can specify which messages are to be chunked by applying the `ChunkingBehavior` attribute to operations within the contract.</span></span> <span data-ttu-id="cd0dd-156">El atributo expone una propiedad `AppliesTo` que permite al desarrollador especificar si la desfragmentación se aplica al mensaje de entrada, el mensaje de salida o ambos.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-156">The attribute exposes an `AppliesTo` property that allows the developer to specify whether chunking applies to the input message, the output message or both.</span></span> <span data-ttu-id="cd0dd-157">En el ejemplo siguiente se muestra el uso del atributo `ChunkingBehavior`:</span><span class="sxs-lookup"><span data-stu-id="cd0dd-157">The following example shows the usage of `ChunkingBehavior` attribute:</span></span>

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

<span data-ttu-id="cd0dd-158">De este modelo de programación, `ChunkingBindingElement` compila una lista de URI de acción que identifica los mensajes que se deben fragmentar.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-158">From this programming model, the `ChunkingBindingElement` compiles a list of action URIs that identify messages to be chunked.</span></span> <span data-ttu-id="cd0dd-159">La acción de cada mensaje saliente se compara contra esta lista para determinar si el mensaje se debería fragmentar o enviar directamente.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-159">The action of each outgoing message is compared against this list to determine if the message should be chunked or sent directly.</span></span>

## <a name="implementing-the-send-operation"></a><span data-ttu-id="cd0dd-160">Implementar la operación Send</span><span class="sxs-lookup"><span data-stu-id="cd0dd-160">Implementing the Send Operation</span></span>

<span data-ttu-id="cd0dd-161">A un nivel alto, la operación Send comprueba primero si el mensaje saliente debe fragmentarse y, si no, envía el mensaje directamente mediante el canal interno.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-161">At a high level, the Send operation first checks whether the outgoing message must be chunked and, if not, sends the message directly using the inner channel.</span></span>

<span data-ttu-id="cd0dd-162">Si el mensaje debe fragmentarse, Send crea un nuevo `ChunkingWriter` y llama `WriteBodyContents` en el mensaje saliente pasándole este `ChunkingWriter`.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-162">If the message must be chunked, Send creates a new `ChunkingWriter` and calls `WriteBodyContents` on the outgoing message passing it this `ChunkingWriter`.</span></span> <span data-ttu-id="cd0dd-163">`ChunkingWriter` realiza a continuación la fragmentación del mensaje (incluyendo copiar los encabezados originales del mensaje al fragmento inicial del mensaje) y envía fragmentos mediante el canal interno.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-163">The `ChunkingWriter` then does the message chunking (including copying original message headers to the start chunk message) and sends chunks using the inner channel.</span></span>

<span data-ttu-id="cd0dd-164">Detalles que se han de tener en cuenta:</span><span class="sxs-lookup"><span data-stu-id="cd0dd-164">A few details worth noting:</span></span>

- <span data-ttu-id="cd0dd-165">Send primero llama a `ThrowIfDisposedOrNotOpened` para asegurar que se abre `CommunicationState`.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-165">Send first calls `ThrowIfDisposedOrNotOpened` to ensure the `CommunicationState` is opened.</span></span>

- <span data-ttu-id="cd0dd-166">El envío se sincroniza, para que solo un mensaje se pueda enviar a la vez para cada sesión.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-166">Sending is synchronized so that only one message can be sent at a time for each session.</span></span> <span data-ttu-id="cd0dd-167">Hay un `ManualResetEvent` denominado `sendingDone` que se restablece cuando se envía un mensaje fragmentado.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-167">There is a `ManualResetEvent` named `sendingDone` that is reset when a chunked message is being sent.</span></span> <span data-ttu-id="cd0dd-168">Una vez enviado el fragmento del mensaje final, se establece este evento.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-168">Once the end chunk message is sent, this event is set.</span></span> <span data-ttu-id="cd0dd-169">El método Send espera a que este evento esté establecido antes de intentar enviar el mensaje saliente.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-169">The Send method waits for this event to be set before it tries to send the outgoing message.</span></span>

- <span data-ttu-id="cd0dd-170">Send bloquea el `CommunicationObject.ThisLock` para evitar cambios de estado sincronizados mientras se realiza el envío.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-170">Send locks the `CommunicationObject.ThisLock` to prevent synchronized state changes while sending.</span></span> <span data-ttu-id="cd0dd-171">Consulte la documentación <xref:System.ServiceModel.Channels.CommunicationObject> para obtener más información sobre los estados y el equipo de estado <xref:System.ServiceModel.Channels.CommunicationObject>.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-171">See the <xref:System.ServiceModel.Channels.CommunicationObject> documentation for more information about <xref:System.ServiceModel.Channels.CommunicationObject> states and state machine.</span></span>

- <span data-ttu-id="cd0dd-172">El tiempo de espera pasado a Send se utiliza como tiempo de espera para la operación de envío al completo, la cual incluye el envío de todos los fragmentos.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-172">The timeout passed to Send is used as the timeout for the entire send operation which includes sending all of the chunks.</span></span>

- <span data-ttu-id="cd0dd-173">El diseño <xref:System.Xml.XmlDictionaryWriter> personalizado fue elegido para evitar almacenar en búfer el cuerpo del mensaje original completo.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-173">The custom <xref:System.Xml.XmlDictionaryWriter> design was chosen to avoid buffering the entire original message body.</span></span> <span data-ttu-id="cd0dd-174">Si deseáramos obtener un <xref:System.Xml.XmlDictionaryReader> en el cuerpo utilizando `message.GetReaderAtBodyContents` el cuerpo completo se almacenaría en búfer.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-174">If we were to get an <xref:System.Xml.XmlDictionaryReader> on the body using `message.GetReaderAtBodyContents` the entire body would be buffered.</span></span> <span data-ttu-id="cd0dd-175">En su lugar, tenemos un personalizado  <xref:System.Xml.XmlDictionaryWriter> que se pasa a `message.WriteBodyContents` .</span><span class="sxs-lookup"><span data-stu-id="cd0dd-175">Instead, we have a custom  <xref:System.Xml.XmlDictionaryWriter> that is passed to `message.WriteBodyContents`.</span></span> <span data-ttu-id="cd0dd-176">Mientras el mensaje llama a WriteBase64 en el sistema de escritura, el sistema de escritura empaqueta los fragmentos en los mensajes y los envía utilizando el canal interno.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-176">As the message calls WriteBase64 on the writer, the writer packages up chunks into messages and sends them using the inner channel.</span></span> <span data-ttu-id="cd0dd-177">WriteBase64 se bloquea hasta que se envía el fragmento.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-177">WriteBase64 blocks until the chunk is sent.</span></span>

## <a name="implementing-the-receive-operation"></a><span data-ttu-id="cd0dd-178">Implementar la operación Receive</span><span class="sxs-lookup"><span data-stu-id="cd0dd-178">Implementing the Receive Operation</span></span>

<span data-ttu-id="cd0dd-179">A un nivel alto, la operación Receive comprueba primero que el mensaje entrante no es `null` y que su acción es `ChunkingAction`.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-179">At a high level, the Receive operation first checks that the incoming message is not `null` and that its action is the `ChunkingAction`.</span></span> <span data-ttu-id="cd0dd-180">Si no cumple ambos criterios, el mensaje se devuelve sin modificar desde Receive.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-180">If it does not meet both criteria, the message is returned unchanged from Receive.</span></span> <span data-ttu-id="cd0dd-181">De lo contrario, Receive crea un nuevo `ChunkingReader` y un nuevo `ChunkingMessage` ajustado alrededor de él (llamando a `GetNewChunkingMessage`).</span><span class="sxs-lookup"><span data-stu-id="cd0dd-181">Otherwise, Receive creates a new `ChunkingReader` and a new `ChunkingMessage` wrapped around it (by calling `GetNewChunkingMessage`).</span></span> <span data-ttu-id="cd0dd-182">Antes de devolver ese nuevo `ChunkingMessage`, Receive utiliza un subproceso de un conjunto de subprocesos para ejecutar `ReceiveChunkLoop`, que llama `innerChannel.Receive` en un bucle y entrega fragmentos a `ChunkingReader` hasta que se reciba el fragmento de mensaje final o se alcance el tiempo de espera de recepción.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-182">Before returning that new `ChunkingMessage`, Receive uses a threadpool thread to execute `ReceiveChunkLoop`, which calls `innerChannel.Receive` in a loop and hands off chunks to the `ChunkingReader` until the end chunk message is received or the receive timeout is hit.</span></span>

<span data-ttu-id="cd0dd-183">Detalles que se han de tener en cuenta:</span><span class="sxs-lookup"><span data-stu-id="cd0dd-183">A few details worth noting:</span></span>

- <span data-ttu-id="cd0dd-184">Al igual que Send, Receive primero llama `ThrowIfDisposedOrNotOepned` para asegurar que se abre `CommunicationState`.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-184">Like Send, Receive first calls `ThrowIfDisposedOrNotOepned` to ensure the `CommunicationState` is Opened.</span></span>

- <span data-ttu-id="cd0dd-185">Receive también se sincroniza para que solo se pueda recibir un mensaje de la sesión al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-185">Receive is also synchronized so that only one message can be received at a time from the session.</span></span> <span data-ttu-id="cd0dd-186">Esto es especialmente importante porque una vez se recibe un fragmento de mensaje de inicio, se espera que todos los mensajes siguientes recibidos sean fragmentos de esta nueva secuencia de fragmentos hasta que se reciba un fragmento de mensaje final.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-186">This is especially important because once a start chunk message is received, all subsequent received messages are expected to be chunks within this new chunk sequence until an end chunk message is received.</span></span> <span data-ttu-id="cd0dd-187">Receive no puede incorporar los cambios de los mensajes del canal interno hasta que no se reciban todos los fragmentos que pertenecen al mensaje que se está desfragmentando.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-187">Receive cannot pull messages from the inner channel until all chunks that belong to the message currently being de-chunked are received.</span></span> <span data-ttu-id="cd0dd-188">Para lograr esto, Receive utiliza un `ManualResetEvent` denominado `currentMessageCompleted`, que se establece cuando el fragmento de mensaje final se recibe y se restablece cuando se recibe un nuevo fragmento de mensaje de inicio.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-188">To accomplish this, Receive uses a `ManualResetEvent` named `currentMessageCompleted`, which is set when the end chunk message is received and reset when a new start chunk message is received.</span></span>

- <span data-ttu-id="cd0dd-189">A diferencia de Send, Receive no evita las transiciones de estado sincronizadas mientras recibe.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-189">Unlike Send, Receive does not prevent synchronized state transitions while receiving.</span></span> <span data-ttu-id="cd0dd-190">Por ejemplo, se puede llamar a Close mientras se recibe y se espera hasta que las recepciones pendientes del mensaje original se completen o se alcance el valor de tiempo de espera especificado.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-190">For example, Close can be called while receiving and waits until the pending receive of the original message is completed or the specified timeout value is reached.</span></span>

- <span data-ttu-id="cd0dd-191">El tiempo de espera pasado a Receive se utiliza como tiempo de espera para la operación de recepción completa, que incluye la recepción todos los fragmentos.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-191">The timeout passed to Receive is used as the timeout for the entire receive operation, which includes receiving all of the chunks.</span></span>

- <span data-ttu-id="cd0dd-192">Si la capa que consume el mensaje está consumiendo el cuerpo del mensaje a una tasa menor que la tasa de llegadas de fragmentos de mensajes, el `ChunkingReader` almacena en búfer esos fragmentos de entrada hasta el límite especificado por `ChunkingBindingElement.MaxBufferedChunks`.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-192">If the layer that consumes the message is consuming the message body at a rate lower than the rate of incoming chunk messages, the `ChunkingReader` buffers those incoming chunks up to the limit specified by `ChunkingBindingElement.MaxBufferedChunks`.</span></span> <span data-ttu-id="cd0dd-193">Una vez alcanzado ese límite, ningún fragmento más se extrae de la capa inferior hasta que un fragmento almacenado en búfer se utiliza o se alcanza el tiempo de espera para la recepción.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-193">Once that limit is reached, no more chunks are pulled from the lower layer until either a buffered chunk is consumed or the receive timeout is reached.</span></span>

## <a name="communicationobject-overrides"></a><span data-ttu-id="cd0dd-194">Invalidaciones de CommunicationObject</span><span class="sxs-lookup"><span data-stu-id="cd0dd-194">CommunicationObject Overrides</span></span>

### <a name="onopen"></a><span data-ttu-id="cd0dd-195">OnOpen</span><span class="sxs-lookup"><span data-stu-id="cd0dd-195">OnOpen</span></span>

<span data-ttu-id="cd0dd-196">`OnOpen` llama `innerChannel.Open` para abrir el canal interno.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-196">`OnOpen` calls `innerChannel.Open` to open the inner channel.</span></span>

### <a name="onclose"></a><span data-ttu-id="cd0dd-197">OnClose</span><span class="sxs-lookup"><span data-stu-id="cd0dd-197">OnClose</span></span>

<span data-ttu-id="cd0dd-198">`OnClose` establece primero `stopReceive` a `true` para señalar el `ReceiveChunkLoop` pendiente para detenerse.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-198">`OnClose` first sets `stopReceive` to `true` to signal the pending `ReceiveChunkLoop` to stop.</span></span> <span data-ttu-id="cd0dd-199">Después espera a `receiveStopped` <xref:System.Threading.ManualResetEvent> , que se establece cuando se `ReceiveChunkLoop` detiene.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-199">It then waits for the `receiveStopped` <xref:System.Threading.ManualResetEvent>, which is set when `ReceiveChunkLoop` stops.</span></span> <span data-ttu-id="cd0dd-200">Suponiendo las pausas `ReceiveChunkLoop` dentro del tiempo de espera especificado, `OnClose` llama `innerChannel.Close` con el tiempo de espera restante.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-200">Assuming the `ReceiveChunkLoop` stops within the specified timeout, `OnClose` calls `innerChannel.Close` with the remaining timeout.</span></span>

### <a name="onabort"></a><span data-ttu-id="cd0dd-201">OnAbort</span><span class="sxs-lookup"><span data-stu-id="cd0dd-201">OnAbort</span></span>

<span data-ttu-id="cd0dd-202">`OnAbort` llama `innerChannel.Abort` para anular el canal interno.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-202">`OnAbort` calls `innerChannel.Abort` to abort the inner channel.</span></span> <span data-ttu-id="cd0dd-203">Si hay un `ReceiveChunkLoop` pendiente, recibe a una excepción de la llamada `innerChannel.Receive` pendiente.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-203">If there is a pending `ReceiveChunkLoop` it gets an exception from the pending `innerChannel.Receive` call.</span></span>

### <a name="onfaulted"></a><span data-ttu-id="cd0dd-204">OnFaulted</span><span class="sxs-lookup"><span data-stu-id="cd0dd-204">OnFaulted</span></span>

<span data-ttu-id="cd0dd-205">`ChunkingChannel` no requiere comportamiento especial cuando el canal tiene errores, por lo que no se invalida `OnFaulted`.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-205">The `ChunkingChannel` does not require special behavior when the channel is faulted so `OnFaulted` is not overridden.</span></span>

## <a name="implementing-channel-factory"></a><span data-ttu-id="cd0dd-206">Implementar el generador de canales</span><span class="sxs-lookup"><span data-stu-id="cd0dd-206">Implementing Channel Factory</span></span>

<span data-ttu-id="cd0dd-207">`ChunkingChannelFactory` es responsable de crear instancias de `ChunkingDuplexSessionChannel` y de colocar en cascada las transiciones de estado al generador de canales interno.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-207">The `ChunkingChannelFactory` is responsible for creating instances of `ChunkingDuplexSessionChannel` and for cascading state transitions to the inner channel factory.</span></span>

<span data-ttu-id="cd0dd-208">`OnCreateChannel` utiliza el generador de canales interno para crear un canal interno `IDuplexSessionChannel`.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-208">`OnCreateChannel` uses the inner channel factory to create an `IDuplexSessionChannel` inner channel.</span></span> <span data-ttu-id="cd0dd-209">Crea a continuación un nuevo `ChunkingDuplexSessionChannel` que le pasa este canal interno junto con la lista de acciones de mensaje para ser fragmentada y el número máximo de fragmentos para almacenar en búfer cuando se produce la recepción.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-209">It then creates a new `ChunkingDuplexSessionChannel` passing it this inner channel along with the list of message actions to be chunked and the maximum number of chunks to buffer upon receive.</span></span> <span data-ttu-id="cd0dd-210">La lista de acciones de mensaje para ser fragmentada y el número máximo de fragmentos para almacenar en búfer son dos parámetros pasados a `ChunkingChannelFactory` en su constructor.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-210">The list of message actions to be chunked and the maximum number of chunks to buffer are two parameters passed to `ChunkingChannelFactory` in its constructor.</span></span> <span data-ttu-id="cd0dd-211">La sección en `ChunkingBindingElement` describe de dónde proceden estos valores.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-211">The section on `ChunkingBindingElement` describes where these values come from.</span></span>

<span data-ttu-id="cd0dd-212">`OnOpen`, `OnClose`, `OnAbort` y sus equivalentes asincrónicos llaman al método de transición de estado correspondiente en el generador de canales interno.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-212">The `OnOpen`, `OnClose`, `OnAbort` and their asynchronous equivalents call the corresponding state transition method on the inner channel factory.</span></span>

## <a name="implementing-channel-listener"></a><span data-ttu-id="cd0dd-213">Implementar el escuchado del canal</span><span class="sxs-lookup"><span data-stu-id="cd0dd-213">Implementing Channel Listener</span></span>

<span data-ttu-id="cd0dd-214">`ChunkingChannelListener` es un contenedor alrededor de una escucha de canal interno.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-214">The `ChunkingChannelListener` is a wrapper around an inner channel listener.</span></span> <span data-ttu-id="cd0dd-215">Su función principal, además de delegar llamadas a esa escucha del canal interno, es ajustar nuevo `ChunkingDuplexSessionChannels` alrededor de los canales aceptados por la escucha del canal interno.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-215">Its main function, besides delegate calls to that inner channel listener, is to wrap new `ChunkingDuplexSessionChannels` around channels accepted from the inner channel listener.</span></span> <span data-ttu-id="cd0dd-216">Esto se hace en `OnAcceptChannel` y `OnEndAcceptChannel`.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-216">This is done in `OnAcceptChannel` and `OnEndAcceptChannel`.</span></span> <span data-ttu-id="cd0dd-217">El `ChunkingDuplexSessionChannel` recientemente creado se pasa al canal interno junto con los otros parámetros descritos previamente.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-217">The newly created `ChunkingDuplexSessionChannel` is passed the inner channel along with the other parameters previously described.</span></span>

## <a name="implementing-binding-element-and-binding"></a><span data-ttu-id="cd0dd-218">Implementar elemento de enlace y enlace</span><span class="sxs-lookup"><span data-stu-id="cd0dd-218">Implementing Binding Element and Binding</span></span>

<span data-ttu-id="cd0dd-219">`ChunkingBindingElement` es el responsable de crear el `ChunkingChannelFactory` y `ChunkingChannelListener`.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-219">`ChunkingBindingElement` is responsible for creating the `ChunkingChannelFactory` and `ChunkingChannelListener`.</span></span> <span data-ttu-id="cd0dd-220">`ChunkingBindingElement`Comprueba si T en `CanBuildChannelFactory` \<T> y `CanBuildChannelListener` \<T> es de tipo `IDuplexSessionChannel` (el único canal que admite el canal de fragmentación) y que los otros elementos de enlace del enlace admiten este tipo de canal.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-220">The `ChunkingBindingElement` checks whether T in `CanBuildChannelFactory`\<T> and `CanBuildChannelListener`\<T> is of type `IDuplexSessionChannel` (the only channel supported by the chunking channel) and that the other binding elements in the binding support this channel type.</span></span>

<span data-ttu-id="cd0dd-221">`BuildChannelFactory`\<T> en primer lugar, comprueba que el tipo de canal solicitado se puede compilar y, a continuación, obtiene una lista de acciones de mensaje que se van a fragmentar.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-221">`BuildChannelFactory`\<T> first checks that the requested channel type can be built and then gets a list of message actions to be chunked.</span></span> <span data-ttu-id="cd0dd-222">Para más información, consulte la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-222">For more information, see the following section.</span></span> <span data-ttu-id="cd0dd-223">Crea a continuación un nuevo `ChunkingChannelFactory` que le pasa el generador de canales interno (tal y como se devolvió desde `context.BuildInnerChannelFactory<IDuplexSessionChannel>`), la lista de acciones de mensaje, y el número máximo de fragmentos para almacenar en búfer.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-223">It then creates a new `ChunkingChannelFactory` passing it the inner channel factory (as returned from `context.BuildInnerChannelFactory<IDuplexSessionChannel>`), the list of message actions, and the maximum number of chunks to buffer.</span></span> <span data-ttu-id="cd0dd-224">El número máximo de fragmentos procede de una propiedad llamada `MaxBufferedChunks` expuesta por el `ChunkingBindingElement`.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-224">The maximum number of chunks comes from a property called `MaxBufferedChunks` exposed by the `ChunkingBindingElement`.</span></span>

<span data-ttu-id="cd0dd-225">`BuildChannelListener<T>` tiene una implementación similar para crear `ChunkingChannelListener` y pasarle el agente de escucha de canal interno.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-225">`BuildChannelListener<T>` has a similar implementation for creating `ChunkingChannelListener` and passing it the inner channel listener.</span></span>

<span data-ttu-id="cd0dd-226">Hay un enlace de ejemplo incluido en este ejemplo denominado `TcpChunkingBinding`.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-226">There is an example binding included in this sample named `TcpChunkingBinding`.</span></span> <span data-ttu-id="cd0dd-227">Este enlace está compuesto de dos elementos de enlace: `TcpTransportBindingElement` y `ChunkingBindingElement`.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-227">This binding consists of two binding elements: `TcpTransportBindingElement` and `ChunkingBindingElement`.</span></span> <span data-ttu-id="cd0dd-228">Además de exponer la propiedad `MaxBufferedChunks`, el enlace también establece algunas de las propiedades `TcpTransportBindingElement` como `MaxReceivedMessageSize` (lo establece a `ChunkingUtils.ChunkSize` + 100KB bytes para los encabezados).</span><span class="sxs-lookup"><span data-stu-id="cd0dd-228">In addition to exposing the `MaxBufferedChunks` property, the binding also sets some of the `TcpTransportBindingElement` properties such as `MaxReceivedMessageSize` (sets it to `ChunkingUtils.ChunkSize` + 100KB bytes for headers).</span></span>

<span data-ttu-id="cd0dd-229">`TcpChunkingBinding` también implementa `IBindingRuntimePreferences` y devuelve true desde el método `ReceiveSynchronously` que indica que solo las llamadas sincrónicas Receive se implementan.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-229">`TcpChunkingBinding` also implements `IBindingRuntimePreferences` and returns true from the `ReceiveSynchronously` method indicating that only the synchronous Receive calls are implemented.</span></span>

### <a name="determining-which-messages-to-chunk"></a><span data-ttu-id="cd0dd-230">Determinar qué mensajes se fragmentan</span><span class="sxs-lookup"><span data-stu-id="cd0dd-230">Determining Which Messages To Chunk</span></span>

<span data-ttu-id="cd0dd-231">El canal de fragmentación solo fragmenta los mensajes identificados a través del atributo `ChunkingBehavior`.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-231">The chunking channel chunks only the messages identified through the `ChunkingBehavior` attribute.</span></span> <span data-ttu-id="cd0dd-232">La clase `ChunkingBehavior` implementa `IOperationBehavior` y se implementa llamando al método `AddBindingParameter`.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-232">The `ChunkingBehavior` class implements `IOperationBehavior` and is implemented by calling the `AddBindingParameter` method.</span></span> <span data-ttu-id="cd0dd-233">En este método,el `ChunkingBehavior` examina el valor de su propiedad (`AppliesTo`, `InMessage` o ambos) `OutMessage` para determinar qué mensajes deberían fragmentarse.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-233">In this method, the `ChunkingBehavior` examines the value of its `AppliesTo` property (`InMessage`, `OutMessage` or both) to determine which messages should be chunked.</span></span> <span data-ttu-id="cd0dd-234">Obtiene a continuación la acción de cada uno de esos mensajes (de la colección Messages en `OperationDescription`) y lo agrega a una colección de cadenas contenida dentro de una instancia de `ChunkingBindingParameter`.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-234">It then gets the action of each of those messages (from the Messages collection on `OperationDescription`) and adds it to a string collection contained within an instance of `ChunkingBindingParameter`.</span></span> <span data-ttu-id="cd0dd-235">Agrega a continuación `ChunkingBindingParameter` al `BindingParameterCollection`proporcionado.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-235">It then adds this `ChunkingBindingParameter` to the provided `BindingParameterCollection`.</span></span>

<span data-ttu-id="cd0dd-236">Esta `BindingParameterCollection` se pasa dentro del `BindingContext` a cada elemento de enlace en el enlace cuando ese elemento de enlace compila el generador de canales o la escucha del canal.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-236">This `BindingParameterCollection` is passed inside the `BindingContext` to each binding element in the binding when that binding element builds the channel factory or the channel listener.</span></span> <span data-ttu-id="cd0dd-237">La `ChunkingBindingElement` implementación de `BuildChannelFactory<T>` y `BuildChannelListener<T>` extrae este `ChunkingBindingParameter` de los `BindingContext’` s `BindingParameterCollection` .</span><span class="sxs-lookup"><span data-stu-id="cd0dd-237">The `ChunkingBindingElement`'s implementation of `BuildChannelFactory<T>` and `BuildChannelListener<T>` pull this `ChunkingBindingParameter` out of the `BindingContext’`s `BindingParameterCollection`.</span></span> <span data-ttu-id="cd0dd-238">La colección de acciones contenida dentro de `ChunkingBindingParameter` se pasa a continuación al `ChunkingChannelFactory` o `ChunkingChannelListener`, que a su vez lo pasa al `ChunkingDuplexSessionChannel`.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-238">The collection of actions contained within the `ChunkingBindingParameter` is then passed to the `ChunkingChannelFactory` or `ChunkingChannelListener`, which in turn passes it to the `ChunkingDuplexSessionChannel`.</span></span>

## <a name="running-the-sample"></a><span data-ttu-id="cd0dd-239">Ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="cd0dd-239">Running the Sample</span></span>

#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="cd0dd-240">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="cd0dd-240">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="cd0dd-241">Instale ASP.NET 4,0 con el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-241">Install ASP.NET 4.0 using the following command.</span></span>

    ```console
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable
    ```

2. <span data-ttu-id="cd0dd-242">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="cd0dd-242">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

3. <span data-ttu-id="cd0dd-243">Para compilar la solución, siga las instrucciones de [creación de los ejemplos de Windows Communication Foundation](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="cd0dd-243">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

4. <span data-ttu-id="cd0dd-244">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="cd0dd-244">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

5. <span data-ttu-id="cd0dd-245">Ejecute primero Service.exe, a continuación, ejecute Client.exe e inspeccione ambas ventanas de la consola para ver el resultado.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-245">Run Service.exe first, then run Client.exe and watch both console windows for output.</span></span>

<span data-ttu-id="cd0dd-246">Al ejecutar el ejemplo, se espera el resultado siguiente.</span><span class="sxs-lookup"><span data-stu-id="cd0dd-246">When running the sample, the following output is expected.</span></span>

<span data-ttu-id="cd0dd-247">Cliente:</span><span class="sxs-lookup"><span data-stu-id="cd0dd-247">Client:</span></span>

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

<span data-ttu-id="cd0dd-248">Servidor: </span><span class="sxs-lookup"><span data-stu-id="cd0dd-248">Server:</span></span>

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
