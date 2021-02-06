---
description: 'Más información acerca de: <binaryMessageEncoding>'
title: <binaryMessageEncoding>
ms.date: 03/30/2017
ms.assetid: e4ae3cd4-6b67-4ce1-af4b-9400e0a38dba
ms.openlocfilehash: 910b8b70bab40c1eb099ed2b54c0545e73e96c6f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99639502"
---
# \<binaryMessageEncoding>

<span data-ttu-id="4bde0-102">Define un codificador del mensaje binario que codifica los mensajes de la Windows Communication Foundation (WCF) en binario en la conexión.</span><span class="sxs-lookup"><span data-stu-id="4bde0-102">Defines a binary message encoder that encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binaryMessageEncoding>**  
  
## <a name="syntax"></a><span data-ttu-id="4bde0-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4bde0-103">Syntax</span></span>  
  
```xml  
<binaryMessageEncoding maxReadPoolSize="Integer"
                       maxSessionSize="Integer"
                       maxWritePoolSize="Integer"
                       messageVersion="Soap11Addressing10/Soap12Addressing10" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4bde0-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4bde0-104">Attributes and Elements</span></span>  

 <span data-ttu-id="4bde0-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="4bde0-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4bde0-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="4bde0-106">Attributes</span></span>  
  
|<span data-ttu-id="4bde0-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="4bde0-107">Attribute</span></span>|<span data-ttu-id="4bde0-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="4bde0-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4bde0-109">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="4bde0-109">maxReadPoolSize</span></span>|<span data-ttu-id="4bde0-110">Entero que define cuántos mensajes pueden leerse simultáneamente sin asignar nuevos lectores.</span><span class="sxs-lookup"><span data-stu-id="4bde0-110">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="4bde0-111">Los tamaños de grupo más grandes hacen que el sistema sea más tolerante a picos de actividad a costa de un espacio de trabajo mayor.</span><span class="sxs-lookup"><span data-stu-id="4bde0-111">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="4bde0-112">El valor predeterminado es 64.</span><span class="sxs-lookup"><span data-stu-id="4bde0-112">The default is 64.</span></span>|  
|<span data-ttu-id="4bde0-113">maxSessionSize</span><span class="sxs-lookup"><span data-stu-id="4bde0-113">maxSessionSize</span></span>|<span data-ttu-id="4bde0-114">Un entero positivo que establece el tamaño, en bytes, del búfer utilizado para codificar.</span><span class="sxs-lookup"><span data-stu-id="4bde0-114">A positive integer that sets the size, in bytes, of the buffer used for encoding.</span></span> <span data-ttu-id="4bde0-115">Un búfer mayor aumenta la velocidad de codificación a costa del tamaño del espacio de trabajo.</span><span class="sxs-lookup"><span data-stu-id="4bde0-115">A larger buffer increases encoding speed at the expense of the size of the working set.</span></span> <span data-ttu-id="4bde0-116">El valor predeterminado es 2048.</span><span class="sxs-lookup"><span data-stu-id="4bde0-116">The default is 2048.</span></span>|  
|<span data-ttu-id="4bde0-117">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="4bde0-117">maxWritePoolSize</span></span>|<span data-ttu-id="4bde0-118">Entero que define cuántos mensajes pueden enviarse simultáneamente sin asignar nuevos escritores.</span><span class="sxs-lookup"><span data-stu-id="4bde0-118">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="4bde0-119">Los tamaños de grupo más grandes hacen que el sistema sea más tolerante a picos de actividad a costa de un espacio de trabajo mayor.</span><span class="sxs-lookup"><span data-stu-id="4bde0-119">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="4bde0-120">El valor predeterminado es 16.</span><span class="sxs-lookup"><span data-stu-id="4bde0-120">The default is 16.</span></span>|  
|<span data-ttu-id="4bde0-121">messageVersion</span><span class="sxs-lookup"><span data-stu-id="4bde0-121">messageVersion</span></span>|<span data-ttu-id="4bde0-122">Especifica las versiones del mensaje SOAP y de WS-Addressing que se usan o se esperan.</span><span class="sxs-lookup"><span data-stu-id="4bde0-122">Specifies the SOAP message and WS-Addressing versions that are used or expected.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4bde0-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4bde0-123">Child Elements</span></span>  
  
|<span data-ttu-id="4bde0-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="4bde0-124">Element</span></span>|<span data-ttu-id="4bde0-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="4bde0-125">Description</span></span>|  
|-------------|-----------------|  
|[\<readerQuotas>](/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="4bde0-126">Define las restricciones en la complejidad de los mensajes SOAP que pueden ser procesados por los puntos de conexión configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="4bde0-126">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="4bde0-127">Este elemento es del tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="4bde0-127">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4bde0-128">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4bde0-128">Parent Elements</span></span>  
  
|<span data-ttu-id="4bde0-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="4bde0-129">Element</span></span>|<span data-ttu-id="4bde0-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="4bde0-130">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="4bde0-131">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="4bde0-131">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4bde0-132">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4bde0-132">Remarks</span></span>  

 <span data-ttu-id="4bde0-133">La codificación es el proceso de transformación de un mensaje en una secuencia de bytes.</span><span class="sxs-lookup"><span data-stu-id="4bde0-133">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="4bde0-134">La descodificación es el proceso inverso.</span><span class="sxs-lookup"><span data-stu-id="4bde0-134">Decoding is the reverse process.</span></span> <span data-ttu-id="4bde0-135">Windows Communication Foundation (WCF) incluye tres tipos de codificación para los mensajes SOAP: Texto, Binario y Mecanismo de optimización de transmisión del mensaje (MTOM).</span><span class="sxs-lookup"><span data-stu-id="4bde0-135">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="4bde0-136">El elemento `binaryMessageEncoding` especifica el formato binario de .NET para XML y tiene las opciones para especificar la codificación de caracteres, así como la versión de SOAP y WS-Addressing que se va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="4bde0-136">The `binaryMessageEncoding` element specifies the .NET Binary Format for XML and has options to specify the character encoding and the SOAP and WS-Addressing version to be used.</span></span> <span data-ttu-id="4bde0-137">El codificador del mensaje binario codifica los mensajes de Windows Communication Foundation (WCF) en binario en la conexión.</span><span class="sxs-lookup"><span data-stu-id="4bde0-137">The binary message encoder encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span> <span data-ttu-id="4bde0-138">Aunque esta codificación realiza transmisiones muy rápidas de mensajes, la interoperabilidad basada en estándares WS-\* se pierde.</span><span class="sxs-lookup"><span data-stu-id="4bde0-138">While this encoding results in very fast transmission of messages, interoperability based on the WS-\* standards is lost.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4bde0-139">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4bde0-139">Example</span></span>  
  
```xml  
<binaryMessageEncoding maxReadPoolSize="211"
                       maxWritePoolSize="2132"
                       maxSessionSize="3141" />
```  
  
## <a name="see-also"></a><span data-ttu-id="4bde0-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="4bde0-140">See also</span></span>

- <xref:System.ServiceModel.Configuration.BinaryMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>
- [<span data-ttu-id="4bde0-141">Codificación de mensajes</span><span class="sxs-lookup"><span data-stu-id="4bde0-141">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="4bde0-142">Elección de un codificador de mensajes</span><span class="sxs-lookup"><span data-stu-id="4bde0-142">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="4bde0-143">Enlaces</span><span class="sxs-lookup"><span data-stu-id="4bde0-143">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="4bde0-144">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="4bde0-144">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="4bde0-145">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="4bde0-145">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
