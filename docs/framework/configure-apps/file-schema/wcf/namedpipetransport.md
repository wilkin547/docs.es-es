---
title: <namedPipeTransport>
ms.date: 03/30/2017
ms.assetid: 9fc3f42f-43e2-4ab1-8bc7-3c95a9220df1
ms.openlocfilehash: 00631ad88d771ed8f45638f28c84df05917fd3a0
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "73736591"
---
# \<namedPipeTransport>
<span data-ttu-id="ff18f-101">Define un transporte que hace que un canal transfiera mensajes mediante las canalizaciones con nombre cuando está incluido en un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="ff18f-101">Defines a transport that causes a channel to transfer messages using named pipes when it is included in a custom binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<namedPipeTransport>**  
  
## <a name="syntax"></a><span data-ttu-id="ff18f-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ff18f-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ff18f-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ff18f-103">Attributes and Elements</span></span>  
<span data-ttu-id="ff18f-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ff18f-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ff18f-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="ff18f-105">Attributes</span></span>  
<span data-ttu-id="ff18f-106">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="ff18f-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ff18f-107">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ff18f-107">Child Elements</span></span>  
  
|<span data-ttu-id="ff18f-108">Elemento</span><span class="sxs-lookup"><span data-stu-id="ff18f-108">Element</span></span>|<span data-ttu-id="ff18f-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="ff18f-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ff18f-110">ChannelInitializationTimeout</span><span class="sxs-lookup"><span data-stu-id="ff18f-110">ChannelInitializationTimeout</span></span>|<span data-ttu-id="ff18f-111">Obtiene o establece un <xref:System.TimeSpan> que determina el tiempo máximo que un canal puede estar en el estado de la inicialización antes de que se desconecte.</span><span class="sxs-lookup"><span data-stu-id="ff18f-111">Gets or sets a <xref:System.TimeSpan> that determines the maximum time a channel can be in the initialization status before being disconnected.</span></span>|  
|<span data-ttu-id="ff18f-112">ConnectionBufferSize</span><span class="sxs-lookup"><span data-stu-id="ff18f-112">ConnectionBufferSize</span></span>|<span data-ttu-id="ff18f-113">Obtiene o establece el tamaño del búfer usado para transmitir un bloque del mensaje serializado en la conexión del cliente o servicio.</span><span class="sxs-lookup"><span data-stu-id="ff18f-113">Gets or sets the size of the buffer used to transmit a chunk of the serialized message on the wire from the client or service.</span></span>|  
|<span data-ttu-id="ff18f-114">hostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="ff18f-114">hostNameComparisonMode</span></span>|<span data-ttu-id="ff18f-115">Obtiene o establece un valor que indica si el nombre del host se usa para alcanzar el servicio al coincidir con el URI.</span><span class="sxs-lookup"><span data-stu-id="ff18f-115">Gets or sets a value that indicates whether the hostname is used to reach the service when matching on the URI.</span></span>|  
|<span data-ttu-id="ff18f-116">manualAddressing</span><span class="sxs-lookup"><span data-stu-id="ff18f-116">manualAddressing</span></span>|<span data-ttu-id="ff18f-117">Obtiene o establece un valor que indica si se requiere la dirección manual del mensaje.</span><span class="sxs-lookup"><span data-stu-id="ff18f-117">Gets or sets a value that indicates whether manual addressing of the message is required.</span></span>|  
|<span data-ttu-id="ff18f-118">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="ff18f-118">maxBufferPoolSize</span></span>|<span data-ttu-id="ff18f-119">Obtiene o establece el tamaño máximo, en bytes, de cualquier grupo de búferes utilizado por el transporte.</span><span class="sxs-lookup"><span data-stu-id="ff18f-119">Gets or sets the maximum size, in bytes, of any buffer pools used by the transport.</span></span>|  
|<span data-ttu-id="ff18f-120">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="ff18f-120">maxBufferSize</span></span>|<span data-ttu-id="ff18f-121">Obtiene o establece el tamaño máximo del búfer que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="ff18f-121">Gets or sets the maximum size of the buffer to use.</span></span> <span data-ttu-id="ff18f-122">Para mensajes transmitidos por secuencias, este valor debería ser por lo menos el tamaño máximo posible de los encabezados de mensaje, que se leen en modo almacenado en búfer.</span><span class="sxs-lookup"><span data-stu-id="ff18f-122">For streamed messages, this value should be at least the maximum possible size of the message headers, which are read in buffered mode.</span></span>|  
|<span data-ttu-id="ff18f-123">maxOutputDelay</span><span class="sxs-lookup"><span data-stu-id="ff18f-123">maxOutputDelay</span></span>|<span data-ttu-id="ff18f-124">Obtiene o establece el intervalo máximo de tiempo que un bloque de mensaje o un mensaje completo pueden estar almacenados en búfer en memoria antes de que se envíen.</span><span class="sxs-lookup"><span data-stu-id="ff18f-124">Gets or sets the maximum interval of time that a chunk of a message or a full message can remain buffered in memory before being sent out.</span></span>|  
|<span data-ttu-id="ff18f-125">maxPendingAccepts</span><span class="sxs-lookup"><span data-stu-id="ff18f-125">maxPendingAccepts</span></span>|<span data-ttu-id="ff18f-126">Obtiene o establece el número máximo de canales que un servicio puede tener en espera en un agente de escucha para procesar conexiones entrantes en el servicio.</span><span class="sxs-lookup"><span data-stu-id="ff18f-126">Gets or sets the maximum number of channels a service can have waiting on a listener for processing incoming connections to the service.</span></span>|  
|<span data-ttu-id="ff18f-127">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="ff18f-127">maxPendingConnections</span></span>|<span data-ttu-id="ff18f-128">Obtiene o establece el número máximo de conexiones pendientes de distribución en el servicio.</span><span class="sxs-lookup"><span data-stu-id="ff18f-128">Gets or sets the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="ff18f-129">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="ff18f-129">maxReceivedMessageSize</span></span>|<span data-ttu-id="ff18f-130">Obtiene y establece el tamaño máximo permitido del mensaje, en bytes, que se puede recibir.</span><span class="sxs-lookup"><span data-stu-id="ff18f-130">Gets and sets the maximum allowable message size, in bytes, that can be received.</span></span>|  
|<span data-ttu-id="ff18f-131">transferMode</span><span class="sxs-lookup"><span data-stu-id="ff18f-131">transferMode</span></span>|<span data-ttu-id="ff18f-132">Obtiene o establece un valor que indica si los mensajes están almacenados en búfer o se transmiten por secuencias mediante el transporte orientado a la conexión.</span><span class="sxs-lookup"><span data-stu-id="ff18f-132">Gets or sets a value that indicates whether the messages are buffered or streamed with the connection-oriented transport.</span></span>|  
|[<span data-ttu-id="ff18f-133">\<connectionPoolSettings>de\<namedPipeTransport></span><span class="sxs-lookup"><span data-stu-id="ff18f-133">\<connectionPoolSettings> of \<namedPipeTransport></span></span>](connectionpoolsettings.md)|<span data-ttu-id="ff18f-134">Especifica valores adicionales del grupo de conexiones para un enlace de canalización con nombre.</span><span class="sxs-lookup"><span data-stu-id="ff18f-134">Specifies additional connection pool settings for a Named Pipe binding.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ff18f-135">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ff18f-135">Parent Elements</span></span>  
  
