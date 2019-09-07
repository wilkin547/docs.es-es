---
title: <connectionPoolSettings> de <tcpTransport>
ms.date: 03/30/2017
ms.assetid: 2fbc3aa7-fcc9-4193-99a3-85d31d60d3f7
ms.openlocfilehash: f9b0fff741c32c1a3d6f9461f478e89acc18114e
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398099"
---
# <a name="connectionpoolsettings-of-tcptransport"></a><span data-ttu-id="4ad13-102">\<connectionPoolSettings > \<tcpTransport ></span><span class="sxs-lookup"><span data-stu-id="4ad13-102">\<connectionPoolSettings> of \<tcpTransport></span></span>
<span data-ttu-id="4ad13-103">Especifica los valores de grupo de conexiones adicionales para un transporte TCP.</span><span class="sxs-lookup"><span data-stu-id="4ad13-103">Specifies additional connection pool settings for a TCP transport.</span></span>  
  
<span data-ttu-id="4ad13-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4ad13-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4ad13-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="4ad13-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="4ad13-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de enlaces**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="4ad13-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="4ad13-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="4ad13-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="4ad13-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de enlace**</span><span class="sxs-lookup"><span data-stu-id="4ad13-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="4ad13-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> tcpTransport**](tcptransport.md)</span><span class="sxs-lookup"><span data-stu-id="4ad13-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<tcpTransport>**](tcptransport.md)</span></span>\
<span data-ttu-id="4ad13-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> connectionPoolSettings**</span><span class="sxs-lookup"><span data-stu-id="4ad13-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<connectionPoolSettings>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ad13-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4ad13-111">Syntax</span></span>  
  
