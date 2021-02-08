---
description: 'Más información acerca de: <connectionPoolSettings>'
title: <connectionPoolSettings>
ms.date: 03/30/2017
ms.assetid: 6fa7fa65-2c6e-4eab-b8cf-7690112c0be5
ms.openlocfilehash: 5acf2d800f1a18f45750d0fabd23516f987b2c5e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99782174"
---
# \<connectionPoolSettings>

<span data-ttu-id="eab0b-102">Especifica valores adicionales del grupo de conexiones para un enlace de canalización con nombre.</span><span class="sxs-lookup"><span data-stu-id="eab0b-102">Specifies additional connection pool settings for a Named Pipe binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedPipeTransport>**](namedpipetransport.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<connectionPoolSettings>**  
  
## <a name="syntax"></a><span data-ttu-id="eab0b-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="eab0b-103">Syntax</span></span>  
  
```xml  
<connectionPoolSettings groupName="String"
                        idleTimeout="TimeSpan"
                        maxOutboundConnectionsPerEndpoint="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eab0b-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="eab0b-104">Attributes and Elements</span></span>  

 <span data-ttu-id="eab0b-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="eab0b-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eab0b-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="eab0b-106">Attributes</span></span>  
  
|<span data-ttu-id="eab0b-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="eab0b-107">Attribute</span></span>|<span data-ttu-id="eab0b-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="eab0b-108">Description</span></span>|  
|---------------|-----------------|  
|`groupName`|<span data-ttu-id="eab0b-109">Una cadena que define el nombre del grupo de conexiones que se usa para canales salientes.</span><span class="sxs-lookup"><span data-stu-id="eab0b-109">A string that defines the name of the connection pool used for outgoing channels.</span></span> <span data-ttu-id="eab0b-110">En modo de transmisión, las conexiones no se comparten, lo cual significa que la agrupación de conexiones está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="eab0b-110">In streamed mode, connections are not shared, meaning that connection pooling is disabled.</span></span> <span data-ttu-id="eab0b-111">La cadena predeterminada es “default”.</span><span class="sxs-lookup"><span data-stu-id="eab0b-111">The default is a "default" string.</span></span> <span data-ttu-id="eab0b-112">Puede modificar este valor para aislar las conexiones para un cliente determinado en grupos independientes.</span><span class="sxs-lookup"><span data-stu-id="eab0b-112">You can modify this value to isolate the connections for a particular client into separate groups.</span></span>|  
|`idleTimeout`|<span data-ttu-id="eab0b-113">Un <xref:System.TimeSpan> positivo que especifica el tiempo máximo que la conexión puede estar inactiva antes de que se desconecte.</span><span class="sxs-lookup"><span data-stu-id="eab0b-113">A positive <xref:System.TimeSpan> that specifies the maximum time the connection can be idle before being disconnected.</span></span> <span data-ttu-id="eab0b-114">El valor predeterminado es 00:02:00.</span><span class="sxs-lookup"><span data-stu-id="eab0b-114">The default is 00:02:00.</span></span>|  
|`maxOutboundConnectionsPerEndpoint`|<span data-ttu-id="eab0b-115">Un entero positivo que especifica el número máximo de conexiones a un punto de conexión remoto que inicia el servicio.</span><span class="sxs-lookup"><span data-stu-id="eab0b-115">A positive integer that specifies the maximum number of connections to a remote endpoint initiated by the service.</span></span> <span data-ttu-id="eab0b-116">Las conexiones que sobrepasen el límite se pondrán a la cola hasta que quede disponible un espacio por debajo del límite.</span><span class="sxs-lookup"><span data-stu-id="eab0b-116">Connections in excess of the limit are queued until a space below the limit becomes available.</span></span> <span data-ttu-id="eab0b-117">`idleTimeout` limita la duración en la que las conexiones siguen en cola antes de que se inicie una excepción.</span><span class="sxs-lookup"><span data-stu-id="eab0b-117">The `idleTimeout` limits the duration in which connections remain queued before an exception is thrown.</span></span> <span data-ttu-id="eab0b-118">El valor predeterminado es 10.</span><span class="sxs-lookup"><span data-stu-id="eab0b-118">The default is 10.</span></span><br /><br /> <span data-ttu-id="eab0b-119">Este atributo limita el número de conexiones activas simultáneas del cliente a un extremo de servicio determinado.</span><span class="sxs-lookup"><span data-stu-id="eab0b-119">This attribute limits the number of simultaneous active connections from the client to a particular service endpoint.</span></span> <span data-ttu-id="eab0b-120">Si este valor se supera debido a más conexiones de cliente activas, el servicio puede se le muestre al cliente sin respuesta.</span><span class="sxs-lookup"><span data-stu-id="eab0b-120">If this value is exceeded by having more active client connections, the service may appear unresponsive to the client.</span></span> <span data-ttu-id="eab0b-121">En este caso, este valor se debería ajustar para superar el número máximo de conexiones de cliente simultáneas esperadas a un extremo determinado.</span><span class="sxs-lookup"><span data-stu-id="eab0b-121">In this case, this value should be adjusted to exceed the maximum number of expected simultaneous client connections to a specific endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="eab0b-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="eab0b-122">Child Elements</span></span>  

 <span data-ttu-id="eab0b-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="eab0b-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="eab0b-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="eab0b-124">Parent Elements</span></span>  
  
|<span data-ttu-id="eab0b-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="eab0b-125">Element</span></span>|<span data-ttu-id="eab0b-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="eab0b-126">Description</span></span>|  
|-------------|-----------------|  
|[\<namedPipeTransport>](namedpipetransport.md)|<span data-ttu-id="eab0b-127">Define un transporte que hace que un canal transfiera mensajes mediante canalizaciones con nombre.</span><span class="sxs-lookup"><span data-stu-id="eab0b-127">Defines a transport that causes a channel to transfer messages using named pipes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="eab0b-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="eab0b-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.NamedPipeConnectionPoolSettingsElement>
- <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement.ConnectionPoolSettings%2A>
- <xref:System.ServiceModel.Channels.NamedPipeConnectionPoolSettings>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="eab0b-129">Transportes</span><span class="sxs-lookup"><span data-stu-id="eab0b-129">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="eab0b-130">Elección del transporte</span><span class="sxs-lookup"><span data-stu-id="eab0b-130">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="eab0b-131">Enlaces</span><span class="sxs-lookup"><span data-stu-id="eab0b-131">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="eab0b-132">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="eab0b-132">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="eab0b-133">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="eab0b-133">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
