---
title: '&lt;webSocketSettings&gt;'
ms.date: 03/30/2017
ms.assetid: bbf97e02-8dd1-4922-acac-3cd33397b249
ms.openlocfilehash: 134a233a337c40d21f7547fe385ec788cef2165b
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54150063"
---
# <a name="ltwebsocketsettingsgt"></a><span data-ttu-id="8698e-102">&lt;webSocketSettings&gt;</span><span class="sxs-lookup"><span data-stu-id="8698e-102">&lt;webSocketSettings&gt;</span></span>
<span data-ttu-id="8698e-103">Un elemento de configuración usado para especificar valores de WebSockets.</span><span class="sxs-lookup"><span data-stu-id="8698e-103">A configuration element used to specify Web Socket settings.</span></span>  
  
<span data-ttu-id="8698e-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="8698e-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="8698e-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="8698e-105">\<bindings></span></span>  
<span data-ttu-id="8698e-106">\<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="8698e-106">\<netHttpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8698e-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8698e-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8698e-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="8698e-108">Attributes and Elements</span></span>  
 <span data-ttu-id="8698e-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="8698e-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8698e-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="8698e-110">Attributes</span></span>  
  
|<span data-ttu-id="8698e-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="8698e-111">Attribute</span></span>|<span data-ttu-id="8698e-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="8698e-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8698e-113">createNotificationOnConnection</span><span class="sxs-lookup"><span data-stu-id="8698e-113">createNotificationOnConnection</span></span>|<span data-ttu-id="8698e-114">Especifica si se envía una notificación al realizar la conexión.</span><span class="sxs-lookup"><span data-stu-id="8698e-114">Specifies whether a notification is sent upon connection.</span></span>|  
|<span data-ttu-id="8698e-115">disablePayloadMasking</span><span class="sxs-lookup"><span data-stu-id="8698e-115">disablePayloadMasking</span></span>|<span data-ttu-id="8698e-116">Especifica si el enmascaramiento de WebSocket está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="8698e-116">Specifies whether Web Socket masking is disabled.</span></span>|  
|<span data-ttu-id="8698e-117">keepAliveInterval</span><span class="sxs-lookup"><span data-stu-id="8698e-117">keepAliveInterval</span></span>|<span data-ttu-id="8698e-118">Especifica el intervalo entre mensajes de mantenimiento de conexión.</span><span class="sxs-lookup"><span data-stu-id="8698e-118">Specifies the keep alive interval.</span></span>|  
|<span data-ttu-id="8698e-119">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="8698e-119">maxPendingConnections</span></span>|<span data-ttu-id="8698e-120">Especifica el número máximo de conexiones pendientes de distribución en el servicio.</span><span class="sxs-lookup"><span data-stu-id="8698e-120">Specifies the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="8698e-121">receiveBufferSize</span><span class="sxs-lookup"><span data-stu-id="8698e-121">receiveBufferSize</span></span>|<span data-ttu-id="8698e-122">Especifica el tamaño de búfer de recibir.</span><span class="sxs-lookup"><span data-stu-id="8698e-122">Specifies the size of the receive buffer.</span></span>|  
|<span data-ttu-id="8698e-123">sendBufferSize</span><span class="sxs-lookup"><span data-stu-id="8698e-123">sendBufferSize</span></span>|<span data-ttu-id="8698e-124">Especifica el tamaño de búfer de enviar.</span><span class="sxs-lookup"><span data-stu-id="8698e-124">Specifies the size of the send buffer.</span></span>|  
|<span data-ttu-id="8698e-125">subProtocol</span><span class="sxs-lookup"><span data-stu-id="8698e-125">subProtocol</span></span>|<span data-ttu-id="8698e-126">Especifica el subprotocolo WebSocket.</span><span class="sxs-lookup"><span data-stu-id="8698e-126">Specifies the Web Socket subprotocol.</span></span>|  
|<span data-ttu-id="8698e-127">transportUsage</span><span class="sxs-lookup"><span data-stu-id="8698e-127">transportUsage</span></span>|<span data-ttu-id="8698e-128">Especifica cuándo usar WebSockets.</span><span class="sxs-lookup"><span data-stu-id="8698e-128">Specifies when to use Web Sockets.</span></span>|  
  
## <a name="transportusage-attribute"></a><span data-ttu-id="8698e-129">Atributo transportUsage</span><span class="sxs-lookup"><span data-stu-id="8698e-129">transportUsage Attribute</span></span>  
  
|<span data-ttu-id="8698e-130">Valor</span><span class="sxs-lookup"><span data-stu-id="8698e-130">Value</span></span>|<span data-ttu-id="8698e-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="8698e-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8698e-132">WhenDuplex</span><span class="sxs-lookup"><span data-stu-id="8698e-132">WhenDuplex</span></span>|<span data-ttu-id="8698e-133">Use el protocolo WebSocket cuando el contrato sea dúplex.</span><span class="sxs-lookup"><span data-stu-id="8698e-133">Use the Web Socket protocol when the contract is duplex.</span></span>|  
|<span data-ttu-id="8698e-134">Siempre</span><span class="sxs-lookup"><span data-stu-id="8698e-134">Always</span></span>|<span data-ttu-id="8698e-135">Use siempre el protocolo WebSocket independientemente del contrato.</span><span class="sxs-lookup"><span data-stu-id="8698e-135">Always use the Web Socket protocol regardless of the contract.</span></span>|  
|<span data-ttu-id="8698e-136">Nunca</span><span class="sxs-lookup"><span data-stu-id="8698e-136">Never</span></span>|<span data-ttu-id="8698e-137">Nunca use el protocolo WebSocket.</span><span class="sxs-lookup"><span data-stu-id="8698e-137">Never use the Web Socket protocol.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8698e-138">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="8698e-138">Child Elements</span></span>  
 <span data-ttu-id="8698e-139">Ninguna</span><span class="sxs-lookup"><span data-stu-id="8698e-139">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8698e-140">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8698e-140">Parent Elements</span></span>  
  
|<span data-ttu-id="8698e-141">Elemento</span><span class="sxs-lookup"><span data-stu-id="8698e-141">Element</span></span>|<span data-ttu-id="8698e-142">Descripción</span><span class="sxs-lookup"><span data-stu-id="8698e-142">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8698e-143">\<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="8698e-143">\<netHttpBinding></span></span>|<span data-ttu-id="8698e-144">Especifica el NetHttpBinding</span><span class="sxs-lookup"><span data-stu-id="8698e-144">Specifies the NetHttpBinding</span></span>|  
  
## <a name="example"></a><span data-ttu-id="8698e-145">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8698e-145">Example</span></span>  
 <span data-ttu-id="8698e-146">El ejemplo siguiente muestra cómo usar el \<webSocketSettings > elemento.</span><span class="sxs-lookup"><span data-stu-id="8698e-146">The following example shows how to use the \<webSocketSettings> element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8698e-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="8698e-147">See Also</span></span>  
 <xref:System.ServiceModel.Channels.Binding>  
 <xref:System.ServiceModel.Channels.BindingElement>  
 <xref:System.ServiceModel.BasicHttpBinding>  
 <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>  
 [<span data-ttu-id="8698e-148">Enlaces</span><span class="sxs-lookup"><span data-stu-id="8698e-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="8698e-149">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="8698e-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="8698e-150">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="8698e-150">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="8698e-151">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="8698e-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
