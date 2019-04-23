---
title: <connectionPoolSettings> de <tcpTransport>
ms.date: 03/30/2017
ms.assetid: 2fbc3aa7-fcc9-4193-99a3-85d31d60d3f7
ms.openlocfilehash: 93363c5ff1753ff02956404da7697780078c9839
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59129979"
---
# <a name="connectionpoolsettings-of-tcptransport"></a><span data-ttu-id="f94bd-102">\<connectionPoolSettings > de \<tcpTransport ></span><span class="sxs-lookup"><span data-stu-id="f94bd-102">\<connectionPoolSettings> of \<tcpTransport></span></span>
<span data-ttu-id="f94bd-103">Especifica los valores de grupo de conexiones adicionales para un transporte TCP.</span><span class="sxs-lookup"><span data-stu-id="f94bd-103">Specifies additional connection pool settings for a TCP transport.</span></span>  
  
 <span data-ttu-id="f94bd-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="f94bd-104">\<system.serviceModel></span></span>  
<span data-ttu-id="f94bd-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="f94bd-105">\<bindings></span></span>  
<span data-ttu-id="f94bd-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="f94bd-106">\<customBinding></span></span>  
<span data-ttu-id="f94bd-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="f94bd-107">\<binding></span></span>  
<span data-ttu-id="f94bd-108">\<tcpTransport></span><span class="sxs-lookup"><span data-stu-id="f94bd-108">\<tcpTransport></span></span>  
<span data-ttu-id="f94bd-109">\<connectionPoolSettings></span><span class="sxs-lookup"><span data-stu-id="f94bd-109">\<connectionPoolSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f94bd-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f94bd-110">Syntax</span></span>  
  
