---
title: '&lt;connectionPoolSettings&gt;'
ms.date: 03/30/2017
ms.assetid: 6fa7fa65-2c6e-4eab-b8cf-7690112c0be5
ms.openlocfilehash: 1e3001f60ae0f18fee88678cae1e9e55d90822c9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54526773"
---
# <a name="ltconnectionpoolsettingsgt"></a><span data-ttu-id="4f42c-102">&lt;connectionPoolSettings&gt;</span><span class="sxs-lookup"><span data-stu-id="4f42c-102">&lt;connectionPoolSettings&gt;</span></span>
<span data-ttu-id="4f42c-103">Especifica valores adicionales del grupo de conexiones para un enlace de canalización con nombre.</span><span class="sxs-lookup"><span data-stu-id="4f42c-103">Specifies additional connection pool settings for a Named Pipe binding.</span></span>  
  
 <span data-ttu-id="4f42c-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="4f42c-104">\<system.serviceModel></span></span>  
<span data-ttu-id="4f42c-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="4f42c-105">\<bindings></span></span>  
<span data-ttu-id="4f42c-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="4f42c-106">\<customBinding></span></span>  
<span data-ttu-id="4f42c-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="4f42c-107">\<binding></span></span>  
<span data-ttu-id="4f42c-108">\<namePipeTransport></span><span class="sxs-lookup"><span data-stu-id="4f42c-108">\<namePipeTransport></span></span>  
<span data-ttu-id="4f42c-109">\<connectionPoolSettings></span><span class="sxs-lookup"><span data-stu-id="4f42c-109">\<connectionPoolSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f42c-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4f42c-110">Syntax</span></span>  
  
```xml  
<connectionPoolSettings groupName="String"
                        idleTimeout="TimeSpan"
                        maxOutboundConnectionsPerEndpopint="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4f42c-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4f42c-111">Attributes and Elements</span></span>  
 <span data-ttu-id="4f42c-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="4f42c-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4f42c-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="4f42c-113">Attributes</span></span>  
  
|<span data-ttu-id="4f42c-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="4f42c-114">Attribute</span></span>|<span data-ttu-id="4f42c-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="4f42c-115">Description</span></span>|  
|---------------|-----------------|  
|`groupName`|<span data-ttu-id="4f42c-116">Una cadena que define el nombre del grupo de conexiones que se usa para canales salientes.</span><span class="sxs-lookup"><span data-stu-id="4f42c-116">A string that defines the name of the connection pool used for outgoing channels.</span></span> <span data-ttu-id="4f42c-117">En modo de transmisión, las conexiones no se comparten, lo cual significa que la agrupación de conexiones está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="4f42c-117">In streamed mode, connections are not shared, meaning that connection pooling is disabled.</span></span> <span data-ttu-id="4f42c-118">La cadena predeterminada es “default”.</span><span class="sxs-lookup"><span data-stu-id="4f42c-118">The default is a "default" string.</span></span> <span data-ttu-id="4f42c-119">Puede modificar este valor para aislar las conexiones para un cliente determinado en grupos independientes.</span><span class="sxs-lookup"><span data-stu-id="4f42c-119">You can modify this value to isolate the connections for a particular client into separate groups.</span></span>|  
|`idleTimeout`|<span data-ttu-id="4f42c-120">Un <xref:System.TimeSpan> positivo que especifica el tiempo máximo que la conexión puede estar inactiva antes de que se desconecte.</span><span class="sxs-lookup"><span data-stu-id="4f42c-120">A positive <xref:System.TimeSpan> that specifies the maximum time the connection can be idle before being disconnected.</span></span> <span data-ttu-id="4f42c-121">El valor predeterminado es 00:02:00.</span><span class="sxs-lookup"><span data-stu-id="4f42c-121">The default is 00:02:00.</span></span>|  
|`maxOutboundConnectionsPerEndpoint`|<span data-ttu-id="4f42c-122">Un entero positivo que especifica el número máximo de conexiones a un extremo remoto que inicia el servicio.</span><span class="sxs-lookup"><span data-stu-id="4f42c-122">A positive integer that specifies the maximum number of connections to a remote endpoint initiated by the service.</span></span> <span data-ttu-id="4f42c-123">Las conexiones que sobrepasen el límite se pondrán a la cola hasta que quede disponible un espacio por debajo del límite.</span><span class="sxs-lookup"><span data-stu-id="4f42c-123">Connections in excess of the limit are queued until a space below the limit becomes available.</span></span> <span data-ttu-id="4f42c-124">`idleTimeout` limita la duración en la que las conexiones siguen en cola antes de que se inicie una excepción.</span><span class="sxs-lookup"><span data-stu-id="4f42c-124">The `idleTimeout` limits the duration in which connections remain queued before an exception is thrown.</span></span> <span data-ttu-id="4f42c-125">El valor predeterminado es 10.</span><span class="sxs-lookup"><span data-stu-id="4f42c-125">The default is 10.</span></span><br /><br /> <span data-ttu-id="4f42c-126">Este atributo limita el número de conexiones activas simultáneas del cliente a un extremo de servicio determinado.</span><span class="sxs-lookup"><span data-stu-id="4f42c-126">This attribute limits the number of simultaneous active connections from the client to a particular service endpoint.</span></span> <span data-ttu-id="4f42c-127">Si este valor se supera debido a más conexiones de cliente activas, el servicio puede se le muestre al cliente sin respuesta.</span><span class="sxs-lookup"><span data-stu-id="4f42c-127">If this value is exceeded by having more active client connections, the service may appear unresponsive to the client.</span></span> <span data-ttu-id="4f42c-128">En este caso, este valor se debería ajustar para superar el número máximo de conexiones de cliente simultáneas esperadas a un punto de conexión determinado.</span><span class="sxs-lookup"><span data-stu-id="4f42c-128">In this case, this value should be adjusted to exceed the maximum number of expected simultaneous client connections to a specific endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4f42c-129">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4f42c-129">Child Elements</span></span>  
 <span data-ttu-id="4f42c-130">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="4f42c-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4f42c-131">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4f42c-131">Parent Elements</span></span>  
  
|<span data-ttu-id="4f42c-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="4f42c-132">Element</span></span>|<span data-ttu-id="4f42c-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="4f42c-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4f42c-134">\<namedPipeTransport></span><span class="sxs-lookup"><span data-stu-id="4f42c-134">\<namedPipeTransport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/namedpipetransport.md)|<span data-ttu-id="4f42c-135">Define un transporte que hace que un canal transfiera mensajes mediante canalizaciones con nombre.</span><span class="sxs-lookup"><span data-stu-id="4f42c-135">Defines a transport that causes a channel to transfer messages using named pipes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4f42c-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="4f42c-136">See also</span></span>
- <xref:System.ServiceModel.Configuration.NamedPipeConnectionPoolSettingsElement>
- <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement.ConnectionPoolSettings%2A>
- <xref:System.ServiceModel.Channels.NamedPipeConnectionPoolSettings>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="4f42c-137">Transportes</span><span class="sxs-lookup"><span data-stu-id="4f42c-137">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)
- [<span data-ttu-id="4f42c-138">Elección del transporte</span><span class="sxs-lookup"><span data-stu-id="4f42c-138">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="4f42c-139">Enlaces</span><span class="sxs-lookup"><span data-stu-id="4f42c-139">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="4f42c-140">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="4f42c-140">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="4f42c-141">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="4f42c-141">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="4f42c-142">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="4f42c-142">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
