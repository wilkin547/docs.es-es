---
title: '&lt;byteStreamMessageEncoding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bbadd8dd-60a2-4007-b959-89373a8a7d60
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 165bf4cd1c0c5c1a6adae91650d38984bc47ef6e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="ltbytestreammessageencodinggt"></a><span data-ttu-id="00036-102">&lt;byteStreamMessageEncoding&gt;</span><span class="sxs-lookup"><span data-stu-id="00036-102">&lt;byteStreamMessageEncoding&gt;</span></span>
<span data-ttu-id="00036-103">Especifica la codificación de mensajes como un flujo de bytes, con la opción especificar la codificación de caracteres.</span><span class="sxs-lookup"><span data-stu-id="00036-103">Specifies the message encoding as a stream of bytes, with the option to specify the character encoding.</span></span>  
  
 <span data-ttu-id="00036-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="00036-104">\<system.serviceModel></span></span>  
<span data-ttu-id="00036-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="00036-105">\<bindings></span></span>  
<span data-ttu-id="00036-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="00036-106">\<customBinding></span></span>  
<span data-ttu-id="00036-107">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="00036-107">\<binding></span></span>  
<span data-ttu-id="00036-108">\<binaryMessageEncoding ></span><span class="sxs-lookup"><span data-stu-id="00036-108">\<binaryMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00036-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="00036-109">Syntax</span></span>  
  
```xml  
<byteStreamMessageEncoding/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="00036-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="00036-110">Attributes and Elements</span></span>  
 <span data-ttu-id="00036-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="00036-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="00036-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="00036-112">Attributes</span></span>  
  
|<span data-ttu-id="00036-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="00036-113">Attribute</span></span>|<span data-ttu-id="00036-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="00036-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="00036-115">messageVersion</span><span class="sxs-lookup"><span data-stu-id="00036-115">messageVersion</span></span>|<span data-ttu-id="00036-116">Especifica la versión SOAP de los mensajes enviados utilizando el enlace.</span><span class="sxs-lookup"><span data-stu-id="00036-116">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="00036-117">Esta propiedad solo se puede establecer en el valor de la versión del mensaje de <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span><span class="sxs-lookup"><span data-stu-id="00036-117">This property can only be set to the message version value of <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span> <span data-ttu-id="00036-118">El codificador de mensajes de flujo de bytes no admite ninguna otra versión del mensaje.</span><span class="sxs-lookup"><span data-stu-id="00036-118">The byte stream message encoder does not support any other message versions.</span></span><br /><br /> <span data-ttu-id="00036-119">Este atributo es del tipo <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="00036-119">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="00036-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="00036-120">Child Elements</span></span>  
  
|<span data-ttu-id="00036-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="00036-121">Element</span></span>|<span data-ttu-id="00036-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="00036-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="00036-123">\<readerQuotas ></span><span class="sxs-lookup"><span data-stu-id="00036-123">\<readerQuotas></span></span>](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="00036-124">Define las restricciones en la complejidad de los mensajes SOAP que pueden ser procesados por los puntos de conexión configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="00036-124">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="00036-125">Este elemento es del tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="00036-125">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="00036-126">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="00036-126">Parent Elements</span></span>  
  
|<span data-ttu-id="00036-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="00036-127">Element</span></span>|<span data-ttu-id="00036-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="00036-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="00036-129">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="00036-129">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="00036-130">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="00036-130">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="00036-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="00036-131">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ByteStreamMessageEncodingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>  
 <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>  
 [<span data-ttu-id="00036-132">Codificación de mensajes</span><span class="sxs-lookup"><span data-stu-id="00036-132">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)  
 [<span data-ttu-id="00036-133">Elegir un codificador de mensajes</span><span class="sxs-lookup"><span data-stu-id="00036-133">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 [<span data-ttu-id="00036-134">Enlaces</span><span class="sxs-lookup"><span data-stu-id="00036-134">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="00036-135">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="00036-135">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="00036-136">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="00036-136">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="00036-137">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="00036-137">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
