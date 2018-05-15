---
title: 'Cliente: generadores de canales y canales'
ms.date: 03/30/2017
ms.assetid: ef245191-fdab-4468-a0da-7c6f25d2110f
ms.openlocfilehash: 91e19c692718ae02e2f125a791904f62fe8401f7
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2018
---
# <a name="client-channel-factories-and-channels"></a><span data-ttu-id="6f872-102">Cliente: generadores de canales y canales</span><span class="sxs-lookup"><span data-stu-id="6f872-102">Client: Channel Factories and Channels</span></span>
<span data-ttu-id="6f872-103">Este tema describe la creación de generadores de canales y de canales.</span><span class="sxs-lookup"><span data-stu-id="6f872-103">This topic discusses the creation of channel factories and channels.</span></span>  
  
## <a name="channel-factories-and-channels"></a><span data-ttu-id="6f872-104">Generadores de canales y canales</span><span class="sxs-lookup"><span data-stu-id="6f872-104">Channel Factories and Channels</span></span>  
 <span data-ttu-id="6f872-105">Los generadores de canales son responsables de la creación de canales.</span><span class="sxs-lookup"><span data-stu-id="6f872-105">Channel factories are responsible for creating channels.</span></span> <span data-ttu-id="6f872-106">Los canales creados por los generadores de canales se utilizan para enviar mensajes.</span><span class="sxs-lookup"><span data-stu-id="6f872-106">Channels created by channel factories are used for sending messages.</span></span> <span data-ttu-id="6f872-107">Estos canales son responsables de obtener el mensaje de la capa anterior, realizando cualquier procesamiento necesario, y, a continuación, de enviar el mensaje a la capa inferior.</span><span class="sxs-lookup"><span data-stu-id="6f872-107">These channels are responsible for getting the message from the layer above, performing whatever processing is necessary, then sending the message to the layer below.</span></span> <span data-ttu-id="6f872-108">El siguiente gráfico ilustra este proceso.</span><span class="sxs-lookup"><span data-stu-id="6f872-108">The following graphic illustrates this process.</span></span>  
  
 <span data-ttu-id="6f872-109">![Generadores cliente y canales](../../../../docs/framework/wcf/extending/media/wcfc-wcfchannelsigure2highlevelfactgoriesc.gif "wcfc_WCFChannelsigure2HIghLevelFactgoriesc")</span><span class="sxs-lookup"><span data-stu-id="6f872-109">![Client Factories and Channels](../../../../docs/framework/wcf/extending/media/wcfc-wcfchannelsigure2highlevelfactgoriesc.gif "wcfc_WCFChannelsigure2HIghLevelFactgoriesc")</span></span>  
<span data-ttu-id="6f872-110">Un generador de canales crea canales.</span><span class="sxs-lookup"><span data-stu-id="6f872-110">A channel factory creates channels.</span></span>  
  
 <span data-ttu-id="6f872-111">Cuando se cierran, los generadores de canales son responsables de cerrar cualquier canal creado por ellos que aún no se haya cerrado.</span><span class="sxs-lookup"><span data-stu-id="6f872-111">When closed, channel factories are responsible for closing any channels they created that are not yet closed.</span></span> <span data-ttu-id="6f872-112">Tenga en cuenta que, en el ejemplo, el modelo es asimétrico debido a que cuando se cierra un agente de escucha del canal solo detiene la aceptación de nuevos canales, pero mantiene abiertos los canales existentes de modo que pueden continuar recibiendo mensajes.</span><span class="sxs-lookup"><span data-stu-id="6f872-112">Note that the model is asymmetric here because when a channel listener is closed, it only stops accepting new channels but leaves existing channels open so that they can continue receiving messages.</span></span>  
  
 <span data-ttu-id="6f872-113">WCF proporciona aplicaciones auxiliares de clase base para este proceso.</span><span class="sxs-lookup"><span data-stu-id="6f872-113">WCF provides base class helpers for this process.</span></span> <span data-ttu-id="6f872-114">(Para un diagrama de las clases de aplicación auxiliar de canal tratados en este tema, consulte [información general del modelo de canal](../../../../docs/framework/wcf/extending/channel-model-overview.md).)</span><span class="sxs-lookup"><span data-stu-id="6f872-114">(For a diagram of the channel helper classes discussed in this topic, see [Channel Model Overview](../../../../docs/framework/wcf/extending/channel-model-overview.md).)</span></span>  
  
