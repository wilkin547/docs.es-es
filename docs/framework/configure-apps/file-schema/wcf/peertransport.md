---
title: <peerTransport>
ms.date: 03/30/2017
ms.assetid: c1a5013a-9dd4-4a27-b114-795b8b323177
ms.openlocfilehash: 6765259f290047a4199a422b4ad0cced2ffee9ae
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59179835"
---
# <a name="peertransport"></a><span data-ttu-id="307df-101">\<peerTransport></span><span class="sxs-lookup"><span data-stu-id="307df-101">\<peerTransport></span></span>
<span data-ttu-id="307df-102">Define un transporte del mismo nivel para un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="307df-102">Defines a peer transport for a custom binding.</span></span>  
  
 <span data-ttu-id="307df-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="307df-103">\<system.serviceModel></span></span>  
<span data-ttu-id="307df-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="307df-104">\<bindings></span></span>  
<span data-ttu-id="307df-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="307df-105">\<customBinding></span></span>  
<span data-ttu-id="307df-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="307df-106">\<binding></span></span>  
<span data-ttu-id="307df-107">\<peerTransport></span><span class="sxs-lookup"><span data-stu-id="307df-107">\<peerTransport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="307df-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="307df-108">Syntax</span></span>  
  
```xml  
<peerTransport listenIpAddress="String"
               maxBufferPoolSize="Integer"
               maxReceivedMessageSize="Integer"
               port="Integer">
  <security>
  </security>
</peerTransport>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="307df-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="307df-109">Attributes and Elements</span></span>  
 <span data-ttu-id="307df-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="307df-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="307df-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="307df-111">Attributes</span></span>  
  
|<span data-ttu-id="307df-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="307df-112">Attribute</span></span>|<span data-ttu-id="307df-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="307df-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="307df-114">listenIpAddress</span><span class="sxs-lookup"><span data-stu-id="307df-114">listenIpAddress</span></span>|<span data-ttu-id="307df-115">Una cadena que especifica una dirección IP en la que el nodo entre pares realizará escuchas para los mensajes del TCP.</span><span class="sxs-lookup"><span data-stu-id="307df-115">A string that specifies an IP address on which the peer node will listen for TCP messages.</span></span> <span data-ttu-id="307df-116">De manera predeterminada, es `null`.</span><span class="sxs-lookup"><span data-stu-id="307df-116">The default is `null`.</span></span>|  
|<span data-ttu-id="307df-117">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="307df-117">maxBufferPoolSize</span></span>|<span data-ttu-id="307df-118">Un entero positivo que especifica el tamaño máximo del grupo de búferes.</span><span class="sxs-lookup"><span data-stu-id="307df-118">A positive integer that specifies the maximum size of the buffer pool.</span></span> <span data-ttu-id="307df-119">El valor predeterminado es 524288.</span><span class="sxs-lookup"><span data-stu-id="307df-119">The default is 524288.</span></span><br /><br /> <span data-ttu-id="307df-120">Muchas partes de los búferes de uso WCF.</span><span class="sxs-lookup"><span data-stu-id="307df-120">Many parts of WCF use buffers.</span></span> <span data-ttu-id="307df-121">Crear y destruir búferes cada vez que se usan es caro, y la recolección de elementos no utilizados para los búferes también es cara.</span><span class="sxs-lookup"><span data-stu-id="307df-121">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="307df-122">Con grupos de búferes, puede tomar un búfer del grupo, usarlo y devolverlo al grupo una vez haya terminado.</span><span class="sxs-lookup"><span data-stu-id="307df-122">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="307df-123">Así se evita la sobrecarga al crear y destruir búferes.</span><span class="sxs-lookup"><span data-stu-id="307df-123">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="307df-124">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="307df-124">maxReceivedMessageSize</span></span>|<span data-ttu-id="307df-125">Un entero positivo que define el tamaño de mensaje máximo en bytes incluidos los encabezados.</span><span class="sxs-lookup"><span data-stu-id="307df-125">A positive integer that defines the maximum message size in bytes including headers.</span></span> <span data-ttu-id="307df-126">El remitente de un mensaje recibe un error SOAP cuando el mensaje es demasiado grande para el receptor.</span><span class="sxs-lookup"><span data-stu-id="307df-126">The sender of a message receives a SOAP fault when the message is too large for the receiver.</span></span> <span data-ttu-id="307df-127">El destinatario quita el mensaje y crea una entrada del evento en el registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="307df-127">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="307df-128">El valor predeterminado es 65536.</span><span class="sxs-lookup"><span data-stu-id="307df-128">The default is 65536.</span></span>|  
|<span data-ttu-id="307df-129">puerto</span><span class="sxs-lookup"><span data-stu-id="307df-129">port</span></span>|<span data-ttu-id="307df-130">Un entero que especifica el puerto de la interfaz de red en el que este enlace procesará los mensajes de TCP de canal del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="307df-130">An integer that specifies the network interface port on which this binding will process peer channel TCP messages.</span></span> <span data-ttu-id="307df-131">Dicho valor debe encontrarse entre <xref:System.Net.IPEndPoint.MinPort> y <xref:System.Net.IPEndPoint.MaxPort>.</span><span class="sxs-lookup"><span data-stu-id="307df-131">This value must be between <xref:System.Net.IPEndPoint.MinPort> and <xref:System.Net.IPEndPoint.MaxPort>.</span></span> <span data-ttu-id="307df-132">El valor predeterminado es 0.</span><span class="sxs-lookup"><span data-stu-id="307df-132">The default is 0.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="307df-133">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="307df-133">Child Elements</span></span>  
  
|<span data-ttu-id="307df-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="307df-134">Element</span></span>|<span data-ttu-id="307df-135">Descripción</span><span class="sxs-lookup"><span data-stu-id="307df-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="307df-136">\<security></span><span class="sxs-lookup"><span data-stu-id="307df-136">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md)|<span data-ttu-id="307df-137">Define la configuración de seguridad para este transporte.</span><span class="sxs-lookup"><span data-stu-id="307df-137">Defines the security settings for this transport.</span></span> <span data-ttu-id="307df-138">Este elemento es del tipo <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="307df-138">This element is of type <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="307df-139">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="307df-139">Parent Elements</span></span>  
  
|<span data-ttu-id="307df-140">Elemento</span><span class="sxs-lookup"><span data-stu-id="307df-140">Element</span></span>|<span data-ttu-id="307df-141">Descripción</span><span class="sxs-lookup"><span data-stu-id="307df-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="307df-142">\<binding></span><span class="sxs-lookup"><span data-stu-id="307df-142">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="307df-143">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="307df-143">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="307df-144">Comentarios</span><span class="sxs-lookup"><span data-stu-id="307df-144">Remarks</span></span>  
 <span data-ttu-id="307df-145">Este transporte no se puede utilizar con contratos que tengan operaciones respuesta-solicitud.</span><span class="sxs-lookup"><span data-stu-id="307df-145">This transport cannot be used with contracts that have request/reply operations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="307df-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="307df-146">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportElement>
- <xref:System.ServiceModel.Channels.PeerTransportBindingElement>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="307df-147">Transportes</span><span class="sxs-lookup"><span data-stu-id="307df-147">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)
- [<span data-ttu-id="307df-148">Elección del transporte</span><span class="sxs-lookup"><span data-stu-id="307df-148">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="307df-149">Enlaces</span><span class="sxs-lookup"><span data-stu-id="307df-149">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="307df-150">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="307df-150">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="307df-151">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="307df-151">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="307df-152">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="307df-152">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
