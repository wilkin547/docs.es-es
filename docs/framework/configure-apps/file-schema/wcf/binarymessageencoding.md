---
title: <binaryMessageEncoding>
ms.date: 03/30/2017
ms.assetid: e4ae3cd4-6b67-4ce1-af4b-9400e0a38dba
ms.openlocfilehash: e02ed6ef79fcf52bbe9c33bd9b36a14113e19d1d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59228385"
---
# <a name="binarymessageencoding"></a><span data-ttu-id="95973-101">\<binaryMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="95973-101">\<binaryMessageEncoding></span></span>
<span data-ttu-id="95973-102">Define un codificador del mensaje binario que codifica los mensajes de la Windows Communication Foundation (WCF) en binario en la conexión.</span><span class="sxs-lookup"><span data-stu-id="95973-102">Defines a binary message encoder that encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span>  
  
 <span data-ttu-id="95973-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="95973-103">\<system.serviceModel></span></span>  
<span data-ttu-id="95973-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="95973-104">\<bindings></span></span>  
<span data-ttu-id="95973-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="95973-105">\<customBinding></span></span>  
<span data-ttu-id="95973-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="95973-106">\<binding></span></span>  
<span data-ttu-id="95973-107">\<binaryMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="95973-107">\<binaryMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95973-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="95973-108">Syntax</span></span>  
  
