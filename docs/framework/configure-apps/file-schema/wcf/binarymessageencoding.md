---
title: <binaryMessageEncoding>
ms.date: 03/30/2017
ms.assetid: e4ae3cd4-6b67-4ce1-af4b-9400e0a38dba
ms.openlocfilehash: afe0479d9cbf6d754b309c18e23d3a479870177c
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "73739073"
---
# \<binaryMessageEncoding>
<span data-ttu-id="fcbd2-101">Define un codificador del mensaje binario que codifica los mensajes de la Windows Communication Foundation (WCF) en binario en la conexión.</span><span class="sxs-lookup"><span data-stu-id="fcbd2-101">Defines a binary message encoder that encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binaryMessageEncoding>**  
  
## <a name="syntax"></a><span data-ttu-id="fcbd2-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fcbd2-102">Syntax</span></span>  
  
```xml  
<binaryMessageEncoding maxReadPoolSize="Integer"
                       maxSessionSize="Integer"
                       maxWritePoolSize="Integer"
                       messageVersion="Soap11Addressing10/Soap12Addressing10" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fcbd2-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="fcbd2-103">Attributes and Elements</span></span>  
 <span data-ttu-id="fcbd2-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="fcbd2-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fcbd2-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="fcbd2-105">Attributes</span></span>  
  
|<span data-ttu-id="fcbd2-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="fcbd2-106">Attribute</span></span>|<span data-ttu-id="fcbd2-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="fcbd2-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fcbd2-108">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="fcbd2-108">maxReadPoolSize</span></span>|<span data-ttu-id="fcbd2-109">Entero que define cuántos mensajes pueden leerse simultáneamente sin asignar nuevos lectores.</span><span class="sxs-lookup"><span data-stu-id="fcbd2-109">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="fcbd2-110">Los tamaños de grupo más grandes hacen que el sistema sea más tolerante a picos de actividad a costa de un espacio de trabajo mayor.</span><span class="sxs-lookup"><span data-stu-id="fcbd2-110">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="fcbd2-111">El valor predeterminado es 64.</span><span class="sxs-lookup"><span data-stu-id="fcbd2-111">The default is 64.</span></span>|  
|<span data-ttu-id="fcbd2-112">maxSessionSize</span><span class="sxs-lookup"><span data-stu-id="fcbd2-112">maxSessionSize</span></span>|<span data-ttu-id="fcbd2-113">Un entero positivo que establece el tamaño, en bytes, del búfer utilizado para codificar.</span><span class="sxs-lookup"><span data-stu-id="fcbd2-113">A positive integer that sets the size, in bytes, of the buffer used for encoding.</span></span> <span data-ttu-id="fcbd2-114">Un búfer mayor aumenta la velocidad de codificación a costa del tamaño del espacio de trabajo.</span><span class="sxs-lookup"><span data-stu-id="fcbd2-114">A larger buffer increases encoding speed at the expense of the size of the working set.</span></span> <span data-ttu-id="fcbd2-115">El valor predeterminado es 2048.</span><span class="sxs-lookup"><span data-stu-id="fcbd2-115">The default is 2048.</span></span>|  
|<span data-ttu-id="fcbd2-116">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="fcbd2-116">maxWritePoolSize</span></span>|<span data-ttu-id="fcbd2-117">Entero que define cuántos mensajes pueden enviarse simultáneamente sin asignar nuevos escritores.</span><span class="sxs-lookup"><span data-stu-id="fcbd2-117">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="fcbd2-118">Los tamaños de grupo más grandes hacen que el sistema sea más tolerante a picos de actividad a costa de un espacio de trabajo mayor.</span><span class="sxs-lookup"><span data-stu-id="fcbd2-118">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="fcbd2-119">El valor predeterminado es 16.</span><span class="sxs-lookup"><span data-stu-id="fcbd2-119">The default is 16.</span></span>|  
|<span data-ttu-id="fcbd2-120">messageVersion</span><span class="sxs-lookup"><span data-stu-id="fcbd2-120">messageVersion</span></span>|<span data-ttu-id="fcbd2-121">Especifica las versiones del mensaje SOAP y de WS-Addressing que se usan o se esperan.</span><span class="sxs-lookup"><span data-stu-id="fcbd2-121">Specifies the SOAP message and WS-Addressing versions that are used or expected.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fcbd2-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="fcbd2-122">Child Elements</span></span>  
  
|<span data-ttu-id="fcbd2-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="fcbd2-123">Element</span></span>|<span data-ttu-id="fcbd2-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="fcbd2-124">Description</span></span>|  
|-------------|-----------------|  
|[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="fcbd2-125">Define las restricciones en la complejidad de los mensajes SOAP que pueden ser procesados por los puntos de conexión configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="fcbd2-125">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="fcbd2-126">Este elemento es del tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="fcbd2-126">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fcbd2-127">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="fcbd2-127">Parent Elements</span></span>  
  
|<span data-ttu-id="fcbd2-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="fcbd2-128">Element</span></span>|<span data-ttu-id="fcbd2-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="fcbd2-129">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="fcbd2-130">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="fcbd2-130">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fcbd2-131">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fcbd2-131">Remarks</span></span>  
 <span data-ttu-id="fcbd2-132">La codificación es el proceso de transformación de un mensaje en una secuencia de bytes.</span><span class="sxs-lookup"><span data-stu-id="fcbd2-132">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="fcbd2-133">La descodificación es el proceso inverso.</span><span class="sxs-lookup"><span data-stu-id="fcbd2-133">Decoding is the reverse process.</span></span> <span data-ttu-id="fcbd2-134">Windows Communication Foundation (WCF) incluye tres tipos de codificación para los mensajes SOAP: Texto, Binario y Mecanismo de optimización de transmisión del mensaje (MTOM).</span><span class="sxs-lookup"><span data-stu-id="fcbd2-134">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="fcbd2-135">El elemento `binaryMessageEncoding` especifica el formato binario de .NET para XML y tiene las opciones para especificar la codificación de caracteres, así como la versión de SOAP y WS-Addressing que se va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="fcbd2-135">The `binaryMessageEncoding` element specifies the .NET Binary Format for XML and has options to specify the character encoding and the SOAP and WS-Addressing version to be used.</span></span> <span data-ttu-id="fcbd2-136">El codificador del mensaje binario codifica los mensajes de Windows Communication Foundation (WCF) en binario en la conexión.</span><span class="sxs-lookup"><span data-stu-id="fcbd2-136">The binary message encoder encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span> <span data-ttu-id="fcbd2-137">Aunque esta codificación realiza transmisiones muy rápidas de mensajes, la interoperabilidad basada en estándares WS-\* se pierde.</span><span class="sxs-lookup"><span data-stu-id="fcbd2-137">While this encoding results in very fast transmission of messages, interoperability based on the WS-\* standards is lost.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fcbd2-138">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fcbd2-138">Example</span></span>  
  
```xml  
<binaryMessageEncoding maxReadPoolSize="211"
                       maxWritePoolSize="2132"
                       maxSessionSize="3141" />
```  
  
## <a name="see-also"></a><span data-ttu-id="fcbd2-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fcbd2-139">See also</span></span>

- <xref:System.ServiceModel.Configuration.BinaryMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>
- [<span data-ttu-id="fcbd2-140">Codificación de mensajes</span><span class="sxs-lookup"><span data-stu-id="fcbd2-140">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="fcbd2-141">Elección de un codificador de mensajes</span><span class="sxs-lookup"><span data-stu-id="fcbd2-141">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="fcbd2-142">Enlaces</span><span class="sxs-lookup"><span data-stu-id="fcbd2-142">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="fcbd2-143">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="fcbd2-143">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="fcbd2-144">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="fcbd2-144">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
