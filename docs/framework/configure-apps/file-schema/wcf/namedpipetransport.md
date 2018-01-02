---
title: '&lt;namedPipeTransport&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9fc3f42f-43e2-4ab1-8bc7-3c95a9220df1
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7802bff708cb081aa9f54f76a35ff5842ad60544
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltnamedpipetransportgt"></a><span data-ttu-id="5f541-102">&lt;namedPipeTransport&gt;</span><span class="sxs-lookup"><span data-stu-id="5f541-102">&lt;namedPipeTransport&gt;</span></span>
<span data-ttu-id="5f541-103">Define un transporte que hace que un canal transfiera mensajes mediante las canalizaciones con nombre cuando está incluido en un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="5f541-103">Defines a transport that causes a channel to transfer messages using named pipes when it is included in a custom binding.</span></span>  
  
<span data-ttu-id="5f541-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="5f541-104">\<system.serviceModel></span></span>  
<span data-ttu-id="5f541-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="5f541-105">\<bindings></span></span>  
<span data-ttu-id="5f541-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="5f541-106">\<customBinding></span></span>  
<span data-ttu-id="5f541-107">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="5f541-107">\<binding></span></span>  
<span data-ttu-id="5f541-108">\<namePipeTransport ></span><span class="sxs-lookup"><span data-stu-id="5f541-108">\<namePipeTransport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f541-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5f541-109">Syntax</span></span>  
  
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
                          idleTimeout"TimeSpan"  
                          maxOutboundConnectionsPerEndpopint="Integer" />  
</namedPipeTransport>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5f541-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5f541-110">Attributes and Elements</span></span>  
<span data-ttu-id="5f541-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5f541-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5f541-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="5f541-112">Attributes</span></span>  
<span data-ttu-id="5f541-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="5f541-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5f541-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5f541-114">Child Elements</span></span>  
  