-   <span data-ttu-id="6f872-115">El <xref:System.ServiceModel.Channels.CommunicationObject> la clase implementa <xref:System.ServiceModel.ICommunicationObject> y aplica la máquina de Estados que se describe en el paso 2 de [canales de desarrollo](../../../../docs/framework/wcf/extending/developing-channels.md).</span><span class="sxs-lookup"><span data-stu-id="6f872-115">The <xref:System.ServiceModel.Channels.CommunicationObject> class implements <xref:System.ServiceModel.ICommunicationObject> and enforces the state machine described in step 2 of [Developing Channels](../../../../docs/framework/wcf/extending/developing-channels.md).</span></span>  
  
-   <span data-ttu-id="6f872-116">El "<xref:System.ServiceModel.Channels.ChannelManagerBase> la clase implementa <xref:System.ServiceModel.Channels.CommunicationObject> y proporciona una clase base unificada para <xref:System.ServiceModel.Channels.ChannelFactoryBase?displayProperty=nameWithType> y <xref:System.ServiceModel.Channels.ChannelListenerBase?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6f872-116">The``<xref:System.ServiceModel.Channels.ChannelManagerBase> class implements <xref:System.ServiceModel.Channels.CommunicationObject> and provides a unified base class for <xref:System.ServiceModel.Channels.ChannelFactoryBase?displayProperty=nameWithType> and <xref:System.ServiceModel.Channels.ChannelListenerBase?displayProperty=nameWithType>.</span></span> <span data-ttu-id="6f872-117">La clase <xref:System.ServiceModel.Channels.ChannelManagerBase> trabaja junto con <xref:System.ServiceModel.Channels.ChannelBase>, que es una clase base que implementa <xref:System.ServiceModel.Channels.IChannel>.</span><span class="sxs-lookup"><span data-stu-id="6f872-117">The <xref:System.ServiceModel.Channels.ChannelManagerBase> class works in conjunction with <xref:System.ServiceModel.Channels.ChannelBase>, which is a base class that implements <xref:System.ServiceModel.Channels.IChannel>.</span></span>  
  
-   <span data-ttu-id="6f872-118">El "<xref:System.ServiceModel.Channels.ChannelFactoryBase> la clase implementa <xref:System.ServiceModel.Channels.ChannelManagerBase> y <xref:System.ServiceModel.Channels.IChannelFactory> y consolida los `CreateChannel` sobrecargas en una `OnCreateChannel` método abstracto.</span><span class="sxs-lookup"><span data-stu-id="6f872-118">The``<xref:System.ServiceModel.Channels.ChannelFactoryBase> class implements <xref:System.ServiceModel.Channels.ChannelManagerBase> and <xref:System.ServiceModel.Channels.IChannelFactory> and consolidates the `CreateChannel` overloads into one `OnCreateChannel` abstract method.</span></span>  
  
-   <span data-ttu-id="6f872-119">El "<xref:System.ServiceModel.Channels.ChannelListenerBase> la clase implementa <xref:System.ServiceModel.Channels.IChannelListener>.</span><span class="sxs-lookup"><span data-stu-id="6f872-119">The``<xref:System.ServiceModel.Channels.ChannelListenerBase> class implements <xref:System.ServiceModel.Channels.IChannelListener>.</span></span> <span data-ttu-id="6f872-120">Se encarga de la administración de estados básica.</span><span class="sxs-lookup"><span data-stu-id="6f872-120">It takes care of basic state management.</span></span>  
  
 <span data-ttu-id="6f872-121">El siguiente análisis se basa en el [transporte: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) ejemplo.</span><span class="sxs-lookup"><span data-stu-id="6f872-121">The following discussion is based upon the [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) sample.</span></span>  
  
### <a name="creating-a-channel-factory"></a><span data-ttu-id="6f872-122">Creación de un generador de canales</span><span class="sxs-lookup"><span data-stu-id="6f872-122">Creating a Channel Factory</span></span>  
 <span data-ttu-id="6f872-123">La clase `UdpChannelFactory` se deriva de la clase <xref:System.ServiceModel.Channels.ChannelFactoryBase>.</span><span class="sxs-lookup"><span data-stu-id="6f872-123">The `UdpChannelFactory` derives from <xref:System.ServiceModel.Channels.ChannelFactoryBase>.</span></span> <span data-ttu-id="6f872-124">El ejemplo invalida <xref:System.ServiceModel.Channels.ChannelFactoryBase.GetProperty%2A> para proporcionar acceso a la versión del mensaje del codificador de mensajes.</span><span class="sxs-lookup"><span data-stu-id="6f872-124">The sample overrides <xref:System.ServiceModel.Channels.ChannelFactoryBase.GetProperty%2A> to provide access to the message version of the message encoder.</span></span> <span data-ttu-id="6f872-125">El ejemplo también invalida <xref:System.ServiceModel.Channels.ChannelFactoryBase.OnClose%2A> para anular nuestra instancia de <xref:System.ServiceModel.Channels.BufferManager> cuando se realizan las transiciones del equipo de estados.</span><span class="sxs-lookup"><span data-stu-id="6f872-125">The sample also overrides <xref:System.ServiceModel.Channels.ChannelFactoryBase.OnClose%2A> to tear down our instance of <xref:System.ServiceModel.Channels.BufferManager> when the state machine transitions.</span></span>  
  
