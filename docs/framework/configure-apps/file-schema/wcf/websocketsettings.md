---
title: <webSocketSettings>
ms.date: 03/30/2017
ms.assetid: bbf97e02-8dd1-4922-acac-3cd33397b249
ms.openlocfilehash: fa87a1b0961425d6a9bc84769bef6e87cbc2ce96
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73732556"
---
# <a name="websocketsettings"></a><span data-ttu-id="690ce-101">\<webSocketSettings ></span><span class="sxs-lookup"><span data-stu-id="690ce-101">\<webSocketSettings></span></span>
<span data-ttu-id="690ce-102">Un elemento de configuración usado para especificar valores de WebSockets.</span><span class="sxs-lookup"><span data-stu-id="690ce-102">A configuration element used to specify Web Socket settings.</span></span>  
  
<span data-ttu-id="690ce-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="690ce-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="690ce-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="690ce-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="690ce-105">&nbsp;&nbsp;&nbsp;&nbsp;\<[**enlaces**](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="690ce-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="690ce-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netHttpBinding**](nethttpbinding.md) ></span><span class="sxs-lookup"><span data-stu-id="690ce-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netHttpBinding>**](nethttpbinding.md)</span></span>\
<span data-ttu-id="690ce-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**enlace** ></span><span class="sxs-lookup"><span data-stu-id="690ce-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="690ce-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<webSocketSettings >**</span><span class="sxs-lookup"><span data-stu-id="690ce-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webSocketSettings>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="690ce-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="690ce-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="690ce-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="690ce-110">Attributes and Elements</span></span>  
 <span data-ttu-id="690ce-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="690ce-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="690ce-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="690ce-112">Attributes</span></span>  
  
|<span data-ttu-id="690ce-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="690ce-113">Attribute</span></span>|<span data-ttu-id="690ce-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="690ce-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="690ce-115">createNotificationOnConnection</span><span class="sxs-lookup"><span data-stu-id="690ce-115">createNotificationOnConnection</span></span>|<span data-ttu-id="690ce-116">Especifica si se envía una notificación al realizar la conexión.</span><span class="sxs-lookup"><span data-stu-id="690ce-116">Specifies whether a notification is sent upon connection.</span></span>|  
|<span data-ttu-id="690ce-117">disablePayloadMasking</span><span class="sxs-lookup"><span data-stu-id="690ce-117">disablePayloadMasking</span></span>|<span data-ttu-id="690ce-118">Especifica si el enmascaramiento de WebSocket está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="690ce-118">Specifies whether Web Socket masking is disabled.</span></span>|  
|<span data-ttu-id="690ce-119">keepAliveInterval</span><span class="sxs-lookup"><span data-stu-id="690ce-119">keepAliveInterval</span></span>|<span data-ttu-id="690ce-120">Especifica el intervalo entre mensajes de mantenimiento de conexión.</span><span class="sxs-lookup"><span data-stu-id="690ce-120">Specifies the keep alive interval.</span></span>|  
|<span data-ttu-id="690ce-121">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="690ce-121">maxPendingConnections</span></span>|<span data-ttu-id="690ce-122">Especifica el número máximo de conexiones pendientes de distribución en el servicio.</span><span class="sxs-lookup"><span data-stu-id="690ce-122">Specifies the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="690ce-123">receiveBufferSize</span><span class="sxs-lookup"><span data-stu-id="690ce-123">receiveBufferSize</span></span>|<span data-ttu-id="690ce-124">Especifica el tamaño de búfer de recibir.</span><span class="sxs-lookup"><span data-stu-id="690ce-124">Specifies the size of the receive buffer.</span></span>|  
|<span data-ttu-id="690ce-125">sendBufferSize</span><span class="sxs-lookup"><span data-stu-id="690ce-125">sendBufferSize</span></span>|<span data-ttu-id="690ce-126">Especifica el tamaño de búfer de enviar.</span><span class="sxs-lookup"><span data-stu-id="690ce-126">Specifies the size of the send buffer.</span></span>|  
|<span data-ttu-id="690ce-127">subProtocol</span><span class="sxs-lookup"><span data-stu-id="690ce-127">subProtocol</span></span>|<span data-ttu-id="690ce-128">Especifica el subprotocolo WebSocket.</span><span class="sxs-lookup"><span data-stu-id="690ce-128">Specifies the Web Socket subprotocol.</span></span>|  
|<span data-ttu-id="690ce-129">transportUsage</span><span class="sxs-lookup"><span data-stu-id="690ce-129">transportUsage</span></span>|<span data-ttu-id="690ce-130">Especifica cuándo usar WebSockets.</span><span class="sxs-lookup"><span data-stu-id="690ce-130">Specifies when to use Web Sockets.</span></span>|  
  
