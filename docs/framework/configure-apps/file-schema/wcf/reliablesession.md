---
description: 'Más información acerca de: <reliableSession>'
title: <reliableSession>
ms.date: 03/30/2017
ms.assetid: 129b4a59-37f0-4030-b664-03795d257d29
ms.openlocfilehash: 5b5798326be9b376ece4e590f068f5b5e71bd878
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99683416"
---
# \<reliableSession>

<span data-ttu-id="d212a-102">Define el valor para los mensajes de confianza de WS.</span><span class="sxs-lookup"><span data-stu-id="d212a-102">Defines setting for WS-Reliable Messaging.</span></span> <span data-ttu-id="d212a-103">Cuando este elemento se agrega a un enlace personalizado, el canal resultante puede admitir las convicciones de la entrega exactamente una vez.</span><span class="sxs-lookup"><span data-stu-id="d212a-103">When this element is added to a custom binding, the resulting channel can support exactly-once delivery assurances.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<reliableSession>**  
  
## <a name="syntax"></a><span data-ttu-id="d212a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d212a-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d212a-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d212a-105">Attributes and Elements</span></span>  

 <span data-ttu-id="d212a-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d212a-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d212a-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="d212a-107">Attributes</span></span>  
  
|<span data-ttu-id="d212a-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="d212a-108">Attribute</span></span>|<span data-ttu-id="d212a-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="d212a-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d212a-110">acknowledgementInterval</span><span class="sxs-lookup"><span data-stu-id="d212a-110">acknowledgementInterval</span></span>|<span data-ttu-id="d212a-111"><xref:System.TimeSpan> que contiene el intervalo de tiempo máximo que el canal va a esperar para enviar un reconocimiento para los mensajes recibidos hasta ese punto.</span><span class="sxs-lookup"><span data-stu-id="d212a-111">A <xref:System.TimeSpan> that contains the maximum time interval the channel is going to wait to send an acknowledgment for messages received up to that point.</span></span> <span data-ttu-id="d212a-112">El valor predeterminado es 00:00:02.</span><span class="sxs-lookup"><span data-stu-id="d212a-112">The default is 00:00:0.2.</span></span>|  
|<span data-ttu-id="d212a-113">flowControlEnabled</span><span class="sxs-lookup"><span data-stu-id="d212a-113">flowControlEnabled</span></span>|<span data-ttu-id="d212a-114">Un valor booleano que indica si se activa el control de flujo avanzado, una implementación específica de Microsoft de control de flujo para la mensajería de confianza de WS.</span><span class="sxs-lookup"><span data-stu-id="d212a-114">A Boolean value that indicates whether advanced flow control, a Microsoft-specific implementation of flow control for WS-Reliable messaging, is activated.</span></span> <span data-ttu-id="d212a-115">De manera predeterminada, es `true`.</span><span class="sxs-lookup"><span data-stu-id="d212a-115">The default is `true`.</span></span>|  
|<span data-ttu-id="d212a-116">inactivityTimeOut</span><span class="sxs-lookup"><span data-stu-id="d212a-116">inactivityTimeout</span></span>|<span data-ttu-id="d212a-117">Un <xref:System.TimeSpan> que especifica el tiempo máximo durante el cual el canal va a permitir a la otra parte de la comunicación no enviar ningún mensaje sin que se produzca un error.</span><span class="sxs-lookup"><span data-stu-id="d212a-117">A <xref:System.TimeSpan> that specifies the maximum duration that the channel is going to allow the other communication party not to send any messages, before faulting the channel.</span></span> <span data-ttu-id="d212a-118">El valor predeterminado es 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="d212a-118">The default is 00:10:00.</span></span><br /><br /> <span data-ttu-id="d212a-119">La actividad en un canal se define como la recepción de una aplicación o mensajes de infraestructura.</span><span class="sxs-lookup"><span data-stu-id="d212a-119">Activity on a channel is defined as receiving an application or infrastructure messages.</span></span> <span data-ttu-id="d212a-120">Esta propiedad controla el tiempo máximo para mantener activa una sesión inactiva.</span><span class="sxs-lookup"><span data-stu-id="d212a-120">This property controls the maximum amount of time to keep an inactive session alive.</span></span> <span data-ttu-id="d212a-121">Si transcurre más tiempo sin actividad, la sesión es finalizada por la infraestructura y los errores del canal.</span><span class="sxs-lookup"><span data-stu-id="d212a-121">If longer time passes with no activity, the session is aborted by the infrastructure and the channel faults.</span></span> <span data-ttu-id="d212a-122">**Nota:**  No es necesario que la aplicación envíe mensajes periódicamente para mantener la conexión activa.</span><span class="sxs-lookup"><span data-stu-id="d212a-122">**Note:**  It is not necessary for the application to periodically send messages to keep the connection alive.</span></span>|  
|<span data-ttu-id="d212a-123">maxPendingChannels</span><span class="sxs-lookup"><span data-stu-id="d212a-123">maxPendingChannels</span></span>|<span data-ttu-id="d212a-124">Un entero que especifica el número máximo de canales que pueden esperar en el agente de escucha para ser aceptados.</span><span class="sxs-lookup"><span data-stu-id="d212a-124">An integer that specifies the maximum number of channels that can wait on the listener to be accepted.</span></span> <span data-ttu-id="d212a-125">Este valor debe estar comprendido entre 1 y 16384, ambos inclusive.</span><span class="sxs-lookup"><span data-stu-id="d212a-125">This value should be between 1 to 16384 inclusive.</span></span> <span data-ttu-id="d212a-126">El valor predeterminado es 4.</span><span class="sxs-lookup"><span data-stu-id="d212a-126">The default is 4.</span></span><br /><br /> <span data-ttu-id="d212a-127">Los canales están pendientes cuando esperan a ser aceptados.</span><span class="sxs-lookup"><span data-stu-id="d212a-127">Channels are pending when they are waiting to be accepted.</span></span> <span data-ttu-id="d212a-128">Una vez alcanzado ese límite, no se crea ningún canal.</span><span class="sxs-lookup"><span data-stu-id="d212a-128">Once that limit is reached, no channels are created.</span></span> <span data-ttu-id="d212a-129">Más bien, se colocan en modo pendiente hasta que este número baje (al aceptar los canales pendientes).</span><span class="sxs-lookup"><span data-stu-id="d212a-129">Rather, they are put in pending mode until this number goes down (by accepting pending channels).</span></span> <span data-ttu-id="d212a-130">Éste es un límite por generador.</span><span class="sxs-lookup"><span data-stu-id="d212a-130">This is a per-factory limit.</span></span><br /><br /> <span data-ttu-id="d212a-131">Cuando se alcanza el umbral y una aplicación remota intenta establecer una nueva sesión fiable, se deniega la solicitud y falla la operación abierta que pidió confirmación.</span><span class="sxs-lookup"><span data-stu-id="d212a-131">When the threshold is reached and a remote application tries to establish a new reliable session, the request is denied and the open operation that prompted this faults.</span></span> <span data-ttu-id="d212a-132">Este límite no se aplica al número de canales pendientes de la salida.</span><span class="sxs-lookup"><span data-stu-id="d212a-132">This limit does not apply to the number of pending outgoing channels.</span></span>|  
|<span data-ttu-id="d212a-133">maxRetryCount</span><span class="sxs-lookup"><span data-stu-id="d212a-133">maxRetryCount</span></span>|<span data-ttu-id="d212a-134">Un entero que especifica el número máximo de horas que un canal fiable intenta retransmitir un mensaje para el que no ha recibido reconocimiento, yendo a Enviar en su canal subyacente.</span><span class="sxs-lookup"><span data-stu-id="d212a-134">An integer that specifies the maximum number of times a reliable channel attempts to retransmit a message it has not received an acknowledgment for, by calling Send on its underlying channel.</span></span><br /><br /> <span data-ttu-id="d212a-135">Este valor debería ser mayor que cero.</span><span class="sxs-lookup"><span data-stu-id="d212a-135">This value should be greater than zero.</span></span> <span data-ttu-id="d212a-136">El valor predeterminado es 8.</span><span class="sxs-lookup"><span data-stu-id="d212a-136">The default is 8.</span></span><br /><br /> <span data-ttu-id="d212a-137">Este valor debería ser un entero mayor que cero.</span><span class="sxs-lookup"><span data-stu-id="d212a-137">This value should be an integer greater than zero.</span></span> <span data-ttu-id="d212a-138">Si un reconocimiento no se recibe después de la última retransmisión, el canal falla.</span><span class="sxs-lookup"><span data-stu-id="d212a-138">If an acknowledgment is not received after the last retransmission, the channel faults.</span></span><br /><br /> <span data-ttu-id="d212a-139">Se considera que un mensaje es transferido si el destinatario ha confirmado su entrega.</span><span class="sxs-lookup"><span data-stu-id="d212a-139">A message is considered to be transferred if its delivery at the recipient has been acknowledged by the recipient.</span></span><br /><br /> <span data-ttu-id="d212a-140">Si no se ha recibido reconocimiento tras un cierto tiempo de un mensaje que se ha transmitido, la infraestructura retransmite automáticamente el mensaje.</span><span class="sxs-lookup"><span data-stu-id="d212a-140">If an acknowledgment has not been received within a certain amount of time for a message that has been transmitted, the infrastructure automatically retransmits the message.</span></span> <span data-ttu-id="d212a-141">La infraestructura intenta reenviar el mensaje el máximo número de veces especificado por esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="d212a-141">The infrastructure tries to resend the message for at most the number of times specified by this property.</span></span> <span data-ttu-id="d212a-142">Si un reconocimiento no se recibe después de la última retransmisión, el canal falla.</span><span class="sxs-lookup"><span data-stu-id="d212a-142">If an acknowledgment is not received after the last retransmission, the channel faults.</span></span><br /><br /> <span data-ttu-id="d212a-143">La infraestructura utiliza un algoritmo de espera exponencial para determinar cuándo retransmitir, en función del tiempo medio calculado de ida y vuelta.</span><span class="sxs-lookup"><span data-stu-id="d212a-143">The infrastructure uses an exponential back-off algorithm to determine when to retransmit, based on a computed average round-trip time.</span></span> <span data-ttu-id="d212a-144">El tiempo empieza inicialmente 1 segundo antes de la retransmisión y duplica el retraso en cada intento, lo que da como resultado aproximadamente 8,5 minutos que pasan entre el primer intento de la transmisión y el último intento de la retransmisión.</span><span class="sxs-lookup"><span data-stu-id="d212a-144">The time initially starts at 1 second before retransmission and doubling the delay with every attempt, which results in approximately 8.5 minutes passing between the first transmission attempt and the last retransmission attempt.</span></span> <span data-ttu-id="d212a-145">El tiempo del primer intento de retransmisión se ajusta al cálculo del tiempo de ida y vuelta y varía según el período de tiempo adicional que resulta del número de intentos que se necesitan.</span><span class="sxs-lookup"><span data-stu-id="d212a-145">The time for the first retransmission attempt is adjusted according to the calculated round-trip time and the resulting stretch of time that those attempts take varies accordingly.</span></span> <span data-ttu-id="d212a-146">Esto permite que el tiempo de retransmisión se adapte dinámicamente a las condiciones variantes de la red.</span><span class="sxs-lookup"><span data-stu-id="d212a-146">This allows the retransmission time to dynamically adapt to varying network conditions.</span></span>|  
|<span data-ttu-id="d212a-147">maxTransferWindowSize</span><span class="sxs-lookup"><span data-stu-id="d212a-147">maxTransferWindowSize</span></span>|<span data-ttu-id="d212a-148">Un entero que especifica el tamaño máximo del búfer.</span><span class="sxs-lookup"><span data-stu-id="d212a-148">An integer that specifies the maximum size of the buffer.</span></span> <span data-ttu-id="d212a-149">Los valores válidos están comprendidos entre 1 y 4096, ambos incluidos.</span><span class="sxs-lookup"><span data-stu-id="d212a-149">Valid values are from 1 to 4096 inclusive.</span></span><br /><br /> <span data-ttu-id="d212a-150">En lo que respecta al cliente, este atributo define el tamaño máximo del búfer utilizado por un canal fiable para contener mensajes no confirmados todavía por el receptor.</span><span class="sxs-lookup"><span data-stu-id="d212a-150">On the client, this attribute defines the maximum size of the buffer used by a reliable channel to hold messages not yet acknowledged by the receiver.</span></span> <span data-ttu-id="d212a-151">La unidad de la cuota es un mensaje.</span><span class="sxs-lookup"><span data-stu-id="d212a-151">The unit of the quota is a message.</span></span> <span data-ttu-id="d212a-152">Si el búfer está lleno, las operaciones de ENVÍO siguientes se bloquean.</span><span class="sxs-lookup"><span data-stu-id="d212a-152">If the buffer is full, further SEND operations are blocked.</span></span><br /><br /> <span data-ttu-id="d212a-153">En lo que respecta al receptor, este atributo define el tamaño máximo del búfer utilizado por el canal para almacenar mensajes entrantes no distribuidos en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d212a-153">On the receiver, this attribute defines the maximum size of the buffer used by the channel to store incoming messages not yet dispatched to the application.</span></span> <span data-ttu-id="d212a-154">Si el búfer está lleno, los mensajes siguientes son quitados por el receptor y requieren la retransmisión del cliente.</span><span class="sxs-lookup"><span data-stu-id="d212a-154">If the buffer is full, further messages are silently dropped by the receiver and require retransmission by the client.</span></span>|  
|<span data-ttu-id="d212a-155">ordered</span><span class="sxs-lookup"><span data-stu-id="d212a-155">ordered</span></span>|<span data-ttu-id="d212a-156">Un booleano que especifica si se garantiza que los mensajes lleguen en el orden en el que fueron enviados.</span><span class="sxs-lookup"><span data-stu-id="d212a-156">A Boolean that specifies whether messages are guaranteed to arrive in the order they were sent.</span></span> <span data-ttu-id="d212a-157">Si este valor es `false`, los mensajes pueden llegar desordenados.</span><span class="sxs-lookup"><span data-stu-id="d212a-157">If this setting is `false`, messages can arrive out of order.</span></span> <span data-ttu-id="d212a-158">De manera predeterminada, es `true`.</span><span class="sxs-lookup"><span data-stu-id="d212a-158">The default is `true`.</span></span>|  
|<span data-ttu-id="d212a-159">reliableMessagingVersion</span><span class="sxs-lookup"><span data-stu-id="d212a-159">reliableMessagingVersion</span></span>|<span data-ttu-id="d212a-160">Un valor válido de <xref:System.ServiceModel.ReliableMessagingVersion> que especifica la versión WS-ReliableMessaging que se va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="d212a-160">A valid value from <xref:System.ServiceModel.ReliableMessagingVersion> that specifies the WS-ReliableMessaging version to be used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d212a-161">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d212a-161">Child Elements</span></span>  

 <span data-ttu-id="d212a-162">None</span><span class="sxs-lookup"><span data-stu-id="d212a-162">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d212a-163">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d212a-163">Parent Elements</span></span>  
  
