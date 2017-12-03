---
title: '&lt;reliableSession&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 129b4a59-37f0-4030-b664-03795d257d29
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f8484fe902b356f7fae4e526bdaa5610bf7d7ac6
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="ltreliablesessiongt"></a><span data-ttu-id="6940b-102">&lt;reliableSession&gt;</span><span class="sxs-lookup"><span data-stu-id="6940b-102">&lt;reliableSession&gt;</span></span>
<span data-ttu-id="6940b-103">Define el valor para los mensajes de confianza de WS.</span><span class="sxs-lookup"><span data-stu-id="6940b-103">Defines setting for WS-Reliable Messaging.</span></span> <span data-ttu-id="6940b-104">Cuando este elemento se agrega a un enlace personalizado, el canal resultante puede admitir las convicciones de la entrega exactamente una vez.</span><span class="sxs-lookup"><span data-stu-id="6940b-104">When this element is added to a custom binding, the resulting channel can support exactly-once delivery assurances.</span></span>  
  
 <span data-ttu-id="6940b-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="6940b-105">\<system.serviceModel></span></span>  
<span data-ttu-id="6940b-106">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="6940b-106">\<bindings></span></span>  
<span data-ttu-id="6940b-107">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="6940b-107">\<customBinding></span></span>  
<span data-ttu-id="6940b-108">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="6940b-108">\<binding></span></span>  
<span data-ttu-id="6940b-109">\<reliableSession ></span><span class="sxs-lookup"><span data-stu-id="6940b-109">\<reliableSession></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6940b-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6940b-110">Syntax</span></span>  
  