```xml  
<binaryMessageEncoding maxReadPoolSize="Integer"
                       maxSessionSize="Integer"
                       maxWritePoolSize="Integer"
                       messageVersion="Soap11Addressing10/Soap12Addressing10" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="95973-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="95973-109">Attributes and Elements</span></span>  
 <span data-ttu-id="95973-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="95973-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="95973-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="95973-111">Attributes</span></span>  
  
|<span data-ttu-id="95973-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="95973-112">Attribute</span></span>|<span data-ttu-id="95973-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="95973-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="95973-114">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="95973-114">maxReadPoolSize</span></span>|<span data-ttu-id="95973-115">Entero que define cuántos mensajes pueden leerse simultáneamente sin asignar nuevos lectores.</span><span class="sxs-lookup"><span data-stu-id="95973-115">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="95973-116">Los tamaños de grupo más grandes hacen que el sistema sea más tolerante a picos de actividad a costa de un espacio de trabajo mayor.</span><span class="sxs-lookup"><span data-stu-id="95973-116">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="95973-117">El valor predeterminado es 64.</span><span class="sxs-lookup"><span data-stu-id="95973-117">The default is 64.</span></span>|  
|<span data-ttu-id="95973-118">maxSessionSize</span><span class="sxs-lookup"><span data-stu-id="95973-118">maxSessionSize</span></span>|<span data-ttu-id="95973-119">Un entero positivo que establece el tamaño, en bytes, del búfer utilizado para codificar.</span><span class="sxs-lookup"><span data-stu-id="95973-119">A positive integer that sets the size, in bytes, of the buffer used for encoding.</span></span> <span data-ttu-id="95973-120">Un búfer mayor aumenta la velocidad de codificación a costa del tamaño del espacio de trabajo.</span><span class="sxs-lookup"><span data-stu-id="95973-120">A larger buffer increases encoding speed at the expense of the size of the working set.</span></span> <span data-ttu-id="95973-121">El valor predeterminado es 2048.</span><span class="sxs-lookup"><span data-stu-id="95973-121">The default is 2048.</span></span>|  
|<span data-ttu-id="95973-122">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="95973-122">maxWritePoolSize</span></span>|<span data-ttu-id="95973-123">Entero que define cuántos mensajes pueden enviarse simultáneamente sin asignar nuevos escritores.</span><span class="sxs-lookup"><span data-stu-id="95973-123">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="95973-124">Los tamaños de grupo más grandes hacen que el sistema sea más tolerante a picos de actividad a costa de un espacio de trabajo mayor.</span><span class="sxs-lookup"><span data-stu-id="95973-124">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="95973-125">El valor predeterminado es 16.</span><span class="sxs-lookup"><span data-stu-id="95973-125">The default is 16.</span></span>|  
|<span data-ttu-id="95973-126">messageVersion</span><span class="sxs-lookup"><span data-stu-id="95973-126">messageVersion</span></span>|<span data-ttu-id="95973-127">Especifica las versiones del mensaje SOAP y de WS-Addressing que se usan o se esperan.</span><span class="sxs-lookup"><span data-stu-id="95973-127">Specifies the SOAP message and WS-Addressing versions that are used or expected.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="95973-128">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="95973-128">Child Elements</span></span>  
  
|<span data-ttu-id="95973-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="95973-129">Element</span></span>|<span data-ttu-id="95973-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="95973-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="95973-131">\<readerQuotas></span><span class="sxs-lookup"><span data-stu-id="95973-131">\<readerQuotas></span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="95973-132">Define las restricciones en la complejidad de los mensajes SOAP que pueden ser procesados por los puntos de conexión configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="95973-132">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="95973-133">Este elemento es del tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="95973-133">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="95973-134">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="95973-134">Parent Elements</span></span>  
  
|<span data-ttu-id="95973-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="95973-135">Element</span></span>|<span data-ttu-id="95973-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="95973-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="95973-137">\<binding></span><span class="sxs-lookup"><span data-stu-id="95973-137">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="95973-138">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="95973-138">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="95973-139">Comentarios</span><span class="sxs-lookup"><span data-stu-id="95973-139">Remarks</span></span>  
 <span data-ttu-id="95973-140">La codificación es el proceso de transformación de un mensaje en una secuencia de bytes.</span><span class="sxs-lookup"><span data-stu-id="95973-140">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="95973-141">La descodificación es el proceso inverso.</span><span class="sxs-lookup"><span data-stu-id="95973-141">Decoding is the reverse process.</span></span> <span data-ttu-id="95973-142">Windows Communication Foundation (WCF) incluye tres tipos de codificación para los mensajes SOAP: Texto, binario y mecanismo de optimización de transmisión de mensajes (MTOM).</span><span class="sxs-lookup"><span data-stu-id="95973-142">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="95973-143">El elemento `binaryMessageEncoding` especifica el formato binario de .NET para XML y tiene las opciones para especificar la codificación de caracteres, así como la versión de SOAP y WS-Addressing que se va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="95973-143">The `binaryMessageEncoding` element specifies the .NET Binary Format for XML and has options to specify the character encoding and the SOAP and WS-Addressing version to be used.</span></span> <span data-ttu-id="95973-144">El codificador del mensaje binario codifica los mensajes de Windows Communication Foundation (WCF) en binario en la conexión.</span><span class="sxs-lookup"><span data-stu-id="95973-144">The binary message encoder encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span> <span data-ttu-id="95973-145">Aunque esta codificación realiza transmisiones muy rápidas de mensajes, la interoperabilidad basada en estándares WS-\* se pierde.</span><span class="sxs-lookup"><span data-stu-id="95973-145">While this encoding results in very fast transmission of messages, interoperability based on the WS-\* standards is lost.</span></span>  
  
## <a name="example"></a><span data-ttu-id="95973-146">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="95973-146">Example</span></span>  
  
```xml  
<binaryMessageEncoding maxReadPoolSize="211"
                       maxWritePoolSize="2132"
                       maxSessionSize="3141" />
```  
  
## <a name="see-also"></a><span data-ttu-id="95973-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="95973-147">See also</span></span>

- <xref:System.ServiceModel.Configuration.BinaryMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>
- [<span data-ttu-id="95973-148">Codificación de mensajes</span><span class="sxs-lookup"><span data-stu-id="95973-148">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)
- [<span data-ttu-id="95973-149">Elección de un codificador de mensajes</span><span class="sxs-lookup"><span data-stu-id="95973-149">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="95973-150">Enlaces</span><span class="sxs-lookup"><span data-stu-id="95973-150">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="95973-151">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="95973-151">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="95973-152">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="95973-152">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="95973-153">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="95973-153">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