|<span data-ttu-id="5f541-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="5f541-115">Element</span></span>|<span data-ttu-id="5f541-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="5f541-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5f541-117">ChannelInitializationTimeout</span><span class="sxs-lookup"><span data-stu-id="5f541-117">ChannelInitializationTimeout</span></span>|<span data-ttu-id="5f541-118">Obtiene o establece un <xref:System.TimeSpan> que determina el tiempo máximo que un canal puede estar en el estado de inicialización antes de que se desconecte.</span><span class="sxs-lookup"><span data-stu-id="5f541-118">Gets or sets a <xref:System.TimeSpan> that determines the maximum time a channel can be in the initialization status before being disconnected.</span></span>|  
|<span data-ttu-id="5f541-119">ConnectionBufferSize</span><span class="sxs-lookup"><span data-stu-id="5f541-119">ConnectionBufferSize</span></span>|<span data-ttu-id="5f541-120">Obtiene o establece el tamaño del búfer usado para transmitir un bloque del mensaje serializado en la conexión del cliente o servicio.</span><span class="sxs-lookup"><span data-stu-id="5f541-120">Gets or sets the size of the buffer used to transmit a chunk of the serialized message on the wire from the client or service.</span></span>|  
|<span data-ttu-id="5f541-121">hostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="5f541-121">hostNameComparisonMode</span></span>|<span data-ttu-id="5f541-122">Obtiene o establece un valor que indica si el nombre del host se usa para alcanzar el servicio al coincidir con el URI.</span><span class="sxs-lookup"><span data-stu-id="5f541-122">Gets or sets a value that indicates whether the hostname is used to reach the service when matching on the URI.</span></span>|  
|<span data-ttu-id="5f541-123">manualAddressing</span><span class="sxs-lookup"><span data-stu-id="5f541-123">manualAddressing</span></span>|<span data-ttu-id="5f541-124">Obtiene o establece un valor que indica si se requiere la dirección manual del mensaje.</span><span class="sxs-lookup"><span data-stu-id="5f541-124">Gets or sets a value that indicates whether manual addressing of the message is required.</span></span>|  
|<span data-ttu-id="5f541-125">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="5f541-125">maxBufferPoolSize</span></span>|<span data-ttu-id="5f541-126">Obtiene o establece el tamaño máximo, en bytes, de cualquier grupo de búferes utilizado por el transporte.</span><span class="sxs-lookup"><span data-stu-id="5f541-126">Gets or sets the maximum size, in bytes, of any buffer pools used by the transport.</span></span>|  
|<span data-ttu-id="5f541-127">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="5f541-127">maxBufferSize</span></span>|<span data-ttu-id="5f541-128">Obtiene o establece el tamaño máximo del búfer que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="5f541-128">Gets or sets the maximum size of the buffer to use.</span></span> <span data-ttu-id="5f541-129">Para mensajes transmitidos por secuencias, este valor debería ser por lo menos el tamaño máximo posible de los encabezados de mensaje, que se leen en modo almacenado en búfer.</span><span class="sxs-lookup"><span data-stu-id="5f541-129">For streamed messages, this value should be at least the maximum possible size of the message headers, which are read in buffered mode.</span></span>|  
|<span data-ttu-id="5f541-130">maxOutputDelay</span><span class="sxs-lookup"><span data-stu-id="5f541-130">maxOutputDelay</span></span>|<span data-ttu-id="5f541-131">Obtiene o establece el intervalo máximo de tiempo que un bloque de mensaje o un mensaje completo pueden estar almacenados en búfer en memoria antes de que se envíen.</span><span class="sxs-lookup"><span data-stu-id="5f541-131">Gets or sets the maximum interval of time that a chunk of a message or a full message can remain buffered in memory before being sent out.</span></span>|  
|<span data-ttu-id="5f541-132">maxPendingAccepts</span><span class="sxs-lookup"><span data-stu-id="5f541-132">maxPendingAccepts</span></span>|<span data-ttu-id="5f541-133">Obtiene o establece el número máximo de canales de que un servicio puede tener en espera en un agente de escucha para procesar conexiones entrantes en el servicio.</span><span class="sxs-lookup"><span data-stu-id="5f541-133">Gets or sets the maximum number of channels a service can have waiting on a listener for processing incoming connections to the service.</span></span>|  
|<span data-ttu-id="5f541-134">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="5f541-134">maxPendingConnections</span></span>|<span data-ttu-id="5f541-135">Obtiene o establece el número máximo de conexiones pendientes de distribución en el servicio.</span><span class="sxs-lookup"><span data-stu-id="5f541-135">Gets or sets the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="5f541-136">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="5f541-136">maxReceivedMessageSize</span></span>|<span data-ttu-id="5f541-137">Obtiene y establece el tamaño máximo permitido del mensaje, en bytes, que se pueden recibir.</span><span class="sxs-lookup"><span data-stu-id="5f541-137">Gets and sets the maximum allowable message size, in bytes, that can be received.</span></span>|  
|<span data-ttu-id="5f541-138">transferMode</span><span class="sxs-lookup"><span data-stu-id="5f541-138">transferMode</span></span>|<span data-ttu-id="5f541-139">Obtiene o establece un valor que indica si los mensajes están almacenados en búfer o se transmiten por secuencias mediante el transporte orientado a la conexión.</span><span class="sxs-lookup"><span data-stu-id="5f541-139">Gets or sets a value that indicates whether the messages are buffered or streamed with the connection-oriented transport.</span></span>|  
|[<span data-ttu-id="5f541-140">\<connectionPoolSettings > de \<namedPipeTransport ></span><span class="sxs-lookup"><span data-stu-id="5f541-140">\<connectionPoolSettings> of \<namedPipeTransport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/connectionpoolsettings.md)|<span data-ttu-id="5f541-141">Especifica valores adicionales del grupo de conexiones para un enlace de canalización con nombre.</span><span class="sxs-lookup"><span data-stu-id="5f541-141">Specifies additional connection pool settings for a Named Pipe binding.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5f541-142">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5f541-142">Parent Elements</span></span>  
  
