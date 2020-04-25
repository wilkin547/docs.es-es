---
title: 'Transporte: UDP'
ms.date: 03/30/2017
ms.assetid: 738705de-ad3e-40e0-b363-90305bddb140
ms.openlocfilehash: 3eb7116199cfb23d965918247b74af04d671e79b
ms.sourcegitcommit: 839777281a281684a7e2906dccb3acd7f6a32023
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/24/2020
ms.locfileid: "82141141"
---
# <a name="transport-udp"></a><span data-ttu-id="2def3-102">Transporte: UDP</span><span class="sxs-lookup"><span data-stu-id="2def3-102">Transport: UDP</span></span>
<span data-ttu-id="2def3-103">El ejemplo de transporte UDP muestra cómo implementar unidifusión y multidifusión de UDP como transporte de Windows Communication Foundation personalizado (WCF).</span><span class="sxs-lookup"><span data-stu-id="2def3-103">The UDP Transport sample demonstrates how to implement UDP unicast and multicast as a custom Windows Communication Foundation (WCF) transport.</span></span> <span data-ttu-id="2def3-104">El ejemplo describe el procedimiento recomendado para crear un transporte personalizado en WCF mediante el marco del canal y los siguientes procedimientos recomendados de WCF.</span><span class="sxs-lookup"><span data-stu-id="2def3-104">The sample describes the recommended procedure for creating a custom transport in WCF, by using the channel framework and following WCF best practices.</span></span> <span data-ttu-id="2def3-105">Los pasos para crear un transporte personalizado son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="2def3-105">The steps to create a custom transport are as follows:</span></span>  
  