#### <a name="the-udp-output-channel"></a><span data-ttu-id="6f872-126">Canal de salida UDP</span><span class="sxs-lookup"><span data-stu-id="6f872-126">The UDP Output Channel</span></span>  
 <span data-ttu-id="6f872-127">La clase `UdpOutputChannel` implementa la interfaz <xref:System.ServiceModel.Channels.IOutputChannel>.</span><span class="sxs-lookup"><span data-stu-id="6f872-127">The `UdpOutputChannel` implements <xref:System.ServiceModel.Channels.IOutputChannel>.</span></span> <span data-ttu-id="6f872-128">El constructor valida los argumentos y construye un objeto de destino <xref:System.Net.EndPoint> basado en la <xref:System.ServiceModel.EndpointAddress> a la que se pasa.</span><span class="sxs-lookup"><span data-stu-id="6f872-128">The constructor validates the arguments and constructs a destination <xref:System.Net.EndPoint> object based on the <xref:System.ServiceModel.EndpointAddress> that is passed in.</span></span>  
  
 <span data-ttu-id="6f872-129">La invalidación de <xref:System.ServiceModel.Channels.CommunicationObject.OnOpen%2A> crea un socket que se utiliza para enviar los mensajes a <xref:System.Net.EndPoint>.</span><span class="sxs-lookup"><span data-stu-id="6f872-129">The override of <xref:System.ServiceModel.Channels.CommunicationObject.OnOpen%2A> creates a socket that is used to send messages to this <xref:System.Net.EndPoint>.</span></span>  
  
 `this.socket = new Socket(`  
  
 `this.remoteEndPoint.AddressFamily,`  
  
 `SocketType.Dgram,`  
  
 `ProtocolType.Udp`  
  
 `);`  
  
 <span data-ttu-id="6f872-130">El canal puede cerrarse de forma correcta o incorrecta.</span><span class="sxs-lookup"><span data-stu-id="6f872-130">The channel can be closed gracefully or ungracefully.</span></span> <span data-ttu-id="6f872-131">Si el canal se cierra correctamente, el socket se cierra y se realiza una llamada al método `OnClose` de la clase base.</span><span class="sxs-lookup"><span data-stu-id="6f872-131">If the channel is closed gracefully the socket is closed and a call is made to the base class `OnClose` method.</span></span> <span data-ttu-id="6f872-132">Si se inicia una excepción, la infraestructura llama a `Abort` para garantizar que se limpia el canal.</span><span class="sxs-lookup"><span data-stu-id="6f872-132">If this throws an exception, the infrastructure calls `Abort` to ensure the channel is cleaned up.</span></span>  
  
```  
this.socket.Close();  
base.OnClose(timeout);  
```  
  
 <span data-ttu-id="6f872-133">Implemente `Send()` y `BeginSend()` / `EndSend()`.</span><span class="sxs-lookup"><span data-stu-id="6f872-133">Implement `Send()` and `BeginSend()`/`EndSend()`.</span></span> <span data-ttu-id="6f872-134">De este modo se divide en dos secciones principales.</span><span class="sxs-lookup"><span data-stu-id="6f872-134">This breaks down into two main sections.</span></span> <span data-ttu-id="6f872-135">Primero se serializa el mensaje en una matriz de bytes:</span><span class="sxs-lookup"><span data-stu-id="6f872-135">First serialize the message into a byte array:</span></span>  
  
```  
ArraySegment<byte> messageBuffer = EncodeMessage(message);  
```  
  
 <span data-ttu-id="6f872-136">A continuación, se envían los datos resultantes en la conexión:</span><span class="sxs-lookup"><span data-stu-id="6f872-136">Then send the resulting data on the wire:</span></span>  
  
```  
this.socket.SendTo(  
  messageBuffer.Array,   
  messageBuffer.Offset,   
  messageBuffer.Count,   
  SocketFlags.None,   
  this.remoteEndPoint  
);  
```  
  
## <a name="see-also"></a><span data-ttu-id="6f872-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="6f872-137">See Also</span></span>  
 [<span data-ttu-id="6f872-138">Desarrollo de canales</span><span class="sxs-lookup"><span data-stu-id="6f872-138">Developing Channels</span></span>](../../../../docs/framework/wcf/extending/developing-channels.md)
