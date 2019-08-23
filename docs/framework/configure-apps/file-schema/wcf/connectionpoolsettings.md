---
title: <connectionPoolSettings>
ms.date: 03/30/2017
ms.assetid: 6fa7fa65-2c6e-4eab-b8cf-7690112c0be5
ms.openlocfilehash: 3c8d905a04f8f6d7ecff9b0ef9e7d3c8afa727e3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925973"
---
# <a name="connectionpoolsettings"></a><span data-ttu-id="c1b26-101">\<connectionPoolSettings></span><span class="sxs-lookup"><span data-stu-id="c1b26-101">\<connectionPoolSettings></span></span>
<span data-ttu-id="c1b26-102">Especifica valores adicionales del grupo de conexiones para un enlace de canalización con nombre.</span><span class="sxs-lookup"><span data-stu-id="c1b26-102">Specifies additional connection pool settings for a Named Pipe binding.</span></span>  
  
 <span data-ttu-id="c1b26-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="c1b26-103">\<system.serviceModel></span></span>  
<span data-ttu-id="c1b26-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="c1b26-104">\<bindings></span></span>  
<span data-ttu-id="c1b26-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="c1b26-105">\<customBinding></span></span>  
<span data-ttu-id="c1b26-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="c1b26-106">\<binding></span></span>  
<span data-ttu-id="c1b26-107">\<namePipeTransport></span><span class="sxs-lookup"><span data-stu-id="c1b26-107">\<namePipeTransport></span></span>  
<span data-ttu-id="c1b26-108">\<connectionPoolSettings></span><span class="sxs-lookup"><span data-stu-id="c1b26-108">\<connectionPoolSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1b26-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c1b26-109">Syntax</span></span>  
  
```xml  
<connectionPoolSettings groupName="String"
                        idleTimeout="TimeSpan"
                        maxOutboundConnectionsPerEndpoint="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c1b26-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c1b26-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c1b26-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c1b26-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c1b26-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="c1b26-112">Attributes</span></span>  
  
|<span data-ttu-id="c1b26-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="c1b26-113">Attribute</span></span>|<span data-ttu-id="c1b26-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="c1b26-114">Description</span></span>|  
|---------------|-----------------|  
|`groupName`|<span data-ttu-id="c1b26-115">Una cadena que define el nombre del grupo de conexiones que se usa para canales salientes.</span><span class="sxs-lookup"><span data-stu-id="c1b26-115">A string that defines the name of the connection pool used for outgoing channels.</span></span> <span data-ttu-id="c1b26-116">En modo de transmisión, las conexiones no se comparten, lo cual significa que la agrupación de conexiones está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="c1b26-116">In streamed mode, connections are not shared, meaning that connection pooling is disabled.</span></span> <span data-ttu-id="c1b26-117">La cadena predeterminada es “default”.</span><span class="sxs-lookup"><span data-stu-id="c1b26-117">The default is a "default" string.</span></span> <span data-ttu-id="c1b26-118">Puede modificar este valor para aislar las conexiones para un cliente determinado en grupos independientes.</span><span class="sxs-lookup"><span data-stu-id="c1b26-118">You can modify this value to isolate the connections for a particular client into separate groups.</span></span>|  
|`idleTimeout`|<span data-ttu-id="c1b26-119">Un <xref:System.TimeSpan> positivo que especifica el tiempo máximo que la conexión puede estar inactiva antes de que se desconecte.</span><span class="sxs-lookup"><span data-stu-id="c1b26-119">A positive <xref:System.TimeSpan> that specifies the maximum time the connection can be idle before being disconnected.</span></span> <span data-ttu-id="c1b26-120">El valor predeterminado es 00:02:00.</span><span class="sxs-lookup"><span data-stu-id="c1b26-120">The default is 00:02:00.</span></span>|  
|`maxOutboundConnectionsPerEndpoint`|<span data-ttu-id="c1b26-121">Un entero positivo que especifica el número máximo de conexiones a un punto de conexión remoto que inicia el servicio.</span><span class="sxs-lookup"><span data-stu-id="c1b26-121">A positive integer that specifies the maximum number of connections to a remote endpoint initiated by the service.</span></span> <span data-ttu-id="c1b26-122">Las conexiones que sobrepasen el límite se pondrán a la cola hasta que quede disponible un espacio por debajo del límite.</span><span class="sxs-lookup"><span data-stu-id="c1b26-122">Connections in excess of the limit are queued until a space below the limit becomes available.</span></span> <span data-ttu-id="c1b26-123">`idleTimeout` limita la duración en la que las conexiones siguen en cola antes de que se inicie una excepción.</span><span class="sxs-lookup"><span data-stu-id="c1b26-123">The `idleTimeout` limits the duration in which connections remain queued before an exception is thrown.</span></span> <span data-ttu-id="c1b26-124">El valor predeterminado es 10.</span><span class="sxs-lookup"><span data-stu-id="c1b26-124">The default is 10.</span></span><br /><br /> <span data-ttu-id="c1b26-125">Este atributo limita el número de conexiones activas simultáneas del cliente a un extremo de servicio determinado.</span><span class="sxs-lookup"><span data-stu-id="c1b26-125">This attribute limits the number of simultaneous active connections from the client to a particular service endpoint.</span></span> <span data-ttu-id="c1b26-126">Si este valor se supera debido a más conexiones de cliente activas, el servicio puede se le muestre al cliente sin respuesta.</span><span class="sxs-lookup"><span data-stu-id="c1b26-126">If this value is exceeded by having more active client connections, the service may appear unresponsive to the client.</span></span> <span data-ttu-id="c1b26-127">En este caso, este valor se debería ajustar para superar el número máximo de conexiones de cliente simultáneas esperadas a un extremo determinado.</span><span class="sxs-lookup"><span data-stu-id="c1b26-127">In this case, this value should be adjusted to exceed the maximum number of expected simultaneous client connections to a specific endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c1b26-128">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c1b26-128">Child Elements</span></span>  
 <span data-ttu-id="c1b26-129">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c1b26-129">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c1b26-130">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c1b26-130">Parent Elements</span></span>  
  
|<span data-ttu-id="c1b26-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="c1b26-131">Element</span></span>|<span data-ttu-id="c1b26-132">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="c1b26-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c1b26-133">\<namedPipeTransport></span><span class="sxs-lookup"><span data-stu-id="c1b26-133">\<namedPipeTransport></span></span>](namedpipetransport.md)|<span data-ttu-id="c1b26-134">Define un transporte que hace que un canal transfiera mensajes mediante canalizaciones con nombre.</span><span class="sxs-lookup"><span data-stu-id="c1b26-134">Defines a transport that causes a channel to transfer messages using named pipes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c1b26-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="c1b26-135">See also</span></span>

- <xref:System.ServiceModel.Configuration.NamedPipeConnectionPoolSettingsElement>
- <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement.ConnectionPoolSettings%2A>
- <xref:System.ServiceModel.Channels.NamedPipeConnectionPoolSettings>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="c1b26-136">Transportes</span><span class="sxs-lookup"><span data-stu-id="c1b26-136">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="c1b26-137">Elección del transporte</span><span class="sxs-lookup"><span data-stu-id="c1b26-137">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="c1b26-138">Enlaces</span><span class="sxs-lookup"><span data-stu-id="c1b26-138">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="c1b26-139">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="c1b26-139">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="c1b26-140">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="c1b26-140">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="c1b26-141">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="c1b26-141">\<customBinding></span></span>](custombinding.md)