|<span data-ttu-id="d212a-164">Elemento</span><span class="sxs-lookup"><span data-stu-id="d212a-164">Element</span></span>|<span data-ttu-id="d212a-165">Descripción</span><span class="sxs-lookup"><span data-stu-id="d212a-165">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="d212a-166">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="d212a-166">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d212a-167">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d212a-167">Remarks</span></span>  

 <span data-ttu-id="d212a-168">Las sesiones fiables proporcionan las características para la mensajería y las sesiones de confianza.</span><span class="sxs-lookup"><span data-stu-id="d212a-168">Reliable sessions provide features for reliable messaging and sessions.</span></span> <span data-ttu-id="d212a-169">La mensajería de confianza reintenta la comunicación en caso de error y permite especificar garantías de entrega, como la llegada en orden de los mensajes.</span><span class="sxs-lookup"><span data-stu-id="d212a-169">Reliable messaging retries communication on failure and allows delivery assurances such as in-order arrival of messages to be specified.</span></span> <span data-ttu-id="d212a-170">Las sesiones mantienen el estado de los clientes entre llamadas.</span><span class="sxs-lookup"><span data-stu-id="d212a-170">Sessions maintain state for clients between calls.</span></span> <span data-ttu-id="d212a-171">Este elemento también proporciona, de manera opcional, la entrega ordenada de mensajes.</span><span class="sxs-lookup"><span data-stu-id="d212a-171">This element also optionally provides ordered message delivery.</span></span> <span data-ttu-id="d212a-172">Esta sesión implementada puede cruzar SOAP y los intermediarios de transporte.</span><span class="sxs-lookup"><span data-stu-id="d212a-172">This implemented session can cross SOAP and transport intermediaries.</span></span>  
  
 <span data-ttu-id="d212a-173">Cada elemento de enlace representa un paso del procesamiento al enviar y recibir mensajes.</span><span class="sxs-lookup"><span data-stu-id="d212a-173">Each binding element represents a processing step when sending or receiving messages.</span></span> <span data-ttu-id="d212a-174">En tiempo de ejecución, los elementos de enlace crean los generadores de canales y las escuchas que son necesarios para compilar pilas de canal entrantes y salientes necesarias para enviar y recibir los mensajes.</span><span class="sxs-lookup"><span data-stu-id="d212a-174">At runtime, binding elements create the channel factories and listeners that are necessary to build outgoing and incoming channel stacks required to send and receive messages.</span></span> <span data-ttu-id="d212a-175">`reliableSession` proporciona un nivel opcional en la pila que puede establecer una sesión confiable entre los extremos y configurar el comportamiento de esta sesión.</span><span class="sxs-lookup"><span data-stu-id="d212a-175">The `reliableSession` provides an optional layer in the stack that can establish a reliable session between endpoints and configure the behavior of this session.</span></span>  
  
 <span data-ttu-id="d212a-176">Para obtener más información, vea [sesiones confiables](../../../wcf/feature-details/reliable-sessions.md).</span><span class="sxs-lookup"><span data-stu-id="d212a-176">For more information, see [Reliable Sessions](../../../wcf/feature-details/reliable-sessions.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d212a-177">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d212a-177">Example</span></span>  

 <span data-ttu-id="d212a-178">El ejemplo siguiente muestra cómo configurar un enlace personalizado con varios elementos de codificación de mensajes y transporte, habilitando sobre todo sesiones fiables, que mantienen el estado del cliente y especifican las garantías de la entrega en orden.</span><span class="sxs-lookup"><span data-stu-id="d212a-178">The following example demonstrates how to configure a custom binding with various transport and message encoding elements, especially enabling reliable sessions, which maintains client state and specifies in-order delivery assurances.</span></span> <span data-ttu-id="d212a-179">Esta característica se configura en los archivos de configuración de la aplicación para el cliente y el servicio.</span><span class="sxs-lookup"><span data-stu-id="d212a-179">This feature is configured in the application configuration files for the client and service.</span></span> <span data-ttu-id="d212a-180">El ejemplo muestra la configuración de servicio.</span><span class="sxs-lookup"><span data-stu-id="d212a-180">The example show the service configuration.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <system.serviceModel>
    <services>
      <service name="Microsoft.ServiceModel.Samples.CalculatorService"
               behaviorConfiguration="CalculatorServiceBehavior">
        <!-- This endpoint is exposed at the base address provided by host: http://localhost/servicemodelsamples/service.svc -->
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
          <textMessageEncoding messageVersion="Soap12WSAddressing10"
                               writeEncoding="utf-8" />
          <httpTransport authenticationScheme="Anonymous"
                         bypassProxyOnLocal="false"
                         hostNameComparisonMode="StrongWildcard"
                         proxyAuthenticationScheme="Anonymous"
                         realm=""
                         useDefaultWebProxy="true" />
        </binding>
      </customBinding>
    </bindings>
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->
    <behaviors>
      <serviceBehaviors>
        <behavior name="CalculatorServiceBehavior">
          <serviceMetadata httpGetEnabled="True" />
          <serviceDebug includeExceptionDetailInFaults="False" />
        </behavior>
      </serviceBehaviors>
    </behaviors>
  </system.serviceModel>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="d212a-181">Vea también</span><span class="sxs-lookup"><span data-stu-id="d212a-181">See also</span></span>

- <xref:System.ServiceModel.Configuration.ReliableSessionElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>
- [<span data-ttu-id="d212a-182">Sesiones de confianza</span><span class="sxs-lookup"><span data-stu-id="d212a-182">Reliable Sessions</span></span>](../../../wcf/feature-details/reliable-sessions.md)
- [<span data-ttu-id="d212a-183">Enlaces</span><span class="sxs-lookup"><span data-stu-id="d212a-183">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="d212a-184">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="d212a-184">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="d212a-185">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="d212a-185">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