|<span data-ttu-id="ff18f-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="ff18f-136">Element</span></span>|<span data-ttu-id="ff18f-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="ff18f-137">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="ff18f-138">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="ff18f-138">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ff18f-139">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ff18f-139">Remarks</span></span>  
<span data-ttu-id="ff18f-140">Este transporte utiliza los URI del formulario "net.pipe://hostname/path."</span><span class="sxs-lookup"><span data-stu-id="ff18f-140">This transport uses URIs of the form "net.pipe://hostname/path".</span></span> <span data-ttu-id="ff18f-141">Otros componentes URI son opcionales.</span><span class="sxs-lookup"><span data-stu-id="ff18f-141">Other URI components are optional.</span></span>  
  
<span data-ttu-id="ff18f-142">El elemento `namedPipeTransport` es el punto inicial para crear un enlace personalizado que implementa el protocolo de transporte de canalizaciones con nombre.</span><span class="sxs-lookup"><span data-stu-id="ff18f-142">The `namedPipeTransport` element is the starting point for creating a custom binding that implements the named pipes transport protocol.</span></span> <span data-ttu-id="ff18f-143">Este transporte se utiliza para la comunicación entre WCF y Windows Communication Foundation (WCF) en el equipo.</span><span class="sxs-lookup"><span data-stu-id="ff18f-143">This transport is used for on-machine Windows Communication Foundation (WCF)-to-WCF communication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff18f-144">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ff18f-144">See also</span></span>

- <xref:System.ServiceModel.Configuration.NamedPipeTransportElement>
- <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="ff18f-145">Transportes</span><span class="sxs-lookup"><span data-stu-id="ff18f-145">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="ff18f-146">Elección del transporte</span><span class="sxs-lookup"><span data-stu-id="ff18f-146">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="ff18f-147">Enlaces</span><span class="sxs-lookup"><span data-stu-id="ff18f-147">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="ff18f-148">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="ff18f-148">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="ff18f-149">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="ff18f-149">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