## <a name="transportusage-attribute"></a><span data-ttu-id="690ce-131">Atributo transportUsage</span><span class="sxs-lookup"><span data-stu-id="690ce-131">transportUsage Attribute</span></span>  
  
|<span data-ttu-id="690ce-132">Valor</span><span class="sxs-lookup"><span data-stu-id="690ce-132">Value</span></span>|<span data-ttu-id="690ce-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="690ce-133">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="690ce-134">WhenDuplex</span><span class="sxs-lookup"><span data-stu-id="690ce-134">WhenDuplex</span></span>|<span data-ttu-id="690ce-135">Use el protocolo WebSocket cuando el contrato sea dúplex.</span><span class="sxs-lookup"><span data-stu-id="690ce-135">Use the Web Socket protocol when the contract is duplex.</span></span>|  
|<span data-ttu-id="690ce-136">Siempre</span><span class="sxs-lookup"><span data-stu-id="690ce-136">Always</span></span>|<span data-ttu-id="690ce-137">Use siempre el protocolo WebSocket independientemente del contrato.</span><span class="sxs-lookup"><span data-stu-id="690ce-137">Always use the Web Socket protocol regardless of the contract.</span></span>|  
|<span data-ttu-id="690ce-138">Never</span><span class="sxs-lookup"><span data-stu-id="690ce-138">Never</span></span>|<span data-ttu-id="690ce-139">Nunca use el protocolo WebSocket.</span><span class="sxs-lookup"><span data-stu-id="690ce-139">Never use the Web Socket protocol.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="690ce-140">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="690ce-140">Child Elements</span></span>  
 <span data-ttu-id="690ce-141">Ninguno</span><span class="sxs-lookup"><span data-stu-id="690ce-141">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="690ce-142">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="690ce-142">Parent Elements</span></span>  
  
|<span data-ttu-id="690ce-143">Elemento</span><span class="sxs-lookup"><span data-stu-id="690ce-143">Element</span></span>|<span data-ttu-id="690ce-144">Descripción</span><span class="sxs-lookup"><span data-stu-id="690ce-144">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="690ce-145">\<netHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="690ce-145">\<netHttpBinding></span></span>|<span data-ttu-id="690ce-146">Especifica el NetHttpBinding</span><span class="sxs-lookup"><span data-stu-id="690ce-146">Specifies the NetHttpBinding</span></span>|  
  
## <a name="example"></a><span data-ttu-id="690ce-147">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="690ce-147">Example</span></span>  
 <span data-ttu-id="690ce-148">En el ejemplo siguiente se muestra cómo usar el elemento \<webSocketSettings >.</span><span class="sxs-lookup"><span data-stu-id="690ce-148">The following example shows how to use the \<webSocketSettings> element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="690ce-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="690ce-149">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>
- [<span data-ttu-id="690ce-150">Enlaces</span><span class="sxs-lookup"><span data-stu-id="690ce-150">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="690ce-151">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="690ce-151">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="690ce-152">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="690ce-152">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="690ce-153">\<> de enlace</span><span class="sxs-lookup"><span data-stu-id="690ce-153">\<binding></span></span>](bindings.md)
