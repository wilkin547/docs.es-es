---
title: <byteStreamMessageEncoding>
ms.date: 03/30/2017
ms.assetid: bbadd8dd-60a2-4007-b959-89373a8a7d60
ms.openlocfilehash: 1d4109bde9c1668bc0832689b05e5d1dc3b198e9
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73739069"
---
# <a name="bytestreammessageencoding"></a><span data-ttu-id="b0d59-101">\<byteStreamMessageEncoding ></span><span class="sxs-lookup"><span data-stu-id="b0d59-101">\<byteStreamMessageEncoding></span></span>
<span data-ttu-id="b0d59-102">Especifica la codificación de mensajes como un flujo de bytes, con la opción especificar la codificación de caracteres.</span><span class="sxs-lookup"><span data-stu-id="b0d59-102">Specifies the message encoding as a stream of bytes, with the option to specify the character encoding.</span></span>  
  
<span data-ttu-id="b0d59-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b0d59-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b0d59-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="b0d59-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="b0d59-105">&nbsp;&nbsp;&nbsp;&nbsp;\<[**enlaces**](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="b0d59-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="b0d59-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**customBinding**](custombinding.md) ></span><span class="sxs-lookup"><span data-stu-id="b0d59-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="b0d59-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**enlace** ></span><span class="sxs-lookup"><span data-stu-id="b0d59-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="b0d59-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<byteStreamMessageEncoding >**</span><span class="sxs-lookup"><span data-stu-id="b0d59-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<byteStreamMessageEncoding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0d59-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b0d59-109">Syntax</span></span>  
  
```xml  
<byteStreamMessageEncoding />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b0d59-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b0d59-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b0d59-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b0d59-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b0d59-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="b0d59-112">Attributes</span></span>  
  
|<span data-ttu-id="b0d59-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="b0d59-113">Attribute</span></span>|<span data-ttu-id="b0d59-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="b0d59-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b0d59-115">messageVersion</span><span class="sxs-lookup"><span data-stu-id="b0d59-115">messageVersion</span></span>|<span data-ttu-id="b0d59-116">Especifica la versión SOAP de los mensajes enviados utilizando el enlace.</span><span class="sxs-lookup"><span data-stu-id="b0d59-116">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="b0d59-117">Esta propiedad solo se puede establecer en el valor de la versión del mensaje de <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span><span class="sxs-lookup"><span data-stu-id="b0d59-117">This property can only be set to the message version value of <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span> <span data-ttu-id="b0d59-118">El codificador de mensajes de flujo de bytes no admite ninguna otra versión del mensaje.</span><span class="sxs-lookup"><span data-stu-id="b0d59-118">The byte stream message encoder does not support any other message versions.</span></span><br /><br /> <span data-ttu-id="b0d59-119">Este atributo es del tipo <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="b0d59-119">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b0d59-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b0d59-120">Child Elements</span></span>  
  
|<span data-ttu-id="b0d59-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="b0d59-121">Element</span></span>|<span data-ttu-id="b0d59-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="b0d59-122">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b0d59-123">[\<readerQuotas >](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="b0d59-123">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="b0d59-124">Define las restricciones en la complejidad de los mensajes SOAP que pueden ser procesados por los puntos de conexión configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="b0d59-124">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="b0d59-125">Este elemento es del tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="b0d59-125">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b0d59-126">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b0d59-126">Parent Elements</span></span>  
  
|<span data-ttu-id="b0d59-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="b0d59-127">Element</span></span>|<span data-ttu-id="b0d59-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="b0d59-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b0d59-129">\<> de enlace</span><span class="sxs-lookup"><span data-stu-id="b0d59-129">\<binding></span></span>](bindings.md)|<span data-ttu-id="b0d59-130">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="b0d59-130">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b0d59-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="b0d59-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.ByteStreamMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>
- [<span data-ttu-id="b0d59-132">Codificación de mensajes</span><span class="sxs-lookup"><span data-stu-id="b0d59-132">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="b0d59-133">Elección de un codificador de mensajes</span><span class="sxs-lookup"><span data-stu-id="b0d59-133">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="b0d59-134">Enlaces</span><span class="sxs-lookup"><span data-stu-id="b0d59-134">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="b0d59-135">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="b0d59-135">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="b0d59-136">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="b0d59-136">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="b0d59-137">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="b0d59-137">\<customBinding></span></span>](custombinding.md)
