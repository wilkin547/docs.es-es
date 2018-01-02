---
title: '&lt;connectionPoolSettings&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6fa7fa65-2c6e-4eab-b8cf-7690112c0be5
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 11500830c7c5fd75a9e2880a5875bd21fb070634
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltconnectionpoolsettingsgt"></a><span data-ttu-id="0de32-102">&lt;connectionPoolSettings&gt;</span><span class="sxs-lookup"><span data-stu-id="0de32-102">&lt;connectionPoolSettings&gt;</span></span>
<span data-ttu-id="0de32-103">Especifica valores adicionales del grupo de conexiones para un enlace de canalización con nombre.</span><span class="sxs-lookup"><span data-stu-id="0de32-103">Specifies additional connection pool settings for a Named Pipe binding.</span></span>  
  
 <span data-ttu-id="0de32-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="0de32-104">\<system.serviceModel></span></span>  
<span data-ttu-id="0de32-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="0de32-105">\<bindings></span></span>  
<span data-ttu-id="0de32-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="0de32-106">\<customBinding></span></span>  
<span data-ttu-id="0de32-107">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="0de32-107">\<binding></span></span>  
<span data-ttu-id="0de32-108">\<namePipeTransport ></span><span class="sxs-lookup"><span data-stu-id="0de32-108">\<namePipeTransport></span></span>  
<span data-ttu-id="0de32-109">\<connectionPoolSettings ></span><span class="sxs-lookup"><span data-stu-id="0de32-109">\<connectionPoolSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0de32-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0de32-110">Syntax</span></span>  
  
```xml  
<connectionPoolSettings  
        groupName="String"  
    idleTimeout"TimeSpan"  
    maxOutboundConnectionsPerEndpopint="Integer" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0de32-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="0de32-111">Attributes and Elements</span></span>  
 <span data-ttu-id="0de32-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="0de32-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0de32-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="0de32-113">Attributes</span></span>  
  
|<span data-ttu-id="0de32-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="0de32-114">Attribute</span></span>|<span data-ttu-id="0de32-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="0de32-115">Description</span></span>|  
|---------------|-----------------|  
|`groupName`|<span data-ttu-id="0de32-116">Una cadena que define el nombre del grupo de conexiones que se usa para canales salientes.</span><span class="sxs-lookup"><span data-stu-id="0de32-116">A string that defines the name of the connection pool used for outgoing channels.</span></span> <span data-ttu-id="0de32-117">En modo de transmisión, las conexiones no se comparten, lo cual significa que la agrupación de conexiones está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="0de32-117">In streamed mode, connections are not shared, meaning that connection pooling is disabled.</span></span> <span data-ttu-id="0de32-118">La cadena predeterminada es “default”.</span><span class="sxs-lookup"><span data-stu-id="0de32-118">The default is a "default" string.</span></span> <span data-ttu-id="0de32-119">Puede modificar este valor para aislar las conexiones para un cliente determinado en grupos independientes.</span><span class="sxs-lookup"><span data-stu-id="0de32-119">You can modify this value to isolate the connections for a particular client into separate groups.</span></span>|  
|`idleTimeout`|<span data-ttu-id="0de32-120">Un <xref:System.TimeSpan> positivo que especifica el tiempo máximo que la conexión puede estar inactiva antes de que se desconecte.</span><span class="sxs-lookup"><span data-stu-id="0de32-120">A positive <xref:System.TimeSpan> that specifies the maximum time the connection can be idle before being disconnected.</span></span> <span data-ttu-id="0de32-121">El valor predeterminado es 00:02:00.</span><span class="sxs-lookup"><span data-stu-id="0de32-121">The default is 00:02:00.</span></span>|  
|`maxOutboundConnectionsPerEndpoint`|<span data-ttu-id="0de32-122">Un entero positivo que especifica el número máximo de conexiones a un extremo remoto que inicia el servicio.</span><span class="sxs-lookup"><span data-stu-id="0de32-122">A positive integer that specifies the maximum number of connections to a remote endpoint initiated by the service.</span></span> <span data-ttu-id="0de32-123">Las conexiones que sobrepasen el límite se pondrán a la cola hasta que quede disponible un espacio por debajo del límite.</span><span class="sxs-lookup"><span data-stu-id="0de32-123">Connections in excess of the limit are queued until a space below the limit becomes available.</span></span> <span data-ttu-id="0de32-124">`idleTimeout` limita la duración en la que las conexiones siguen en cola antes de que se inicie una excepción.</span><span class="sxs-lookup"><span data-stu-id="0de32-124">The `idleTimeout` limits the duration in which connections remain queued before an exception is thrown.</span></span> <span data-ttu-id="0de32-125">El valor predeterminado es 10.</span><span class="sxs-lookup"><span data-stu-id="0de32-125">The default is 10.</span></span><br /><br /> <span data-ttu-id="0de32-126">Este atributo limita el número de conexiones activas simultáneas del cliente a un extremo de servicio determinado.</span><span class="sxs-lookup"><span data-stu-id="0de32-126">This attribute limits the number of simultaneous active connections from the client to a particular service endpoint.</span></span> <span data-ttu-id="0de32-127">Si este valor se supera debido a más conexiones de cliente activas, el servicio puede se le muestre al cliente sin respuesta.</span><span class="sxs-lookup"><span data-stu-id="0de32-127">If this value is exceeded by having more active client connections, the service may appear unresponsive to the client.</span></span> <span data-ttu-id="0de32-128">En este caso, este valor se debería ajustar para superar el número máximo de conexiones de cliente simultáneas esperadas a un punto de conexión determinado.</span><span class="sxs-lookup"><span data-stu-id="0de32-128">In this case, this value should be adjusted to exceed the maximum number of expected simultaneous client connections to a specific endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0de32-129">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0de32-129">Child Elements</span></span>  
 <span data-ttu-id="0de32-130">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="0de32-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0de32-131">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0de32-131">Parent Elements</span></span>  
  
|<span data-ttu-id="0de32-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="0de32-132">Element</span></span>|<span data-ttu-id="0de32-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="0de32-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0de32-134">\<namedPipeTransport ></span><span class="sxs-lookup"><span data-stu-id="0de32-134">\<namedPipeTransport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/namedpipetransport.md)|<span data-ttu-id="0de32-135">Define un transporte que hace que un canal transfiera mensajes mediante canalizaciones con nombre.</span><span class="sxs-lookup"><span data-stu-id="0de32-135">Defines a transport that causes a channel to transfer messages using named pipes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0de32-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="0de32-136">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.NamedPipeConnectionPoolSettingsElement>  
 <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement.ConnectionPoolSettings%2A>  
 <xref:System.ServiceModel.Channels.NamedPipeConnectionPoolSettings>  
 <xref:System.ServiceModel.Channels.TransportBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="0de32-137">Transportes</span><span class="sxs-lookup"><span data-stu-id="0de32-137">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)  
 [<span data-ttu-id="0de32-138">Elección del transporte</span><span class="sxs-lookup"><span data-stu-id="0de32-138">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 [<span data-ttu-id="0de32-139">Enlaces</span><span class="sxs-lookup"><span data-stu-id="0de32-139">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="0de32-140">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="0de32-140">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="0de32-141">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="0de32-141">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="0de32-142">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="0de32-142">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
