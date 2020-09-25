---
title: <webSocketSettings>
ms.date: 03/30/2017
ms.assetid: bbf97e02-8dd1-4922-acac-3cd33397b249
ms.openlocfilehash: 6cfddfb9ebfc7c3447af977e14738baabebc8fe9
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177856"
---
# \<webSocketSettings>

<span data-ttu-id="bec21-101">Un elemento de configuración usado para especificar valores de WebSockets.</span><span class="sxs-lookup"><span data-stu-id="bec21-101">A configuration element used to specify Web Socket settings.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netHttpBinding>**](nethttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webSocketSettings>**  
  
## <a name="syntax"></a><span data-ttu-id="bec21-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bec21-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bec21-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="bec21-103">Attributes and Elements</span></span>  

 <span data-ttu-id="bec21-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="bec21-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bec21-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="bec21-105">Attributes</span></span>  
  
|<span data-ttu-id="bec21-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="bec21-106">Attribute</span></span>|<span data-ttu-id="bec21-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="bec21-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bec21-108">createNotificationOnConnection</span><span class="sxs-lookup"><span data-stu-id="bec21-108">createNotificationOnConnection</span></span>|<span data-ttu-id="bec21-109">Especifica si se envía una notificación al realizar la conexión.</span><span class="sxs-lookup"><span data-stu-id="bec21-109">Specifies whether a notification is sent upon connection.</span></span>|  
|<span data-ttu-id="bec21-110">disablePayloadMasking</span><span class="sxs-lookup"><span data-stu-id="bec21-110">disablePayloadMasking</span></span>|<span data-ttu-id="bec21-111">Especifica si el enmascaramiento de WebSocket está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="bec21-111">Specifies whether Web Socket masking is disabled.</span></span>|  
|<span data-ttu-id="bec21-112">keepAliveInterval</span><span class="sxs-lookup"><span data-stu-id="bec21-112">keepAliveInterval</span></span>|<span data-ttu-id="bec21-113">Especifica el intervalo entre mensajes de mantenimiento de conexión.</span><span class="sxs-lookup"><span data-stu-id="bec21-113">Specifies the keep alive interval.</span></span>|  
|<span data-ttu-id="bec21-114">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="bec21-114">maxPendingConnections</span></span>|<span data-ttu-id="bec21-115">Especifica el número máximo de conexiones pendientes de distribución en el servicio.</span><span class="sxs-lookup"><span data-stu-id="bec21-115">Specifies the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="bec21-116">receiveBufferSize</span><span class="sxs-lookup"><span data-stu-id="bec21-116">receiveBufferSize</span></span>|<span data-ttu-id="bec21-117">Especifica el tamaño de búfer de recibir.</span><span class="sxs-lookup"><span data-stu-id="bec21-117">Specifies the size of the receive buffer.</span></span>|  
|<span data-ttu-id="bec21-118">sendBufferSize</span><span class="sxs-lookup"><span data-stu-id="bec21-118">sendBufferSize</span></span>|<span data-ttu-id="bec21-119">Especifica el tamaño de búfer de enviar.</span><span class="sxs-lookup"><span data-stu-id="bec21-119">Specifies the size of the send buffer.</span></span>|  
|<span data-ttu-id="bec21-120">subProtocol</span><span class="sxs-lookup"><span data-stu-id="bec21-120">subProtocol</span></span>|<span data-ttu-id="bec21-121">Especifica el subprotocolo WebSocket.</span><span class="sxs-lookup"><span data-stu-id="bec21-121">Specifies the Web Socket subprotocol.</span></span>|  
|<span data-ttu-id="bec21-122">transportUsage</span><span class="sxs-lookup"><span data-stu-id="bec21-122">transportUsage</span></span>|<span data-ttu-id="bec21-123">Especifica cuándo usar WebSockets.</span><span class="sxs-lookup"><span data-stu-id="bec21-123">Specifies when to use Web Sockets.</span></span>|  
  
## <a name="transportusage-attribute"></a><span data-ttu-id="bec21-124">Atributo transportUsage</span><span class="sxs-lookup"><span data-stu-id="bec21-124">transportUsage Attribute</span></span>  
  
|<span data-ttu-id="bec21-125">Value</span><span class="sxs-lookup"><span data-stu-id="bec21-125">Value</span></span>|<span data-ttu-id="bec21-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="bec21-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="bec21-127">WhenDuplex</span><span class="sxs-lookup"><span data-stu-id="bec21-127">WhenDuplex</span></span>|<span data-ttu-id="bec21-128">Use el protocolo WebSocket cuando el contrato sea dúplex.</span><span class="sxs-lookup"><span data-stu-id="bec21-128">Use the Web Socket protocol when the contract is duplex.</span></span>|  
|<span data-ttu-id="bec21-129">Siempre</span><span class="sxs-lookup"><span data-stu-id="bec21-129">Always</span></span>|<span data-ttu-id="bec21-130">Use siempre el protocolo WebSocket independientemente del contrato.</span><span class="sxs-lookup"><span data-stu-id="bec21-130">Always use the Web Socket protocol regardless of the contract.</span></span>|  
|<span data-ttu-id="bec21-131">Nunca</span><span class="sxs-lookup"><span data-stu-id="bec21-131">Never</span></span>|<span data-ttu-id="bec21-132">Nunca use el protocolo WebSocket.</span><span class="sxs-lookup"><span data-stu-id="bec21-132">Never use the Web Socket protocol.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bec21-133">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="bec21-133">Child Elements</span></span>  

 <span data-ttu-id="bec21-134">None</span><span class="sxs-lookup"><span data-stu-id="bec21-134">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bec21-135">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="bec21-135">Parent Elements</span></span>  
  
|<span data-ttu-id="bec21-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="bec21-136">Element</span></span>|<span data-ttu-id="bec21-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="bec21-137">Description</span></span>|  
|-------------|-----------------|  
|\<netHttpBinding>|<span data-ttu-id="bec21-138">Especifica el NetHttpBinding</span><span class="sxs-lookup"><span data-stu-id="bec21-138">Specifies the NetHttpBinding</span></span>|  
  
## <a name="example"></a><span data-ttu-id="bec21-139">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bec21-139">Example</span></span>  

 <span data-ttu-id="bec21-140">El ejemplo siguiente muestra cómo usar el elemento \<webSocketSettings>.</span><span class="sxs-lookup"><span data-stu-id="bec21-140">The following example shows how to use the \<webSocketSettings> element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bec21-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bec21-141">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>
- [<span data-ttu-id="bec21-142">Enlaces</span><span class="sxs-lookup"><span data-stu-id="bec21-142">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="bec21-143">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="bec21-143">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="bec21-144">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="bec21-144">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
