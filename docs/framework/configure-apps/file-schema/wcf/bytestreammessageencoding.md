---
description: 'Más información acerca de: <byteStreamMessageEncoding>'
title: <byteStreamMessageEncoding>
ms.date: 03/30/2017
ms.assetid: bbadd8dd-60a2-4007-b959-89373a8a7d60
ms.openlocfilehash: 9cbb4eacb1a960481ee262db662160b5a342e27f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99639294"
---
# \<byteStreamMessageEncoding>

<span data-ttu-id="56379-102">Especifica la codificación de mensajes como un flujo de bytes, con la opción especificar la codificación de caracteres.</span><span class="sxs-lookup"><span data-stu-id="56379-102">Specifies the message encoding as a stream of bytes, with the option to specify the character encoding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<byteStreamMessageEncoding>**  
  
## <a name="syntax"></a><span data-ttu-id="56379-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="56379-103">Syntax</span></span>  
  
```xml  
<byteStreamMessageEncoding />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="56379-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="56379-104">Attributes and Elements</span></span>  

 <span data-ttu-id="56379-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="56379-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="56379-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="56379-106">Attributes</span></span>  
  
|<span data-ttu-id="56379-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="56379-107">Attribute</span></span>|<span data-ttu-id="56379-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="56379-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="56379-109">messageVersion</span><span class="sxs-lookup"><span data-stu-id="56379-109">messageVersion</span></span>|<span data-ttu-id="56379-110">Especifica la versión SOAP de los mensajes enviados utilizando el enlace.</span><span class="sxs-lookup"><span data-stu-id="56379-110">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="56379-111">Esta propiedad solo se puede establecer en el valor de la versión del mensaje de <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span><span class="sxs-lookup"><span data-stu-id="56379-111">This property can only be set to the message version value of <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span> <span data-ttu-id="56379-112">El codificador de mensajes de flujo de bytes no admite ninguna otra versión del mensaje.</span><span class="sxs-lookup"><span data-stu-id="56379-112">The byte stream message encoder does not support any other message versions.</span></span><br /><br /> <span data-ttu-id="56379-113">Este atributo es del tipo <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="56379-113">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="56379-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="56379-114">Child Elements</span></span>  
  
|<span data-ttu-id="56379-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="56379-115">Element</span></span>|<span data-ttu-id="56379-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="56379-116">Description</span></span>|  
|-------------|-----------------|  
|[\<readerQuotas>](/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="56379-117">Define las restricciones en la complejidad de los mensajes SOAP que pueden ser procesados por los puntos de conexión configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="56379-117">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="56379-118">Este elemento es del tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="56379-118">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="56379-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="56379-119">Parent Elements</span></span>  
  
|<span data-ttu-id="56379-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="56379-120">Element</span></span>|<span data-ttu-id="56379-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="56379-121">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="56379-122">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="56379-122">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="56379-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="56379-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.ByteStreamMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>
- [<span data-ttu-id="56379-124">Codificación de mensajes</span><span class="sxs-lookup"><span data-stu-id="56379-124">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="56379-125">Elección de un codificador de mensajes</span><span class="sxs-lookup"><span data-stu-id="56379-125">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="56379-126">Enlaces</span><span class="sxs-lookup"><span data-stu-id="56379-126">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="56379-127">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="56379-127">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="56379-128">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="56379-128">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
