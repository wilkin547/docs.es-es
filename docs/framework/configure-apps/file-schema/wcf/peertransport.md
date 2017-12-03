---
title: '&lt;peerTransport&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c1a5013a-9dd4-4a27-b114-795b8b323177
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bfa8c480524c920ac2f73236b6548072e7805ab2
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="ltpeertransportgt"></a><span data-ttu-id="a45d3-102">&lt;peerTransport&gt;</span><span class="sxs-lookup"><span data-stu-id="a45d3-102">&lt;peerTransport&gt;</span></span>
<span data-ttu-id="a45d3-103">Define un transporte del mismo nivel para un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="a45d3-103">Defines a peer transport for a custom binding.</span></span>  
  
 <span data-ttu-id="a45d3-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="a45d3-104">\<system.serviceModel></span></span>  
<span data-ttu-id="a45d3-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="a45d3-105">\<bindings></span></span>  
<span data-ttu-id="a45d3-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="a45d3-106">\<customBinding></span></span>  
<span data-ttu-id="a45d3-107">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="a45d3-107">\<binding></span></span>  
<span data-ttu-id="a45d3-108">\<peerTransport ></span><span class="sxs-lookup"><span data-stu-id="a45d3-108">\<peerTransport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a45d3-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a45d3-109">Syntax</span></span>  
  
