---
title: <connectionPoolSettings> de <tcpTransport>
ms.date: 03/30/2017
ms.assetid: 2fbc3aa7-fcc9-4193-99a3-85d31d60d3f7
ms.openlocfilehash: f9b0fff741c32c1a3d6f9461f478e89acc18114e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398099"
---
# <a name="connectionpoolsettings-of-tcptransport"></a><span data-ttu-id="80443-102">\<connectionPoolSettings> de \<tcpTransport></span><span class="sxs-lookup"><span data-stu-id="80443-102">\<connectionPoolSettings> of \<tcpTransport></span></span>
<span data-ttu-id="80443-103">Especifica los valores de grupo de conexiones adicionales para un transporte TCP.</span><span class="sxs-lookup"><span data-stu-id="80443-103">Specifies additional connection pool settings for a TCP transport.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<tcpTransport>**](tcptransport.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<connectionPoolSettings>**  
  
## <a name="syntax"></a><span data-ttu-id="80443-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="80443-104">Syntax</span></span>  
  
```xml  
<connectionPoolSettings groupName="String"
                        idleTimeout="TimeSpan"
                        leaseTimeout="TimeSpan"
                        maxOutboundConnectionsPerEndpoint="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="80443-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="80443-105">Attributes and Elements</span></span>  
 <span data-ttu-id="80443-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="80443-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="80443-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="80443-107">Attributes</span></span>  
  
|<span data-ttu-id="80443-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="80443-108">Attribute</span></span>|<span data-ttu-id="80443-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="80443-109">Description</span></span>|  
|---------------|-----------------|  
|`groupName`|<span data-ttu-id="80443-110">Una cadena que define el nombre del grupo de conexiones que se usa para canales salientes.</span><span class="sxs-lookup"><span data-stu-id="80443-110">A string that defines the name of the connection pool used for outgoing channels.</span></span> <span data-ttu-id="80443-111">En modo de transmisión, las conexiones no se comparten, lo cual significa que la agrupación de conexiones está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="80443-111">In streamed mode, connections are not shared, meaning that connection pooling is disabled.</span></span> <span data-ttu-id="80443-112">La cadena predeterminada es “default”.</span><span class="sxs-lookup"><span data-stu-id="80443-112">The default is a "default" string.</span></span> <span data-ttu-id="80443-113">Puede modificar este valor para aislar las conexiones para un cliente determinado en grupos independientes.</span><span class="sxs-lookup"><span data-stu-id="80443-113">You can modify this value to isolate the connections for a particular client into separate groups.</span></span>|  
|`idleTimeout`|<span data-ttu-id="80443-114">Un <xref:System.TimeSpan> positivo que especifica el tiempo máximo que la conexión puede estar inactiva antes de que se desconecte.</span><span class="sxs-lookup"><span data-stu-id="80443-114">A positive <xref:System.TimeSpan> that specifies the maximum time the connection can be idle before being disconnected.</span></span> <span data-ttu-id="80443-115">El valor predeterminado es 00:02:00.</span><span class="sxs-lookup"><span data-stu-id="80443-115">The default is 00:02:00.</span></span>|  
|`leaseTimeout`|<span data-ttu-id="80443-116"><xref:System.TimeSpan> que especifica el tiempo después del que se cierra una conexión activa.</span><span class="sxs-lookup"><span data-stu-id="80443-116">A <xref:System.TimeSpan> that specifies the time after which an active connection is closed.</span></span> <span data-ttu-id="80443-117">El valor predeterminado es 00:05:00.</span><span class="sxs-lookup"><span data-stu-id="80443-117">The default is 00:05:00.</span></span><br /><br /> <span data-ttu-id="80443-118">Se cierra una conexión después de que se haya devuelto a la conexión caché y no durante la transmisión activa.</span><span class="sxs-lookup"><span data-stu-id="80443-118">A connection is closed after it has been returned to the connection cache and not during active transmission.</span></span> <span data-ttu-id="80443-119">El caché de conexión utilizado por el transporte TCP crea conexiones nuevas, como se requiere para cada punto de conexión, hasta el límite del caché establecido por `maxOutboundConnectionsPerEndpoint.`.</span><span class="sxs-lookup"><span data-stu-id="80443-119">The connection cache used by the TCP transport creates new connections as required for each endpoint, up to the cache limit that is set by `maxOutboundConnectionsPerEndpoint.`</span></span>|  
|`maxOutboundConnectionsPerEndpoint`|<span data-ttu-id="80443-120">Un entero positivo que especifica el número máximo de conexiones a un punto de conexión remoto que inicia el servicio.</span><span class="sxs-lookup"><span data-stu-id="80443-120">A positive integer that specifies the maximum number of connections to a remote endpoint initiated by the service.</span></span> <span data-ttu-id="80443-121">Las conexiones que sobrepasen el límite se pondrán a la cola hasta que quede disponible un espacio por debajo del límite.</span><span class="sxs-lookup"><span data-stu-id="80443-121">Connections in excess of the limit are queued until a space below the limit becomes available.</span></span> <span data-ttu-id="80443-122">`idleTimeout` limita la duración en la que las conexiones siguen en cola antes de que se inicie una excepción.</span><span class="sxs-lookup"><span data-stu-id="80443-122">The `idleTimeout` limits the duration in which connections remain queued before an exception is thrown.</span></span> <span data-ttu-id="80443-123">El valor predeterminado es 10.</span><span class="sxs-lookup"><span data-stu-id="80443-123">The default is 10.</span></span><br /><br /> <span data-ttu-id="80443-124">Este atributo limita el número de conexiones activas simultáneas del cliente a un extremo de servicio determinado.</span><span class="sxs-lookup"><span data-stu-id="80443-124">This attribute limits the number of simultaneous active connections from the client to a particular service endpoint.</span></span> <span data-ttu-id="80443-125">Si este valor se supera debido a más conexiones de cliente activas, el servicio puede se le muestre al cliente sin respuesta.</span><span class="sxs-lookup"><span data-stu-id="80443-125">If this value is exceeded by having more active client connections, the service may appear unresponsive to the client.</span></span> <span data-ttu-id="80443-126">En este caso, este valor se debería ajustar para superar el número máximo de conexiones de cliente simultáneas esperadas a un extremo determinado.</span><span class="sxs-lookup"><span data-stu-id="80443-126">In this case, this value should be adjusted to exceed the maximum number of expected simultaneous client connections to a specific endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="80443-127">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="80443-127">Child Elements</span></span>  
 <span data-ttu-id="80443-128">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="80443-128">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="80443-129">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="80443-129">Parent Elements</span></span>  
  
|<span data-ttu-id="80443-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="80443-130">Element</span></span>|<span data-ttu-id="80443-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="80443-131">Description</span></span>|  
|-------------|-----------------|  
|[\<namedPipeTransport>](namedpipetransport.md)|<span data-ttu-id="80443-132">Define un transporte que hace que un canal transfiera mensajes mediante canalizaciones con nombre.</span><span class="sxs-lookup"><span data-stu-id="80443-132">Defines a transport that causes a channel to transfer messages using named pipes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="80443-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="80443-133">See also</span></span>

- <xref:System.ServiceModel.Configuration.TcpConnectionPoolSettingsElement>
- <xref:System.ServiceModel.Channels.TcpTransportBindingElement.ConnectionPoolSettings%2A>
- <xref:System.ServiceModel.Channels.TcpConnectionPoolSettings>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="80443-134">Transportes</span><span class="sxs-lookup"><span data-stu-id="80443-134">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="80443-135">Elección del transporte</span><span class="sxs-lookup"><span data-stu-id="80443-135">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="80443-136">Enlaces</span><span class="sxs-lookup"><span data-stu-id="80443-136">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="80443-137">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="80443-137">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="80443-138">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="80443-138">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
