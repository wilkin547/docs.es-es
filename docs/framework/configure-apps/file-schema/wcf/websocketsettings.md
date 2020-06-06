---
title: <webSocketSettings>
ms.date: 03/30/2017
ms.assetid: bbf97e02-8dd1-4922-acac-3cd33397b249
ms.openlocfilehash: fa87a1b0961425d6a9bc84769bef6e87cbc2ce96
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "73732556"
---
# \<webSocketSettings>
<span data-ttu-id="f5217-101">Un elemento de configuración usado para especificar valores de WebSockets.</span><span class="sxs-lookup"><span data-stu-id="f5217-101">A configuration element used to specify Web Socket settings.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netHttpBinding>**](nethttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webSocketSettings>**  
  
## <a name="syntax"></a><span data-ttu-id="f5217-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f5217-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f5217-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f5217-103">Attributes and Elements</span></span>  
 <span data-ttu-id="f5217-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f5217-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f5217-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="f5217-105">Attributes</span></span>  
  
|<span data-ttu-id="f5217-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="f5217-106">Attribute</span></span>|<span data-ttu-id="f5217-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="f5217-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f5217-108">createNotificationOnConnection</span><span class="sxs-lookup"><span data-stu-id="f5217-108">createNotificationOnConnection</span></span>|<span data-ttu-id="f5217-109">Especifica si se envía una notificación al realizar la conexión.</span><span class="sxs-lookup"><span data-stu-id="f5217-109">Specifies whether a notification is sent upon connection.</span></span>|  
|<span data-ttu-id="f5217-110">disablePayloadMasking</span><span class="sxs-lookup"><span data-stu-id="f5217-110">disablePayloadMasking</span></span>|<span data-ttu-id="f5217-111">Especifica si el enmascaramiento de WebSocket está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="f5217-111">Specifies whether Web Socket masking is disabled.</span></span>|  
|<span data-ttu-id="f5217-112">keepAliveInterval</span><span class="sxs-lookup"><span data-stu-id="f5217-112">keepAliveInterval</span></span>|<span data-ttu-id="f5217-113">Especifica el intervalo entre mensajes de mantenimiento de conexión.</span><span class="sxs-lookup"><span data-stu-id="f5217-113">Specifies the keep alive interval.</span></span>|  
|<span data-ttu-id="f5217-114">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="f5217-114">maxPendingConnections</span></span>|<span data-ttu-id="f5217-115">Especifica el número máximo de conexiones pendientes de distribución en el servicio.</span><span class="sxs-lookup"><span data-stu-id="f5217-115">Specifies the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="f5217-116">receiveBufferSize</span><span class="sxs-lookup"><span data-stu-id="f5217-116">receiveBufferSize</span></span>|<span data-ttu-id="f5217-117">Especifica el tamaño de búfer de recibir.</span><span class="sxs-lookup"><span data-stu-id="f5217-117">Specifies the size of the receive buffer.</span></span>|  
|<span data-ttu-id="f5217-118">sendBufferSize</span><span class="sxs-lookup"><span data-stu-id="f5217-118">sendBufferSize</span></span>|<span data-ttu-id="f5217-119">Especifica el tamaño de búfer de enviar.</span><span class="sxs-lookup"><span data-stu-id="f5217-119">Specifies the size of the send buffer.</span></span>|  
|<span data-ttu-id="f5217-120">subProtocol</span><span class="sxs-lookup"><span data-stu-id="f5217-120">subProtocol</span></span>|<span data-ttu-id="f5217-121">Especifica el subprotocolo WebSocket.</span><span class="sxs-lookup"><span data-stu-id="f5217-121">Specifies the Web Socket subprotocol.</span></span>|  
|<span data-ttu-id="f5217-122">transportUsage</span><span class="sxs-lookup"><span data-stu-id="f5217-122">transportUsage</span></span>|<span data-ttu-id="f5217-123">Especifica cuándo usar WebSockets.</span><span class="sxs-lookup"><span data-stu-id="f5217-123">Specifies when to use Web Sockets.</span></span>|  
  
## <a name="transportusage-attribute"></a><span data-ttu-id="f5217-124">Atributo transportUsage</span><span class="sxs-lookup"><span data-stu-id="f5217-124">transportUsage Attribute</span></span>  
  
|<span data-ttu-id="f5217-125">Value</span><span class="sxs-lookup"><span data-stu-id="f5217-125">Value</span></span>|<span data-ttu-id="f5217-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="f5217-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f5217-127">WhenDuplex</span><span class="sxs-lookup"><span data-stu-id="f5217-127">WhenDuplex</span></span>|<span data-ttu-id="f5217-128">Use el protocolo WebSocket cuando el contrato sea dúplex.</span><span class="sxs-lookup"><span data-stu-id="f5217-128">Use the Web Socket protocol when the contract is duplex.</span></span>|  
|<span data-ttu-id="f5217-129">Siempre</span><span class="sxs-lookup"><span data-stu-id="f5217-129">Always</span></span>|<span data-ttu-id="f5217-130">Use siempre el protocolo WebSocket independientemente del contrato.</span><span class="sxs-lookup"><span data-stu-id="f5217-130">Always use the Web Socket protocol regardless of the contract.</span></span>|  
|<span data-ttu-id="f5217-131">Nunca</span><span class="sxs-lookup"><span data-stu-id="f5217-131">Never</span></span>|<span data-ttu-id="f5217-132">Nunca use el protocolo WebSocket.</span><span class="sxs-lookup"><span data-stu-id="f5217-132">Never use the Web Socket protocol.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f5217-133">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f5217-133">Child Elements</span></span>  
 <span data-ttu-id="f5217-134">None</span><span class="sxs-lookup"><span data-stu-id="f5217-134">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f5217-135">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f5217-135">Parent Elements</span></span>  
  
|<span data-ttu-id="f5217-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="f5217-136">Element</span></span>|<span data-ttu-id="f5217-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="f5217-137">Description</span></span>|  
|-------------|-----------------|  
|\<netHttpBinding>|<span data-ttu-id="f5217-138">Especifica el NetHttpBinding</span><span class="sxs-lookup"><span data-stu-id="f5217-138">Specifies the NetHttpBinding</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f5217-139">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f5217-139">Example</span></span>  
 <span data-ttu-id="f5217-140">El ejemplo siguiente muestra cómo usar el elemento \<webSocketSettings>.</span><span class="sxs-lookup"><span data-stu-id="f5217-140">The following example shows how to use the \<webSocketSettings> element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f5217-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f5217-141">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>
- [<span data-ttu-id="f5217-142">Enlaces</span><span class="sxs-lookup"><span data-stu-id="f5217-142">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="f5217-143">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="f5217-143">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="f5217-144">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="f5217-144">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