```xml  
<connectionPoolSettings groupName="String"
                        idleTimeout="TimeSpan"
                        leaseTimeout="TimeSpan"
                        maxOutboundConnectionsPerEndpoint="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4ad13-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4ad13-112">Attributes and Elements</span></span>  
 <span data-ttu-id="4ad13-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="4ad13-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4ad13-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="4ad13-114">Attributes</span></span>  
  
|<span data-ttu-id="4ad13-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="4ad13-115">Attribute</span></span>|<span data-ttu-id="4ad13-116">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="4ad13-116">Description</span></span>|  
|---------------|-----------------|  
|`groupName`|<span data-ttu-id="4ad13-117">Una cadena que define el nombre del grupo de conexiones que se usa para canales salientes.</span><span class="sxs-lookup"><span data-stu-id="4ad13-117">A string that defines the name of the connection pool used for outgoing channels.</span></span> <span data-ttu-id="4ad13-118">En modo de transmisión, las conexiones no se comparten, lo cual significa que la agrupación de conexiones está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="4ad13-118">In streamed mode, connections are not shared, meaning that connection pooling is disabled.</span></span> <span data-ttu-id="4ad13-119">La cadena predeterminada es “default”.</span><span class="sxs-lookup"><span data-stu-id="4ad13-119">The default is a "default" string.</span></span> <span data-ttu-id="4ad13-120">Puede modificar este valor para aislar las conexiones para un cliente determinado en grupos independientes.</span><span class="sxs-lookup"><span data-stu-id="4ad13-120">You can modify this value to isolate the connections for a particular client into separate groups.</span></span>|  
|`idleTimeout`|<span data-ttu-id="4ad13-121">Un <xref:System.TimeSpan> positivo que especifica el tiempo máximo que la conexión puede estar inactiva antes de que se desconecte.</span><span class="sxs-lookup"><span data-stu-id="4ad13-121">A positive <xref:System.TimeSpan> that specifies the maximum time the connection can be idle before being disconnected.</span></span> <span data-ttu-id="4ad13-122">El valor predeterminado es 00:02:00.</span><span class="sxs-lookup"><span data-stu-id="4ad13-122">The default is 00:02:00.</span></span>|  
|`leaseTimeout`|<span data-ttu-id="4ad13-123"><xref:System.TimeSpan> que especifica el tiempo después del que se cierra una conexión activa.</span><span class="sxs-lookup"><span data-stu-id="4ad13-123">A <xref:System.TimeSpan> that specifies the time after which an active connection is closed.</span></span> <span data-ttu-id="4ad13-124">El valor predeterminado es 00:05:00.</span><span class="sxs-lookup"><span data-stu-id="4ad13-124">The default is 00:05:00.</span></span><br /><br /> <span data-ttu-id="4ad13-125">Se cierra una conexión después de que se haya devuelto a la conexión caché y no durante la transmisión activa.</span><span class="sxs-lookup"><span data-stu-id="4ad13-125">A connection is closed after it has been returned to the connection cache and not during active transmission.</span></span> <span data-ttu-id="4ad13-126">El caché de conexión utilizado por el transporte TCP crea conexiones nuevas, como se requiere para cada punto de conexión, hasta el límite del caché establecido por `maxOutboundConnectionsPerEndpoint.`.</span><span class="sxs-lookup"><span data-stu-id="4ad13-126">The connection cache used by the TCP transport creates new connections as required for each endpoint, up to the cache limit that is set by `maxOutboundConnectionsPerEndpoint.`</span></span>|  
|`maxOutboundConnectionsPerEndpoint`|<span data-ttu-id="4ad13-127">Un entero positivo que especifica el número máximo de conexiones a un punto de conexión remoto que inicia el servicio.</span><span class="sxs-lookup"><span data-stu-id="4ad13-127">A positive integer that specifies the maximum number of connections to a remote endpoint initiated by the service.</span></span> <span data-ttu-id="4ad13-128">Las conexiones que sobrepasen el límite se pondrán a la cola hasta que quede disponible un espacio por debajo del límite.</span><span class="sxs-lookup"><span data-stu-id="4ad13-128">Connections in excess of the limit are queued until a space below the limit becomes available.</span></span> <span data-ttu-id="4ad13-129">`idleTimeout` limita la duración en la que las conexiones siguen en cola antes de que se inicie una excepción.</span><span class="sxs-lookup"><span data-stu-id="4ad13-129">The `idleTimeout` limits the duration in which connections remain queued before an exception is thrown.</span></span> <span data-ttu-id="4ad13-130">El valor predeterminado es 10.</span><span class="sxs-lookup"><span data-stu-id="4ad13-130">The default is 10.</span></span><br /><br /> <span data-ttu-id="4ad13-131">Este atributo limita el número de conexiones activas simultáneas del cliente a un extremo de servicio determinado.</span><span class="sxs-lookup"><span data-stu-id="4ad13-131">This attribute limits the number of simultaneous active connections from the client to a particular service endpoint.</span></span> <span data-ttu-id="4ad13-132">Si este valor se supera debido a más conexiones de cliente activas, el servicio puede se le muestre al cliente sin respuesta.</span><span class="sxs-lookup"><span data-stu-id="4ad13-132">If this value is exceeded by having more active client connections, the service may appear unresponsive to the client.</span></span> <span data-ttu-id="4ad13-133">En este caso, este valor se debería ajustar para superar el número máximo de conexiones de cliente simultáneas esperadas a un extremo determinado.</span><span class="sxs-lookup"><span data-stu-id="4ad13-133">In this case, this value should be adjusted to exceed the maximum number of expected simultaneous client connections to a specific endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4ad13-134">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4ad13-134">Child Elements</span></span>  
 <span data-ttu-id="4ad13-135">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="4ad13-135">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4ad13-136">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4ad13-136">Parent Elements</span></span>  
  
|<span data-ttu-id="4ad13-137">Elemento</span><span class="sxs-lookup"><span data-stu-id="4ad13-137">Element</span></span>|<span data-ttu-id="4ad13-138">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="4ad13-138">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4ad13-139">\<namedPipeTransport></span><span class="sxs-lookup"><span data-stu-id="4ad13-139">\<namedPipeTransport></span></span>](namedpipetransport.md)|<span data-ttu-id="4ad13-140">Define un transporte que hace que un canal transfiera mensajes mediante canalizaciones con nombre.</span><span class="sxs-lookup"><span data-stu-id="4ad13-140">Defines a transport that causes a channel to transfer messages using named pipes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4ad13-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="4ad13-141">See also</span></span>

- <xref:System.ServiceModel.Configuration.TcpConnectionPoolSettingsElement>
- <xref:System.ServiceModel.Channels.TcpTransportBindingElement.ConnectionPoolSettings%2A>
- <xref:System.ServiceModel.Channels.TcpConnectionPoolSettings>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="4ad13-142">Transportes</span><span class="sxs-lookup"><span data-stu-id="4ad13-142">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="4ad13-143">Elección del transporte</span><span class="sxs-lookup"><span data-stu-id="4ad13-143">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="4ad13-144">Enlaces</span><span class="sxs-lookup"><span data-stu-id="4ad13-144">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="4ad13-145">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="4ad13-145">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="4ad13-146">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="4ad13-146">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="4ad13-147">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="4ad13-147">\<customBinding></span></span>](custombinding.md)
