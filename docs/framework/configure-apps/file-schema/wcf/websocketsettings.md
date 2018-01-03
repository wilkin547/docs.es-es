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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7ee0f555fc1e3412032e0a7dda3a747bbfef6f4d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltwebsocketsettingsgt"></a><span data-ttu-id="22723-102">&lt;webSocketSettings&gt;</span><span class="sxs-lookup"><span data-stu-id="22723-102">&lt;webSocketSettings&gt;</span></span>
<span data-ttu-id="22723-103">Un elemento de configuración usado para especificar valores de WebSockets.</span><span class="sxs-lookup"><span data-stu-id="22723-103">A configuration element used to specify Web Socket settings.</span></span>  
  
<span data-ttu-id="22723-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="22723-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="22723-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="22723-105">\<bindings></span></span>  
<span data-ttu-id="22723-106">\<netHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="22723-106">\<netHttpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22723-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="22723-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="22723-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="22723-108">Attributes and Elements</span></span>  
 <span data-ttu-id="22723-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="22723-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="22723-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="22723-110">Attributes</span></span>  
  
|<span data-ttu-id="22723-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="22723-111">Attribute</span></span>|<span data-ttu-id="22723-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="22723-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="22723-113">createNotificationOnConnection</span><span class="sxs-lookup"><span data-stu-id="22723-113">createNotificationOnConnection</span></span>|<span data-ttu-id="22723-114">Especifica si se envía una notificación al realizar la conexión.</span><span class="sxs-lookup"><span data-stu-id="22723-114">Specifies whether a notification is sent upon connection.</span></span>|  
|<span data-ttu-id="22723-115">disablePayloadMasking</span><span class="sxs-lookup"><span data-stu-id="22723-115">disablePayloadMasking</span></span>|<span data-ttu-id="22723-116">Especifica si el enmascaramiento de WebSocket está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="22723-116">Specifies whether Web Socket masking is disabled.</span></span>|  
|<span data-ttu-id="22723-117">keepAliveInterval</span><span class="sxs-lookup"><span data-stu-id="22723-117">keepAliveInterval</span></span>|<span data-ttu-id="22723-118">Especifica el intervalo entre mensajes de mantenimiento de conexión.</span><span class="sxs-lookup"><span data-stu-id="22723-118">Specifies the keep alive interval.</span></span>|  
|<span data-ttu-id="22723-119">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="22723-119">maxPendingConnections</span></span>|<span data-ttu-id="22723-120">Especifica el número máximo de conexiones pendientes de distribución en el servicio.</span><span class="sxs-lookup"><span data-stu-id="22723-120">Specifies the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="22723-121">receiveBufferSize</span><span class="sxs-lookup"><span data-stu-id="22723-121">receiveBufferSize</span></span>|<span data-ttu-id="22723-122">Especifica el tamaño de búfer de recibir.</span><span class="sxs-lookup"><span data-stu-id="22723-122">Specifies the size of the receive buffer.</span></span>|  
|<span data-ttu-id="22723-123">sendBufferSize</span><span class="sxs-lookup"><span data-stu-id="22723-123">sendBufferSize</span></span>|<span data-ttu-id="22723-124">Especifica el tamaño de búfer de enviar.</span><span class="sxs-lookup"><span data-stu-id="22723-124">Specifies the size of the send buffer.</span></span>|  
|<span data-ttu-id="22723-125">subProtocol</span><span class="sxs-lookup"><span data-stu-id="22723-125">subProtocol</span></span>|<span data-ttu-id="22723-126">Especifica el subprotocolo WebSocket.</span><span class="sxs-lookup"><span data-stu-id="22723-126">Specifies the Web Socket subprotocol.</span></span>|  
|<span data-ttu-id="22723-127">transportUsage</span><span class="sxs-lookup"><span data-stu-id="22723-127">transportUsage</span></span>|<span data-ttu-id="22723-128">Especifica cuándo usar WebSockets.</span><span class="sxs-lookup"><span data-stu-id="22723-128">Specifies when to use Web Sockets.</span></span>|  
  
## <a name="transportusage-attribute"></a><span data-ttu-id="22723-129">Atributo transportUsage</span><span class="sxs-lookup"><span data-stu-id="22723-129">transportUsage Attribute</span></span>  
  
|<span data-ttu-id="22723-130">Valor</span><span class="sxs-lookup"><span data-stu-id="22723-130">Value</span></span>|<span data-ttu-id="22723-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="22723-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="22723-132">WhenDuplex</span><span class="sxs-lookup"><span data-stu-id="22723-132">WhenDuplex</span></span>|<span data-ttu-id="22723-133">Use el protocolo WebSocket cuando el contrato sea dúplex.</span><span class="sxs-lookup"><span data-stu-id="22723-133">Use the Web Socket protocol when the contract is duplex.</span></span>|  
|<span data-ttu-id="22723-134">Siempre</span><span class="sxs-lookup"><span data-stu-id="22723-134">Always</span></span>|<span data-ttu-id="22723-135">Use siempre el protocolo WebSocket independientemente del contrato.</span><span class="sxs-lookup"><span data-stu-id="22723-135">Always use the Web Socket protocol regardless of the contract.</span></span>|  
|<span data-ttu-id="22723-136">Nunca</span><span class="sxs-lookup"><span data-stu-id="22723-136">Never</span></span>|<span data-ttu-id="22723-137">Nunca use el protocolo WebSocket.</span><span class="sxs-lookup"><span data-stu-id="22723-137">Never use the Web Socket protocol.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="22723-138">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="22723-138">Child Elements</span></span>  
 <span data-ttu-id="22723-139">Ninguna</span><span class="sxs-lookup"><span data-stu-id="22723-139">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="22723-140">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="22723-140">Parent Elements</span></span>  
  
|<span data-ttu-id="22723-141">Elemento</span><span class="sxs-lookup"><span data-stu-id="22723-141">Element</span></span>|<span data-ttu-id="22723-142">Descripción</span><span class="sxs-lookup"><span data-stu-id="22723-142">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="22723-143">\<netHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="22723-143">\<netHttpBinding></span></span>|<span data-ttu-id="22723-144">Especifica el NetHttpBinding</span><span class="sxs-lookup"><span data-stu-id="22723-144">Specifies the NetHttpBinding</span></span>|  
  
## <a name="example"></a><span data-ttu-id="22723-145">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="22723-145">Example</span></span>  
 <span data-ttu-id="22723-146">En el ejemplo siguiente se muestra cómo utilizar el \<webSocketSettings > elemento.</span><span class="sxs-lookup"><span data-stu-id="22723-146">The following example shows how to use the \<webSocketSettings> element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="22723-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="22723-147">See Also</span></span>  
 <xref:System.ServiceModel.Channels.Binding>  
 <xref:System.ServiceModel.Channels.BindingElement>  
 <xref:System.ServiceModel.BasicHttpBinding>  
 <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>  
 [<span data-ttu-id="22723-148">Enlaces</span><span class="sxs-lookup"><span data-stu-id="22723-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="22723-149">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="22723-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="22723-150">Utilización de enlaces para configurar los clientes y servicios de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="22723-150">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="22723-151">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="22723-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
