---
title: <webSocketSettings>
ms.date: 03/30/2017
ms.assetid: bbf97e02-8dd1-4922-acac-3cd33397b249
ms.openlocfilehash: 80784f40130e572ae374bd9b26e701360dbfcaa5
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399130"
---
# <a name="websocketsettings"></a><span data-ttu-id="0807c-101">\<webSocketSettings></span><span class="sxs-lookup"><span data-stu-id="0807c-101">\<webSocketSettings></span></span>
<span data-ttu-id="0807c-102">Un elemento de configuración usado para especificar valores de WebSockets.</span><span class="sxs-lookup"><span data-stu-id="0807c-102">A configuration element used to specify Web Socket settings.</span></span>  
  
<span data-ttu-id="0807c-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0807c-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0807c-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="0807c-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="0807c-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de enlaces**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="0807c-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="0807c-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> netHttpBinding**](nethttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="0807c-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netHttpBinding>**](nethttpbinding.md)</span></span>\
<span data-ttu-id="0807c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de enlace**</span><span class="sxs-lookup"><span data-stu-id="0807c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="0807c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> webSocketSettings**</span><span class="sxs-lookup"><span data-stu-id="0807c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webSocketSettings>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0807c-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0807c-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0807c-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="0807c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="0807c-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="0807c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0807c-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="0807c-112">Attributes</span></span>  
  
|<span data-ttu-id="0807c-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="0807c-113">Attribute</span></span>|<span data-ttu-id="0807c-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="0807c-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0807c-115">createNotificationOnConnection</span><span class="sxs-lookup"><span data-stu-id="0807c-115">createNotificationOnConnection</span></span>|<span data-ttu-id="0807c-116">Especifica si se envía una notificación al realizar la conexión.</span><span class="sxs-lookup"><span data-stu-id="0807c-116">Specifies whether a notification is sent upon connection.</span></span>|  
|<span data-ttu-id="0807c-117">disablePayloadMasking</span><span class="sxs-lookup"><span data-stu-id="0807c-117">disablePayloadMasking</span></span>|<span data-ttu-id="0807c-118">Especifica si el enmascaramiento de WebSocket está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="0807c-118">Specifies whether Web Socket masking is disabled.</span></span>|  
|<span data-ttu-id="0807c-119">keepAliveInterval</span><span class="sxs-lookup"><span data-stu-id="0807c-119">keepAliveInterval</span></span>|<span data-ttu-id="0807c-120">Especifica el intervalo entre mensajes de mantenimiento de conexión.</span><span class="sxs-lookup"><span data-stu-id="0807c-120">Specifies the keep alive interval.</span></span>|  
|<span data-ttu-id="0807c-121">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="0807c-121">maxPendingConnections</span></span>|<span data-ttu-id="0807c-122">Especifica el número máximo de conexiones pendientes de distribución en el servicio.</span><span class="sxs-lookup"><span data-stu-id="0807c-122">Specifies the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="0807c-123">receiveBufferSize</span><span class="sxs-lookup"><span data-stu-id="0807c-123">receiveBufferSize</span></span>|<span data-ttu-id="0807c-124">Especifica el tamaño de búfer de recibir.</span><span class="sxs-lookup"><span data-stu-id="0807c-124">Specifies the size of the receive buffer.</span></span>|  
|<span data-ttu-id="0807c-125">sendBufferSize</span><span class="sxs-lookup"><span data-stu-id="0807c-125">sendBufferSize</span></span>|<span data-ttu-id="0807c-126">Especifica el tamaño de búfer de enviar.</span><span class="sxs-lookup"><span data-stu-id="0807c-126">Specifies the size of the send buffer.</span></span>|  
|<span data-ttu-id="0807c-127">subProtocol</span><span class="sxs-lookup"><span data-stu-id="0807c-127">subProtocol</span></span>|<span data-ttu-id="0807c-128">Especifica el subprotocolo WebSocket.</span><span class="sxs-lookup"><span data-stu-id="0807c-128">Specifies the Web Socket subprotocol.</span></span>|  
|<span data-ttu-id="0807c-129">transportUsage</span><span class="sxs-lookup"><span data-stu-id="0807c-129">transportUsage</span></span>|<span data-ttu-id="0807c-130">Especifica cuándo usar WebSockets.</span><span class="sxs-lookup"><span data-stu-id="0807c-130">Specifies when to use Web Sockets.</span></span>|  
  
## <a name="transportusage-attribute"></a><span data-ttu-id="0807c-131">Atributo transportUsage</span><span class="sxs-lookup"><span data-stu-id="0807c-131">transportUsage Attribute</span></span>  
  
|<span data-ttu-id="0807c-132">Valor</span><span class="sxs-lookup"><span data-stu-id="0807c-132">Value</span></span>|<span data-ttu-id="0807c-133">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="0807c-133">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0807c-134">WhenDuplex</span><span class="sxs-lookup"><span data-stu-id="0807c-134">WhenDuplex</span></span>|<span data-ttu-id="0807c-135">Use el protocolo WebSocket cuando el contrato sea dúplex.</span><span class="sxs-lookup"><span data-stu-id="0807c-135">Use the Web Socket protocol when the contract is duplex.</span></span>|  
|<span data-ttu-id="0807c-136">Siempre</span><span class="sxs-lookup"><span data-stu-id="0807c-136">Always</span></span>|<span data-ttu-id="0807c-137">Use siempre el protocolo WebSocket independientemente del contrato.</span><span class="sxs-lookup"><span data-stu-id="0807c-137">Always use the Web Socket protocol regardless of the contract.</span></span>|  
|<span data-ttu-id="0807c-138">Nunca</span><span class="sxs-lookup"><span data-stu-id="0807c-138">Never</span></span>|<span data-ttu-id="0807c-139">Nunca use el protocolo WebSocket.</span><span class="sxs-lookup"><span data-stu-id="0807c-139">Never use the Web Socket protocol.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0807c-140">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0807c-140">Child Elements</span></span>  
 <span data-ttu-id="0807c-141">None</span><span class="sxs-lookup"><span data-stu-id="0807c-141">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0807c-142">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0807c-142">Parent Elements</span></span>  
  
|<span data-ttu-id="0807c-143">Elemento</span><span class="sxs-lookup"><span data-stu-id="0807c-143">Element</span></span>|<span data-ttu-id="0807c-144">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="0807c-144">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0807c-145">\<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="0807c-145">\<netHttpBinding></span></span>|<span data-ttu-id="0807c-146">Especifica el NetHttpBinding</span><span class="sxs-lookup"><span data-stu-id="0807c-146">Specifies the NetHttpBinding</span></span>|  
  
## <a name="example"></a><span data-ttu-id="0807c-147">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0807c-147">Example</span></span>  
 <span data-ttu-id="0807c-148">En el ejemplo siguiente se muestra cómo usar \<el elemento > de webSocketSettings.</span><span class="sxs-lookup"><span data-stu-id="0807c-148">The following example shows how to use the \<webSocketSettings> element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0807c-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="0807c-149">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>
- [<span data-ttu-id="0807c-150">Enlaces</span><span class="sxs-lookup"><span data-stu-id="0807c-150">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="0807c-151">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="0807c-151">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="0807c-152">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="0807c-152">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="0807c-153">\<binding></span><span class="sxs-lookup"><span data-stu-id="0807c-153">\<binding></span></span>](../../../misc/binding.md)
