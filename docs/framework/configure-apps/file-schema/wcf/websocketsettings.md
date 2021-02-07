---
description: 'Más información acerca de: <webSocketSettings>'
title: <webSocketSettings>
ms.date: 03/30/2017
ms.assetid: bbf97e02-8dd1-4922-acac-3cd33397b249
ms.openlocfilehash: a0b67a0088491c73ed0214191283ae5292a654b0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99682493"
---
# \<webSocketSettings>

<span data-ttu-id="6d729-102">Un elemento de configuración usado para especificar valores de WebSockets.</span><span class="sxs-lookup"><span data-stu-id="6d729-102">A configuration element used to specify Web Socket settings.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netHttpBinding>**](nethttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webSocketSettings>**  
  
## <a name="syntax"></a><span data-ttu-id="6d729-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6d729-103">Syntax</span></span>  
  
```xml  
<netHttpBinding>
  <binding>
    <webSocketSettings createNotificationOnConnection="Boolean"
                       disablePayloadMasking="Boolean"
                       keepAliveInterval="TimeSpan"
                       maxPendingConnections="Integer"
                       receiveBufferSize="Integer"
                       sendBufferSize="Integer"
                       subProtocol="String"
                       transportUsage="WhenDuplex/Always/Never" />
  </binding>
</netHttpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6d729-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="6d729-104">Attributes and Elements</span></span>  

 <span data-ttu-id="6d729-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="6d729-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6d729-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="6d729-106">Attributes</span></span>  
  
|<span data-ttu-id="6d729-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="6d729-107">Attribute</span></span>|<span data-ttu-id="6d729-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="6d729-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6d729-109">createNotificationOnConnection</span><span class="sxs-lookup"><span data-stu-id="6d729-109">createNotificationOnConnection</span></span>|<span data-ttu-id="6d729-110">Especifica si se envía una notificación al realizar la conexión.</span><span class="sxs-lookup"><span data-stu-id="6d729-110">Specifies whether a notification is sent upon connection.</span></span>|  
|<span data-ttu-id="6d729-111">disablePayloadMasking</span><span class="sxs-lookup"><span data-stu-id="6d729-111">disablePayloadMasking</span></span>|<span data-ttu-id="6d729-112">Especifica si el enmascaramiento de WebSocket está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="6d729-112">Specifies whether Web Socket masking is disabled.</span></span>|  
|<span data-ttu-id="6d729-113">keepAliveInterval</span><span class="sxs-lookup"><span data-stu-id="6d729-113">keepAliveInterval</span></span>|<span data-ttu-id="6d729-114">Especifica el intervalo entre mensajes de mantenimiento de conexión.</span><span class="sxs-lookup"><span data-stu-id="6d729-114">Specifies the keep alive interval.</span></span>|  
|<span data-ttu-id="6d729-115">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="6d729-115">maxPendingConnections</span></span>|<span data-ttu-id="6d729-116">Especifica el número máximo de conexiones pendientes de distribución en el servicio.</span><span class="sxs-lookup"><span data-stu-id="6d729-116">Specifies the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="6d729-117">receiveBufferSize</span><span class="sxs-lookup"><span data-stu-id="6d729-117">receiveBufferSize</span></span>|<span data-ttu-id="6d729-118">Especifica el tamaño de búfer de recibir.</span><span class="sxs-lookup"><span data-stu-id="6d729-118">Specifies the size of the receive buffer.</span></span>|  
|<span data-ttu-id="6d729-119">sendBufferSize</span><span class="sxs-lookup"><span data-stu-id="6d729-119">sendBufferSize</span></span>|<span data-ttu-id="6d729-120">Especifica el tamaño de búfer de enviar.</span><span class="sxs-lookup"><span data-stu-id="6d729-120">Specifies the size of the send buffer.</span></span>|  
|<span data-ttu-id="6d729-121">subProtocol</span><span class="sxs-lookup"><span data-stu-id="6d729-121">subProtocol</span></span>|<span data-ttu-id="6d729-122">Especifica el subprotocolo WebSocket.</span><span class="sxs-lookup"><span data-stu-id="6d729-122">Specifies the Web Socket subprotocol.</span></span>|  
|<span data-ttu-id="6d729-123">transportUsage</span><span class="sxs-lookup"><span data-stu-id="6d729-123">transportUsage</span></span>|<span data-ttu-id="6d729-124">Especifica cuándo usar WebSockets.</span><span class="sxs-lookup"><span data-stu-id="6d729-124">Specifies when to use Web Sockets.</span></span>|  
  
## <a name="transportusage-attribute"></a><span data-ttu-id="6d729-125">Atributo transportUsage</span><span class="sxs-lookup"><span data-stu-id="6d729-125">transportUsage Attribute</span></span>  
  
|<span data-ttu-id="6d729-126">Value</span><span class="sxs-lookup"><span data-stu-id="6d729-126">Value</span></span>|<span data-ttu-id="6d729-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="6d729-127">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6d729-128">WhenDuplex</span><span class="sxs-lookup"><span data-stu-id="6d729-128">WhenDuplex</span></span>|<span data-ttu-id="6d729-129">Use el protocolo WebSocket cuando el contrato sea dúplex.</span><span class="sxs-lookup"><span data-stu-id="6d729-129">Use the Web Socket protocol when the contract is duplex.</span></span>|  
|<span data-ttu-id="6d729-130">Siempre</span><span class="sxs-lookup"><span data-stu-id="6d729-130">Always</span></span>|<span data-ttu-id="6d729-131">Use siempre el protocolo WebSocket independientemente del contrato.</span><span class="sxs-lookup"><span data-stu-id="6d729-131">Always use the Web Socket protocol regardless of the contract.</span></span>|  
|<span data-ttu-id="6d729-132">Nunca</span><span class="sxs-lookup"><span data-stu-id="6d729-132">Never</span></span>|<span data-ttu-id="6d729-133">Nunca use el protocolo WebSocket.</span><span class="sxs-lookup"><span data-stu-id="6d729-133">Never use the Web Socket protocol.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6d729-134">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="6d729-134">Child Elements</span></span>  

 <span data-ttu-id="6d729-135">None</span><span class="sxs-lookup"><span data-stu-id="6d729-135">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6d729-136">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="6d729-136">Parent Elements</span></span>  
  
|<span data-ttu-id="6d729-137">Elemento</span><span class="sxs-lookup"><span data-stu-id="6d729-137">Element</span></span>|<span data-ttu-id="6d729-138">Descripción</span><span class="sxs-lookup"><span data-stu-id="6d729-138">Description</span></span>|  
|-------------|-----------------|  
|\<netHttpBinding>|<span data-ttu-id="6d729-139">Especifica el NetHttpBinding</span><span class="sxs-lookup"><span data-stu-id="6d729-139">Specifies the NetHttpBinding</span></span>|  
  
## <a name="example"></a><span data-ttu-id="6d729-140">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6d729-140">Example</span></span>  

 <span data-ttu-id="6d729-141">El ejemplo siguiente muestra cómo usar el elemento \<webSocketSettings>.</span><span class="sxs-lookup"><span data-stu-id="6d729-141">The following example shows how to use the \<webSocketSettings> element.</span></span>  
  
```xml  
<netHttpBinding>
  <binding>
    <webSocketSettings createNotificationOnConnection="true"
                       disablePayloadMasking="false"
                       keepAliveInterval="00:10:00"
                       maxPendingConnections="100"
                       receiveBufferSize="1000"
                       sendBufferSize="1000"
                       subProtocol="Soap"
                       transportUsage="WhenDuplex/Always/Never" />
  </binding>
</netHttpBinding>
```  
  
## <a name="see-also"></a><span data-ttu-id="6d729-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="6d729-142">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>
- [<span data-ttu-id="6d729-143">Enlaces</span><span class="sxs-lookup"><span data-stu-id="6d729-143">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="6d729-144">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="6d729-144">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="6d729-145">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="6d729-145">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
