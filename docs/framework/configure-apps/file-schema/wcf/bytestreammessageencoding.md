---
title: <byteStreamMessageEncoding>
ms.date: 03/30/2017
ms.assetid: bbadd8dd-60a2-4007-b959-89373a8a7d60
ms.openlocfilehash: ceb40558cd979a54f72c2e9aa88f3af47bee9b68
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183902"
---
# \<byteStreamMessageEncoding>

<span data-ttu-id="0d7c5-101">Especifica la codificación de mensajes como un flujo de bytes, con la opción especificar la codificación de caracteres.</span><span class="sxs-lookup"><span data-stu-id="0d7c5-101">Specifies the message encoding as a stream of bytes, with the option to specify the character encoding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<byteStreamMessageEncoding>**  
  
## <a name="syntax"></a><span data-ttu-id="0d7c5-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0d7c5-102">Syntax</span></span>  
  
```xml  
<byteStreamMessageEncoding />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0d7c5-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="0d7c5-103">Attributes and Elements</span></span>  

 <span data-ttu-id="0d7c5-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="0d7c5-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0d7c5-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="0d7c5-105">Attributes</span></span>  
  
|<span data-ttu-id="0d7c5-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="0d7c5-106">Attribute</span></span>|<span data-ttu-id="0d7c5-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="0d7c5-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0d7c5-108">messageVersion</span><span class="sxs-lookup"><span data-stu-id="0d7c5-108">messageVersion</span></span>|<span data-ttu-id="0d7c5-109">Especifica la versión SOAP de los mensajes enviados utilizando el enlace.</span><span class="sxs-lookup"><span data-stu-id="0d7c5-109">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="0d7c5-110">Esta propiedad solo se puede establecer en el valor de la versión del mensaje de <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span><span class="sxs-lookup"><span data-stu-id="0d7c5-110">This property can only be set to the message version value of <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span> <span data-ttu-id="0d7c5-111">El codificador de mensajes de flujo de bytes no admite ninguna otra versión del mensaje.</span><span class="sxs-lookup"><span data-stu-id="0d7c5-111">The byte stream message encoder does not support any other message versions.</span></span><br /><br /> <span data-ttu-id="0d7c5-112">Este atributo es del tipo <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="0d7c5-112">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0d7c5-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0d7c5-113">Child Elements</span></span>  
  
|<span data-ttu-id="0d7c5-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="0d7c5-114">Element</span></span>|<span data-ttu-id="0d7c5-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="0d7c5-115">Description</span></span>|  
|-------------|-----------------|  
|[\<readerQuotas>](/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="0d7c5-116">Define las restricciones en la complejidad de los mensajes SOAP que pueden ser procesados por los puntos de conexión configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="0d7c5-116">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="0d7c5-117">Este elemento es del tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="0d7c5-117">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0d7c5-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0d7c5-118">Parent Elements</span></span>  
  
|<span data-ttu-id="0d7c5-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="0d7c5-119">Element</span></span>|<span data-ttu-id="0d7c5-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="0d7c5-120">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="0d7c5-121">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="0d7c5-121">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0d7c5-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0d7c5-122">See also</span></span>

- <xref:System.ServiceModel.Configuration.ByteStreamMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>
- [<span data-ttu-id="0d7c5-123">Codificación de mensajes</span><span class="sxs-lookup"><span data-stu-id="0d7c5-123">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="0d7c5-124">Elección de un codificador de mensajes</span><span class="sxs-lookup"><span data-stu-id="0d7c5-124">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="0d7c5-125">Enlaces</span><span class="sxs-lookup"><span data-stu-id="0d7c5-125">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="0d7c5-126">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="0d7c5-126">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="0d7c5-127">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="0d7c5-127">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
