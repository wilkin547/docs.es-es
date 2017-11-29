---
title: '&lt;webSocketSettings&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bbf97e02-8dd1-4922-acac-3cd33397b249
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2714b27916a47ae8e002ea857c93377736c4eff5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltwebsocketsettingsgt"></a><span data-ttu-id="f49c1-102">&lt;webSocketSettings&gt;</span><span class="sxs-lookup"><span data-stu-id="f49c1-102">&lt;webSocketSettings&gt;</span></span>
<span data-ttu-id="f49c1-103">Un elemento de configuración usado para especificar valores de WebSockets.</span><span class="sxs-lookup"><span data-stu-id="f49c1-103">A configuration element used to specify Web Socket settings.</span></span>  
  
<span data-ttu-id="f49c1-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="f49c1-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="f49c1-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="f49c1-105">\<bindings></span></span>  
<span data-ttu-id="f49c1-106">\<netHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="f49c1-106">\<netHttpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f49c1-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f49c1-107">Syntax</span></span>  
  
```xml  
<netHttpBinding>  
  <binding>   
    <webSocketSettings createNotificationOnConnection="boolean" 
                       disablePayloadMasking="boolean" 
                       keepAliveInterval="TimeSpan" 
                       maxPendingConnections="Integer" 
                       receiveBufferSize="Integer" 
                       sendBufferSize="Integer" 
                       subProtocol="String" 
                       transportUsage="WhenDuplex/Always/Never"/>
  </binding>  
</netHttpBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f49c1-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f49c1-108">Attributes and Elements</span></span>  
 <span data-ttu-id="f49c1-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f49c1-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f49c1-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="f49c1-110">Attributes</span></span>  
  
|<span data-ttu-id="f49c1-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="f49c1-111">Attribute</span></span>|<span data-ttu-id="f49c1-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="f49c1-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f49c1-113">createNotificationOnConnection</span><span class="sxs-lookup"><span data-stu-id="f49c1-113">createNotificationOnConnection</span></span>|<span data-ttu-id="f49c1-114">Especifica si se envía una notificación al realizar la conexión.</span><span class="sxs-lookup"><span data-stu-id="f49c1-114">Specifies whether a notification is sent upon connection.</span></span>|  
|<span data-ttu-id="f49c1-115">disablePayloadMasking</span><span class="sxs-lookup"><span data-stu-id="f49c1-115">disablePayloadMasking</span></span>|<span data-ttu-id="f49c1-116">Especifica si el enmascaramiento de WebSocket está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="f49c1-116">Specifies whether Web Socket masking is disabled.</span></span>|  
|<span data-ttu-id="f49c1-117">keepAliveInterval</span><span class="sxs-lookup"><span data-stu-id="f49c1-117">keepAliveInterval</span></span>|<span data-ttu-id="f49c1-118">Especifica el intervalo entre mensajes de mantenimiento de conexión.</span><span class="sxs-lookup"><span data-stu-id="f49c1-118">Specifies the keep alive interval.</span></span>|  
|<span data-ttu-id="f49c1-119">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="f49c1-119">maxPendingConnections</span></span>|<span data-ttu-id="f49c1-120">Especifica el número máximo de conexiones pendientes de distribución en el servicio.</span><span class="sxs-lookup"><span data-stu-id="f49c1-120">Specifies the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="f49c1-121">receiveBufferSize</span><span class="sxs-lookup"><span data-stu-id="f49c1-121">receiveBufferSize</span></span>|<span data-ttu-id="f49c1-122">Especifica el tamaño de búfer de recibir.</span><span class="sxs-lookup"><span data-stu-id="f49c1-122">Specifies the size of the receive buffer.</span></span>|  
|<span data-ttu-id="f49c1-123">sendBufferSize</span><span class="sxs-lookup"><span data-stu-id="f49c1-123">sendBufferSize</span></span>|<span data-ttu-id="f49c1-124">Especifica el tamaño de búfer de enviar.</span><span class="sxs-lookup"><span data-stu-id="f49c1-124">Specifies the size of the send buffer.</span></span>|  
|<span data-ttu-id="f49c1-125">subProtocol</span><span class="sxs-lookup"><span data-stu-id="f49c1-125">subProtocol</span></span>|<span data-ttu-id="f49c1-126">Especifica el subprotocolo WebSocket.</span><span class="sxs-lookup"><span data-stu-id="f49c1-126">Specifies the Web Socket subprotocol.</span></span>|  
|<span data-ttu-id="f49c1-127">transportUsage</span><span class="sxs-lookup"><span data-stu-id="f49c1-127">transportUsage</span></span>|<span data-ttu-id="f49c1-128">Especifica cuándo usar WebSockets.</span><span class="sxs-lookup"><span data-stu-id="f49c1-128">Specifies when to use Web Sockets.</span></span>|  
  
## <a name="transportusage-attribute"></a><span data-ttu-id="f49c1-129">Atributo transportUsage</span><span class="sxs-lookup"><span data-stu-id="f49c1-129">transportUsage Attribute</span></span>  
  
|<span data-ttu-id="f49c1-130">Valor</span><span class="sxs-lookup"><span data-stu-id="f49c1-130">Value</span></span>|<span data-ttu-id="f49c1-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="f49c1-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f49c1-132">WhenDuplex</span><span class="sxs-lookup"><span data-stu-id="f49c1-132">WhenDuplex</span></span>|<span data-ttu-id="f49c1-133">Use el protocolo WebSocket cuando el contrato sea dúplex.</span><span class="sxs-lookup"><span data-stu-id="f49c1-133">Use the Web Socket protocol when the contract is duplex.</span></span>|  
|<span data-ttu-id="f49c1-134">Siempre</span><span class="sxs-lookup"><span data-stu-id="f49c1-134">Always</span></span>|<span data-ttu-id="f49c1-135">Use siempre el protocolo WebSocket independientemente del contrato.</span><span class="sxs-lookup"><span data-stu-id="f49c1-135">Always use the Web Socket protocol regardless of the contract.</span></span>|  
|<span data-ttu-id="f49c1-136">Nunca</span><span class="sxs-lookup"><span data-stu-id="f49c1-136">Never</span></span>|<span data-ttu-id="f49c1-137">Nunca use el protocolo WebSocket.</span><span class="sxs-lookup"><span data-stu-id="f49c1-137">Never use the Web Socket protocol.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f49c1-138">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f49c1-138">Child Elements</span></span>  
 <span data-ttu-id="f49c1-139">Ninguna</span><span class="sxs-lookup"><span data-stu-id="f49c1-139">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f49c1-140">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f49c1-140">Parent Elements</span></span>  
  
|<span data-ttu-id="f49c1-141">Elemento</span><span class="sxs-lookup"><span data-stu-id="f49c1-141">Element</span></span>|<span data-ttu-id="f49c1-142">Descripción</span><span class="sxs-lookup"><span data-stu-id="f49c1-142">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f49c1-143">\<netHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="f49c1-143">\<netHttpBinding></span></span>|<span data-ttu-id="f49c1-144">Especifica el NetHttpBinding</span><span class="sxs-lookup"><span data-stu-id="f49c1-144">Specifies the NetHttpBinding</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f49c1-145">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f49c1-145">Example</span></span>  
 <span data-ttu-id="f49c1-146">En el ejemplo siguiente se muestra cómo utilizar el \<webSocketSettings > elemento.</span><span class="sxs-lookup"><span data-stu-id="f49c1-146">The following example shows how to use the \<webSocketSettings> element.</span></span>  
  
```xml  
<netHttpBinding>  
        <binding>  
          <webSocketSettings createNotificationOnConnection="true"  
                              disablePayloadMasking="false  
                              keepAliveInterval="00:10:00"  
                              maxPendingConnections="100"  
                              receiveBufferSize="1000"  
                              sendBufferSize="1000"  
                              subProtocol="Soap"  
                              transportUsage="WhenDuplex/Always/Never"/>  
  
        </binding>  
      </netHttpBinding>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f49c1-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="f49c1-147">See Also</span></span>  
 <xref:System.ServiceModel.Channels.Binding>  
 <xref:System.ServiceModel.Channels.BindingElement>  
 <xref:System.ServiceModel.BasicHttpBinding>  
 <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>  
 [<span data-ttu-id="f49c1-148">Enlaces</span><span class="sxs-lookup"><span data-stu-id="f49c1-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="f49c1-149">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="f49c1-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="f49c1-150">Utilización de enlaces para configurar los clientes y servicios de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="f49c1-150">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="f49c1-151">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="f49c1-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
