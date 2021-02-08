---
description: 'Más información acerca de: <tcpTransport>'
title: <tcpTransport>
ms.date: 03/30/2017
ms.assetid: 8fcd18c1-9958-42e7-b442-7903f7bdb563
ms.openlocfilehash: b660443ac58e8ed72d70adb5bf9e9e87b060e3af
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786621"
---
# \<tcpTransport>

<span data-ttu-id="db071-102">Define un transporte del TCP que puede ser utilizado por un canal para la transferencia de mensajes de un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="db071-102">Defines a TCP transport that can be used by a channel to transfers messages for a custom binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<tcpTransport>**  
  
## <a name="syntax"></a><span data-ttu-id="db071-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="db071-103">Syntax</span></span>  
  
```xml  
<tcpTransport channelInitializationTimeout="TimeSpan"
              connectionBufferSize="Integer"
              hostNameComparisonMode="StrongWildcard/Exact/WeakWildcard"
              listenBacklog="Integer"
              manualAddressing="Boolean"
              maxBufferPoolSize="Integer"
              maxBufferSize="Integer"
              maxOutputDelay="TimeSpan"
              maxPendingAccepts="Integer"
              maxPendingConnections="Integer"
              maxReceivedMessageSize="Integer"
              portSharingEnabled="Boolean"
              teredoEnabled="Boolean"
              transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse" >
  <connectionPoolSettings groupName="String"
                          idleTimeout="TimeSpan"
                          leaseTimeout="TimeSpan"
                          maxOutboundConnectionsPerEndpoint="Integer" />
</tcpTransport>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="db071-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="db071-104">Attributes and Elements</span></span>  

 <span data-ttu-id="db071-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="db071-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="db071-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="db071-106">Attributes</span></span>  
  
|<span data-ttu-id="db071-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="db071-107">Attribute</span></span>|<span data-ttu-id="db071-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="db071-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="db071-109">channelInitializationTimeout</span><span class="sxs-lookup"><span data-stu-id="db071-109">channelInitializationTimeout</span></span>|<span data-ttu-id="db071-110">Obtiene o establece el límite de tiempo para inicializar un canal que se va a aceptar.</span><span class="sxs-lookup"><span data-stu-id="db071-110">Gets or sets the time limit for initializing a channel to be accepted.</span></span>  <span data-ttu-id="db071-111">El tiempo máximo que un canal puede estar en el estado de inicialización antes de que se desconecte, en segundos.</span><span class="sxs-lookup"><span data-stu-id="db071-111">The maximum time a channel can be in the initialization state before being disconnected in seconds.</span></span> <span data-ttu-id="db071-112">Esta cuota incluye el tiempo que una conexión TCP puede realizar para autenticarse a sí misma mediante el protocolo de trama de mensajes de .NET.</span><span class="sxs-lookup"><span data-stu-id="db071-112">This quota includes the time a TCP connection can take to authenticate itself using the .NET Message Framing protocol.</span></span> <span data-ttu-id="db071-113">Un cliente debe enviar algunos datos iniciales antes de que el servidor tenga información suficiente para realizar la autenticación.</span><span class="sxs-lookup"><span data-stu-id="db071-113">A client needs to send some initial data before the server has enough information to perform authentication.</span></span> <span data-ttu-id="db071-114">El valor predeterminado es 30 segundos.</span><span class="sxs-lookup"><span data-stu-id="db071-114">The default is 30 seconds.</span></span>|  
|<span data-ttu-id="db071-115">connectionBufferSize</span><span class="sxs-lookup"><span data-stu-id="db071-115">connectionBufferSize</span></span>|<span data-ttu-id="db071-116">Obtiene o establece el tamaño del búfer usado para transmitir un bloque del mensaje serializado en la conexión del cliente o servicio.</span><span class="sxs-lookup"><span data-stu-id="db071-116">Gets or sets the size of the buffer used to transmit a chunk of the serialized message on the wire from the client or service.</span></span>|  
|<span data-ttu-id="db071-117">hostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="db071-117">hostNameComparisonMode</span></span>|<span data-ttu-id="db071-118">Obtiene o establece un valor que indica si el nombre del host se usa para alcanzar el servicio al coincidir con el URI.</span><span class="sxs-lookup"><span data-stu-id="db071-118">Gets or sets a value that indicates whether the hostname is used to reach the service when matching on the URI.</span></span>|  
|<span data-ttu-id="db071-119">listenBacklog</span><span class="sxs-lookup"><span data-stu-id="db071-119">listenBacklog</span></span>|<span data-ttu-id="db071-120">El número máximo de solicitudes de conexión en cola que pueden estar pendientes para un servicio web.</span><span class="sxs-lookup"><span data-stu-id="db071-120">The maximum number of queued connection requests that can be pending for a Web service.</span></span> <span data-ttu-id="db071-121">El atributo `connectionLeaseTimeout` limita el tiempo durante el cual el cliente espera a ser conectado antes de iniciar una excepción de conexión.</span><span class="sxs-lookup"><span data-stu-id="db071-121">The `connectionLeaseTimeout` attribute limits the duration the client will wait to be connected before throwing a connection exception.</span></span> <span data-ttu-id="db071-122">Esta es una propiedad del nivel de socket que controla el número máximo de solicitudes de conexión en cola que pueden estar pendientes para un servicio web.</span><span class="sxs-lookup"><span data-stu-id="db071-122">This is a socket level property which controls the maximum number of queued connection requests that can be pending for a Web service.</span></span> <span data-ttu-id="db071-123">Cuando ListenBacklog es demasiado bajo, WCF dejará de aceptar solicitudes y, por lo tanto, quitará nuevas conexiones hasta que el servidor confirme algunas de las conexiones en cola existentes.</span><span class="sxs-lookup"><span data-stu-id="db071-123">When ListenBacklog is too low, WCF will stop accepting requests and therefore drop new connections until the server acknowledges some of the existing queued connections.</span></span> <span data-ttu-id="db071-124">El valor predeterminado es 16 \* número de procesadores.</span><span class="sxs-lookup"><span data-stu-id="db071-124">The default is 16 \* number of processors.</span></span>|  
|<span data-ttu-id="db071-125">manualAddressing</span><span class="sxs-lookup"><span data-stu-id="db071-125">manualAddressing</span></span>|<span data-ttu-id="db071-126">Obtiene o establece un valor que indica si se requiere la dirección manual del mensaje.</span><span class="sxs-lookup"><span data-stu-id="db071-126">Gets or sets a value that indicates whether manual addressing of the message is required.</span></span>|  
|<span data-ttu-id="db071-127">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="db071-127">maxBufferPoolSize</span></span>|<span data-ttu-id="db071-128">Obtiene o establece el tamaño máximo de cualquier grupo de búferes utilizado por el transporte.</span><span class="sxs-lookup"><span data-stu-id="db071-128">Gets or sets the maximum size of any buffer pools used by the transport.</span></span>|  
|<span data-ttu-id="db071-129">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="db071-129">maxBufferSize</span></span>|<span data-ttu-id="db071-130">Obtiene o establece el tamaño máximo del búfer que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="db071-130">Gets or sets the maximum size of the buffer to use.</span></span> <span data-ttu-id="db071-131">Para mensajes transmitidos por secuencias, este valor debería ser por lo menos el tamaño máximo posible de los encabezados de mensaje, que se leen en modo almacenado en búfer.</span><span class="sxs-lookup"><span data-stu-id="db071-131">For streamed messages, this value should be at least the maximum possible size of the message headers, which are read in buffered mode.</span></span>|  
|<span data-ttu-id="db071-132">maxOutputDelay</span><span class="sxs-lookup"><span data-stu-id="db071-132">maxOutputDelay</span></span>|<span data-ttu-id="db071-133">Obtiene o establece el intervalo máximo de tiempo que un bloque de mensaje o un mensaje completo pueden estar almacenados en búfer en memoria antes de que se envíen.</span><span class="sxs-lookup"><span data-stu-id="db071-133">Gets or sets the maximum interval of time that a chunk of a message or a full message can remain buffered in memory before being sent out.</span></span>|  
|<span data-ttu-id="db071-134">maxPendingAccepts</span><span class="sxs-lookup"><span data-stu-id="db071-134">maxPendingAccepts</span></span>|<span data-ttu-id="db071-135">Obtiene o establece el número máximo de operaciones de aceptación asincrónica pendientes disponibles para procesar conexiones entrantes en el servicio.</span><span class="sxs-lookup"><span data-stu-id="db071-135">Gets or sets the maximum number of pending asynchronous accept operations that are available for processing incoming connections to the service.</span></span>|  
|<span data-ttu-id="db071-136">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="db071-136">maxPendingConnections</span></span>|<span data-ttu-id="db071-137">Obtiene o establece el número máximo de conexiones pendientes de distribución en el servicio.</span><span class="sxs-lookup"><span data-stu-id="db071-137">Gets or sets the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="db071-138">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="db071-138">maxReceivedMessageSize</span></span>|<span data-ttu-id="db071-139">Obtiene y establece el tamaño máximo permitido del mensaje que se puede recibir.</span><span class="sxs-lookup"><span data-stu-id="db071-139">Gets and sets the maximum allowable message size that can be received.</span></span>|  
|<span data-ttu-id="db071-140">portSharingEnabled</span><span class="sxs-lookup"><span data-stu-id="db071-140">portSharingEnabled</span></span>|<span data-ttu-id="db071-141">Un valor booleano que especifica si el uso compartido de puerto TCP está habilitado para esta conexión.</span><span class="sxs-lookup"><span data-stu-id="db071-141">A Boolean value that specifies if TCP port sharing is enabled for this connection.</span></span> <span data-ttu-id="db071-142">Si éste es `false`, cada enlace utilizará su propio puerto exclusivo.</span><span class="sxs-lookup"><span data-stu-id="db071-142">If this is `false`, each binding will use its own exclusive port.</span></span> <span data-ttu-id="db071-143">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="db071-143">The default is `false`.</span></span><br /><br /> <span data-ttu-id="db071-144">Este valor sólo es pertinente a los servicios.</span><span class="sxs-lookup"><span data-stu-id="db071-144">This setting is relevant only to services.</span></span> <span data-ttu-id="db071-145">Los clientes no se ven afectados.</span><span class="sxs-lookup"><span data-stu-id="db071-145">Clients are not affected.</span></span><br /><br /> <span data-ttu-id="db071-146">Para usar esta configuración se necesita que se habilite el servicio de puerto TCP compartido Windows Communication Foundation (WCF), cambiando su tipo de inicio a manual o automático.</span><span class="sxs-lookup"><span data-stu-id="db071-146">Using this setting requires enabling the Windows Communication Foundation (WCF) TCP Port Sharing Service by changing its Startup Type to Manual or Automatic</span></span>|  
|<span data-ttu-id="db071-147">teredoEnabled</span><span class="sxs-lookup"><span data-stu-id="db071-147">teredoEnabled</span></span>|<span data-ttu-id="db071-148">Un valor booleano que especifica si Teredo (una tecnología para direccionar clientes que están detrás de firewalls) está habilitada.</span><span class="sxs-lookup"><span data-stu-id="db071-148">A Boolean value that specifies whether Teredo (a technology for addressing clients that are behind firewalls) is enabled.</span></span> <span data-ttu-id="db071-149">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="db071-149">The default is `false`.</span></span><br /><br /> <span data-ttu-id="db071-150">Esta propiedad habilita Teredo para el socket TCP subyacente.</span><span class="sxs-lookup"><span data-stu-id="db071-150">This property enables Teredo for the underlying TCP socket.</span></span> <span data-ttu-id="db071-151">Para obtener más información, vea [información general sobre Teredo](/previous-versions/windows/it-pro/windows-xp/bb457011(v=technet.10)).</span><span class="sxs-lookup"><span data-stu-id="db071-151">For more information, see [Teredo Overview](/previous-versions/windows/it-pro/windows-xp/bb457011(v=technet.10)).</span></span><br /><br /> <span data-ttu-id="db071-152">Esta propiedad solo es aplicable en Windows XP SP2 y Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="db071-152">This property is applicable only on Windows XP SP2 and Windows Server 2003.</span></span> <span data-ttu-id="db071-153">Windows Vista tiene una opción de configuración de todo el equipo para Teredo, por lo que al ejecutar vista, se omite esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="db071-153">Windows Vista has a machine-wide configuration option for Teredo, so when running Vista, this property is ignored.</span></span> <span data-ttu-id="db071-154">Teredo requiere que los equipos de servicio y del cliente tengan la pila de Microsoft IPv6 instalada y correctamente configurada para el uso de Teredo.</span><span class="sxs-lookup"><span data-stu-id="db071-154">Teredo requires that the client and service machines both have the Microsoft IPv6 stack installed and correctly configured for Teredo usage.</span></span>|  
|<span data-ttu-id="db071-155">transferMode</span><span class="sxs-lookup"><span data-stu-id="db071-155">transferMode</span></span>|<span data-ttu-id="db071-156">Obtiene o establece un valor que indica si los mensajes están almacenados en búfer o se transmiten por secuencias mediante el transporte orientado a la conexión.</span><span class="sxs-lookup"><span data-stu-id="db071-156">Gets or sets a value that indicates whether the messages are buffered or streamed with the connection-oriented transport.</span></span>|  
|<span data-ttu-id="db071-157">connectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="db071-157">connectionPoolSettings</span></span>|<span data-ttu-id="db071-158">Especifica valores adicionales del grupo de conexiones para un enlace de canalización con nombre.</span><span class="sxs-lookup"><span data-stu-id="db071-158">Specifies additional connection pool settings for a Named Pipe binding.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="db071-159">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="db071-159">Child Elements</span></span>  

 <span data-ttu-id="db071-160">None</span><span class="sxs-lookup"><span data-stu-id="db071-160">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="db071-161">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="db071-161">Parent Elements</span></span>  
  
|<span data-ttu-id="db071-162">Elemento</span><span class="sxs-lookup"><span data-stu-id="db071-162">Element</span></span>|<span data-ttu-id="db071-163">Descripción</span><span class="sxs-lookup"><span data-stu-id="db071-163">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="db071-164">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="db071-164">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="db071-165">Observaciones</span><span class="sxs-lookup"><span data-stu-id="db071-165">Remarks</span></span>  

 <span data-ttu-id="db071-166">Este transporte utiliza los URI del formulario "net.tcp://hostname:port/path."</span><span class="sxs-lookup"><span data-stu-id="db071-166">This transport uses URIs of the form "net.tcp://hostname:port/path".</span></span> <span data-ttu-id="db071-167">Otros componentes URI son opcionales.</span><span class="sxs-lookup"><span data-stu-id="db071-167">Other URI components are optional.</span></span>  
  
 <span data-ttu-id="db071-168">El elemento `tcpTransport` es el punto inicial para crear un enlace personalizado que implementa el protocolo de transporte TCP.</span><span class="sxs-lookup"><span data-stu-id="db071-168">The `tcpTransport` element is the starting point for creating a custom binding that implements the TCP transport protocol.</span></span> <span data-ttu-id="db071-169">Este transporte está optimizado para la comunicación de WCF a WCF.</span><span class="sxs-lookup"><span data-stu-id="db071-169">This transport is optimized for WCF-to-WCF communication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db071-170">Vea también</span><span class="sxs-lookup"><span data-stu-id="db071-170">See also</span></span>

- <xref:System.ServiceModel.Configuration.TcpTransportElement>
- <xref:System.ServiceModel.Channels.TcpTransportBindingElement>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="db071-171">Transportes</span><span class="sxs-lookup"><span data-stu-id="db071-171">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="db071-172">Elección del transporte</span><span class="sxs-lookup"><span data-stu-id="db071-172">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="db071-173">Enlaces</span><span class="sxs-lookup"><span data-stu-id="db071-173">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="db071-174">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="db071-174">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="db071-175">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="db071-175">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
