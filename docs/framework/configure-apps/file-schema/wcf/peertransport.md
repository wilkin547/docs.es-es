---
title: <peerTransport>
ms.date: 03/30/2017
ms.assetid: c1a5013a-9dd4-4a27-b114-795b8b323177
ms.openlocfilehash: 68832c3a5bd4cc423642a6272e70cbecab86d6a8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91181549"
---
# \<peerTransport>

<span data-ttu-id="f50d0-101">Define un transporte del mismo nivel para un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="f50d0-101">Defines a peer transport for a custom binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<peerTransport>**  
  
## <a name="syntax"></a><span data-ttu-id="f50d0-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f50d0-102">Syntax</span></span>  
  
```xml  
<peerTransport listenIpAddress="String"
               maxBufferPoolSize="Integer"
               maxReceivedMessageSize="Integer"
               port="Integer">
  <security>
  </security>
</peerTransport>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f50d0-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f50d0-103">Attributes and Elements</span></span>  

 <span data-ttu-id="f50d0-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f50d0-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f50d0-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="f50d0-105">Attributes</span></span>  
  
|<span data-ttu-id="f50d0-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="f50d0-106">Attribute</span></span>|<span data-ttu-id="f50d0-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="f50d0-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f50d0-108">listenIpAddress</span><span class="sxs-lookup"><span data-stu-id="f50d0-108">listenIpAddress</span></span>|<span data-ttu-id="f50d0-109">Una cadena que especifica una dirección IP en la que el nodo entre pares realizará escuchas para los mensajes del TCP.</span><span class="sxs-lookup"><span data-stu-id="f50d0-109">A string that specifies an IP address on which the peer node will listen for TCP messages.</span></span> <span data-ttu-id="f50d0-110">El valor predeterminado es `null`.</span><span class="sxs-lookup"><span data-stu-id="f50d0-110">The default is `null`.</span></span>|  
|<span data-ttu-id="f50d0-111">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="f50d0-111">maxBufferPoolSize</span></span>|<span data-ttu-id="f50d0-112">Un entero positivo que especifica el tamaño máximo del grupo de búferes.</span><span class="sxs-lookup"><span data-stu-id="f50d0-112">A positive integer that specifies the maximum size of the buffer pool.</span></span> <span data-ttu-id="f50d0-113">El valor predeterminado es 524288.</span><span class="sxs-lookup"><span data-stu-id="f50d0-113">The default is 524288.</span></span><br /><br /> <span data-ttu-id="f50d0-114">Muchas partes de los búferes de uso WCF.</span><span class="sxs-lookup"><span data-stu-id="f50d0-114">Many parts of WCF use buffers.</span></span> <span data-ttu-id="f50d0-115">Crear y destruir búferes cada vez que se usan es caro, y la recolección de elementos no utilizados para los búferes también es cara.</span><span class="sxs-lookup"><span data-stu-id="f50d0-115">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="f50d0-116">Con grupos de búferes, puede tomar un búfer del grupo, usarlo y devolverlo al grupo una vez haya terminado.</span><span class="sxs-lookup"><span data-stu-id="f50d0-116">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="f50d0-117">Así se evita la sobrecarga al crear y destruir búferes.</span><span class="sxs-lookup"><span data-stu-id="f50d0-117">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="f50d0-118">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="f50d0-118">maxReceivedMessageSize</span></span>|<span data-ttu-id="f50d0-119">Un entero positivo que define el tamaño de mensaje máximo en bytes incluidos los encabezados.</span><span class="sxs-lookup"><span data-stu-id="f50d0-119">A positive integer that defines the maximum message size in bytes including headers.</span></span> <span data-ttu-id="f50d0-120">El remitente de un mensaje recibe un error SOAP cuando el mensaje es demasiado grande para el receptor.</span><span class="sxs-lookup"><span data-stu-id="f50d0-120">The sender of a message receives a SOAP fault when the message is too large for the receiver.</span></span> <span data-ttu-id="f50d0-121">El destinatario quita el mensaje y crea una entrada del evento en el registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="f50d0-121">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="f50d0-122">El valor predeterminado es 65536.</span><span class="sxs-lookup"><span data-stu-id="f50d0-122">The default is 65536.</span></span>|  
|<span data-ttu-id="f50d0-123">port</span><span class="sxs-lookup"><span data-stu-id="f50d0-123">port</span></span>|<span data-ttu-id="f50d0-124">Un entero que especifica el puerto de la interfaz de red en el que este enlace procesará los mensajes de TCP de canal del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="f50d0-124">An integer that specifies the network interface port on which this binding will process peer channel TCP messages.</span></span> <span data-ttu-id="f50d0-125">Dicho valor debe encontrarse entre <xref:System.Net.IPEndPoint.MinPort> y <xref:System.Net.IPEndPoint.MaxPort>.</span><span class="sxs-lookup"><span data-stu-id="f50d0-125">This value must be between <xref:System.Net.IPEndPoint.MinPort> and <xref:System.Net.IPEndPoint.MaxPort>.</span></span> <span data-ttu-id="f50d0-126">El valor predeterminado es 0.</span><span class="sxs-lookup"><span data-stu-id="f50d0-126">The default is 0.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f50d0-127">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f50d0-127">Child Elements</span></span>  
  
|<span data-ttu-id="f50d0-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="f50d0-128">Element</span></span>|<span data-ttu-id="f50d0-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="f50d0-129">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-peertransport.md)|<span data-ttu-id="f50d0-130">Define la configuración de seguridad para este transporte.</span><span class="sxs-lookup"><span data-stu-id="f50d0-130">Defines the security settings for this transport.</span></span> <span data-ttu-id="f50d0-131">Este elemento es del tipo <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="f50d0-131">This element is of type <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f50d0-132">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f50d0-132">Parent Elements</span></span>  
  
|<span data-ttu-id="f50d0-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="f50d0-133">Element</span></span>|<span data-ttu-id="f50d0-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="f50d0-134">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="f50d0-135">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="f50d0-135">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f50d0-136">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f50d0-136">Remarks</span></span>  

 <span data-ttu-id="f50d0-137">Este transporte no se puede utilizar con contratos que tengan operaciones respuesta-solicitud.</span><span class="sxs-lookup"><span data-stu-id="f50d0-137">This transport cannot be used with contracts that have request/reply operations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f50d0-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f50d0-138">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportElement>
- <xref:System.ServiceModel.Channels.PeerTransportBindingElement>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="f50d0-139">Transportes</span><span class="sxs-lookup"><span data-stu-id="f50d0-139">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="f50d0-140">Elección del transporte</span><span class="sxs-lookup"><span data-stu-id="f50d0-140">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="f50d0-141">Enlaces</span><span class="sxs-lookup"><span data-stu-id="f50d0-141">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="f50d0-142">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="f50d0-142">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="f50d0-143">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="f50d0-143">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
