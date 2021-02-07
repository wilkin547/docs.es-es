---
description: 'Más información acerca de: <peerTransport>'
title: <peerTransport>
ms.date: 03/30/2017
ms.assetid: c1a5013a-9dd4-4a27-b114-795b8b323177
ms.openlocfilehash: babc4196c63d46b7515ac67812d5d584eb3ffcac
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99683624"
---
# \<peerTransport>

<span data-ttu-id="3b02a-102">Define un transporte del mismo nivel para un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="3b02a-102">Defines a peer transport for a custom binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<peerTransport>**  
  
## <a name="syntax"></a><span data-ttu-id="3b02a-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3b02a-103">Syntax</span></span>  
  
```xml  
<peerTransport listenIpAddress="String"
               maxBufferPoolSize="Integer"
               maxReceivedMessageSize="Integer"
               port="Integer">
  <security>
  </security>
</peerTransport>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3b02a-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3b02a-104">Attributes and Elements</span></span>  

 <span data-ttu-id="3b02a-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3b02a-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3b02a-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="3b02a-106">Attributes</span></span>  
  
|<span data-ttu-id="3b02a-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="3b02a-107">Attribute</span></span>|<span data-ttu-id="3b02a-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="3b02a-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3b02a-109">listenIpAddress</span><span class="sxs-lookup"><span data-stu-id="3b02a-109">listenIpAddress</span></span>|<span data-ttu-id="3b02a-110">Una cadena que especifica una dirección IP en la que el nodo entre pares realizará escuchas para los mensajes del TCP.</span><span class="sxs-lookup"><span data-stu-id="3b02a-110">A string that specifies an IP address on which the peer node will listen for TCP messages.</span></span> <span data-ttu-id="3b02a-111">De manera predeterminada, es `null`.</span><span class="sxs-lookup"><span data-stu-id="3b02a-111">The default is `null`.</span></span>|  
|<span data-ttu-id="3b02a-112">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="3b02a-112">maxBufferPoolSize</span></span>|<span data-ttu-id="3b02a-113">Un entero positivo que especifica el tamaño máximo del grupo de búferes.</span><span class="sxs-lookup"><span data-stu-id="3b02a-113">A positive integer that specifies the maximum size of the buffer pool.</span></span> <span data-ttu-id="3b02a-114">El valor predeterminado es 524288.</span><span class="sxs-lookup"><span data-stu-id="3b02a-114">The default is 524288.</span></span><br /><br /> <span data-ttu-id="3b02a-115">Muchas partes de los búferes de uso WCF.</span><span class="sxs-lookup"><span data-stu-id="3b02a-115">Many parts of WCF use buffers.</span></span> <span data-ttu-id="3b02a-116">Crear y destruir búferes cada vez que se usan es caro, y la recolección de elementos no utilizados para los búferes también es cara.</span><span class="sxs-lookup"><span data-stu-id="3b02a-116">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="3b02a-117">Con grupos de búferes, puede tomar un búfer del grupo, usarlo y devolverlo al grupo una vez haya terminado.</span><span class="sxs-lookup"><span data-stu-id="3b02a-117">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="3b02a-118">Así se evita la sobrecarga al crear y destruir búferes.</span><span class="sxs-lookup"><span data-stu-id="3b02a-118">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="3b02a-119">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="3b02a-119">maxReceivedMessageSize</span></span>|<span data-ttu-id="3b02a-120">Un entero positivo que define el tamaño de mensaje máximo en bytes incluidos los encabezados.</span><span class="sxs-lookup"><span data-stu-id="3b02a-120">A positive integer that defines the maximum message size in bytes including headers.</span></span> <span data-ttu-id="3b02a-121">El remitente de un mensaje recibe un error SOAP cuando el mensaje es demasiado grande para el receptor.</span><span class="sxs-lookup"><span data-stu-id="3b02a-121">The sender of a message receives a SOAP fault when the message is too large for the receiver.</span></span> <span data-ttu-id="3b02a-122">El destinatario quita el mensaje y crea una entrada del evento en el registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="3b02a-122">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="3b02a-123">El valor predeterminado es 65536.</span><span class="sxs-lookup"><span data-stu-id="3b02a-123">The default is 65536.</span></span>|  
|<span data-ttu-id="3b02a-124">port</span><span class="sxs-lookup"><span data-stu-id="3b02a-124">port</span></span>|<span data-ttu-id="3b02a-125">Un entero que especifica el puerto de la interfaz de red en el que este enlace procesará los mensajes de TCP de canal del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="3b02a-125">An integer that specifies the network interface port on which this binding will process peer channel TCP messages.</span></span> <span data-ttu-id="3b02a-126">Dicho valor debe encontrarse entre <xref:System.Net.IPEndPoint.MinPort> y <xref:System.Net.IPEndPoint.MaxPort>.</span><span class="sxs-lookup"><span data-stu-id="3b02a-126">This value must be between <xref:System.Net.IPEndPoint.MinPort> and <xref:System.Net.IPEndPoint.MaxPort>.</span></span> <span data-ttu-id="3b02a-127">El valor predeterminado es 0.</span><span class="sxs-lookup"><span data-stu-id="3b02a-127">The default is 0.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3b02a-128">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3b02a-128">Child Elements</span></span>  
  
|<span data-ttu-id="3b02a-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="3b02a-129">Element</span></span>|<span data-ttu-id="3b02a-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="3b02a-130">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-peertransport.md)|<span data-ttu-id="3b02a-131">Define la configuración de seguridad para este transporte.</span><span class="sxs-lookup"><span data-stu-id="3b02a-131">Defines the security settings for this transport.</span></span> <span data-ttu-id="3b02a-132">Este elemento es del tipo <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="3b02a-132">This element is of type <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3b02a-133">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3b02a-133">Parent Elements</span></span>  
  
|<span data-ttu-id="3b02a-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="3b02a-134">Element</span></span>|<span data-ttu-id="3b02a-135">Descripción</span><span class="sxs-lookup"><span data-stu-id="3b02a-135">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="3b02a-136">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="3b02a-136">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3b02a-137">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3b02a-137">Remarks</span></span>  

 <span data-ttu-id="3b02a-138">Este transporte no se puede utilizar con contratos que tengan operaciones respuesta-solicitud.</span><span class="sxs-lookup"><span data-stu-id="3b02a-138">This transport cannot be used with contracts that have request/reply operations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b02a-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="3b02a-139">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportElement>
- <xref:System.ServiceModel.Channels.PeerTransportBindingElement>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="3b02a-140">Transportes</span><span class="sxs-lookup"><span data-stu-id="3b02a-140">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="3b02a-141">Elección del transporte</span><span class="sxs-lookup"><span data-stu-id="3b02a-141">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="3b02a-142">Enlaces</span><span class="sxs-lookup"><span data-stu-id="3b02a-142">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="3b02a-143">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="3b02a-143">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="3b02a-144">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="3b02a-144">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
