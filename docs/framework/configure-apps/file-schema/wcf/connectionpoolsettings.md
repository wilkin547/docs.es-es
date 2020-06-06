---
title: <connectionPoolSettings>
ms.date: 03/30/2017
ms.assetid: 6fa7fa65-2c6e-4eab-b8cf-7690112c0be5
ms.openlocfilehash: 842173c7bd9673a1e08c93d5ed650a42b9d979e5
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400480"
---
# \<connectionPoolSettings>
<span data-ttu-id="320de-101">Especifica valores adicionales del grupo de conexiones para un enlace de canalización con nombre.</span><span class="sxs-lookup"><span data-stu-id="320de-101">Specifies additional connection pool settings for a Named Pipe binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedPipeTransport>**](namedpipetransport.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<connectionPoolSettings>**  
  
## <a name="syntax"></a><span data-ttu-id="320de-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="320de-102">Syntax</span></span>  
  
```xml  
<connectionPoolSettings groupName="String"
                        idleTimeout="TimeSpan"
                        maxOutboundConnectionsPerEndpoint="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="320de-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="320de-103">Attributes and Elements</span></span>  
 <span data-ttu-id="320de-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="320de-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="320de-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="320de-105">Attributes</span></span>  
  
|<span data-ttu-id="320de-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="320de-106">Attribute</span></span>|<span data-ttu-id="320de-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="320de-107">Description</span></span>|  
|---------------|-----------------|  
|`groupName`|<span data-ttu-id="320de-108">Una cadena que define el nombre del grupo de conexiones que se usa para canales salientes.</span><span class="sxs-lookup"><span data-stu-id="320de-108">A string that defines the name of the connection pool used for outgoing channels.</span></span> <span data-ttu-id="320de-109">En modo de transmisión, las conexiones no se comparten, lo cual significa que la agrupación de conexiones está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="320de-109">In streamed mode, connections are not shared, meaning that connection pooling is disabled.</span></span> <span data-ttu-id="320de-110">La cadena predeterminada es “default”.</span><span class="sxs-lookup"><span data-stu-id="320de-110">The default is a "default" string.</span></span> <span data-ttu-id="320de-111">Puede modificar este valor para aislar las conexiones para un cliente determinado en grupos independientes.</span><span class="sxs-lookup"><span data-stu-id="320de-111">You can modify this value to isolate the connections for a particular client into separate groups.</span></span>|  
|`idleTimeout`|<span data-ttu-id="320de-112">Un <xref:System.TimeSpan> positivo que especifica el tiempo máximo que la conexión puede estar inactiva antes de que se desconecte.</span><span class="sxs-lookup"><span data-stu-id="320de-112">A positive <xref:System.TimeSpan> that specifies the maximum time the connection can be idle before being disconnected.</span></span> <span data-ttu-id="320de-113">El valor predeterminado es 00:02:00.</span><span class="sxs-lookup"><span data-stu-id="320de-113">The default is 00:02:00.</span></span>|  
|`maxOutboundConnectionsPerEndpoint`|<span data-ttu-id="320de-114">Un entero positivo que especifica el número máximo de conexiones a un punto de conexión remoto que inicia el servicio.</span><span class="sxs-lookup"><span data-stu-id="320de-114">A positive integer that specifies the maximum number of connections to a remote endpoint initiated by the service.</span></span> <span data-ttu-id="320de-115">Las conexiones que sobrepasen el límite se pondrán a la cola hasta que quede disponible un espacio por debajo del límite.</span><span class="sxs-lookup"><span data-stu-id="320de-115">Connections in excess of the limit are queued until a space below the limit becomes available.</span></span> <span data-ttu-id="320de-116">`idleTimeout` limita la duración en la que las conexiones siguen en cola antes de que se inicie una excepción.</span><span class="sxs-lookup"><span data-stu-id="320de-116">The `idleTimeout` limits the duration in which connections remain queued before an exception is thrown.</span></span> <span data-ttu-id="320de-117">El valor predeterminado es 10.</span><span class="sxs-lookup"><span data-stu-id="320de-117">The default is 10.</span></span><br /><br /> <span data-ttu-id="320de-118">Este atributo limita el número de conexiones activas simultáneas del cliente a un extremo de servicio determinado.</span><span class="sxs-lookup"><span data-stu-id="320de-118">This attribute limits the number of simultaneous active connections from the client to a particular service endpoint.</span></span> <span data-ttu-id="320de-119">Si este valor se supera debido a más conexiones de cliente activas, el servicio puede se le muestre al cliente sin respuesta.</span><span class="sxs-lookup"><span data-stu-id="320de-119">If this value is exceeded by having more active client connections, the service may appear unresponsive to the client.</span></span> <span data-ttu-id="320de-120">En este caso, este valor se debería ajustar para superar el número máximo de conexiones de cliente simultáneas esperadas a un extremo determinado.</span><span class="sxs-lookup"><span data-stu-id="320de-120">In this case, this value should be adjusted to exceed the maximum number of expected simultaneous client connections to a specific endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="320de-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="320de-121">Child Elements</span></span>  
 <span data-ttu-id="320de-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="320de-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="320de-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="320de-123">Parent Elements</span></span>  
  
|<span data-ttu-id="320de-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="320de-124">Element</span></span>|<span data-ttu-id="320de-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="320de-125">Description</span></span>|  
|-------------|-----------------|  
|[\<namedPipeTransport>](namedpipetransport.md)|<span data-ttu-id="320de-126">Define un transporte que hace que un canal transfiera mensajes mediante canalizaciones con nombre.</span><span class="sxs-lookup"><span data-stu-id="320de-126">Defines a transport that causes a channel to transfer messages using named pipes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="320de-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="320de-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.NamedPipeConnectionPoolSettingsElement>
- <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement.ConnectionPoolSettings%2A>
- <xref:System.ServiceModel.Channels.NamedPipeConnectionPoolSettings>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="320de-128">Transportes</span><span class="sxs-lookup"><span data-stu-id="320de-128">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="320de-129">Elección del transporte</span><span class="sxs-lookup"><span data-stu-id="320de-129">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="320de-130">Enlaces</span><span class="sxs-lookup"><span data-stu-id="320de-130">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="320de-131">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="320de-131">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="320de-132">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="320de-132">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
