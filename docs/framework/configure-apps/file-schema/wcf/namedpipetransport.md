---
title: '&lt;namedPipeTransport&gt;'
ms.date: 03/30/2017
ms.assetid: 9fc3f42f-43e2-4ab1-8bc7-3c95a9220df1
ms.openlocfilehash: bf9229411143345847247f36de07b5c014d3f259
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149605"
---
# <a name="ltnamedpipetransportgt"></a><span data-ttu-id="2340c-102">&lt;namedPipeTransport&gt;</span><span class="sxs-lookup"><span data-stu-id="2340c-102">&lt;namedPipeTransport&gt;</span></span>
<span data-ttu-id="2340c-103">Define un transporte que hace que un canal transfiera mensajes mediante las canalizaciones con nombre cuando está incluido en un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="2340c-103">Defines a transport that causes a channel to transfer messages using named pipes when it is included in a custom binding.</span></span>  
  
<span data-ttu-id="2340c-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="2340c-104">\<system.serviceModel></span></span>  
<span data-ttu-id="2340c-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="2340c-105">\<bindings></span></span>  
<span data-ttu-id="2340c-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="2340c-106">\<customBinding></span></span>  
<span data-ttu-id="2340c-107">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="2340c-107">\<binding></span></span>  
<span data-ttu-id="2340c-108">\<namePipeTransport ></span><span class="sxs-lookup"><span data-stu-id="2340c-108">\<namePipeTransport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2340c-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2340c-109">Syntax</span></span>  
  
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
                          maxOutboundConnectionsPerEndpopint="Integer" />
</namedPipeTransport>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2340c-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="2340c-110">Attributes and Elements</span></span>  
<span data-ttu-id="2340c-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="2340c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2340c-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="2340c-112">Attributes</span></span>  
<span data-ttu-id="2340c-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="2340c-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2340c-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="2340c-114">Child Elements</span></span>  
  
|<span data-ttu-id="2340c-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="2340c-115">Element</span></span>|<span data-ttu-id="2340c-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="2340c-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2340c-117">ChannelInitializationTimeout</span><span class="sxs-lookup"><span data-stu-id="2340c-117">ChannelInitializationTimeout</span></span>|<span data-ttu-id="2340c-118">Obtiene o establece un <xref:System.TimeSpan> que determina el tiempo máximo que un canal puede estar en el estado de inicialización antes de que se desconecte.</span><span class="sxs-lookup"><span data-stu-id="2340c-118">Gets or sets a <xref:System.TimeSpan> that determines the maximum time a channel can be in the initialization status before being disconnected.</span></span>|  
|<span data-ttu-id="2340c-119">ConnectionBufferSize</span><span class="sxs-lookup"><span data-stu-id="2340c-119">ConnectionBufferSize</span></span>|<span data-ttu-id="2340c-120">Obtiene o establece el tamaño del búfer usado para transmitir un bloque del mensaje serializado en la conexión del cliente o servicio.</span><span class="sxs-lookup"><span data-stu-id="2340c-120">Gets or sets the size of the buffer used to transmit a chunk of the serialized message on the wire from the client or service.</span></span>|  
|<span data-ttu-id="2340c-121">hostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="2340c-121">hostNameComparisonMode</span></span>|<span data-ttu-id="2340c-122">Obtiene o establece un valor que indica si el nombre del host se usa para alcanzar el servicio al coincidir con el URI.</span><span class="sxs-lookup"><span data-stu-id="2340c-122">Gets or sets a value that indicates whether the hostname is used to reach the service when matching on the URI.</span></span>|  
|<span data-ttu-id="2340c-123">manualAddressing</span><span class="sxs-lookup"><span data-stu-id="2340c-123">manualAddressing</span></span>|<span data-ttu-id="2340c-124">Obtiene o establece un valor que indica si se requiere la dirección manual del mensaje.</span><span class="sxs-lookup"><span data-stu-id="2340c-124">Gets or sets a value that indicates whether manual addressing of the message is required.</span></span>|  
|<span data-ttu-id="2340c-125">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="2340c-125">maxBufferPoolSize</span></span>|<span data-ttu-id="2340c-126">Obtiene o establece el tamaño máximo, en bytes, de cualquier grupo de búferes utilizado por el transporte.</span><span class="sxs-lookup"><span data-stu-id="2340c-126">Gets or sets the maximum size, in bytes, of any buffer pools used by the transport.</span></span>|  
|<span data-ttu-id="2340c-127">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="2340c-127">maxBufferSize</span></span>|<span data-ttu-id="2340c-128">Obtiene o establece el tamaño máximo del búfer que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="2340c-128">Gets or sets the maximum size of the buffer to use.</span></span> <span data-ttu-id="2340c-129">Para mensajes transmitidos por secuencias, este valor debería ser por lo menos el tamaño máximo posible de los encabezados de mensaje, que se leen en modo almacenado en búfer.</span><span class="sxs-lookup"><span data-stu-id="2340c-129">For streamed messages, this value should be at least the maximum possible size of the message headers, which are read in buffered mode.</span></span>|  
|<span data-ttu-id="2340c-130">maxOutputDelay</span><span class="sxs-lookup"><span data-stu-id="2340c-130">maxOutputDelay</span></span>|<span data-ttu-id="2340c-131">Obtiene o establece el intervalo máximo de tiempo que un bloque de mensaje o un mensaje completo pueden estar almacenados en búfer en memoria antes de que se envíen.</span><span class="sxs-lookup"><span data-stu-id="2340c-131">Gets or sets the maximum interval of time that a chunk of a message or a full message can remain buffered in memory before being sent out.</span></span>|  
|<span data-ttu-id="2340c-132">maxPendingAccepts</span><span class="sxs-lookup"><span data-stu-id="2340c-132">maxPendingAccepts</span></span>|<span data-ttu-id="2340c-133">Obtiene o establece el número máximo de canales de que un servicio puede tener en espera en un agente de escucha para procesar conexiones entrantes al servicio.</span><span class="sxs-lookup"><span data-stu-id="2340c-133">Gets or sets the maximum number of channels a service can have waiting on a listener for processing incoming connections to the service.</span></span>|  
|<span data-ttu-id="2340c-134">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="2340c-134">maxPendingConnections</span></span>|<span data-ttu-id="2340c-135">Obtiene o establece el número máximo de conexiones pendientes de distribución en el servicio.</span><span class="sxs-lookup"><span data-stu-id="2340c-135">Gets or sets the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="2340c-136">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="2340c-136">maxReceivedMessageSize</span></span>|<span data-ttu-id="2340c-137">Obtiene y establece el tamaño máximo permitido del mensaje, en bytes, que se pueden recibir.</span><span class="sxs-lookup"><span data-stu-id="2340c-137">Gets and sets the maximum allowable message size, in bytes, that can be received.</span></span>|  
|<span data-ttu-id="2340c-138">transferMode</span><span class="sxs-lookup"><span data-stu-id="2340c-138">transferMode</span></span>|<span data-ttu-id="2340c-139">Obtiene o establece un valor que indica si los mensajes están almacenados en búfer o se transmiten por secuencias mediante el transporte orientado a la conexión.</span><span class="sxs-lookup"><span data-stu-id="2340c-139">Gets or sets a value that indicates whether the messages are buffered or streamed with the connection-oriented transport.</span></span>|  
|[<span data-ttu-id="2340c-140">\<connectionPoolSettings > de \<namedPipeTransport ></span><span class="sxs-lookup"><span data-stu-id="2340c-140">\<connectionPoolSettings> of \<namedPipeTransport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/connectionpoolsettings.md)|<span data-ttu-id="2340c-141">Especifica valores adicionales del grupo de conexiones para un enlace de canalización con nombre.</span><span class="sxs-lookup"><span data-stu-id="2340c-141">Specifies additional connection pool settings for a Named Pipe binding.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2340c-142">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="2340c-142">Parent Elements</span></span>  
  
