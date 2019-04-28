---
title: <byteStreamMessageEncoding>
ms.date: 03/30/2017
ms.assetid: bbadd8dd-60a2-4007-b959-89373a8a7d60
ms.openlocfilehash: ce9f282ea1101befe3bf99762efa61e9b47b74cf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673379"
---
# <a name="bytestreammessageencoding"></a><span data-ttu-id="32c83-101">\<byteStreamMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="32c83-101">\<byteStreamMessageEncoding></span></span>
<span data-ttu-id="32c83-102">Especifica la codificación de mensajes como un flujo de bytes, con la opción especificar la codificación de caracteres.</span><span class="sxs-lookup"><span data-stu-id="32c83-102">Specifies the message encoding as a stream of bytes, with the option to specify the character encoding.</span></span>  
  
 <span data-ttu-id="32c83-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="32c83-103">\<system.serviceModel></span></span>  
<span data-ttu-id="32c83-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="32c83-104">\<bindings></span></span>  
<span data-ttu-id="32c83-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="32c83-105">\<customBinding></span></span>  
<span data-ttu-id="32c83-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="32c83-106">\<binding></span></span>  
<span data-ttu-id="32c83-107">\<binaryMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="32c83-107">\<binaryMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32c83-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="32c83-108">Syntax</span></span>  
  
```xml  
<byteStreamMessageEncoding />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="32c83-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="32c83-109">Attributes and Elements</span></span>  
 <span data-ttu-id="32c83-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="32c83-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="32c83-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="32c83-111">Attributes</span></span>  
  
|<span data-ttu-id="32c83-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="32c83-112">Attribute</span></span>|<span data-ttu-id="32c83-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="32c83-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="32c83-114">messageVersion</span><span class="sxs-lookup"><span data-stu-id="32c83-114">messageVersion</span></span>|<span data-ttu-id="32c83-115">Especifica la versión SOAP de los mensajes enviados utilizando el enlace.</span><span class="sxs-lookup"><span data-stu-id="32c83-115">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="32c83-116">Esta propiedad solo se puede establecer en el valor de la versión del mensaje de <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span><span class="sxs-lookup"><span data-stu-id="32c83-116">This property can only be set to the message version value of <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span> <span data-ttu-id="32c83-117">El codificador de mensajes de flujo de bytes no admite ninguna otra versión del mensaje.</span><span class="sxs-lookup"><span data-stu-id="32c83-117">The byte stream message encoder does not support any other message versions.</span></span><br /><br /> <span data-ttu-id="32c83-118">Este atributo es del tipo <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="32c83-118">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="32c83-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="32c83-119">Child Elements</span></span>  
  
|<span data-ttu-id="32c83-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="32c83-120">Element</span></span>|<span data-ttu-id="32c83-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="32c83-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="32c83-122">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="32c83-122">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="32c83-123">Define las restricciones en la complejidad de los mensajes SOAP que pueden ser procesados por los puntos de conexión configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="32c83-123">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="32c83-124">Este elemento es del tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="32c83-124">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="32c83-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="32c83-125">Parent Elements</span></span>  
  
|<span data-ttu-id="32c83-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="32c83-126">Element</span></span>|<span data-ttu-id="32c83-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="32c83-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="32c83-128">\<binding></span><span class="sxs-lookup"><span data-stu-id="32c83-128">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="32c83-129">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="32c83-129">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="32c83-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="32c83-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.ByteStreamMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>
- [<span data-ttu-id="32c83-131">Codificación de mensajes</span><span class="sxs-lookup"><span data-stu-id="32c83-131">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)
- [<span data-ttu-id="32c83-132">Elección de un codificador de mensajes</span><span class="sxs-lookup"><span data-stu-id="32c83-132">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="32c83-133">Enlaces</span><span class="sxs-lookup"><span data-stu-id="32c83-133">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="32c83-134">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="32c83-134">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="32c83-135">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="32c83-135">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="32c83-136">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="32c83-136">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
