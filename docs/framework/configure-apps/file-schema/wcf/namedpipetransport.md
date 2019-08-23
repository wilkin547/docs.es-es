---
title: <namedPipeTransport>
ms.date: 03/30/2017
ms.assetid: 9fc3f42f-43e2-4ab1-8bc7-3c95a9220df1
ms.openlocfilehash: 473d0fbd543a056ec2b152f43a76a0417a18016f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933201"
---
# <a name="namedpipetransport"></a><span data-ttu-id="cfe82-101">\<namedPipeTransport></span><span class="sxs-lookup"><span data-stu-id="cfe82-101">\<namedPipeTransport></span></span>
<span data-ttu-id="cfe82-102">Define un transporte que hace que un canal transfiera mensajes mediante las canalizaciones con nombre cuando está incluido en un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="cfe82-102">Defines a transport that causes a channel to transfer messages using named pipes when it is included in a custom binding.</span></span>  
  
<span data-ttu-id="cfe82-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="cfe82-103">\<system.serviceModel></span></span>  
<span data-ttu-id="cfe82-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="cfe82-104">\<bindings></span></span>  
<span data-ttu-id="cfe82-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="cfe82-105">\<customBinding></span></span>  
<span data-ttu-id="cfe82-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="cfe82-106">\<binding></span></span>  
<span data-ttu-id="cfe82-107">\<namePipeTransport></span><span class="sxs-lookup"><span data-stu-id="cfe82-107">\<namePipeTransport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfe82-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cfe82-108">Syntax</span></span>  
  