1. <span data-ttu-id="2def3-106">Decida qué [patrones de intercambio de mensajes](#MessageExchangePatterns) de canal (IOutputChannel, IInputChannel, IDuplexChannel, IRequestChannel o IReplyChannel) admitirán ChannelFactory y ChannelListener.</span><span class="sxs-lookup"><span data-stu-id="2def3-106">Decide which of the channel [Message Exchange Patterns](#MessageExchangePatterns) (IOutputChannel, IInputChannel, IDuplexChannel, IRequestChannel, or IReplyChannel) your ChannelFactory and ChannelListener will support.</span></span> <span data-ttu-id="2def3-107">A continuación, decida si se admitirán las variaciones con sesión de estas interfaces.</span><span class="sxs-lookup"><span data-stu-id="2def3-107">Then decide whether you will support the sessionful variations of these interfaces.</span></span>  
  
2. <span data-ttu-id="2def3-108">Cree un generador de canales y un agente de escucha que admitan el patrón de intercambio de mensajes.</span><span class="sxs-lookup"><span data-stu-id="2def3-108">Create a channel factory and listener that support your Message Exchange Pattern.</span></span>  
  
3. <span data-ttu-id="2def3-109">Asegúrese de que se normalizan las excepciones específicas de red en la clase derivada adecuada de <xref:System.ServiceModel.CommunicationException>.</span><span class="sxs-lookup"><span data-stu-id="2def3-109">Ensure that any network-specific exceptions are normalized to the appropriate derived class of <xref:System.ServiceModel.CommunicationException>.</span></span>  
  
4. <span data-ttu-id="2def3-110">Agregue un [ \<elemento>de enlace](../../configure-apps/file-schema/wcf/bindings.md) que agrega el transporte personalizado a una pila de canales.</span><span class="sxs-lookup"><span data-stu-id="2def3-110">Add a [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element that adds the custom transport to a channel stack.</span></span> <span data-ttu-id="2def3-111">Para obtener más información, vea [Agregar un elemento de enlace](#AddingABindingElement).</span><span class="sxs-lookup"><span data-stu-id="2def3-111">For more information, see [Adding a Binding Element](#AddingABindingElement).</span></span>  
  
5. <span data-ttu-id="2def3-112">Agregue una sección de extensión de elemento de enlace para exponer el nuevo elemento de enlace al sistema de configuración.</span><span class="sxs-lookup"><span data-stu-id="2def3-112">Add a binding element extension section to expose the new binding element to the configuration system.</span></span>  
  
6. <span data-ttu-id="2def3-113">Agregue las extensiones de metadatos para comunicar las funciones a otros puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="2def3-113">Add metadata extensions to communicate capabilities to other endpoints.</span></span>  
  
7. <span data-ttu-id="2def3-114">Agregue un enlace que configura previamente una pila de elementos de enlace según un perfil bien determinado.</span><span class="sxs-lookup"><span data-stu-id="2def3-114">Add a binding that pre-configures a stack of binding elements according to a well-defined profile.</span></span> <span data-ttu-id="2def3-115">Para obtener más información, vea [Agregar un enlace estándar](#AddingAStandardBinding).</span><span class="sxs-lookup"><span data-stu-id="2def3-115">For more information, see [Adding a Standard Binding](#AddingAStandardBinding).</span></span>  
  
8. <span data-ttu-id="2def3-116">Agregue una sección de enlace y un elemento de configuración de enlace para exponer el enlace al sistema de configuración.</span><span class="sxs-lookup"><span data-stu-id="2def3-116">Add a binding section and binding configuration element to expose the binding to the configuration system.</span></span> <span data-ttu-id="2def3-117">Para obtener más información, consulte [Agregar compatibilidad con la configuración](#AddingConfigurationSupport).</span><span class="sxs-lookup"><span data-stu-id="2def3-117">For more information, see [Adding Configuration Support](#AddingConfigurationSupport).</span></span>  
  
<a name="MessageExchangePatterns"></a>
## <a name="message-exchange-patterns"></a><span data-ttu-id="2def3-118">Modelos de intercambio de mensajes</span><span class="sxs-lookup"><span data-stu-id="2def3-118">Message Exchange Patterns</span></span>  
 <span data-ttu-id="2def3-119">El primer paso a la hora de escribir un transporte personalizado es decidir qué patrones de intercambio de mensajes (MEP) son necesarios para el transporte.</span><span class="sxs-lookup"><span data-stu-id="2def3-119">The first step in writing a custom transport is to decide which Message Exchange Patterns (MEPs) are required for the transport.</span></span> <span data-ttu-id="2def3-120">Hay tres MEP entre los que elegir:</span><span class="sxs-lookup"><span data-stu-id="2def3-120">There are three MEPs to choose from:</span></span>  
  
- <span data-ttu-id="2def3-121">Datagrama (IInputChannel/IOutputChannel)</span><span class="sxs-lookup"><span data-stu-id="2def3-121">Datagram (IInputChannel/IOutputChannel)</span></span>  
  
     <span data-ttu-id="2def3-122">Al utilizar un MEP de datagrama, un cliente envía un mensaje mediante un intercambio de tipo desencadenar y omitir.</span><span class="sxs-lookup"><span data-stu-id="2def3-122">When using a datagram MEP, a client sends a message using a "fire and forget" exchange.</span></span> <span data-ttu-id="2def3-123">Un intercambio de este tipo es uno que exige una confirmación fuera de banda de entrega correcta.</span><span class="sxs-lookup"><span data-stu-id="2def3-123">A fire and forget exchange is one that requires out-of-band confirmation of successful delivery.</span></span> <span data-ttu-id="2def3-124">El mensaje se podría perderse por el camino y no llegar nunca al servicio.</span><span class="sxs-lookup"><span data-stu-id="2def3-124">The message might be lost in transit and never reach the service.</span></span> <span data-ttu-id="2def3-125">Si la operación de envío se completa correctamente en la parte del cliente, no garantiza que el extremo remoto haya recibido el mensaje.</span><span class="sxs-lookup"><span data-stu-id="2def3-125">If the send operation completes successfully at the client end, it does not guarantee that the remote endpoint has received the message.</span></span> <span data-ttu-id="2def3-126">El datagrama es un bloque de creación fundamental para la mensajería, ya que puede crear sus propios protocolos encima de él, incluidos protocolos confiables y seguros.</span><span class="sxs-lookup"><span data-stu-id="2def3-126">The datagram is a fundamental building block for messaging, as you can build your own protocols on top of it—including reliable protocols and secure protocols.</span></span> <span data-ttu-id="2def3-127">Los canales de datagrama del cliente implementan la interfaz <xref:System.ServiceModel.Channels.IOutputChannel> y los del servicio, la interfaz <xref:System.ServiceModel.Channels.IInputChannel>.</span><span class="sxs-lookup"><span data-stu-id="2def3-127">Client datagram channels implement the <xref:System.ServiceModel.Channels.IOutputChannel> interface and service datagram channels implement the <xref:System.ServiceModel.Channels.IInputChannel> interface.</span></span>  
  
- <span data-ttu-id="2def3-128">Solicitud-respuesta (IRequestChannel/IReplyChannel)</span><span class="sxs-lookup"><span data-stu-id="2def3-128">Request-Response (IRequestChannel/IReplyChannel)</span></span>  
  
     <span data-ttu-id="2def3-129">En este MEP, un mensaje se envía y se recibe una respuesta.</span><span class="sxs-lookup"><span data-stu-id="2def3-129">In this MEP, a message is sent, and a reply is received.</span></span> <span data-ttu-id="2def3-130">El patrón está compuesto de los pares solicitud-respuesta.</span><span class="sxs-lookup"><span data-stu-id="2def3-130">The pattern consists of request-response pairs.</span></span> <span data-ttu-id="2def3-131">Los ejemplos de llamadas de solicitud-respuesta son llamadas a procedimiento remoto (RPC) y solicitudes GET del explorador.</span><span class="sxs-lookup"><span data-stu-id="2def3-131">Examples of request-response calls are remote procedure calls (RPC) and browser GETs.</span></span> <span data-ttu-id="2def3-132">Este patrón también se conoce como "dúplex medio".</span><span class="sxs-lookup"><span data-stu-id="2def3-132">This pattern is also known as Half-Duplex.</span></span> <span data-ttu-id="2def3-133">En este MEP, los canales de cliente implementan <xref:System.ServiceModel.Channels.IRequestChannel> y los canales de servicio <xref:System.ServiceModel.Channels.IReplyChannel>.</span><span class="sxs-lookup"><span data-stu-id="2def3-133">In this MEP, client channels implement <xref:System.ServiceModel.Channels.IRequestChannel> and service channels implement <xref:System.ServiceModel.Channels.IReplyChannel>.</span></span>  
  
- <span data-ttu-id="2def3-134">Dúplex (IDuplexChannel)</span><span class="sxs-lookup"><span data-stu-id="2def3-134">Duplex (IDuplexChannel)</span></span>  
  
     <span data-ttu-id="2def3-135">El MEP dúplex permite que un cliente envíe un número arbitrario de mensajes y que se reciban en cualquier orden.</span><span class="sxs-lookup"><span data-stu-id="2def3-135">The duplex MEP allows an arbitrary number of messages to be sent by a client and received in any order.</span></span> <span data-ttu-id="2def3-136">El MEP de dúplex es como una conversación telefónica, donde cada palabra que se pronuncia es un mensaje.</span><span class="sxs-lookup"><span data-stu-id="2def3-136">The duplex MEP is like a phone conversation, where each word being spoken is a message.</span></span> <span data-ttu-id="2def3-137">Dado que ambos lados pueden enviar y recibir en este MEP, la interfaz implementada por los canales de servicio y cliente es <xref:System.ServiceModel.Channels.IDuplexChannel>.</span><span class="sxs-lookup"><span data-stu-id="2def3-137">Because both sides can send and receive in this MEP, the interface implemented by the client and service channels is <xref:System.ServiceModel.Channels.IDuplexChannel>.</span></span>  
  
 <span data-ttu-id="2def3-138">Cada uno de estos MEP también puede admitir sesiones.</span><span class="sxs-lookup"><span data-stu-id="2def3-138">Each of these MEPs can also support sessions.</span></span> <span data-ttu-id="2def3-139">La funcionalidad agregada proporcionada por un canal con reconocimiento de sesión es que pone en correlación todos los mensajes enviados y recibidos en un canal.</span><span class="sxs-lookup"><span data-stu-id="2def3-139">The added functionality provided by a session-aware channel is that it correlates all messages sent and received on a channel.</span></span> <span data-ttu-id="2def3-140">El patrón de solicitud-respuesta es una sesión autónoma de dos mensajes, ya que la solicitud y la respuesta se ponen en correlación.</span><span class="sxs-lookup"><span data-stu-id="2def3-140">The Request-Response pattern is a stand-alone two-message session, as the request and reply are correlated.</span></span> <span data-ttu-id="2def3-141">Por el contrario, el patrón de solicitud-respuesta que admite las sesiones implica que se ponen en correlación todos los pares de solicitud/respuesta en ese canal entre sí.</span><span class="sxs-lookup"><span data-stu-id="2def3-141">In contrast, the Request-Response pattern that supports sessions implies that all request/response pairs on that channel are correlated with each other.</span></span> <span data-ttu-id="2def3-142">Esto le da un total de seis MEP (datagrama, solicitud-respuesta, dúplex, datagrama con sesiones, solicitud-respuesta con sesiones y dúplex con sesiones) entre los que elegir.</span><span class="sxs-lookup"><span data-stu-id="2def3-142">This gives you a total of six MEPs—Datagram, Request-Response, Duplex, Datagram with sessions, Request-Response with sessions, and Duplex with sessions—to choose from.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2def3-143">En el caso del transporte de UDP, el único MEP que se admite es el datagrama, ya que UDP es en sí mismo un protocolo de tipo "desencadenar y omitir".</span><span class="sxs-lookup"><span data-stu-id="2def3-143">For the UDP transport, the only MEP that is supported is Datagram, because UDP is inherently a "fire and forget" protocol.</span></span>  
  
### <a name="the-icommunicationobject-and-the-wcf-object-lifecycle"></a><span data-ttu-id="2def3-144">ICommunicationObject y el ciclo de vida del objeto WCF</span><span class="sxs-lookup"><span data-stu-id="2def3-144">The ICommunicationObject and the WCF object lifecycle</span></span>  
 <span data-ttu-id="2def3-145">WCF tiene una máquina de Estados común que se usa para administrar el ciclo de vida <xref:System.ServiceModel.Channels.IChannel>de <xref:System.ServiceModel.Channels.IChannelFactory>objetos como <xref:System.ServiceModel.Channels.IChannelListener> , y que se usan para la comunicación.</span><span class="sxs-lookup"><span data-stu-id="2def3-145">WCF has a common state machine that is used for managing the lifecycle of objects like <xref:System.ServiceModel.Channels.IChannel>, <xref:System.ServiceModel.Channels.IChannelFactory>, and <xref:System.ServiceModel.Channels.IChannelListener> that are used for communication.</span></span> <span data-ttu-id="2def3-146">Hay cinco estados donde estos objetos de comunicación pueden existir.</span><span class="sxs-lookup"><span data-stu-id="2def3-146">There are five states in which these communication objects can exist.</span></span> <span data-ttu-id="2def3-147">La enumeración <xref:System.ServiceModel.CommunicationState> representa estos estados y son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="2def3-147">These states are represented by the <xref:System.ServiceModel.CommunicationState> enumeration, and are as follows:</span></span>  
  
- <span data-ttu-id="2def3-148">Creado: este es el estado de una interfaz <xref:System.ServiceModel.ICommunicationObject> la primera vez que se crean instancias de ella.</span><span class="sxs-lookup"><span data-stu-id="2def3-148">Created: This is the state of a <xref:System.ServiceModel.ICommunicationObject> when it is first instantiated.</span></span> <span data-ttu-id="2def3-149">No se produce ninguna entrada/salida (E/S) en este estado.</span><span class="sxs-lookup"><span data-stu-id="2def3-149">No input/output (I/O) occurs in this state.</span></span>  
  
- <span data-ttu-id="2def3-150">Abriendo: transición de objetos a este estado cuando se llama al método <xref:System.ServiceModel.ICommunicationObject.Open%2A>.</span><span class="sxs-lookup"><span data-stu-id="2def3-150">Opening: Objects transition to this state when <xref:System.ServiceModel.ICommunicationObject.Open%2A> is called.</span></span> <span data-ttu-id="2def3-151">En este punto, las propiedades se convierten en inmutables y puede comenzar la entrada/salida.</span><span class="sxs-lookup"><span data-stu-id="2def3-151">At this point properties are made immutable, and input/output can begin.</span></span> <span data-ttu-id="2def3-152">Esta transición solo es válida desde el estado Creado.</span><span class="sxs-lookup"><span data-stu-id="2def3-152">This transition is valid only from the Created state.</span></span>  
  
- <span data-ttu-id="2def3-153">Abierto: los objetos pasan a este estado cuando el proceso de apertura se completa.</span><span class="sxs-lookup"><span data-stu-id="2def3-153">Opened: Objects transition to this state when the open process completes.</span></span> <span data-ttu-id="2def3-154">Esta transición solo es válida desde el estado Abriendo.</span><span class="sxs-lookup"><span data-stu-id="2def3-154">This transition is valid only from the Opening state.</span></span> <span data-ttu-id="2def3-155">En este punto, se puede usar el objeto para la transferencia.</span><span class="sxs-lookup"><span data-stu-id="2def3-155">At this point, the object is fully usable for transfer.</span></span>  
  
- <span data-ttu-id="2def3-156">Cerrando: los objetos pasan a este estado cuando se llama al método <xref:System.ServiceModel.ICommunicationObject.Close%2A> para que el apagado sea correcto.</span><span class="sxs-lookup"><span data-stu-id="2def3-156">Closing: Objects transition to this state when <xref:System.ServiceModel.ICommunicationObject.Close%2A> is called for a graceful shutdown.</span></span> <span data-ttu-id="2def3-157">Esta transición solo es válida desde el estado Abierto.</span><span class="sxs-lookup"><span data-stu-id="2def3-157">This transition is valid only from the Opened state.</span></span>  
  
- <span data-ttu-id="2def3-158">Cerrado: en este estado, no se pueden utilizar los objetos.</span><span class="sxs-lookup"><span data-stu-id="2def3-158">Closed: In the Closed state objects are no longer usable.</span></span> <span data-ttu-id="2def3-159">En general, aún se puede acceder a la mayoría de la configuración para su inspección pero no se puede producir ninguna comunicación.</span><span class="sxs-lookup"><span data-stu-id="2def3-159">In general, most configuration is still accessible for inspection, but no communication can occur.</span></span> <span data-ttu-id="2def3-160">Este estado es equivalente a eliminarse.</span><span class="sxs-lookup"><span data-stu-id="2def3-160">This state is equivalent to being disposed.</span></span>  
  
- <span data-ttu-id="2def3-161">Con error: en este estado, se puede tener acceso a los objetos para inspeccionarlos pero no se pueden usar.</span><span class="sxs-lookup"><span data-stu-id="2def3-161">Faulted: In the Faulted state, objects are accessible to inspection but no longer usable.</span></span> <span data-ttu-id="2def3-162">Cuando se produce un error no recuperable, el objeto pasa a este estado.</span><span class="sxs-lookup"><span data-stu-id="2def3-162">When a non-recoverable error occurs, the object transitions into this state.</span></span> <span data-ttu-id="2def3-163">La única transición válida desde este estado es en el `Closed` estado.</span><span class="sxs-lookup"><span data-stu-id="2def3-163">The only valid transition from this state is into the `Closed` state.</span></span>  
  
 <span data-ttu-id="2def3-164">Hay eventos que se desencadenan para cada transición de estado.</span><span class="sxs-lookup"><span data-stu-id="2def3-164">There are events that fire for each state transition.</span></span> <span data-ttu-id="2def3-165">Se puede llamar al método <xref:System.ServiceModel.ICommunicationObject.Abort%2A> en cualquier momento, lo que provoca que el objeto pase inmediatamente de su estado actual al estado Cerrado.</span><span class="sxs-lookup"><span data-stu-id="2def3-165">The <xref:System.ServiceModel.ICommunicationObject.Abort%2A> method can be called at any time, and causes the object to transition immediately from its current state into the Closed state.</span></span> <span data-ttu-id="2def3-166">Al llamar <xref:System.ServiceModel.ICommunicationObject.Abort%2A>, se finaliza cualquier trabajo inacabado.</span><span class="sxs-lookup"><span data-stu-id="2def3-166">Calling <xref:System.ServiceModel.ICommunicationObject.Abort%2A> terminates any unfinished work.</span></span>  
  
<a name="ChannelAndChannelListener"></a>
## <a name="channel-factory-and-channel-listener"></a><span data-ttu-id="2def3-167">Generador de canales y agente de escucha de canales</span><span class="sxs-lookup"><span data-stu-id="2def3-167">Channel Factory and Channel Listener</span></span>  
 <span data-ttu-id="2def3-168">El paso siguiente para escribir un transporte personalizado es crear una implementación de <xref:System.ServiceModel.Channels.IChannelFactory> para los canales de cliente y de <xref:System.ServiceModel.Channels.IChannelListener> para los canales de servicio.</span><span class="sxs-lookup"><span data-stu-id="2def3-168">The next step in writing a custom transport is to create an implementation of <xref:System.ServiceModel.Channels.IChannelFactory> for client channels and of <xref:System.ServiceModel.Channels.IChannelListener> for service channels.</span></span> <span data-ttu-id="2def3-169">La capa de canal usa un patrón de generador para crear canales.</span><span class="sxs-lookup"><span data-stu-id="2def3-169">The channel layer uses a factory pattern for constructing channels.</span></span> <span data-ttu-id="2def3-170">WCF proporciona aplicaciones auxiliares de clase base para este proceso.</span><span class="sxs-lookup"><span data-stu-id="2def3-170">WCF provides base class helpers for this process.</span></span>  
  
- <span data-ttu-id="2def3-171">La clase <xref:System.ServiceModel.Channels.CommunicationObject> implementa <xref:System.ServiceModel.ICommunicationObject> y aplica el equipo de estado descrito previamente en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="2def3-171">The <xref:System.ServiceModel.Channels.CommunicationObject> class implements <xref:System.ServiceModel.ICommunicationObject> and enforces the state machine previously described in Step 2.</span></span>

- <span data-ttu-id="2def3-172">La <xref:System.ServiceModel.Channels.ChannelManagerBase> clase implementa <xref:System.ServiceModel.Channels.CommunicationObject> y proporciona una clase base unificada para <xref:System.ServiceModel.Channels.ChannelFactoryBase> y <xref:System.ServiceModel.Channels.ChannelListenerBase>.</span><span class="sxs-lookup"><span data-stu-id="2def3-172">The <xref:System.ServiceModel.Channels.ChannelManagerBase> class implements <xref:System.ServiceModel.Channels.CommunicationObject> and provides a unified base class for <xref:System.ServiceModel.Channels.ChannelFactoryBase> and <xref:System.ServiceModel.Channels.ChannelListenerBase>.</span></span> <span data-ttu-id="2def3-173">La clase <xref:System.ServiceModel.Channels.ChannelManagerBase> trabaja junto con <xref:System.ServiceModel.Channels.ChannelBase>, que es una clase base que implementa <xref:System.ServiceModel.Channels.IChannel>.</span><span class="sxs-lookup"><span data-stu-id="2def3-173">The <xref:System.ServiceModel.Channels.ChannelManagerBase> class works in conjunction with <xref:System.ServiceModel.Channels.ChannelBase>, which is a base class that implements <xref:System.ServiceModel.Channels.IChannel>.</span></span>  
  
- <span data-ttu-id="2def3-174">La <xref:System.ServiceModel.Channels.ChannelFactoryBase> clase implementa <xref:System.ServiceModel.Channels.ChannelManagerBase> y <xref:System.ServiceModel.Channels.IChannelFactory> y consolida las `CreateChannel` sobrecargas en un `OnCreateChannel` método abstracto.</span><span class="sxs-lookup"><span data-stu-id="2def3-174">The <xref:System.ServiceModel.Channels.ChannelFactoryBase> class implements <xref:System.ServiceModel.Channels.ChannelManagerBase> and <xref:System.ServiceModel.Channels.IChannelFactory> and consolidates the `CreateChannel` overloads into one `OnCreateChannel` abstract method.</span></span>  
  
- <span data-ttu-id="2def3-175">La <xref:System.ServiceModel.Channels.ChannelListenerBase> clase implementa <xref:System.ServiceModel.Channels.IChannelListener>.</span><span class="sxs-lookup"><span data-stu-id="2def3-175">The <xref:System.ServiceModel.Channels.ChannelListenerBase> class implements <xref:System.ServiceModel.Channels.IChannelListener>.</span></span> <span data-ttu-id="2def3-176">Se encarga de la administración de estados básica.</span><span class="sxs-lookup"><span data-stu-id="2def3-176">It takes care of basic state management.</span></span>  
  
 <span data-ttu-id="2def3-177">En este ejemplo, la implementación del generador se encuentra en UdpChannelFactory.cs y la implementación del agente de escucha se encuentra en UdpChannelListener.cs.</span><span class="sxs-lookup"><span data-stu-id="2def3-177">In this sample, the factory implementation is contained in UdpChannelFactory.cs and the listener implementation is contained in UdpChannelListener.cs.</span></span> <span data-ttu-id="2def3-178">Las implementaciones <xref:System.ServiceModel.Channels.IChannel> están en UdpOutputChannel.cs y UdpInputChannel.cs.</span><span class="sxs-lookup"><span data-stu-id="2def3-178">The <xref:System.ServiceModel.Channels.IChannel> implementations are in UdpOutputChannel.cs and UdpInputChannel.cs.</span></span>  
  
### <a name="the-udp-channel-factory"></a><span data-ttu-id="2def3-179">Generador de canales UDP</span><span class="sxs-lookup"><span data-stu-id="2def3-179">The UDP Channel Factory</span></span>  
 <span data-ttu-id="2def3-180">La clase `UdpChannelFactory` se deriva de la clase <xref:System.ServiceModel.Channels.ChannelFactoryBase>.</span><span class="sxs-lookup"><span data-stu-id="2def3-180">The `UdpChannelFactory` derives from <xref:System.ServiceModel.Channels.ChannelFactoryBase>.</span></span> <span data-ttu-id="2def3-181">El ejemplo invalida <xref:System.ServiceModel.Channels.ChannelFactoryBase.GetProperty%2A> para proporcionar acceso a la versión del mensaje del codificador de mensajes.</span><span class="sxs-lookup"><span data-stu-id="2def3-181">The sample overrides <xref:System.ServiceModel.Channels.ChannelFactoryBase.GetProperty%2A> to provide access to the message version of the message encoder.</span></span> <span data-ttu-id="2def3-182">El ejemplo también invalida <xref:System.ServiceModel.Channels.ChannelFactoryBase.OnClose%2A> de manera que podamos anular nuestra instancia de <xref:System.ServiceModel.Channels.BufferManager> cuando se realizan las transiciones del equipo de estado.</span><span class="sxs-lookup"><span data-stu-id="2def3-182">The sample also overrides <xref:System.ServiceModel.Channels.ChannelFactoryBase.OnClose%2A> so that we can tear down our instance of <xref:System.ServiceModel.Channels.BufferManager> when the state machine transitions.</span></span>  
  
#### <a name="the-udp-output-channel"></a><span data-ttu-id="2def3-183">Canal de salida UDP</span><span class="sxs-lookup"><span data-stu-id="2def3-183">The UDP Output Channel</span></span>  
 <span data-ttu-id="2def3-184">La clase `UdpOutputChannel` implementa la interfaz <xref:System.ServiceModel.Channels.IOutputChannel>.</span><span class="sxs-lookup"><span data-stu-id="2def3-184">The `UdpOutputChannel` implements <xref:System.ServiceModel.Channels.IOutputChannel>.</span></span> <span data-ttu-id="2def3-185">El constructor valida los argumentos y construye un objeto de destino <xref:System.Net.EndPoint> basado en la <xref:System.ServiceModel.EndpointAddress> a la que se pasa.</span><span class="sxs-lookup"><span data-stu-id="2def3-185">The constructor validates the arguments and constructs a destination <xref:System.Net.EndPoint> object based on the <xref:System.ServiceModel.EndpointAddress> that is passed in.</span></span>  
  
```csharp
this.socket = new Socket(this.remoteEndPoint.AddressFamily, SocketType.Dgram, ProtocolType.Udp);  
```  
  
 <span data-ttu-id="2def3-186">El canal puede cerrarse de forma correcta o incorrecta.</span><span class="sxs-lookup"><span data-stu-id="2def3-186">The channel can be closed gracefully or ungracefully.</span></span> <span data-ttu-id="2def3-187">Si el canal se cierra correctamente, el socket se cierra y se realiza una llamada al método `OnClose` de la clase base.</span><span class="sxs-lookup"><span data-stu-id="2def3-187">If the channel is closed gracefully the socket is closed and a call is made to the base class `OnClose` method.</span></span> <span data-ttu-id="2def3-188">Si se inicia una excepción, la infraestructura llama a `Abort` para garantizar que se limpia el canal.</span><span class="sxs-lookup"><span data-stu-id="2def3-188">If this throws an exception, the infrastructure calls `Abort` to ensure the channel is cleaned up.</span></span>  
  
```csharp
this.socket.Close(0);  
```  
  
 <span data-ttu-id="2def3-189">A continuación, `Send()` implementamos y `BeginSend()` / `EndSend()`.</span><span class="sxs-lookup"><span data-stu-id="2def3-189">We then implement `Send()` and `BeginSend()`/`EndSend()`.</span></span> <span data-ttu-id="2def3-190">De este modo se divide en dos secciones principales.</span><span class="sxs-lookup"><span data-stu-id="2def3-190">This breaks down into two main sections.</span></span> <span data-ttu-id="2def3-191">Primero se serializa el mensaje en una matriz de bytes.</span><span class="sxs-lookup"><span data-stu-id="2def3-191">First we serialize the message into a byte array.</span></span>  
  
```csharp
ArraySegment<byte> messageBuffer = EncodeMessage(message);  
```  
  
 <span data-ttu-id="2def3-192">A continuación, se envían los datos resultantes en la conexión.</span><span class="sxs-lookup"><span data-stu-id="2def3-192">Then we send the resulting data on the wire.</span></span>  
  
```csharp
this.socket.SendTo(messageBuffer.Array, messageBuffer.Offset, messageBuffer.Count, SocketFlags.None, this.remoteEndPoint);  
```  
  
### <a name="the-udpchannellistener"></a><span data-ttu-id="2def3-193">UdpChannelListener</span><span class="sxs-lookup"><span data-stu-id="2def3-193">The UdpChannelListener</span></span>  
 <span data-ttu-id="2def3-194">`UdpChannelListener` Que el ejemplo implementa se deriva de la <xref:System.ServiceModel.Channels.ChannelListenerBase> clase.</span><span class="sxs-lookup"><span data-stu-id="2def3-194">The `UdpChannelListener` that the sample implements derives from the <xref:System.ServiceModel.Channels.ChannelListenerBase> class.</span></span> <span data-ttu-id="2def3-195">Utiliza un socket UDP único para recibir datagramas.</span><span class="sxs-lookup"><span data-stu-id="2def3-195">It uses a single UDP socket to receive datagrams.</span></span> <span data-ttu-id="2def3-196">El método `OnOpen` recibe datos utilizando el socket UDP en un bucle asincrónico.</span><span class="sxs-lookup"><span data-stu-id="2def3-196">The `OnOpen` method receives data using the UDP socket in an asynchronous loop.</span></span> <span data-ttu-id="2def3-197">Los datos se convierten en mensajes utilizando el marco de trabajo de codificación de mensajes:</span><span class="sxs-lookup"><span data-stu-id="2def3-197">The data are then converted into messages using the Message Encoding Framework.</span></span>  
  
```csharp
message = MessageEncoderFactory.Encoder.ReadMessage(new ArraySegment<byte>(buffer, 0, count), bufferManager);  
```  
  
 <span data-ttu-id="2def3-198">Dado que el mismo canal del datagrama representa mensajes que llegan de varios orígenes, `UdpChannelListener` es un agente de escucha singleton.</span><span class="sxs-lookup"><span data-stu-id="2def3-198">Because the same datagram channel represents messages that arrive from a number of sources, the `UdpChannelListener` is a singleton listener.</span></span> <span data-ttu-id="2def3-199">Hay, como máximo, un activo <xref:System.ServiceModel.Channels.IChannel> asociado a este agente de escucha a la vez.</span><span class="sxs-lookup"><span data-stu-id="2def3-199">There is, at most, one active <xref:System.ServiceModel.Channels.IChannel> associated with this listener at a time.</span></span> <span data-ttu-id="2def3-200">El ejemplo solo genera otro si se elimina subsiguientemente un canal que es devuelto por el método `AcceptChannel`.</span><span class="sxs-lookup"><span data-stu-id="2def3-200">The sample generates another one only if a channel that is returned by the `AcceptChannel` method is subsequently disposed.</span></span> <span data-ttu-id="2def3-201">Cuando se recibe un mensaje, se pone en cola en este canal singleton.</span><span class="sxs-lookup"><span data-stu-id="2def3-201">When a message is received, it is enqueued into this singleton channel.</span></span>  
  
#### <a name="udpinputchannel"></a><span data-ttu-id="2def3-202">UdpInputChannel</span><span class="sxs-lookup"><span data-stu-id="2def3-202">UdpInputChannel</span></span>  
 <span data-ttu-id="2def3-203">La `UdpInputChannel` clase implementa `IInputChannel`.</span><span class="sxs-lookup"><span data-stu-id="2def3-203">The `UdpInputChannel` class implements `IInputChannel`.</span></span> <span data-ttu-id="2def3-204">Está compuesto de una cola de mensajes entrantes que es rellenada por el socket `UdpChannelListener`.</span><span class="sxs-lookup"><span data-stu-id="2def3-204">It consists of a queue of incoming messages that is populated by the `UdpChannelListener`'s socket.</span></span> <span data-ttu-id="2def3-205">Estos mensajes se quitan de la cola mediante el método `IInputChannel.Receive`.</span><span class="sxs-lookup"><span data-stu-id="2def3-205">These messages are dequeued by the `IInputChannel.Receive` method.</span></span>  
  
<a name="AddingABindingElement"></a>
## <a name="adding-a-binding-element"></a><span data-ttu-id="2def3-206">Adición de un elemento de enlace</span><span class="sxs-lookup"><span data-stu-id="2def3-206">Adding a Binding Element</span></span>  
 <span data-ttu-id="2def3-207">Ahora que se han creado los generadores y canales, se deben exponer en el tiempo de ejecución de ServiceModel mediante un enlace.</span><span class="sxs-lookup"><span data-stu-id="2def3-207">Now that the factories and channels are built, we must expose them to the ServiceModel runtime through a binding.</span></span> <span data-ttu-id="2def3-208">Un enlace es una colección de elementos de enlace que representa la pila de comunicación asociada con una dirección de servicio.</span><span class="sxs-lookup"><span data-stu-id="2def3-208">A binding is a collection of binding elements that represents the communication stack associated with a service address.</span></span> <span data-ttu-id="2def3-209">Cada elemento de la pila se representa mediante un [ \<enlace>](../../configure-apps/file-schema/wcf/bindings.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="2def3-209">Each element in the stack is represented by a [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element.</span></span>  
  
 <span data-ttu-id="2def3-210">En el ejemplo, el elemento de enlace es `UdpTransportBindingElement`, que deriva de <xref:System.ServiceModel.Channels.TransportBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="2def3-210">In the sample, the binding element is `UdpTransportBindingElement`, which derives from <xref:System.ServiceModel.Channels.TransportBindingElement>.</span></span> <span data-ttu-id="2def3-211">Invalida los métodos siguientes para crear los generadores asociados con el enlace.</span><span class="sxs-lookup"><span data-stu-id="2def3-211">It overrides the following methods to build the factories associated with our binding.</span></span>  
  
```csharp
public IChannelFactory<TChannel> BuildChannelFactory<TChannel>(BindingContext context)  
{  
    return (IChannelFactory<TChannel>)(object)new UdpChannelFactory(this, context);  
}  
  
public IChannelListener<TChannel> BuildChannelListener<TChannel>(BindingContext context)  
{  
    return (IChannelListener<TChannel>)(object)new UdpChannelListener(this, context);  
}  
```  
  
 <span data-ttu-id="2def3-212">También contiene los miembros para clonar `BindingElement` y devolver nuestro esquema (soap.udp).</span><span class="sxs-lookup"><span data-stu-id="2def3-212">It also contains members for cloning the `BindingElement` and returning our scheme (soap.udp).</span></span>  
  
## <a name="adding-metadata-support-for-a-transport-binding-element"></a><span data-ttu-id="2def3-213">Agregación de compatibilidad con metadatos para un elemento de enlace de transporte</span><span class="sxs-lookup"><span data-stu-id="2def3-213">Adding Metadata Support for a Transport Binding Element</span></span>  
 <span data-ttu-id="2def3-214">Para integrar nuestro transporte en el sistema de metadatos, debe admitir la importación y exportación de la directiva.</span><span class="sxs-lookup"><span data-stu-id="2def3-214">To integrate our transport into the metadata system, we must support both the import and export of policy.</span></span> <span data-ttu-id="2def3-215">Esto nos permite generar clientes de nuestro enlace a través de la [herramienta de utilidad de metadatos de ServiceModel (SvcUtil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="2def3-215">This allows us to generate clients of our binding through the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span>  
  
### <a name="adding-wsdl-support"></a><span data-ttu-id="2def3-216">Agregación de la compatibilidad con WSDL</span><span class="sxs-lookup"><span data-stu-id="2def3-216">Adding WSDL Support</span></span>  
 <span data-ttu-id="2def3-217">El elemento de enlace del transporte en un enlace es el responsable de la exportación e importación de la información de direccionamiento en metadatos.</span><span class="sxs-lookup"><span data-stu-id="2def3-217">The transport binding element in a binding is responsible for exporting and importing addressing information in metadata.</span></span> <span data-ttu-id="2def3-218">Al utilizar un enlace SOAP, el elemento de enlace del transporte también debería exportar un URI de transporte correcto en los metadatos.</span><span class="sxs-lookup"><span data-stu-id="2def3-218">When using a SOAP binding, the transport binding element should also export a correct transport URI in metadata.</span></span>  
  
#### <a name="wsdl-export"></a><span data-ttu-id="2def3-219">Exportación de WSDL</span><span class="sxs-lookup"><span data-stu-id="2def3-219">WSDL Export</span></span>  
 <span data-ttu-id="2def3-220">Para exportar información de direccionamiento, `UdpTransportBindingElement` implementa la interfaz `IWsdlExportExtension`.</span><span class="sxs-lookup"><span data-stu-id="2def3-220">To export addressing information the `UdpTransportBindingElement` implements the `IWsdlExportExtension` interface.</span></span> <span data-ttu-id="2def3-221">El método `ExportEndpoint` agrega la información de direccionamiento correcta al puerto WSDL.</span><span class="sxs-lookup"><span data-stu-id="2def3-221">The `ExportEndpoint` method adds the correct addressing information to the WSDL port.</span></span>  
  
```csharp
if (context.WsdlPort != null)  
{  
    AddAddressToWsdlPort(context.WsdlPort, context.Endpoint.Address, encodingBindingElement.MessageVersion.Addressing);  
}  
```  
  
 <span data-ttu-id="2def3-222">La implementación `UdpTransportBindingElement` del método `ExportEndpoint` también exporta un URI de transporte cuando el punto de conexión utiliza un enlace SOAP.</span><span class="sxs-lookup"><span data-stu-id="2def3-222">The `UdpTransportBindingElement` implementation of the `ExportEndpoint` method also exports a transport URI when the endpoint uses a SOAP binding.</span></span>  
  
```csharp
WsdlNS.SoapBinding soapBinding = GetSoapBinding(context, exporter);  
if (soapBinding != null)  
{  
    soapBinding.Transport = UdpPolicyStrings.UdpNamespace;  
}  
```  
  
#### <a name="wsdl-import"></a><span data-ttu-id="2def3-223">Importación de WSDL</span><span class="sxs-lookup"><span data-stu-id="2def3-223">WSDL Import</span></span>  
 <span data-ttu-id="2def3-224">Para extender el sistema de importación de WSDL para que administre la importación de direcciones, debemos agregar la configuración siguiente al archivo de configuración para Svcutil.exe, tal y como se muestra en el archivo Svcutil.exe.config:</span><span class="sxs-lookup"><span data-stu-id="2def3-224">To extend the WSDL import system to handle importing the addresses, we must add the following configuration to the configuration file for Svcutil.exe as shown in the Svcutil.exe.config file.</span></span>  
  
```xml
<configuration>  
  <system.serviceModel>  
    <client>  
      <metadata>  
        <policyImporters>  
          <extension type=" Microsoft.ServiceModel.Samples.UdpBindingElementImporter, UdpTransport" />  
        </policyImporters>  
      </metadata>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="2def3-225">Al ejecutar Svcutil.exe, hay dos opciones para conseguir que Svcutil.exe cargue las extensiones de importación de WSDL:</span><span class="sxs-lookup"><span data-stu-id="2def3-225">When running Svcutil.exe, there are two options for getting Svcutil.exe to load the WSDL import extensions:</span></span>  
  
1. <span data-ttu-id="2def3-226">Señale SvcUtil. exe a nuestro archivo de configuración mediante/SvcutilConfig\<: file>.</span><span class="sxs-lookup"><span data-stu-id="2def3-226">Point Svcutil.exe to our configuration file using the /SvcutilConfig:\<file>.</span></span>  
  
2. <span data-ttu-id="2def3-227">Agregue la sección de configuración a Svcutil.exe.config en el mismo directorio como Svcutil.exe.</span><span class="sxs-lookup"><span data-stu-id="2def3-227">Add the configuration section to Svcutil.exe.config in the same directory as Svcutil.exe.</span></span>  
  
 <span data-ttu-id="2def3-228">El tipo `UdpBindingElementImporter` implementa la interfaz `IWsdlImportExtension`.</span><span class="sxs-lookup"><span data-stu-id="2def3-228">The `UdpBindingElementImporter` type implements the `IWsdlImportExtension` interface.</span></span> <span data-ttu-id="2def3-229">El método `ImportEndpoint` importa la dirección del puerto WSDL.</span><span class="sxs-lookup"><span data-stu-id="2def3-229">The `ImportEndpoint` method imports the address from the WSDL port.</span></span>  
  
```csharp
BindingElementCollection bindingElements = context.Endpoint.Binding.CreateBindingElements();  
TransportBindingElement transportBindingElement = bindingElements.Find<TransportBindingElement>();  
if (transportBindingElement is UdpTransportBindingElement)  
{  
    ImportAddress(context);  
}  
```  
  
### <a name="adding-policy-support"></a><span data-ttu-id="2def3-230">Agregación de compatibilidad de directiva</span><span class="sxs-lookup"><span data-stu-id="2def3-230">Adding Policy Support</span></span>  
 <span data-ttu-id="2def3-231">El elemento de enlace personalizado puede exportar aserciones de directiva en el enlace de WSDL para que un extremo de servicio exprese las funciones de ese elemento de enlace.</span><span class="sxs-lookup"><span data-stu-id="2def3-231">The custom binding element can export policy assertions in the WSDL binding for a service endpoint to express the capabilities of that binding element.</span></span>  
  
#### <a name="policy-export"></a><span data-ttu-id="2def3-232">Exportación de directivas</span><span class="sxs-lookup"><span data-stu-id="2def3-232">Policy Export</span></span>  
 <span data-ttu-id="2def3-233">El `UdpTransportBindingElement` tipo implementa `IPolicyExportExtension` para agregar compatibilidad para la exportación de la Directiva.</span><span class="sxs-lookup"><span data-stu-id="2def3-233">The `UdpTransportBindingElement` type implements `IPolicyExportExtension` to add support for exporting policy.</span></span> <span data-ttu-id="2def3-234">Como resultado, `System.ServiceModel.MetadataExporter` incluye `UdpTransportBindingElement` en la generación de directiva para cualquier enlace que la incluya.</span><span class="sxs-lookup"><span data-stu-id="2def3-234">As a result, `System.ServiceModel.MetadataExporter` includes `UdpTransportBindingElement` in the generation of policy for any binding that includes it.</span></span>  
  
 <span data-ttu-id="2def3-235">En `IPolicyExportExtension.ExportPolicy`, agregamos una aserción para UDP y otra si estamos en modo de multidifusión.</span><span class="sxs-lookup"><span data-stu-id="2def3-235">In `IPolicyExportExtension.ExportPolicy`, we add an assertion for UDP and another assertion if we are in multicast mode.</span></span> <span data-ttu-id="2def3-236">Esto se debe a que el modo de multidifusión afecta a cómo se construye la pila de comunicaciones, y, por tanto, debe coordinarse entre ambos lados.</span><span class="sxs-lookup"><span data-stu-id="2def3-236">This is because multicast mode affects how the communication stack is constructed, and thus must be coordinated between both sides.</span></span>  
  
```csharp
ICollection<XmlElement> bindingAssertions = context.GetBindingAssertions();  
XmlDocument xmlDocument = new XmlDocument();  
bindingAssertions.Add(xmlDocument.CreateElement(  
UdpPolicyStrings.Prefix, UdpPolicyStrings.TransportAssertion, UdpPolicyStrings.UdpNamespace));  
if (Multicast)  
{  
    bindingAssertions.Add(xmlDocument.CreateElement(
        UdpPolicyStrings.Prefix,
        UdpPolicyStrings.MulticastAssertion,
        UdpPolicyStrings.UdpNamespace));  
}  
```  
  
 <span data-ttu-id="2def3-237">Dado que los elementos de enlace de transporte personalizados son responsables de la administración del direccionamiento, la implementación `IPolicyExportExtension` en el `UdpTransportBindingElement` también debe administrar la exportación de las aserciones de directivas WS-Addressing adecuadas para indicar la versión de WS-Addressing que se está utilizando.</span><span class="sxs-lookup"><span data-stu-id="2def3-237">Because custom transport binding elements are responsible for handling addressing, the `IPolicyExportExtension` implementation on the `UdpTransportBindingElement` must also handle exporting the appropriate WS-Addressing policy assertions to indicate the version of WS-Addressing being used.</span></span>  
  
```csharp
AddWSAddressingAssertion(context, encodingBindingElement.MessageVersion.Addressing);  
```  
  
#### <a name="policy-import"></a><span data-ttu-id="2def3-238">Importación de directivas</span><span class="sxs-lookup"><span data-stu-id="2def3-238">Policy Import</span></span>  
 <span data-ttu-id="2def3-239">Para extender el sistema de importación de directivas, debe agregar la siguiente configuración al archivo de configuración para Svcutil.exe tal y como se muestra en el archivo Svcutil.exe.config.</span><span class="sxs-lookup"><span data-stu-id="2def3-239">To extend the Policy Import system, we must add the following configuration to the configuration file for Svcutil.exe as shown in the Svcutil.exe.config file.</span></span>  
  
```xml
<configuration>  
  <system.serviceModel>  
    <client>  
      <metadata>  
        <policyImporters>  
          <extension type=" Microsoft.ServiceModel.Samples.UdpBindingElementImporter, UdpTransport" />  
        </policyImporters>  
      </metadata>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="2def3-240">A continuación, implementamos `IPolicyImporterExtension` desde nuestra clase registrada (`UdpBindingElementImporter`).</span><span class="sxs-lookup"><span data-stu-id="2def3-240">Then we implement `IPolicyImporterExtension` from our registered class (`UdpBindingElementImporter`).</span></span> <span data-ttu-id="2def3-241">En `ImportPolicy()`, examinamos las aserciones en nuestro espacio de nombres y procesamos las que se encargan de la generación del transporte y de la comprobación de si es multidifusión.</span><span class="sxs-lookup"><span data-stu-id="2def3-241">In `ImportPolicy()`, we look through the assertions in our namespace, and process the ones for generating the transport and check whether it is multicast.</span></span> <span data-ttu-id="2def3-242">También debemos quitar las aserciones que administramos de la lista de aserciones de enlace.</span><span class="sxs-lookup"><span data-stu-id="2def3-242">We also must remove the assertions we handle from the list of binding assertions.</span></span> <span data-ttu-id="2def3-243">De nuevo, al ejecutar Svcutil.exe, hay dos opciones para la integración:</span><span class="sxs-lookup"><span data-stu-id="2def3-243">Again, when running Svcutil.exe, there are two options for integration:</span></span>  
  
1. <span data-ttu-id="2def3-244">Señale SvcUtil. exe a nuestro archivo de configuración mediante/SvcutilConfig\<: file>.</span><span class="sxs-lookup"><span data-stu-id="2def3-244">Point Svcutil.exe to our configuration file using the /SvcutilConfig:\<file>.</span></span>  
  
2. <span data-ttu-id="2def3-245">Agregue la sección de configuración a Svcutil.exe.config en el mismo directorio como Svcutil.exe.</span><span class="sxs-lookup"><span data-stu-id="2def3-245">Add the configuration section to Svcutil.exe.config in the same directory as Svcutil.exe.</span></span>  
  
<a name="AddingAStandardBinding"></a>
## <a name="adding-a-standard-binding"></a><span data-ttu-id="2def3-246">Adición de un enlace estándar</span><span class="sxs-lookup"><span data-stu-id="2def3-246">Adding a Standard Binding</span></span>  
 <span data-ttu-id="2def3-247">Nuestro elemento de enlace se puede utilizar de las dos maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="2def3-247">Our binding element can be used in the following two ways:</span></span>  
  
- <span data-ttu-id="2def3-248">A través de un enlace personalizado: un enlace personalizado permite al usuario crear su propio enlace basado en un conjunto arbitrario de elementos de enlace.</span><span class="sxs-lookup"><span data-stu-id="2def3-248">Through a custom binding: A custom binding allows the user to create their own binding based on an arbitrary set of binding elements.</span></span>  
  
- <span data-ttu-id="2def3-249">Usando un enlace proporcionado por el sistema que incluye nuestro elemento de enlace.</span><span class="sxs-lookup"><span data-stu-id="2def3-249">By using a system-provided binding that includes our binding element.</span></span> <span data-ttu-id="2def3-250">WCF proporciona varios de estos enlaces definidos por el sistema, como `BasicHttpBinding`, `NetTcpBinding`y. `WsHttpBinding`</span><span class="sxs-lookup"><span data-stu-id="2def3-250">WCF provides a number of these system-defined bindings, such as `BasicHttpBinding`, `NetTcpBinding`, and `WsHttpBinding`.</span></span> <span data-ttu-id="2def3-251">Cada uno de estos enlaces está asociado a un perfil bien definido.</span><span class="sxs-lookup"><span data-stu-id="2def3-251">Each of these bindings is associated with a well-defined profile.</span></span>  
  
 <span data-ttu-id="2def3-252">El ejemplo implementa el enlace del perfil en `SampleProfileUdpBinding`, que deriva de <xref:System.ServiceModel.Channels.Binding>.</span><span class="sxs-lookup"><span data-stu-id="2def3-252">The sample implements profile binding in `SampleProfileUdpBinding`, which derives from <xref:System.ServiceModel.Channels.Binding>.</span></span> <span data-ttu-id="2def3-253">`SampleProfileUdpBinding` contiene hasta cuatro elementos de enlace dentro de él: `UdpTransportBindingElement`, `TextMessageEncodingBindingElement CompositeDuplexBindingElement` y `ReliableSessionBindingElement`.</span><span class="sxs-lookup"><span data-stu-id="2def3-253">The `SampleProfileUdpBinding` contains up to four binding elements within it: `UdpTransportBindingElement`, `TextMessageEncodingBindingElement CompositeDuplexBindingElement`, and `ReliableSessionBindingElement`.</span></span>  
  
```csharp
public override BindingElementCollection CreateBindingElements()  
{
    BindingElementCollection bindingElements = new BindingElementCollection();  
    if (ReliableSessionEnabled)  
    {  
        bindingElements.Add(session);  
        bindingElements.Add(compositeDuplex);  
    }  
    bindingElements.Add(encoding);  
    bindingElements.Add(transport);  
    return bindingElements.Clone();  
}  
```  
  
### <a name="adding-a-custom-standard-binding-importer"></a><span data-ttu-id="2def3-254">Agregación de un importador de enlace estándar personalizado</span><span class="sxs-lookup"><span data-stu-id="2def3-254">Adding a Custom Standard Binding Importer</span></span>  
 <span data-ttu-id="2def3-255">Svcutil.exe y el tipo `WsdlImporter`, de forma predeterminada, reconocen e importan los enlaces definidos por el sistema.</span><span class="sxs-lookup"><span data-stu-id="2def3-255">Svcutil.exe and the `WsdlImporter` type, by default, recognizes and imports system-defined bindings.</span></span> <span data-ttu-id="2def3-256">De lo contrario, el enlace se importa como una instancia `CustomBinding`.</span><span class="sxs-lookup"><span data-stu-id="2def3-256">Otherwise, the binding gets imported as a `CustomBinding` instance.</span></span> <span data-ttu-id="2def3-257">Para permitir que Svcutil.exe y `WsdlImporter` importen el `SampleProfileUdpBinding`, el `UdpBindingElementImporter` actúa también como un importador de enlaces estándar personalizado.</span><span class="sxs-lookup"><span data-stu-id="2def3-257">To enable Svcutil.exe and the `WsdlImporter` to import the `SampleProfileUdpBinding` the `UdpBindingElementImporter` also acts as a custom standard binding importer.</span></span>  
  
 <span data-ttu-id="2def3-258">Un importador de este tipo implementa el método `ImportEndpoint` en la interfaz `IWsdlImportExtension` para examinar la instancia `CustomBinding` importada desde los metadatos para ver si el enlace estándar concreto podría haberla generado.</span><span class="sxs-lookup"><span data-stu-id="2def3-258">A custom standard binding importer implements the `ImportEndpoint` method on the `IWsdlImportExtension` interface to examine the `CustomBinding` instance imported from metadata to see whether it could have been generated by a specific standard binding.</span></span>  
  
```csharp
if (context.Endpoint.Binding is CustomBinding)  
{  
    Binding binding;  
    if (transportBindingElement is UdpTransportBindingElement)  
    {  
        //if TryCreate is true, the CustomBinding will be replace by a SampleProfileUdpBinding in the  
        //generated config file for better typed generation.  
        if (SampleProfileUdpBinding.TryCreate(bindingElements, out binding))  
        {  
            binding.Name = context.Endpoint.Binding.Name;  
            binding.Namespace = context.Endpoint.Binding.Namespace;  
            context.Endpoint.Binding = binding;  
        }  
    }  
}  
```  
  
 <span data-ttu-id="2def3-259">Generalmente, la implementación de un importador de enlaces estándar personalizado, implica la comprobación de las propiedades de los elementos de enlace importados para comprobar que solo las propiedades que pudo establecer el enlace estándar han cambiado y el resto propiedades son sus valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="2def3-259">Generally, implementing a custom standard binding importer involves checking the properties of the imported binding elements to verify that only properties that could have been set by the standard binding have changed and all other properties are their defaults.</span></span> <span data-ttu-id="2def3-260">Una estrategia básica para implementar un importador de enlace estándar consiste en crear una instancia de enlace estándar, propagar las propiedades desde los elementos de enlace a la instancia de enlace estándar que admite enlaces estándar y, a continuación, comparar los elementos de enlace desde el enlace estándar con los elementos de enlace importados.</span><span class="sxs-lookup"><span data-stu-id="2def3-260">A basic strategy for implementing a standard binding importer is to create an instance of the standard binding, propagate the properties from the binding elements to the standard binding instance that the standard binding supports, and the compare the binding elements from the standard binding with the imported binding elements.</span></span>  
  
<a name="AddingConfigurationSupport"></a>
## <a name="adding-configuration-support"></a><span data-ttu-id="2def3-261">Agregación de la compatibilidad de configuración</span><span class="sxs-lookup"><span data-stu-id="2def3-261">Adding Configuration Support</span></span>  
 <span data-ttu-id="2def3-262">Para exponer nuestro transporte a través de la configuración, debemos implementar dos secciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="2def3-262">To expose our transport through configuration, we must implement two configuration sections.</span></span> <span data-ttu-id="2def3-263">El primero es `BindingElementExtensionElement` para `UdpTransportBindingElement`.</span><span class="sxs-lookup"><span data-stu-id="2def3-263">The first is a `BindingElementExtensionElement` for `UdpTransportBindingElement`.</span></span> <span data-ttu-id="2def3-264">Esto es para que las implementaciones de `CustomBinding` puedan hacer referencia a nuestro elemento de enlace.</span><span class="sxs-lookup"><span data-stu-id="2def3-264">This is so that `CustomBinding` implementations can reference our binding element.</span></span> <span data-ttu-id="2def3-265">El segundo es `Configuration` para `SampleProfileUdpBinding`.</span><span class="sxs-lookup"><span data-stu-id="2def3-265">The second is a `Configuration` for our `SampleProfileUdpBinding`.</span></span>  
  
### <a name="binding-element-extension-element"></a><span data-ttu-id="2def3-266">Elemento de extensión de elemento de enlace</span><span class="sxs-lookup"><span data-stu-id="2def3-266">Binding Element Extension Element</span></span>  
 <span data-ttu-id="2def3-267">La sección `UdpTransportElement` es un objeto `BindingElementExtensionElement` que expone `UdpTransportBindingElement` en el sistema de configuración.</span><span class="sxs-lookup"><span data-stu-id="2def3-267">The section `UdpTransportElement` is a `BindingElementExtensionElement` that exposes `UdpTransportBindingElement` to the configuration system.</span></span> <span data-ttu-id="2def3-268">Con algunas invalidaciones básicas, definimos el nombre de la sección de configuración, el tipo del elemento de enlace y cómo crear el elemento de enlace.</span><span class="sxs-lookup"><span data-stu-id="2def3-268">With a few basic overrides, we define our configuration section name, the type of our binding element and how to create our binding element.</span></span> <span data-ttu-id="2def3-269">Podemos registrar a continuación como se muestra nuestra sección de extensión en un archivo de configuración en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="2def3-269">We can then register our extension section in a configuration file as shown in the following code.</span></span>  
  
```xml
<configuration>  
  <system.serviceModel>  
    <extensions>  
      <bindingElementExtensions>  
        <add name="udpTransport" type="Microsoft.ServiceModel.Samples.UdpTransportElement, UdpTransport" />  
      </bindingElementExtensions>  
    </extensions>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="2def3-270">Se puede hacer referencia a la extensión desde enlaces personalizados para utilizar UDP como el transporte.</span><span class="sxs-lookup"><span data-stu-id="2def3-270">The extension can be referenced from custom bindings to use UDP as the transport.</span></span>  
  
```xml
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <customBinding>  
       <binding configurationName="UdpCustomBinding">  
         <udpTransport/>  
       </binding>  
      </customBinding>  
    </bindings>  
  </system.serviceModel>  
</configuration>  
```  
  
### <a name="binding-section"></a><span data-ttu-id="2def3-271">Sección de enlace</span><span class="sxs-lookup"><span data-stu-id="2def3-271">Binding Section</span></span>  
 <span data-ttu-id="2def3-272">La sección `SampleProfileUdpBindingCollectionElement` es un objeto `StandardBindingCollectionElement` que expone `SampleProfileUdpBinding` en el sistema de configuración.</span><span class="sxs-lookup"><span data-stu-id="2def3-272">The section `SampleProfileUdpBindingCollectionElement` is a `StandardBindingCollectionElement` that exposes `SampleProfileUdpBinding` to the configuration system.</span></span> <span data-ttu-id="2def3-273">El volumen de la implementación se delega a `SampleProfileUdpBindingConfigurationElement`, que deriva de `StandardBindingElement`.</span><span class="sxs-lookup"><span data-stu-id="2def3-273">The bulk of the implementation is delegated to the `SampleProfileUdpBindingConfigurationElement`, which derives from `StandardBindingElement`.</span></span> <span data-ttu-id="2def3-274">`SampleProfileUdpBindingConfigurationElement` Tiene propiedades que corresponden a las propiedades de `SampleProfileUdpBinding`y a las funciones que se van a asignar desde el `ConfigurationElement` enlace.</span><span class="sxs-lookup"><span data-stu-id="2def3-274">The `SampleProfileUdpBindingConfigurationElement` has properties that correspond to the properties on `SampleProfileUdpBinding`, and functions to map from the `ConfigurationElement` binding.</span></span> <span data-ttu-id="2def3-275">Finalmente, se invalida el método `OnApplyConfiguration` en nuestro `SampleProfileUdpBinding`, tal y como se muestra en el siguiente código muestra.</span><span class="sxs-lookup"><span data-stu-id="2def3-275">Finally, override the `OnApplyConfiguration` method in our `SampleProfileUdpBinding`, as shown in the following sample code.</span></span>  
  
```csharp
protected override void OnApplyConfiguration(string configurationName)  
{  
    if (binding == null)
        throw new ArgumentNullException("binding");

    if (binding.GetType() != typeof(SampleProfileUdpBinding))
    {
        throw new ArgumentException(string.Format(CultureInfo.CurrentCulture,
            "Invalid type for binding. Expected type: {0}. Type passed in: {1}.",
            typeof(SampleProfileUdpBinding).AssemblyQualifiedName,
            binding.GetType().AssemblyQualifiedName));
    }
    SampleProfileUdpBinding udpBinding = (SampleProfileUdpBinding)binding;

    udpBinding.OrderedSession = this.OrderedSession;
    udpBinding.ReliableSessionEnabled = this.ReliableSessionEnabled;
    udpBinding.SessionInactivityTimeout = this.SessionInactivityTimeout;
    if (this.ClientBaseAddress != null)
        udpBinding.ClientBaseAddress = ClientBaseAddress;
}
```  
  
 <span data-ttu-id="2def3-276">Para registrar este controlador con el sistema de configuración, agregamos la siguiente sección al archivo de configuración pertinente.</span><span class="sxs-lookup"><span data-stu-id="2def3-276">To register this handler with the configuration system, we add the following section to the relevant configuration file.</span></span>  
  
```xml
<configuration>  
  <configSections>  
     <sectionGroup name="system.serviceModel">  
        <sectionGroup name="bindings">  
          <section name="sampleProfileUdpBinding" type="Microsoft.ServiceModel.Samples.SampleProfileUdpBindingCollectionElement, UdpTransport" />  
        </sectionGroup>  
     </sectionGroup>  
  </configSections>  
</configuration>  
```  
  
 <span data-ttu-id="2def3-277">A continuación, se puede establecer la referencia desde la sección de configuración serviceModel.</span><span class="sxs-lookup"><span data-stu-id="2def3-277">It can then be referenced from the serviceModel configuration section.</span></span>  
  
```xml
<configuration>  
  <system.serviceModel>  
    <client>  
      <endpoint configurationName="calculator"  
                address="soap.udp://localhost:8001/"
                bindingConfiguration="CalculatorServer"  
                binding="sampleProfileUdpBinding"
                contract= "Microsoft.ServiceModel.Samples.ICalculatorContract">  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="the-udp-test-service-and-client"></a><span data-ttu-id="2def3-278">Servicio de pruebas y cliente UDP</span><span class="sxs-lookup"><span data-stu-id="2def3-278">The UDP Test Service and Client</span></span>  
 <span data-ttu-id="2def3-279">El código de prueba para usar este transporte de ejemplo está disponible en los directorios UdpTestService y UdpTestClient.</span><span class="sxs-lookup"><span data-stu-id="2def3-279">Test code for using this sample transport is available in the UdpTestService and UdpTestClient directories.</span></span> <span data-ttu-id="2def3-280">El código de servicio está compuesto de dos pruebas: una configura los enlaces y puntos de conexión desde el código y la otra lo hace a través de la configuración.</span><span class="sxs-lookup"><span data-stu-id="2def3-280">The service code consists of two tests—one test sets up bindings and endpoints from code and the other does it through configuration.</span></span> <span data-ttu-id="2def3-281">Ambas pruebas utilizan dos extremos.</span><span class="sxs-lookup"><span data-stu-id="2def3-281">Both tests use two endpoints.</span></span> <span data-ttu-id="2def3-282">Un punto de conexión `SampleUdpProfileBinding` utiliza con [ \<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90)) establecido `true`en.</span><span class="sxs-lookup"><span data-stu-id="2def3-282">One endpoint uses the `SampleUdpProfileBinding` with [\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90)) set to `true`.</span></span> <span data-ttu-id="2def3-283">El otro extremo utiliza un enlace personalizado con `UdpTransportBindingElement`.</span><span class="sxs-lookup"><span data-stu-id="2def3-283">The other endpoint uses a custom binding with `UdpTransportBindingElement`.</span></span> <span data-ttu-id="2def3-284">Esto es equivalente a usar `SampleUdpProfileBinding` con [ \<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90)) establecido en `false`.</span><span class="sxs-lookup"><span data-stu-id="2def3-284">This is equivalent to using `SampleUdpProfileBinding` with [\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90)) set to `false`.</span></span> <span data-ttu-id="2def3-285">Ambas pruebas crean un servicio, agregan un extremo para cada enlace, abren el servicio y, a continuación, esperan a que el usuario presione ENTRAR antes de cerrar el servicio.</span><span class="sxs-lookup"><span data-stu-id="2def3-285">Both tests create a service, add an endpoint for each binding, open the service and then wait for the user to hit ENTER before closing the service.</span></span>  
  
 <span data-ttu-id="2def3-286">Al iniciar la aplicación de prueba del servicio, debería ver el resultado siguiente.</span><span class="sxs-lookup"><span data-stu-id="2def3-286">When you start the service test application you should see the following output.</span></span>  
  
```console
Testing Udp From Code.  
Service is started from code...  
Press <ENTER> to terminate the service and start service from config...  
```  
  
 <span data-ttu-id="2def3-287">Puede ejecutar a continuación la aplicación cliente de prueba con los extremos publicados.</span><span class="sxs-lookup"><span data-stu-id="2def3-287">You can then run the test client application against the published endpoints.</span></span> <span data-ttu-id="2def3-288">La aplicación de prueba del cliente crea un cliente para cada extremo y envía cinco mensajes a cada extremo.</span><span class="sxs-lookup"><span data-stu-id="2def3-288">The client test application creates a client for each endpoint and sends five messages to each endpoint.</span></span> <span data-ttu-id="2def3-289">El resultado siguiente se encuentra en el cliente.</span><span class="sxs-lookup"><span data-stu-id="2def3-289">The following output is on the client.</span></span>  
  
```console
Testing Udp From Imported Files Generated By SvcUtil.  
0  
3  
6  
9  
12  
Press <ENTER> to complete test.  
```  
  
 <span data-ttu-id="2def3-290">A continuación, se muestra el resultado completo en el servicio.</span><span class="sxs-lookup"><span data-stu-id="2def3-290">The following is the full output on the service.</span></span>  
  
```console
Service is started from code...  
Press <ENTER> to terminate the service and start service from config...  
Hello, world!  
Hello, world!  
Hello, world!  
Hello, world!  
Hello, world!  
   adding 0 + 0  
   adding 1 + 2  
   adding 2 + 4  
   adding 3 + 6  
   adding 4 + 8  
```  
  
 <span data-ttu-id="2def3-291">Para ejecutar la aplicación cliente en los extremos publicados utilizando la configuración, presione ENTRAR en el servicio y después ejecute de nuevo el cliente de prueba.</span><span class="sxs-lookup"><span data-stu-id="2def3-291">To run the client application against endpoints published using configuration, hit ENTER on the service and then run the test client again.</span></span> <span data-ttu-id="2def3-292">Debería ver el siguiente resultado en el servicio.</span><span class="sxs-lookup"><span data-stu-id="2def3-292">You should see the following output on the service.</span></span>  
  
```console
Testing Udp From Config.  
Service is started from config...  
Press <ENTER> to terminate the service and exit...  
```  
  
 <span data-ttu-id="2def3-293">Ejecutar de nuevo el cliente produce lo mismo que los resultados anteriores.</span><span class="sxs-lookup"><span data-stu-id="2def3-293">Running the client again yields the same as the preceding results.</span></span>  
  
 <span data-ttu-id="2def3-294">Para regenerar el código de cliente y la configuración utilizando Svcutil.exe, inicie la aplicación de servicio y, a continuación, ejecute Svcutil.exe siguiente desde el directorio raíz del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="2def3-294">To regenerate the client code and configuration using Svcutil.exe, start the service application and then run the following Svcutil.exe from the root directory of the sample.</span></span>  
  
```console
svcutil http://localhost:8000/udpsample/ /reference:UdpTransport\bin\UdpTransport.dll /svcutilConfig:svcutil.exe.config  
```  
  
 <span data-ttu-id="2def3-295">Observe que Svcutil.exe no genera la configuración de extensión de enlace para `SampleProfileUdpBinding`, por lo que deberá agregarla manualmente.</span><span class="sxs-lookup"><span data-stu-id="2def3-295">Note that Svcutil.exe does not generate the binding extension configuration for the `SampleProfileUdpBinding`, so you must add it manually.</span></span>  
  
```xml
<configuration>  
  <system.serviceModel>
    <extensions>  
      <!-- This was added manually because svcutil.exe does not add this extension to the file -->  
      <bindingExtensions>  
        <add name="sampleProfileUdpBinding" type="Microsoft.ServiceModel.Samples.SampleProfileUdpBindingCollectionElement, UdpTransport" />  
      </bindingExtensions>  
    </extensions>  
  </system.serviceModel>  
</configuration>  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="2def3-296">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="2def3-296">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="2def3-297">Para compilar la solución, siga las instrucciones de [creación de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="2def3-297">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
2. <span data-ttu-id="2def3-298">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="2def3-298">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
3. <span data-ttu-id="2def3-299">Consulte la sección anterior "Servicio de pruebas y cliente UDP".</span><span class="sxs-lookup"><span data-stu-id="2def3-299">Refer to the preceding "The UDP Test Service and Client" section.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="2def3-300">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="2def3-300">The samples may already be installed on your machine.</span></span> <span data-ttu-id="2def3-301">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="2def3-301">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="2def3-302">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y ejemplos.</span><span class="sxs-lookup"><span data-stu-id="2def3-302">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="2def3-303">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="2def3-303">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Transport\Udp`
