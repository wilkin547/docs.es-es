---
title: <byteStreamMessageEncoding>
ms.date: 03/30/2017
ms.assetid: bbadd8dd-60a2-4007-b959-89373a8a7d60
ms.openlocfilehash: b11f472c0e33003e50be4b45bb49196c64ecb70d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919730"
---
# <a name="bytestreammessageencoding"></a><span data-ttu-id="51558-101">\<byteStreamMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="51558-101">\<byteStreamMessageEncoding></span></span>
<span data-ttu-id="51558-102">Especifica la codificación de mensajes como un flujo de bytes, con la opción especificar la codificación de caracteres.</span><span class="sxs-lookup"><span data-stu-id="51558-102">Specifies the message encoding as a stream of bytes, with the option to specify the character encoding.</span></span>  
  
 <span data-ttu-id="51558-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="51558-103">\<system.serviceModel></span></span>  
<span data-ttu-id="51558-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="51558-104">\<bindings></span></span>  
<span data-ttu-id="51558-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="51558-105">\<customBinding></span></span>  
<span data-ttu-id="51558-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="51558-106">\<binding></span></span>  
<span data-ttu-id="51558-107">\<binaryMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="51558-107">\<binaryMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51558-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="51558-108">Syntax</span></span>  
  
```xml  
<byteStreamMessageEncoding />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="51558-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="51558-109">Attributes and Elements</span></span>  
 <span data-ttu-id="51558-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="51558-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="51558-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="51558-111">Attributes</span></span>  
  
|<span data-ttu-id="51558-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="51558-112">Attribute</span></span>|<span data-ttu-id="51558-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="51558-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="51558-114">messageVersion</span><span class="sxs-lookup"><span data-stu-id="51558-114">messageVersion</span></span>|<span data-ttu-id="51558-115">Especifica la versión SOAP de los mensajes enviados utilizando el enlace.</span><span class="sxs-lookup"><span data-stu-id="51558-115">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="51558-116">Esta propiedad solo se puede establecer en el valor de la versión del mensaje de <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span><span class="sxs-lookup"><span data-stu-id="51558-116">This property can only be set to the message version value of <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span> <span data-ttu-id="51558-117">El codificador de mensajes de flujo de bytes no admite ninguna otra versión del mensaje.</span><span class="sxs-lookup"><span data-stu-id="51558-117">The byte stream message encoder does not support any other message versions.</span></span><br /><br /> <span data-ttu-id="51558-118">Este atributo es del tipo <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="51558-118">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="51558-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="51558-119">Child Elements</span></span>  
  
|<span data-ttu-id="51558-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="51558-120">Element</span></span>|<span data-ttu-id="51558-121">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="51558-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="51558-122">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="51558-122">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="51558-123">Define las restricciones en la complejidad de los mensajes SOAP que pueden ser procesados por los puntos de conexión configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="51558-123">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="51558-124">Este elemento es del tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="51558-124">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="51558-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="51558-125">Parent Elements</span></span>  
  
|<span data-ttu-id="51558-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="51558-126">Element</span></span>|<span data-ttu-id="51558-127">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="51558-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="51558-128">\<binding></span><span class="sxs-lookup"><span data-stu-id="51558-128">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="51558-129">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="51558-129">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="51558-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="51558-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.ByteStreamMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>
- [<span data-ttu-id="51558-131">Codificación de mensajes</span><span class="sxs-lookup"><span data-stu-id="51558-131">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="51558-132">Elección de un codificador de mensajes</span><span class="sxs-lookup"><span data-stu-id="51558-132">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="51558-133">Enlaces</span><span class="sxs-lookup"><span data-stu-id="51558-133">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="51558-134">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="51558-134">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="51558-135">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="51558-135">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="51558-136">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="51558-136">\<customBinding></span></span>](custombinding.md)