```xml  
<namedPipeTransport channelInitializationTimeout="TimeSpan"
                    connectionBufferSize="Integer"
                    hostNameComparisonMode="StrongWildcard/Exact/WeakWildcard"
                    manualAddressing="Boolean"
                    maxBufferPoolSize="Integer"
                    maxBufferSize="Integer"
                    maxOutputDelay="TimeSpan"
                    maxPendingAccepts="Integer"
                    maxPendingConnections="Integer"
                    maxReceivedMessageSize="Integer"
                    transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse">
  <connectionPoolSettings groupName="String"
                          idleTimeout="TimeSpan"
                          maxOutboundConnectionsPerEndpoint="Integer" />
</namedPipeTransport>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cfe82-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="cfe82-109">Attributes and Elements</span></span>  
<span data-ttu-id="cfe82-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="cfe82-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cfe82-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="cfe82-111">Attributes</span></span>  
<span data-ttu-id="cfe82-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="cfe82-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="cfe82-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="cfe82-113">Child Elements</span></span>  
  
|<span data-ttu-id="cfe82-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="cfe82-114">Element</span></span>|<span data-ttu-id="cfe82-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="cfe82-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cfe82-116">ChannelInitializationTimeout</span><span class="sxs-lookup"><span data-stu-id="cfe82-116">ChannelInitializationTimeout</span></span>|<span data-ttu-id="cfe82-117">Obtiene o establece un <xref:System.TimeSpan> valor de que determina el tiempo máximo que un canal puede estar en el estado de inicialización antes de que se desconecte.</span><span class="sxs-lookup"><span data-stu-id="cfe82-117">Gets or sets a <xref:System.TimeSpan> that determines the maximum time a channel can be in the initialization status before being disconnected.</span></span>|  
|<span data-ttu-id="cfe82-118">ConnectionBufferSize</span><span class="sxs-lookup"><span data-stu-id="cfe82-118">ConnectionBufferSize</span></span>|<span data-ttu-id="cfe82-119">Obtiene o establece el tamaño del búfer usado para transmitir un bloque del mensaje serializado en la conexión del cliente o servicio.</span><span class="sxs-lookup"><span data-stu-id="cfe82-119">Gets or sets the size of the buffer used to transmit a chunk of the serialized message on the wire from the client or service.</span></span>|  
|<span data-ttu-id="cfe82-120">hostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="cfe82-120">hostNameComparisonMode</span></span>|<span data-ttu-id="cfe82-121">Obtiene o establece un valor que indica si el nombre del host se usa para alcanzar el servicio al coincidir con el URI.</span><span class="sxs-lookup"><span data-stu-id="cfe82-121">Gets or sets a value that indicates whether the hostname is used to reach the service when matching on the URI.</span></span>|  
|<span data-ttu-id="cfe82-122">manualAddressing</span><span class="sxs-lookup"><span data-stu-id="cfe82-122">manualAddressing</span></span>|<span data-ttu-id="cfe82-123">Obtiene o establece un valor que indica si se requiere la dirección manual del mensaje.</span><span class="sxs-lookup"><span data-stu-id="cfe82-123">Gets or sets a value that indicates whether manual addressing of the message is required.</span></span>|  
|<span data-ttu-id="cfe82-124">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="cfe82-124">maxBufferPoolSize</span></span>|<span data-ttu-id="cfe82-125">Obtiene o establece el tamaño máximo, en bytes, de cualquier grupo de búferes utilizado por el transporte.</span><span class="sxs-lookup"><span data-stu-id="cfe82-125">Gets or sets the maximum size, in bytes, of any buffer pools used by the transport.</span></span>|  
|<span data-ttu-id="cfe82-126">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="cfe82-126">maxBufferSize</span></span>|<span data-ttu-id="cfe82-127">Obtiene o establece el tamaño máximo del búfer que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="cfe82-127">Gets or sets the maximum size of the buffer to use.</span></span> <span data-ttu-id="cfe82-128">Para mensajes transmitidos por secuencias, este valor debería ser por lo menos el tamaño máximo posible de los encabezados de mensaje, que se leen en modo almacenado en búfer.</span><span class="sxs-lookup"><span data-stu-id="cfe82-128">For streamed messages, this value should be at least the maximum possible size of the message headers, which are read in buffered mode.</span></span>|  
|<span data-ttu-id="cfe82-129">maxOutputDelay</span><span class="sxs-lookup"><span data-stu-id="cfe82-129">maxOutputDelay</span></span>|<span data-ttu-id="cfe82-130">Obtiene o establece el intervalo máximo de tiempo que un bloque de mensaje o un mensaje completo pueden estar almacenados en búfer en memoria antes de que se envíen.</span><span class="sxs-lookup"><span data-stu-id="cfe82-130">Gets or sets the maximum interval of time that a chunk of a message or a full message can remain buffered in memory before being sent out.</span></span>|  
|<span data-ttu-id="cfe82-131">maxPendingAccepts</span><span class="sxs-lookup"><span data-stu-id="cfe82-131">maxPendingAccepts</span></span>|<span data-ttu-id="cfe82-132">Obtiene o establece el número máximo de canales que un servicio puede tener en espera en un agente de escucha para procesar las conexiones entrantes al servicio.</span><span class="sxs-lookup"><span data-stu-id="cfe82-132">Gets or sets the maximum number of channels a service can have waiting on a listener for processing incoming connections to the service.</span></span>|  
|<span data-ttu-id="cfe82-133">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="cfe82-133">maxPendingConnections</span></span>|<span data-ttu-id="cfe82-134">Obtiene o establece el número máximo de conexiones pendientes de distribución en el servicio.</span><span class="sxs-lookup"><span data-stu-id="cfe82-134">Gets or sets the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="cfe82-135">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="cfe82-135">maxReceivedMessageSize</span></span>|<span data-ttu-id="cfe82-136">Obtiene y establece el tamaño máximo permitido del mensaje, en bytes, que se puede recibir.</span><span class="sxs-lookup"><span data-stu-id="cfe82-136">Gets and sets the maximum allowable message size, in bytes, that can be received.</span></span>|  
|<span data-ttu-id="cfe82-137">transferMode</span><span class="sxs-lookup"><span data-stu-id="cfe82-137">transferMode</span></span>|<span data-ttu-id="cfe82-138">Obtiene o establece un valor que indica si los mensajes están almacenados en búfer o se transmiten por secuencias mediante el transporte orientado a la conexión.</span><span class="sxs-lookup"><span data-stu-id="cfe82-138">Gets or sets a value that indicates whether the messages are buffered or streamed with the connection-oriented transport.</span></span>|  
|[<span data-ttu-id="cfe82-139">\<connectionPoolSettings > \<namedPipeTransport ></span><span class="sxs-lookup"><span data-stu-id="cfe82-139">\<connectionPoolSettings> of \<namedPipeTransport></span></span>](connectionpoolsettings.md)|<span data-ttu-id="cfe82-140">Especifica valores adicionales del grupo de conexiones para un enlace de canalización con nombre.</span><span class="sxs-lookup"><span data-stu-id="cfe82-140">Specifies additional connection pool settings for a Named Pipe binding.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cfe82-141">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="cfe82-141">Parent Elements</span></span>  
  
|<span data-ttu-id="cfe82-142">Elemento</span><span class="sxs-lookup"><span data-stu-id="cfe82-142">Element</span></span>|<span data-ttu-id="cfe82-143">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="cfe82-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cfe82-144">\<binding></span><span class="sxs-lookup"><span data-stu-id="cfe82-144">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="cfe82-145">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="cfe82-145">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cfe82-146">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cfe82-146">Remarks</span></span>  
<span data-ttu-id="cfe82-147">Este transporte utiliza los URI del formulario "net.pipe://hostname/path."</span><span class="sxs-lookup"><span data-stu-id="cfe82-147">This transport uses URIs of the form "net.pipe://hostname/path".</span></span> <span data-ttu-id="cfe82-148">Otros componentes URI son opcionales.</span><span class="sxs-lookup"><span data-stu-id="cfe82-148">Other URI components are optional.</span></span>  
  
<span data-ttu-id="cfe82-149">El elemento `namedPipeTransport` es el punto inicial para crear un enlace personalizado que implementa el protocolo de transporte de canalizaciones con nombre.</span><span class="sxs-lookup"><span data-stu-id="cfe82-149">The `namedPipeTransport` element is the starting point for creating a custom binding that implements the named pipes transport protocol.</span></span> <span data-ttu-id="cfe82-150">Este transporte se utiliza para la comunicación entre WCF y Windows Communication Foundation (WCF) en el equipo.</span><span class="sxs-lookup"><span data-stu-id="cfe82-150">This transport is used for on-machine Windows Communication Foundation (WCF)-to-WCF communication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfe82-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="cfe82-151">See also</span></span>

- <xref:System.ServiceModel.Configuration.NamedPipeTransportElement>
- <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="cfe82-152">Transportes</span><span class="sxs-lookup"><span data-stu-id="cfe82-152">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="cfe82-153">Elección del transporte</span><span class="sxs-lookup"><span data-stu-id="cfe82-153">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="cfe82-154">Enlaces</span><span class="sxs-lookup"><span data-stu-id="cfe82-154">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="cfe82-155">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="cfe82-155">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="cfe82-156">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="cfe82-156">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="cfe82-157">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="cfe82-157">\<customBinding></span></span>](custombinding.md)