|<span data-ttu-id="5f541-143">Elemento</span><span class="sxs-lookup"><span data-stu-id="5f541-143">Element</span></span>|<span data-ttu-id="5f541-144">Descripción</span><span class="sxs-lookup"><span data-stu-id="5f541-144">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5f541-145">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="5f541-145">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="5f541-146">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="5f541-146">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5f541-147">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5f541-147">Remarks</span></span>  
<span data-ttu-id="5f541-148">Este transporte utiliza los URI del formulario "net.pipe://hostname/path."</span><span class="sxs-lookup"><span data-stu-id="5f541-148">This transport uses URIs of the form "net.pipe://hostname/path".</span></span> <span data-ttu-id="5f541-149">Otros componentes URI son opcionales.</span><span class="sxs-lookup"><span data-stu-id="5f541-149">Other URI components are optional.</span></span>  
  
<span data-ttu-id="5f541-150">El elemento `namedPipeTransport` es el punto inicial para crear un enlace personalizado que implementa el protocolo de transporte de canalizaciones con nombre.</span><span class="sxs-lookup"><span data-stu-id="5f541-150">The `namedPipeTransport` element is the starting point for creating a custom binding that implements the named pipes transport protocol.</span></span> <span data-ttu-id="5f541-151">Este transporte se utiliza para la comunicación entre WCF y Windows Communication Foundation (WCF) en el equipo.</span><span class="sxs-lookup"><span data-stu-id="5f541-151">This transport is used for on-machine Windows Communication Foundation (WCF)-to-WCF communication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f541-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="5f541-152">See Also</span></span>  
<span data-ttu-id="5f541-153"><xref:System.ServiceModel.Configuration.NamedPipeTransportElement></span><span class="sxs-lookup"><span data-stu-id="5f541-153"><xref:System.ServiceModel.Configuration.NamedPipeTransportElement></span></span>   
<span data-ttu-id="5f541-154"><xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement></span><span class="sxs-lookup"><span data-stu-id="5f541-154"><xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement></span></span>   
<span data-ttu-id="5f541-155"><xref:System.ServiceModel.Channels.TransportBindingElement></span><span class="sxs-lookup"><span data-stu-id="5f541-155"><xref:System.ServiceModel.Channels.TransportBindingElement></span></span>   
<span data-ttu-id="5f541-156"><xref:System.ServiceModel.Channels.CustomBinding></span><span class="sxs-lookup"><span data-stu-id="5f541-156"><xref:System.ServiceModel.Channels.CustomBinding></span></span>   
<span data-ttu-id="5f541-157">[Transportes](../../../../../docs/framework/wcf/feature-details/transports.md) </span><span class="sxs-lookup"><span data-stu-id="5f541-157">[Transports](../../../../../docs/framework/wcf/feature-details/transports.md) </span></span>  
<span data-ttu-id="5f541-158">[Elegir un transporte](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md) </span><span class="sxs-lookup"><span data-stu-id="5f541-158">[Choosing a Transport](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md) </span></span>  
<span data-ttu-id="5f541-159">[Enlaces](../../../../../docs/framework/wcf/bindings.md) </span><span class="sxs-lookup"><span data-stu-id="5f541-159">[Bindings](../../../../../docs/framework/wcf/bindings.md) </span></span>  
<span data-ttu-id="5f541-160">[Extensión de enlaces](../../../../../docs/framework/wcf/extending/extending-bindings.md) </span><span class="sxs-lookup"><span data-stu-id="5f541-160">[Extending Bindings](../../../../../docs/framework/wcf/extending/extending-bindings.md) </span></span>  
<span data-ttu-id="5f541-161">[Enlaces personalizados](../../../../../docs/framework/wcf/extending/custom-bindings.md) </span><span class="sxs-lookup"><span data-stu-id="5f541-161">[Custom Bindings](../../../../../docs/framework/wcf/extending/custom-bindings.md) </span></span>  
[<span data-ttu-id="5f541-162">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="5f541-162">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
