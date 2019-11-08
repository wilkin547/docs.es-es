---
title: <peerTransport>
ms.date: 03/30/2017
ms.assetid: c1a5013a-9dd4-4a27-b114-795b8b323177
ms.openlocfilehash: 99fb013e052329ae4b99c4db89565ace8935c456
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73736509"
---
# <a name="peertransport"></a><span data-ttu-id="dc5b2-101">\<peerTransport ></span><span class="sxs-lookup"><span data-stu-id="dc5b2-101">\<peerTransport></span></span>
<span data-ttu-id="dc5b2-102">Define un transporte del mismo nivel para un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="dc5b2-102">Defines a peer transport for a custom binding.</span></span>  
  
<span data-ttu-id="dc5b2-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="dc5b2-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="dc5b2-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="dc5b2-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="dc5b2-105">&nbsp;&nbsp;&nbsp;&nbsp;\<[**enlaces**](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="dc5b2-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="dc5b2-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**customBinding**](custombinding.md) ></span><span class="sxs-lookup"><span data-stu-id="dc5b2-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="dc5b2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**enlace** ></span><span class="sxs-lookup"><span data-stu-id="dc5b2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="dc5b2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<peerTransport >**</span><span class="sxs-lookup"><span data-stu-id="dc5b2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<peerTransport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc5b2-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dc5b2-109">Syntax</span></span>  
  