```xml  
<peerTransport   
    listenIpAddress="String"  
    maxBufferPoolSize="Integer"  
    maxReceivedMessageSize="Integer"  
    port="Integer"  
        <security>  
    </security>  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a45d3-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a45d3-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a45d3-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a45d3-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a45d3-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="a45d3-112">Attributes</span></span>  
  
|<span data-ttu-id="a45d3-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="a45d3-113">Attribute</span></span>|<span data-ttu-id="a45d3-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="a45d3-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a45d3-115">listenIpAddress</span><span class="sxs-lookup"><span data-stu-id="a45d3-115">listenIpAddress</span></span>|<span data-ttu-id="a45d3-116">Una cadena que especifica una dirección IP en la que el nodo entre pares realizará escuchas para los mensajes del TCP.</span><span class="sxs-lookup"><span data-stu-id="a45d3-116">A string that specifies an IP address on which the peer node will listen for TCP messages.</span></span> <span data-ttu-id="a45d3-117">De manera predeterminada, es `null`.</span><span class="sxs-lookup"><span data-stu-id="a45d3-117">The default is `null`.</span></span>|  
|<span data-ttu-id="a45d3-118">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="a45d3-118">maxBufferPoolSize</span></span>|<span data-ttu-id="a45d3-119">Un entero positivo que especifica el tamaño máximo del grupo de búferes.</span><span class="sxs-lookup"><span data-stu-id="a45d3-119">A positive integer that specifies the maximum size of the buffer pool.</span></span> <span data-ttu-id="a45d3-120">El valor predeterminado es 524288.</span><span class="sxs-lookup"><span data-stu-id="a45d3-120">The default is 524288.</span></span><br /><br /> <span data-ttu-id="a45d3-121">Muchas partes de los búferes de uso WCF.</span><span class="sxs-lookup"><span data-stu-id="a45d3-121">Many parts of WCF use buffers.</span></span> <span data-ttu-id="a45d3-122">Crear y destruir búferes cada vez que se usan es caro, y la recolección de elementos no utilizados para los búferes también es cara.</span><span class="sxs-lookup"><span data-stu-id="a45d3-122">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="a45d3-123">Con grupos de búferes, puede tomar un búfer del grupo, usarlo y devolverlo al grupo una vez haya terminado.</span><span class="sxs-lookup"><span data-stu-id="a45d3-123">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="a45d3-124">Así se evita la sobrecarga al crear y destruir búferes.</span><span class="sxs-lookup"><span data-stu-id="a45d3-124">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="a45d3-125">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="a45d3-125">maxReceivedMessageSize</span></span>|<span data-ttu-id="a45d3-126">Un entero positivo que define el tamaño de mensaje máximo en bytes incluidos los encabezados.</span><span class="sxs-lookup"><span data-stu-id="a45d3-126">A positive integer that defines the maximum message size in bytes including headers.</span></span> <span data-ttu-id="a45d3-127">El remitente de un mensaje recibe un error SOAP cuando el mensaje es demasiado grande para el receptor.</span><span class="sxs-lookup"><span data-stu-id="a45d3-127">The sender of a message receives a SOAP fault when the message is too large for the receiver.</span></span> <span data-ttu-id="a45d3-128">El destinatario quita el mensaje y crea una entrada del evento en el registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="a45d3-128">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="a45d3-129">El valor predeterminado es 65536.</span><span class="sxs-lookup"><span data-stu-id="a45d3-129">The default is 65536.</span></span>|  
|<span data-ttu-id="a45d3-130">puerto</span><span class="sxs-lookup"><span data-stu-id="a45d3-130">port</span></span>|<span data-ttu-id="a45d3-131">Un entero que especifica el puerto de la interfaz de red en el que este enlace procesará los mensajes de TCP de canal del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="a45d3-131">An integer that specifies the network interface port on which this binding will process peer channel TCP messages.</span></span> <span data-ttu-id="a45d3-132">Dicho valor debe encontrarse entre <xref:System.Net.IPEndPoint.MinPort> y <xref:System.Net.IPEndPoint.MaxPort>.</span><span class="sxs-lookup"><span data-stu-id="a45d3-132">This value must be between <xref:System.Net.IPEndPoint.MinPort> and <xref:System.Net.IPEndPoint.MaxPort>.</span></span> <span data-ttu-id="a45d3-133">El valor predeterminado es 0.</span><span class="sxs-lookup"><span data-stu-id="a45d3-133">The default is 0.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a45d3-134">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a45d3-134">Child Elements</span></span>  
  
|<span data-ttu-id="a45d3-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="a45d3-135">Element</span></span>|<span data-ttu-id="a45d3-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="a45d3-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a45d3-137">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="a45d3-137">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md)|<span data-ttu-id="a45d3-138">Define la configuración de seguridad para este transporte.</span><span class="sxs-lookup"><span data-stu-id="a45d3-138">Defines the security settings for this transport.</span></span> <span data-ttu-id="a45d3-139">Este elemento es del tipo <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="a45d3-139">This element is of type <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a45d3-140">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a45d3-140">Parent Elements</span></span>  
  
|<span data-ttu-id="a45d3-141">Elemento</span><span class="sxs-lookup"><span data-stu-id="a45d3-141">Element</span></span>|<span data-ttu-id="a45d3-142">Descripción</span><span class="sxs-lookup"><span data-stu-id="a45d3-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a45d3-143">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="a45d3-143">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="a45d3-144">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="a45d3-144">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a45d3-145">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a45d3-145">Remarks</span></span>  
 <span data-ttu-id="a45d3-146">Este transporte no se puede utilizar con contratos que tengan operaciones respuesta-solicitud.</span><span class="sxs-lookup"><span data-stu-id="a45d3-146">This transport cannot be used with contracts that have request/reply operations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a45d3-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="a45d3-147">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerTransportElement>  
 <xref:System.ServiceModel.Channels.PeerTransportBindingElement>  
 <xref:System.ServiceModel.Channels.TransportBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="a45d3-148">Transportes</span><span class="sxs-lookup"><span data-stu-id="a45d3-148">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)  
 [<span data-ttu-id="a45d3-149">Elegir un transporte</span><span class="sxs-lookup"><span data-stu-id="a45d3-149">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 [<span data-ttu-id="a45d3-150">Enlaces</span><span class="sxs-lookup"><span data-stu-id="a45d3-150">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="a45d3-151">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="a45d3-151">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="a45d3-152">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="a45d3-152">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="a45d3-153">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="a45d3-153">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
