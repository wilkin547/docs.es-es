---
title: <byteStreamMessageEncoding>
ms.date: 03/30/2017
ms.assetid: bbadd8dd-60a2-4007-b959-89373a8a7d60
ms.openlocfilehash: 1d4109bde9c1668bc0832689b05e5d1dc3b198e9
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "73739069"
---
# \<byteStreamMessageEncoding>
<span data-ttu-id="0d782-101">Especifica la codificación de mensajes como un flujo de bytes, con la opción especificar la codificación de caracteres.</span><span class="sxs-lookup"><span data-stu-id="0d782-101">Specifies the message encoding as a stream of bytes, with the option to specify the character encoding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<byteStreamMessageEncoding>**  
  
## <a name="syntax"></a><span data-ttu-id="0d782-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0d782-102">Syntax</span></span>  
  
```xml  
<byteStreamMessageEncoding />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0d782-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="0d782-103">Attributes and Elements</span></span>  
 <span data-ttu-id="0d782-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="0d782-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0d782-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="0d782-105">Attributes</span></span>  
  
|<span data-ttu-id="0d782-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="0d782-106">Attribute</span></span>|<span data-ttu-id="0d782-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="0d782-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0d782-108">messageVersion</span><span class="sxs-lookup"><span data-stu-id="0d782-108">messageVersion</span></span>|<span data-ttu-id="0d782-109">Especifica la versión SOAP de los mensajes enviados utilizando el enlace.</span><span class="sxs-lookup"><span data-stu-id="0d782-109">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="0d782-110">Esta propiedad solo se puede establecer en el valor de la versión del mensaje de <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span><span class="sxs-lookup"><span data-stu-id="0d782-110">This property can only be set to the message version value of <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span> <span data-ttu-id="0d782-111">El codificador de mensajes de flujo de bytes no admite ninguna otra versión del mensaje.</span><span class="sxs-lookup"><span data-stu-id="0d782-111">The byte stream message encoder does not support any other message versions.</span></span><br /><br /> <span data-ttu-id="0d782-112">Este atributo es del tipo <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="0d782-112">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0d782-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0d782-113">Child Elements</span></span>  
  
|<span data-ttu-id="0d782-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="0d782-114">Element</span></span>|<span data-ttu-id="0d782-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="0d782-115">Description</span></span>|  
|-------------|-----------------|  
|[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="0d782-116">Define las restricciones en la complejidad de los mensajes SOAP que pueden ser procesados por los puntos de conexión configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="0d782-116">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="0d782-117">Este elemento es del tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="0d782-117">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0d782-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0d782-118">Parent Elements</span></span>  
  
|<span data-ttu-id="0d782-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="0d782-119">Element</span></span>|<span data-ttu-id="0d782-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="0d782-120">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="0d782-121">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="0d782-121">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0d782-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0d782-122">See also</span></span>

- <xref:System.ServiceModel.Configuration.ByteStreamMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>
- [<span data-ttu-id="0d782-123">Codificación de mensajes</span><span class="sxs-lookup"><span data-stu-id="0d782-123">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="0d782-124">Elección de un codificador de mensajes</span><span class="sxs-lookup"><span data-stu-id="0d782-124">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="0d782-125">Enlaces</span><span class="sxs-lookup"><span data-stu-id="0d782-125">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="0d782-126">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="0d782-126">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="0d782-127">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="0d782-127">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