```xml  
<peerTransport listenIpAddress="String"
               maxBufferPoolSize="Integer"
               maxReceivedMessageSize="Integer"
               port="Integer">
  <security>
  </security>
</peerTransport>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dc5b2-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="dc5b2-110">Attributes and Elements</span></span>  
 <span data-ttu-id="dc5b2-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="dc5b2-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dc5b2-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="dc5b2-112">Attributes</span></span>  
  
|<span data-ttu-id="dc5b2-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="dc5b2-113">Attribute</span></span>|<span data-ttu-id="dc5b2-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="dc5b2-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dc5b2-115">listenIpAddress</span><span class="sxs-lookup"><span data-stu-id="dc5b2-115">listenIpAddress</span></span>|<span data-ttu-id="dc5b2-116">Una cadena que especifica una dirección IP en la que el nodo entre pares realizará escuchas para los mensajes del TCP.</span><span class="sxs-lookup"><span data-stu-id="dc5b2-116">A string that specifies an IP address on which the peer node will listen for TCP messages.</span></span> <span data-ttu-id="dc5b2-117">De manera predeterminada, es `null`.</span><span class="sxs-lookup"><span data-stu-id="dc5b2-117">The default is `null`.</span></span>|  
|<span data-ttu-id="dc5b2-118">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="dc5b2-118">maxBufferPoolSize</span></span>|<span data-ttu-id="dc5b2-119">Un entero positivo que especifica el tamaño máximo del grupo de búferes.</span><span class="sxs-lookup"><span data-stu-id="dc5b2-119">A positive integer that specifies the maximum size of the buffer pool.</span></span> <span data-ttu-id="dc5b2-120">El valor predeterminado es 524288.</span><span class="sxs-lookup"><span data-stu-id="dc5b2-120">The default is 524288.</span></span><br /><br /> <span data-ttu-id="dc5b2-121">Muchas partes de los búferes de uso WCF.</span><span class="sxs-lookup"><span data-stu-id="dc5b2-121">Many parts of WCF use buffers.</span></span> <span data-ttu-id="dc5b2-122">Crear y destruir búferes cada vez que se usan es caro, y la recolección de elementos no utilizados para los búferes también es cara.</span><span class="sxs-lookup"><span data-stu-id="dc5b2-122">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="dc5b2-123">Con grupos de búferes, puede tomar un búfer del grupo, usarlo y devolverlo al grupo una vez haya terminado.</span><span class="sxs-lookup"><span data-stu-id="dc5b2-123">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="dc5b2-124">Así se evita la sobrecarga al crear y destruir búferes.</span><span class="sxs-lookup"><span data-stu-id="dc5b2-124">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="dc5b2-125">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="dc5b2-125">maxReceivedMessageSize</span></span>|<span data-ttu-id="dc5b2-126">Un entero positivo que define el tamaño de mensaje máximo en bytes incluidos los encabezados.</span><span class="sxs-lookup"><span data-stu-id="dc5b2-126">A positive integer that defines the maximum message size in bytes including headers.</span></span> <span data-ttu-id="dc5b2-127">El remitente de un mensaje recibe un error SOAP cuando el mensaje es demasiado grande para el receptor.</span><span class="sxs-lookup"><span data-stu-id="dc5b2-127">The sender of a message receives a SOAP fault when the message is too large for the receiver.</span></span> <span data-ttu-id="dc5b2-128">El destinatario quita el mensaje y crea una entrada del evento en el registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="dc5b2-128">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="dc5b2-129">El valor predeterminado es 65536.</span><span class="sxs-lookup"><span data-stu-id="dc5b2-129">The default is 65536.</span></span>|  
|<span data-ttu-id="dc5b2-130">puerto</span><span class="sxs-lookup"><span data-stu-id="dc5b2-130">port</span></span>|<span data-ttu-id="dc5b2-131">Un entero que especifica el puerto de la interfaz de red en el que este enlace procesará los mensajes de TCP de canal del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="dc5b2-131">An integer that specifies the network interface port on which this binding will process peer channel TCP messages.</span></span> <span data-ttu-id="dc5b2-132">Dicho valor debe encontrarse entre <xref:System.Net.IPEndPoint.MinPort> y <xref:System.Net.IPEndPoint.MaxPort>.</span><span class="sxs-lookup"><span data-stu-id="dc5b2-132">This value must be between <xref:System.Net.IPEndPoint.MinPort> and <xref:System.Net.IPEndPoint.MaxPort>.</span></span> <span data-ttu-id="dc5b2-133">El valor predeterminado es 0.</span><span class="sxs-lookup"><span data-stu-id="dc5b2-133">The default is 0.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dc5b2-134">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="dc5b2-134">Child Elements</span></span>  
  
|<span data-ttu-id="dc5b2-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="dc5b2-135">Element</span></span>|<span data-ttu-id="dc5b2-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="dc5b2-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dc5b2-137">\<La ></span><span class="sxs-lookup"><span data-stu-id="dc5b2-137">\<security></span></span>](security-of-peertransport.md)|<span data-ttu-id="dc5b2-138">Define la configuración de seguridad para este transporte.</span><span class="sxs-lookup"><span data-stu-id="dc5b2-138">Defines the security settings for this transport.</span></span> <span data-ttu-id="dc5b2-139">Este elemento es del tipo <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="dc5b2-139">This element is of type <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dc5b2-140">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="dc5b2-140">Parent Elements</span></span>  
  
|<span data-ttu-id="dc5b2-141">Elemento</span><span class="sxs-lookup"><span data-stu-id="dc5b2-141">Element</span></span>|<span data-ttu-id="dc5b2-142">Descripción</span><span class="sxs-lookup"><span data-stu-id="dc5b2-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dc5b2-143">\<> de enlace</span><span class="sxs-lookup"><span data-stu-id="dc5b2-143">\<binding></span></span>](bindings.md)|<span data-ttu-id="dc5b2-144">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="dc5b2-144">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dc5b2-145">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dc5b2-145">Remarks</span></span>  
 <span data-ttu-id="dc5b2-146">Este transporte no se puede utilizar con contratos que tengan operaciones respuesta-solicitud.</span><span class="sxs-lookup"><span data-stu-id="dc5b2-146">This transport cannot be used with contracts that have request/reply operations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc5b2-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="dc5b2-147">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportElement>
- <xref:System.ServiceModel.Channels.PeerTransportBindingElement>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="dc5b2-148">Transportes</span><span class="sxs-lookup"><span data-stu-id="dc5b2-148">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="dc5b2-149">Elección del transporte</span><span class="sxs-lookup"><span data-stu-id="dc5b2-149">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="dc5b2-150">Enlaces</span><span class="sxs-lookup"><span data-stu-id="dc5b2-150">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="dc5b2-151">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="dc5b2-151">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="dc5b2-152">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="dc5b2-152">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="dc5b2-153">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="dc5b2-153">\<customBinding></span></span>](custombinding.md)