```xml  
<reliableSession acknowledgementInterval="TimeSpan"  
        flowControlEnabled="Boolean"   
    inactivityTimeout="TimeSpan"  
    maxPendingChannels="Integer"  
    maxRetryCount="Integer"   
        maxTransferWindowSize="Integer"  
    reliableMessagingVersion="Default/WSReliableMessagingFebruary2005/WSReliableMessaging11"  
    ordered="Boolean" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6940b-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="6940b-111">Attributes and Elements</span></span>  
 <span data-ttu-id="6940b-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="6940b-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6940b-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="6940b-113">Attributes</span></span>  
  
|<span data-ttu-id="6940b-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="6940b-114">Attribute</span></span>|<span data-ttu-id="6940b-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="6940b-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6940b-116">acknowledgementInterval</span><span class="sxs-lookup"><span data-stu-id="6940b-116">acknowledgementInterval</span></span>|<span data-ttu-id="6940b-117"><xref:System.TimeSpan> que contiene el intervalo de tiempo máximo que el canal va a esperar para enviar un reconocimiento para los mensajes recibidos hasta ese punto.</span><span class="sxs-lookup"><span data-stu-id="6940b-117">A <xref:System.TimeSpan> that contains the maximum time interval the channel is going to wait to send an acknowledgment for messages received up to that point.</span></span> <span data-ttu-id="6940b-118">El valor predeterminado es 00:00:02.</span><span class="sxs-lookup"><span data-stu-id="6940b-118">The default is 00:00:0.2.</span></span>|  
|<span data-ttu-id="6940b-119">flowControlEnabled</span><span class="sxs-lookup"><span data-stu-id="6940b-119">flowControlEnabled</span></span>|<span data-ttu-id="6940b-120">Un valor booleano que indica si se activa el control de flujo avanzado, una implementación específica de Microsoft de control de flujo para la mensajería de confianza de WS.</span><span class="sxs-lookup"><span data-stu-id="6940b-120">A Boolean value that indicates whether advanced flow control, a Microsoft-specific implementation of flow control for WS-Reliable messaging, is activated.</span></span> <span data-ttu-id="6940b-121">De manera predeterminada, es `true`.</span><span class="sxs-lookup"><span data-stu-id="6940b-121">The default is `true`.</span></span>|  
|<span data-ttu-id="6940b-122">inactivityTimeOut</span><span class="sxs-lookup"><span data-stu-id="6940b-122">inactivityTimeout</span></span>|<span data-ttu-id="6940b-123">Un <xref:System.TimeSpan> que especifica el tiempo máximo durante el cual el canal va a permitir a la otra parte de la comunicación no enviar ningún mensaje sin que se produzca un error.</span><span class="sxs-lookup"><span data-stu-id="6940b-123">A <xref:System.TimeSpan> that specifies the maximum duration that the channel is going to allow the other communication party not to send any messages, before faulting the channel.</span></span> <span data-ttu-id="6940b-124">El valor predeterminado es 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="6940b-124">The default is 00:10:00.</span></span><br /><br /> <span data-ttu-id="6940b-125">La actividad en un canal se define como la recepción de una aplicación o mensajes de infraestructura.</span><span class="sxs-lookup"><span data-stu-id="6940b-125">Activity on a channel is defined as receiving an application or infrastructure messages.</span></span> <span data-ttu-id="6940b-126">Esta propiedad controla el tiempo máximo para mantener activa una sesión inactiva.</span><span class="sxs-lookup"><span data-stu-id="6940b-126">This property controls the maximum amount of time to keep an inactive session alive.</span></span> <span data-ttu-id="6940b-127">Si transcurre más tiempo sin actividad, la sesión es finalizada por la infraestructura y los errores del canal.</span><span class="sxs-lookup"><span data-stu-id="6940b-127">If longer time passes with no activity, the session is aborted by the infrastructure and the channel faults.</span></span> <span data-ttu-id="6940b-128">**Nota:** no es necesario para la aplicación envíe periódicamente mensajes para mantener activa la conexión.</span><span class="sxs-lookup"><span data-stu-id="6940b-128">**Note:**  It is not necessary for the application to periodically send messages to keep the connection alive.</span></span>|  
|<span data-ttu-id="6940b-129">maxPendingChannels</span><span class="sxs-lookup"><span data-stu-id="6940b-129">maxPendingChannels</span></span>|<span data-ttu-id="6940b-130">Un entero que especifica el número máximo de canales que pueden esperar en el agente de escucha para ser aceptados.</span><span class="sxs-lookup"><span data-stu-id="6940b-130">An integer that specifies the maximum number of channels that can wait on the listener to be accepted.</span></span> <span data-ttu-id="6940b-131">Este valor debe estar comprendido entre 1 y 16384, ambos inclusive.</span><span class="sxs-lookup"><span data-stu-id="6940b-131">This value should be between 1 to 16384 inclusive.</span></span> <span data-ttu-id="6940b-132">El valor predeterminado es 4.</span><span class="sxs-lookup"><span data-stu-id="6940b-132">The default is 4.</span></span><br /><br /> <span data-ttu-id="6940b-133">Los canales están pendientes cuando esperan a ser aceptados.</span><span class="sxs-lookup"><span data-stu-id="6940b-133">Channels are pending when they are waiting to be accepted.</span></span> <span data-ttu-id="6940b-134">Una vez alcanzado ese límite, no se crea ningún canal.</span><span class="sxs-lookup"><span data-stu-id="6940b-134">Once that limit is reached, no channels are created.</span></span> <span data-ttu-id="6940b-135">Más bien, se colocan en modo pendiente hasta que este número baje (al aceptar los canales pendientes).</span><span class="sxs-lookup"><span data-stu-id="6940b-135">Rather, they are put in pending mode until this number goes down (by accepting pending channels).</span></span> <span data-ttu-id="6940b-136">Éste es un límite por generador.</span><span class="sxs-lookup"><span data-stu-id="6940b-136">This is a per-factory limit.</span></span><br /><br /> <span data-ttu-id="6940b-137">Cuando se alcanza el umbral y una aplicación remota intenta establecer una nueva sesión fiable, se deniega la solicitud y falla la operación abierta que pidió confirmación.</span><span class="sxs-lookup"><span data-stu-id="6940b-137">When the threshold is reached and a remote application tries to establish a new reliable session, the request is denied and the open operation that prompted this faults.</span></span> <span data-ttu-id="6940b-138">Este límite no se aplica al número de canales pendientes de la salida.</span><span class="sxs-lookup"><span data-stu-id="6940b-138">This limit does not apply to the number of pending outgoing channels.</span></span>|  
|<span data-ttu-id="6940b-139">maxRetryCount</span><span class="sxs-lookup"><span data-stu-id="6940b-139">maxRetryCount</span></span>|<span data-ttu-id="6940b-140">Un entero que especifica el número máximo de horas que un canal fiable intenta retransmitir un mensaje para el que no ha recibido reconocimiento, yendo a Enviar en su canal subyacente.</span><span class="sxs-lookup"><span data-stu-id="6940b-140">An integer that specifies the maximum number of times a reliable channel attempts to retransmit a message it has not received an acknowledgment for, by calling Send on its underlying channel.</span></span><br /><br /> <span data-ttu-id="6940b-141">Este valor debería ser mayor que cero.</span><span class="sxs-lookup"><span data-stu-id="6940b-141">This value should be greater than zero.</span></span> <span data-ttu-id="6940b-142">El valor predeterminado es 8.</span><span class="sxs-lookup"><span data-stu-id="6940b-142">The default is 8.</span></span><br /><br /> <span data-ttu-id="6940b-143">Este valor debería ser un entero mayor que cero.</span><span class="sxs-lookup"><span data-stu-id="6940b-143">This value should be an integer greater than zero.</span></span> <span data-ttu-id="6940b-144">Si un reconocimiento no se recibe después de la última retransmisión, el canal falla.</span><span class="sxs-lookup"><span data-stu-id="6940b-144">If an acknowledgment is not received after the last retransmission, the channel faults.</span></span><br /><br /> <span data-ttu-id="6940b-145">Se considera que un mensaje es transferido si el destinatario ha confirmado su entrega.</span><span class="sxs-lookup"><span data-stu-id="6940b-145">A message is considered to be transferred if its delivery at the recipient has been acknowledged by the recipient.</span></span><br /><br /> <span data-ttu-id="6940b-146">Si no se ha recibido reconocimiento tras un cierto tiempo de un mensaje que se ha transmitido, la infraestructura retransmite automáticamente el mensaje.</span><span class="sxs-lookup"><span data-stu-id="6940b-146">If an acknowledgment has not been received within a certain amount of time for a message that has been transmitted, the infrastructure automatically retransmits the message.</span></span> <span data-ttu-id="6940b-147">La infraestructura intenta reenviar el mensaje el máximo número de veces especificado por esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="6940b-147">The infrastructure tries to resend the message for at most the number of times specified by this property.</span></span> <span data-ttu-id="6940b-148">Si un reconocimiento no se recibe después de la última retransmisión, el canal falla.</span><span class="sxs-lookup"><span data-stu-id="6940b-148">If an acknowledgment is not received after the last retransmission, the channel faults.</span></span><br /><br /> <span data-ttu-id="6940b-149">La infraestructura utiliza un algoritmo de espera exponencial para determinar cuándo retransmitir, en función del tiempo medio calculado de ida y vuelta.</span><span class="sxs-lookup"><span data-stu-id="6940b-149">The infrastructure uses an exponential back-off algorithm to determine when to retransmit, based on a computed average round-trip time.</span></span> <span data-ttu-id="6940b-150">El tiempo empieza inicialmente 1 segundo antes de la retransmisión y duplica el retraso en cada intento, lo que da como resultado aproximadamente 8,5 minutos que pasan entre el primer intento de la transmisión y el último intento de la retransmisión.</span><span class="sxs-lookup"><span data-stu-id="6940b-150">The time initially starts at 1 second before retransmission and doubling the delay with every attempt, which results in approximately 8.5 minutes passing between the first transmission attempt and the last retransmission attempt.</span></span> <span data-ttu-id="6940b-151">El tiempo del primer intento de retransmisión se ajusta al cálculo del tiempo de ida y vuelta y varía según el período de tiempo adicional que resulta del número de intentos que se necesitan.</span><span class="sxs-lookup"><span data-stu-id="6940b-151">The time for the first retransmission attempt is adjusted according to the calculated round-trip time and the resulting stretch of time that those attempts take varies accordingly.</span></span> <span data-ttu-id="6940b-152">Esto permite que el tiempo de retransmisión se adapte dinámicamente a las condiciones variantes de la red.</span><span class="sxs-lookup"><span data-stu-id="6940b-152">This allows the retransmission time to dynamically adapt to varying network conditions.</span></span>|  
|<span data-ttu-id="6940b-153">maxTransferWindowSize</span><span class="sxs-lookup"><span data-stu-id="6940b-153">maxTransferWindowSize</span></span>|<span data-ttu-id="6940b-154">Un entero que especifica el tamaño máximo del búfer.</span><span class="sxs-lookup"><span data-stu-id="6940b-154">An integer that specifies the maximum size of the buffer.</span></span> <span data-ttu-id="6940b-155">Los valores válidos están comprendidos entre 1 y 4096, ambos incluidos.</span><span class="sxs-lookup"><span data-stu-id="6940b-155">Valid values are from 1 to 4096 inclusive.</span></span><br /><br /> <span data-ttu-id="6940b-156">En lo que respecta al cliente, este atributo define el tamaño máximo del búfer utilizado por un canal fiable para contener mensajes no confirmados todavía por el receptor.</span><span class="sxs-lookup"><span data-stu-id="6940b-156">On the client, this attribute defines the maximum size of the buffer used by a reliable channel to hold messages not yet acknowledged by the receiver.</span></span> <span data-ttu-id="6940b-157">La unidad de la cuota es un mensaje.</span><span class="sxs-lookup"><span data-stu-id="6940b-157">The unit of the quota is a message.</span></span> <span data-ttu-id="6940b-158">Si el búfer está lleno, las operaciones de ENVÍO siguientes se bloquean.</span><span class="sxs-lookup"><span data-stu-id="6940b-158">If the buffer is full, further SEND operations are blocked.</span></span><br /><br /> <span data-ttu-id="6940b-159">En lo que respecta al receptor, este atributo define el tamaño máximo del búfer utilizado por el canal para almacenar mensajes entrantes no distribuidos en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6940b-159">On the receiver, this attribute defines the maximum size of the buffer used by the channel to store incoming messages not yet dispatched to the application.</span></span> <span data-ttu-id="6940b-160">Si el búfer está lleno, los mensajes siguientes son quitados por el receptor y requieren la retransmisión del cliente.</span><span class="sxs-lookup"><span data-stu-id="6940b-160">If the buffer is full, further messages are silently dropped by the receiver and require retransmission by the client.</span></span>|  
|<span data-ttu-id="6940b-161">ordered</span><span class="sxs-lookup"><span data-stu-id="6940b-161">ordered</span></span>|<span data-ttu-id="6940b-162">Un booleano que especifica si se garantiza que los mensajes lleguen en el orden en el que fueron enviados.</span><span class="sxs-lookup"><span data-stu-id="6940b-162">A Boolean that specifies whether messages are guaranteed to arrive in the order they were sent.</span></span> <span data-ttu-id="6940b-163">Si este valor es `false`, los mensajes pueden llegar desordenados.</span><span class="sxs-lookup"><span data-stu-id="6940b-163">If this setting is `false`, messages can arrive out of order.</span></span> <span data-ttu-id="6940b-164">De manera predeterminada, es `true`.</span><span class="sxs-lookup"><span data-stu-id="6940b-164">The default is `true`.</span></span>|  
|<span data-ttu-id="6940b-165">reliableMessagingVersion</span><span class="sxs-lookup"><span data-stu-id="6940b-165">reliableMessagingVersion</span></span>|<span data-ttu-id="6940b-166">Un valor válido de <xref:System.ServiceModel.ReliableMessagingVersion> que especifica la versión WS-ReliableMessaging que se va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="6940b-166">A valid value from <xref:System.ServiceModel.ReliableMessagingVersion> that specifies the WS-ReliableMessaging version to be used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6940b-167">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="6940b-167">Child Elements</span></span>  
 <span data-ttu-id="6940b-168">Ninguna</span><span class="sxs-lookup"><span data-stu-id="6940b-168">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6940b-169">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="6940b-169">Parent Elements</span></span>  
  
|<span data-ttu-id="6940b-170">Elemento</span><span class="sxs-lookup"><span data-stu-id="6940b-170">Element</span></span>|<span data-ttu-id="6940b-171">Descripción</span><span class="sxs-lookup"><span data-stu-id="6940b-171">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6940b-172">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="6940b-172">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="6940b-173">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="6940b-173">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6940b-174">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6940b-174">Remarks</span></span>  
 <span data-ttu-id="6940b-175">Las sesiones fiables proporcionan las características para la mensajería y las sesiones de confianza.</span><span class="sxs-lookup"><span data-stu-id="6940b-175">Reliable sessions provide features for reliable messaging and sessions.</span></span> <span data-ttu-id="6940b-176">La mensajería de confianza reintenta la comunicación en caso de error y permite especificar garantías de entrega, como la llegada en orden de los mensajes.</span><span class="sxs-lookup"><span data-stu-id="6940b-176">Reliable messaging retries communication on failure and allows delivery assurances such as in-order arrival of messages to be specified.</span></span> <span data-ttu-id="6940b-177">Las sesiones mantienen el estado de los clientes entre llamadas.</span><span class="sxs-lookup"><span data-stu-id="6940b-177">Sessions maintain state for clients between calls.</span></span> <span data-ttu-id="6940b-178">Este elemento también proporciona, de manera opcional, la entrega ordenada de mensajes.</span><span class="sxs-lookup"><span data-stu-id="6940b-178">This element also optionally provides ordered message delivery.</span></span> <span data-ttu-id="6940b-179">Esta sesión implementada puede cruzar SOAP y los intermediarios de transporte.</span><span class="sxs-lookup"><span data-stu-id="6940b-179">This implemented session can cross SOAP and transport intermediaries.</span></span>  
  
 <span data-ttu-id="6940b-180">Cada elemento de enlace representa un paso del procesamiento al enviar y recibir mensajes.</span><span class="sxs-lookup"><span data-stu-id="6940b-180">Each binding element represents a processing step when sending or receiving messages.</span></span> <span data-ttu-id="6940b-181">En tiempo de ejecución, los elementos de enlace crean los generadores de canales y las escuchas que son necesarios para compilar pilas de canal entrantes y salientes necesarias para enviar y recibir los mensajes.</span><span class="sxs-lookup"><span data-stu-id="6940b-181">At runtime, binding elements create the channel factories and listeners that are necessary to build outgoing and incoming channel stacks required to send and receive messages.</span></span> <span data-ttu-id="6940b-182">`reliableSession` proporciona un nivel opcional en la pila que puede establecer una sesión confiable entre los extremos y configurar el comportamiento de esta sesión.</span><span class="sxs-lookup"><span data-stu-id="6940b-182">The `reliableSession` provides an optional layer in the stack that can establish a reliable session between endpoints and configure the behavior of this session.</span></span>  
  
 <span data-ttu-id="6940b-183">Para obtener más información, consulte [sesiones confiables](../../../../../docs/framework/wcf/feature-details/reliable-sessions.md).</span><span class="sxs-lookup"><span data-stu-id="6940b-183">For more information, see [Reliable Sessions](../../../../../docs/framework/wcf/feature-details/reliable-sessions.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6940b-184">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6940b-184">Example</span></span>  
 <span data-ttu-id="6940b-185">El ejemplo siguiente muestra cómo configurar un enlace personalizado con varios elementos de codificación de mensajes y transporte, habilitando sobre todo sesiones fiables, que mantienen el estado del cliente y especifican las garantías de la entrega en orden.</span><span class="sxs-lookup"><span data-stu-id="6940b-185">The following example demonstrates how to configure a custom binding with various transport and message encoding elements, especially enabling reliable sessions, which maintains client state and specifies in-order delivery assurances.</span></span> <span data-ttu-id="6940b-186">Esta característica se configura en los archivos de configuración de la aplicación para el cliente y el servicio.</span><span class="sxs-lookup"><span data-stu-id="6940b-186">This feature is configured in the application configuration files for the client and service.</span></span> <span data-ttu-id="6940b-187">El ejemplo muestra la configuración de servicio.</span><span class="sxs-lookup"><span data-stu-id="6940b-187">The example show the service configuration.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service   
          name="Microsoft.ServiceModel.Samples.CalculatorService"  
          behaviorConfiguration="CalculatorServiceBehavior">  
        <!-- This endpoint is exposed at the base address provided by host: http://localhost/servicemodelsamples/service.svc  -->  
        <!-- specify customBinding binding and a binding configuration to use -->  
        <endpoint address=""  
                  binding="customBinding"  
                  bindingConfiguration="Binding1"   
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />  
        <!-- The mex endpoint is exposed at http://localhost/servicemodelsamples/service.svc/mex -->  
        <endpoint address="mex"  
                  binding="mexHttpBinding"  
                  contract="IMetadataExchange" />  
      </service>  
    </services>  
  
    <!-- custom binding configuration - configures HTTP transport, reliable sessions -->  
    <bindings>  
      <customBinding>  
        <binding name="Binding1">  
          <reliableSession />  
          <security authenticationMode="SecureConversation"  
                     requireSecurityContextCancellation="true">  
          </security>  
          <compositeDuplex />  
          <oneWay />  
          <textMessageEncoding messageVersion="Soap12WSAddressing10" writeEncoding="utf-8" />  
          <httpTransport authenticationScheme="Anonymous" bypassProxyOnLocal="false"  
                        hostNameComparisonMode="StrongWildcard"   
                        proxyAuthenticationScheme="Anonymous" realm=""   
                        useDefaultWebProxy="true" />  
        </binding>  
      </customBinding>  
    </bindings>  
  
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="CalculatorServiceBehavior">  
          <serviceMetadata httpGetEnabled="True"/>  
          <serviceDebug includeExceptionDetailInFaults="False" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6940b-188">Vea también</span><span class="sxs-lookup"><span data-stu-id="6940b-188">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ReliableSessionElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>  
 [<span data-ttu-id="6940b-189">Sesiones confiables</span><span class="sxs-lookup"><span data-stu-id="6940b-189">Reliable Sessions</span></span>](../../../../../docs/framework/wcf/feature-details/reliable-sessions.md)  
 [<span data-ttu-id="6940b-190">Enlaces</span><span class="sxs-lookup"><span data-stu-id="6940b-190">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="6940b-191">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="6940b-191">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="6940b-192">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="6940b-192">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="6940b-193">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="6940b-193">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