|<span data-ttu-id="2340c-143">Elemento</span><span class="sxs-lookup"><span data-stu-id="2340c-143">Element</span></span>|<span data-ttu-id="2340c-144">Descripción</span><span class="sxs-lookup"><span data-stu-id="2340c-144">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2340c-145">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="2340c-145">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="2340c-146">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="2340c-146">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2340c-147">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2340c-147">Remarks</span></span>  
<span data-ttu-id="2340c-148">Este transporte utiliza los URI del formulario "net.pipe://hostname/path."</span><span class="sxs-lookup"><span data-stu-id="2340c-148">This transport uses URIs of the form "net.pipe://hostname/path".</span></span> <span data-ttu-id="2340c-149">Otros componentes URI son opcionales.</span><span class="sxs-lookup"><span data-stu-id="2340c-149">Other URI components are optional.</span></span>  
  
<span data-ttu-id="2340c-150">El elemento `namedPipeTransport` es el punto inicial para crear un enlace personalizado que implementa el protocolo de transporte de canalizaciones con nombre.</span><span class="sxs-lookup"><span data-stu-id="2340c-150">The `namedPipeTransport` element is the starting point for creating a custom binding that implements the named pipes transport protocol.</span></span> <span data-ttu-id="2340c-151">Este transporte se utiliza para la comunicación entre WCF y Windows Communication Foundation (WCF) en el equipo.</span><span class="sxs-lookup"><span data-stu-id="2340c-151">This transport is used for on-machine Windows Communication Foundation (WCF)-to-WCF communication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2340c-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="2340c-152">See Also</span></span>  
<xref:System.ServiceModel.Configuration.NamedPipeTransportElement>   
<xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>   
<xref:System.ServiceModel.Channels.TransportBindingElement>   
<xref:System.ServiceModel.Channels.CustomBinding>   
<span data-ttu-id="2340c-153">[Transportes](../../../../../docs/framework/wcf/feature-details/transports.md) </span><span class="sxs-lookup"><span data-stu-id="2340c-153">[Transports](../../../../../docs/framework/wcf/feature-details/transports.md) </span></span>  
<span data-ttu-id="2340c-154">[Elección del transporte](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md) </span><span class="sxs-lookup"><span data-stu-id="2340c-154">[Choosing a Transport](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md) </span></span>  
<span data-ttu-id="2340c-155">[enlaces](../../../../../docs/framework/wcf/bindings.md) </span><span class="sxs-lookup"><span data-stu-id="2340c-155">[Bindings](../../../../../docs/framework/wcf/bindings.md) </span></span>  
<span data-ttu-id="2340c-156">[Extensión de enlaces](../../../../../docs/framework/wcf/extending/extending-bindings.md) </span><span class="sxs-lookup"><span data-stu-id="2340c-156">[Extending Bindings](../../../../../docs/framework/wcf/extending/extending-bindings.md) </span></span>  
<span data-ttu-id="2340c-157">[Enlaces personalizados](../../../../../docs/framework/wcf/extending/custom-bindings.md) </span><span class="sxs-lookup"><span data-stu-id="2340c-157">[Custom Bindings](../../../../../docs/framework/wcf/extending/custom-bindings.md) </span></span>  
[<span data-ttu-id="2340c-158">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="2340c-158">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