```xml  
<connectionPoolSettings groupName="String"
                        idleTimeout="TimeSpan"
                        leaseTimeout="TimeSpan"
                        maxOutboundConnectionsPerEndpopint="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f94bd-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f94bd-111">Attributes and Elements</span></span>  
 <span data-ttu-id="f94bd-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f94bd-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f94bd-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="f94bd-113">Attributes</span></span>  
  
|<span data-ttu-id="f94bd-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="f94bd-114">Attribute</span></span>|<span data-ttu-id="f94bd-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="f94bd-115">Description</span></span>|  
|---------------|-----------------|  
|`groupName`|<span data-ttu-id="f94bd-116">Una cadena que define el nombre del grupo de conexiones que se usa para canales salientes.</span><span class="sxs-lookup"><span data-stu-id="f94bd-116">A string that defines the name of the connection pool used for outgoing channels.</span></span> <span data-ttu-id="f94bd-117">En modo de transmisión, las conexiones no se comparten, lo cual significa que la agrupación de conexiones está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="f94bd-117">In streamed mode, connections are not shared, meaning that connection pooling is disabled.</span></span> <span data-ttu-id="f94bd-118">La cadena predeterminada es “default”.</span><span class="sxs-lookup"><span data-stu-id="f94bd-118">The default is a "default" string.</span></span> <span data-ttu-id="f94bd-119">Puede modificar este valor para aislar las conexiones para un cliente determinado en grupos independientes.</span><span class="sxs-lookup"><span data-stu-id="f94bd-119">You can modify this value to isolate the connections for a particular client into separate groups.</span></span>|  
|`idleTimeout`|<span data-ttu-id="f94bd-120">Un <xref:System.TimeSpan> positivo que especifica el tiempo máximo que la conexión puede estar inactiva antes de que se desconecte.</span><span class="sxs-lookup"><span data-stu-id="f94bd-120">A positive <xref:System.TimeSpan> that specifies the maximum time the connection can be idle before being disconnected.</span></span> <span data-ttu-id="f94bd-121">El valor predeterminado es 00:02:00.</span><span class="sxs-lookup"><span data-stu-id="f94bd-121">The default is 00:02:00.</span></span>|  
|`leaseTimeout`|<span data-ttu-id="f94bd-122"><xref:System.TimeSpan> que especifica el tiempo después del que se cierra una conexión activa.</span><span class="sxs-lookup"><span data-stu-id="f94bd-122">A <xref:System.TimeSpan> that specifies the time after which an active connection is closed.</span></span> <span data-ttu-id="f94bd-123">El valor predeterminado es 00:05:00.</span><span class="sxs-lookup"><span data-stu-id="f94bd-123">The default is 00:05:00.</span></span><br /><br /> <span data-ttu-id="f94bd-124">Se cierra una conexión después de que se haya devuelto a la conexión caché y no durante la transmisión activa.</span><span class="sxs-lookup"><span data-stu-id="f94bd-124">A connection is closed after it has been returned to the connection cache and not during active transmission.</span></span> <span data-ttu-id="f94bd-125">El caché de conexión utilizado por el transporte TCP crea conexiones nuevas, como se requiere para cada punto de conexión, hasta el límite del caché establecido por `maxOutboundConnectionsPerEndpoint.`.</span><span class="sxs-lookup"><span data-stu-id="f94bd-125">The connection cache used by the TCP transport creates new connections as required for each endpoint, up to the cache limit that is set by `maxOutboundConnectionsPerEndpoint.`</span></span>|  
|`maxOutboundConnectionsPerEndpoint`|<span data-ttu-id="f94bd-126">Un entero positivo que especifica el número máximo de conexiones a un punto de conexión remoto que inicia el servicio.</span><span class="sxs-lookup"><span data-stu-id="f94bd-126">A positive integer that specifies the maximum number of connections to a remote endpoint initiated by the service.</span></span> <span data-ttu-id="f94bd-127">Las conexiones que sobrepasen el límite se pondrán a la cola hasta que quede disponible un espacio por debajo del límite.</span><span class="sxs-lookup"><span data-stu-id="f94bd-127">Connections in excess of the limit are queued until a space below the limit becomes available.</span></span> <span data-ttu-id="f94bd-128">`idleTimeout` limita la duración en la que las conexiones siguen en cola antes de que se inicie una excepción.</span><span class="sxs-lookup"><span data-stu-id="f94bd-128">The `idleTimeout` limits the duration in which connections remain queued before an exception is thrown.</span></span> <span data-ttu-id="f94bd-129">El valor predeterminado es 10.</span><span class="sxs-lookup"><span data-stu-id="f94bd-129">The default is 10.</span></span><br /><br /> <span data-ttu-id="f94bd-130">Este atributo limita el número de conexiones activas simultáneas del cliente a un extremo de servicio determinado.</span><span class="sxs-lookup"><span data-stu-id="f94bd-130">This attribute limits the number of simultaneous active connections from the client to a particular service endpoint.</span></span> <span data-ttu-id="f94bd-131">Si este valor se supera debido a más conexiones de cliente activas, el servicio puede se le muestre al cliente sin respuesta.</span><span class="sxs-lookup"><span data-stu-id="f94bd-131">If this value is exceeded by having more active client connections, the service may appear unresponsive to the client.</span></span> <span data-ttu-id="f94bd-132">En este caso, este valor se debería ajustar para superar el número máximo de conexiones de cliente simultáneas esperadas a un extremo determinado.</span><span class="sxs-lookup"><span data-stu-id="f94bd-132">In this case, this value should be adjusted to exceed the maximum number of expected simultaneous client connections to a specific endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f94bd-133">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f94bd-133">Child Elements</span></span>  
 <span data-ttu-id="f94bd-134">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="f94bd-134">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f94bd-135">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f94bd-135">Parent Elements</span></span>  
  
|<span data-ttu-id="f94bd-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="f94bd-136">Element</span></span>|<span data-ttu-id="f94bd-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="f94bd-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f94bd-138">\<namedPipeTransport></span><span class="sxs-lookup"><span data-stu-id="f94bd-138">\<namedPipeTransport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/namedpipetransport.md)|<span data-ttu-id="f94bd-139">Define un transporte que hace que un canal transfiera mensajes mediante canalizaciones con nombre.</span><span class="sxs-lookup"><span data-stu-id="f94bd-139">Defines a transport that causes a channel to transfer messages using named pipes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f94bd-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="f94bd-140">See also</span></span>

- <xref:System.ServiceModel.Configuration.TcpConnectionPoolSettingsElement>
- <xref:System.ServiceModel.Channels.TcpTransportBindingElement.ConnectionPoolSettings%2A>
- <xref:System.ServiceModel.Channels.TcpConnectionPoolSettings>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="f94bd-141">Transportes</span><span class="sxs-lookup"><span data-stu-id="f94bd-141">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)
- [<span data-ttu-id="f94bd-142">Elección del transporte</span><span class="sxs-lookup"><span data-stu-id="f94bd-142">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="f94bd-143">Enlaces</span><span class="sxs-lookup"><span data-stu-id="f94bd-143">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="f94bd-144">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="f94bd-144">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="f94bd-145">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="f94bd-145">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="f94bd-146">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="f94bd-146">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
