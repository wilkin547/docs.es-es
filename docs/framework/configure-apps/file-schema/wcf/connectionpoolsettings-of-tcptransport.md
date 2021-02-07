---
description: 'Más información sobre: <connectionPoolSettings> de <tcpTransport>'
title: <connectionPoolSettings> de <tcpTransport>
ms.date: 03/30/2017
ms.assetid: 2fbc3aa7-fcc9-4193-99a3-85d31d60d3f7
ms.openlocfilehash: 065d3529740714ffd740c2cec71832a7b386b4a3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99698393"
---
# <a name="connectionpoolsettings-of-tcptransport"></a><span data-ttu-id="68f61-103">\<connectionPoolSettings> de \<tcpTransport></span><span class="sxs-lookup"><span data-stu-id="68f61-103">\<connectionPoolSettings> of \<tcpTransport></span></span>

<span data-ttu-id="68f61-104">Especifica los valores de grupo de conexiones adicionales para un transporte TCP.</span><span class="sxs-lookup"><span data-stu-id="68f61-104">Specifies additional connection pool settings for a TCP transport.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<tcpTransport>**](tcptransport.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<connectionPoolSettings>**  
  
## <a name="syntax"></a><span data-ttu-id="68f61-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="68f61-105">Syntax</span></span>  
  
```xml  
<connectionPoolSettings groupName="String"
                        idleTimeout="TimeSpan"
                        leaseTimeout="TimeSpan"
                        maxOutboundConnectionsPerEndpoint="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="68f61-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="68f61-106">Attributes and Elements</span></span>  

 <span data-ttu-id="68f61-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="68f61-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="68f61-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="68f61-108">Attributes</span></span>  
  
|<span data-ttu-id="68f61-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="68f61-109">Attribute</span></span>|<span data-ttu-id="68f61-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="68f61-110">Description</span></span>|  
|---------------|-----------------|  
|`groupName`|<span data-ttu-id="68f61-111">Una cadena que define el nombre del grupo de conexiones que se usa para canales salientes.</span><span class="sxs-lookup"><span data-stu-id="68f61-111">A string that defines the name of the connection pool used for outgoing channels.</span></span> <span data-ttu-id="68f61-112">En modo de transmisión, las conexiones no se comparten, lo cual significa que la agrupación de conexiones está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="68f61-112">In streamed mode, connections are not shared, meaning that connection pooling is disabled.</span></span> <span data-ttu-id="68f61-113">La cadena predeterminada es “default”.</span><span class="sxs-lookup"><span data-stu-id="68f61-113">The default is a "default" string.</span></span> <span data-ttu-id="68f61-114">Puede modificar este valor para aislar las conexiones para un cliente determinado en grupos independientes.</span><span class="sxs-lookup"><span data-stu-id="68f61-114">You can modify this value to isolate the connections for a particular client into separate groups.</span></span>|  
|`idleTimeout`|<span data-ttu-id="68f61-115">Un <xref:System.TimeSpan> positivo que especifica el tiempo máximo que la conexión puede estar inactiva antes de que se desconecte.</span><span class="sxs-lookup"><span data-stu-id="68f61-115">A positive <xref:System.TimeSpan> that specifies the maximum time the connection can be idle before being disconnected.</span></span> <span data-ttu-id="68f61-116">El valor predeterminado es 00:02:00.</span><span class="sxs-lookup"><span data-stu-id="68f61-116">The default is 00:02:00.</span></span>|  
|`leaseTimeout`|<span data-ttu-id="68f61-117"><xref:System.TimeSpan> que especifica el tiempo después del que se cierra una conexión activa.</span><span class="sxs-lookup"><span data-stu-id="68f61-117">A <xref:System.TimeSpan> that specifies the time after which an active connection is closed.</span></span> <span data-ttu-id="68f61-118">El valor predeterminado es 00:05:00.</span><span class="sxs-lookup"><span data-stu-id="68f61-118">The default is 00:05:00.</span></span><br /><br /> <span data-ttu-id="68f61-119">Se cierra una conexión después de que se haya devuelto a la conexión caché y no durante la transmisión activa.</span><span class="sxs-lookup"><span data-stu-id="68f61-119">A connection is closed after it has been returned to the connection cache and not during active transmission.</span></span> <span data-ttu-id="68f61-120">El caché de conexión utilizado por el transporte TCP crea conexiones nuevas, como se requiere para cada punto de conexión, hasta el límite del caché establecido por `maxOutboundConnectionsPerEndpoint.`.</span><span class="sxs-lookup"><span data-stu-id="68f61-120">The connection cache used by the TCP transport creates new connections as required for each endpoint, up to the cache limit that is set by `maxOutboundConnectionsPerEndpoint.`</span></span>|  
|`maxOutboundConnectionsPerEndpoint`|<span data-ttu-id="68f61-121">Un entero positivo que especifica el número máximo de conexiones a un punto de conexión remoto que inicia el servicio.</span><span class="sxs-lookup"><span data-stu-id="68f61-121">A positive integer that specifies the maximum number of connections to a remote endpoint initiated by the service.</span></span> <span data-ttu-id="68f61-122">Las conexiones que sobrepasen el límite se pondrán a la cola hasta que quede disponible un espacio por debajo del límite.</span><span class="sxs-lookup"><span data-stu-id="68f61-122">Connections in excess of the limit are queued until a space below the limit becomes available.</span></span> <span data-ttu-id="68f61-123">`idleTimeout` limita la duración en la que las conexiones siguen en cola antes de que se inicie una excepción.</span><span class="sxs-lookup"><span data-stu-id="68f61-123">The `idleTimeout` limits the duration in which connections remain queued before an exception is thrown.</span></span> <span data-ttu-id="68f61-124">El valor predeterminado es 10.</span><span class="sxs-lookup"><span data-stu-id="68f61-124">The default is 10.</span></span><br /><br /> <span data-ttu-id="68f61-125">Este atributo limita el número de conexiones activas simultáneas del cliente a un extremo de servicio determinado.</span><span class="sxs-lookup"><span data-stu-id="68f61-125">This attribute limits the number of simultaneous active connections from the client to a particular service endpoint.</span></span> <span data-ttu-id="68f61-126">Si este valor se supera debido a más conexiones de cliente activas, el servicio puede se le muestre al cliente sin respuesta.</span><span class="sxs-lookup"><span data-stu-id="68f61-126">If this value is exceeded by having more active client connections, the service may appear unresponsive to the client.</span></span> <span data-ttu-id="68f61-127">En este caso, este valor se debería ajustar para superar el número máximo de conexiones de cliente simultáneas esperadas a un extremo determinado.</span><span class="sxs-lookup"><span data-stu-id="68f61-127">In this case, this value should be adjusted to exceed the maximum number of expected simultaneous client connections to a specific endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="68f61-128">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="68f61-128">Child Elements</span></span>  

 <span data-ttu-id="68f61-129">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="68f61-129">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="68f61-130">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="68f61-130">Parent Elements</span></span>  
  
|<span data-ttu-id="68f61-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="68f61-131">Element</span></span>|<span data-ttu-id="68f61-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="68f61-132">Description</span></span>|  
|-------------|-----------------|  
|[\<namedPipeTransport>](namedpipetransport.md)|<span data-ttu-id="68f61-133">Define un transporte que hace que un canal transfiera mensajes mediante canalizaciones con nombre.</span><span class="sxs-lookup"><span data-stu-id="68f61-133">Defines a transport that causes a channel to transfer messages using named pipes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="68f61-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="68f61-134">See also</span></span>

- <xref:System.ServiceModel.Configuration.TcpConnectionPoolSettingsElement>
- <xref:System.ServiceModel.Channels.TcpTransportBindingElement.ConnectionPoolSettings%2A>
- <xref:System.ServiceModel.Channels.TcpConnectionPoolSettings>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="68f61-135">Transportes</span><span class="sxs-lookup"><span data-stu-id="68f61-135">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="68f61-136">Elección del transporte</span><span class="sxs-lookup"><span data-stu-id="68f61-136">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="68f61-137">Enlaces</span><span class="sxs-lookup"><span data-stu-id="68f61-137">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="68f61-138">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="68f61-138">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="68f61-139">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="68f61-139">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
