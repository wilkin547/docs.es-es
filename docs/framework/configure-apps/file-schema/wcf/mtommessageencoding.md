---
title: <mtomMessageEncoding>
ms.date: 03/30/2017
ms.assetid: 7865d171-cd1e-430a-8421-39cc13541d1b
ms.openlocfilehash: 61b23957c56bad81598dd65b0dd68f7b44d329e5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59146801"
---
# <a name="mtommessageencoding"></a><span data-ttu-id="cc018-101">\<mtomMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="cc018-101">\<mtomMessageEncoding></span></span>
<span data-ttu-id="cc018-102">Especifica la codificación y la versión del mensaje utilizada para los mensajes basados en el mecanismo de optimización de la transmisión de mensajes (MTOM) SOAP.</span><span class="sxs-lookup"><span data-stu-id="cc018-102">Specifies the encoding and message versioning used for SOAP Message Transmission Optimization Mechanism (MTOM) based messages.</span></span>  
  
 <span data-ttu-id="cc018-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="cc018-103">\<system.serviceModel></span></span>  
<span data-ttu-id="cc018-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="cc018-104">\<bindings></span></span>  
<span data-ttu-id="cc018-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="cc018-105">\<customBinding></span></span>  
<span data-ttu-id="cc018-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="cc018-106">\<binding></span></span>  
<span data-ttu-id="cc018-107">\<mtomMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="cc018-107">\<mtomMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc018-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cc018-108">Syntax</span></span>  
  
```xml  
<mtomMessageEncoding maxBufferSize="Integer"
                     maxReadPoolSize="Integer"
                     maxWritePoolSize="Integer"
                     messageVersion="Soap11Addressing1/Soap12Addressing10"
                     writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cc018-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="cc018-109">Attributes and Elements</span></span>  
 <span data-ttu-id="cc018-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="cc018-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cc018-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="cc018-111">Attributes</span></span>  
  
|<span data-ttu-id="cc018-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="cc018-112">Attribute</span></span>|<span data-ttu-id="cc018-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="cc018-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cc018-114">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="cc018-114">maxBufferSize</span></span>|<span data-ttu-id="cc018-115">Un entero que especifica el tamaño máximo del búfer que se puede utilizar.</span><span class="sxs-lookup"><span data-stu-id="cc018-115">An integer that specifies the maximum size of the buffer that can be used.</span></span>|  
|<span data-ttu-id="cc018-116">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="cc018-116">maxReadPoolSize</span></span>|<span data-ttu-id="cc018-117">Un entero que especifica cuántos mensajes pueden leerse simultáneamente sin asignar nuevos lectores.</span><span class="sxs-lookup"><span data-stu-id="cc018-117">An integer that specifies how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="cc018-118">Los tamaños de grupo más grandes hacen que el sistema sea más tolerante a picos de actividad a costa de un espacio de trabajo mayor.</span><span class="sxs-lookup"><span data-stu-id="cc018-118">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="cc018-119">El valor predeterminado es 64.</span><span class="sxs-lookup"><span data-stu-id="cc018-119">The default is 64.</span></span>|  
|<span data-ttu-id="cc018-120">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="cc018-120">maxWritePoolSize</span></span>|<span data-ttu-id="cc018-121">Un entero que especifica cuántos mensajes pueden enviarse simultáneamente sin asignar nuevos escritores.</span><span class="sxs-lookup"><span data-stu-id="cc018-121">An integer that specifies how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="cc018-122">Los tamaños de grupo más grandes hacen que el sistema sea más tolerante a picos de actividad a costa de un espacio de trabajo mayor.</span><span class="sxs-lookup"><span data-stu-id="cc018-122">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="cc018-123">El valor predeterminado es 16.</span><span class="sxs-lookup"><span data-stu-id="cc018-123">The default is 16.</span></span>|  
|<span data-ttu-id="cc018-124">messageVersion</span><span class="sxs-lookup"><span data-stu-id="cc018-124">messageVersion</span></span>|<span data-ttu-id="cc018-125">Especifica la versión SOAP de los mensajes enviados utilizando el enlace.</span><span class="sxs-lookup"><span data-stu-id="cc018-125">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="cc018-126">Los valores válidos son</span><span class="sxs-lookup"><span data-stu-id="cc018-126">Valid values are</span></span><br /><br /> <span data-ttu-id="cc018-127">-Soap11Addressing1</span><span class="sxs-lookup"><span data-stu-id="cc018-127">-   Soap11Addressing1</span></span><br /><span data-ttu-id="cc018-128">-Soap12Addressing10</span><span class="sxs-lookup"><span data-stu-id="cc018-128">-   Soap12Addressing10</span></span><br /><br /> <span data-ttu-id="cc018-129">El valor predeterminado es Soap12Addressing10.</span><span class="sxs-lookup"><span data-stu-id="cc018-129">The default is Soap12Addressing10.</span></span> <span data-ttu-id="cc018-130">Este atributo es del tipo <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="cc018-130">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
|<span data-ttu-id="cc018-131">writeEncoding</span><span class="sxs-lookup"><span data-stu-id="cc018-131">writeEncoding</span></span>|<span data-ttu-id="cc018-132">Especifica el codificador del juego de caracteres que se va a usar para emitir los mensajes en el enlace.</span><span class="sxs-lookup"><span data-stu-id="cc018-132">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="cc018-133">Los valores válidos son</span><span class="sxs-lookup"><span data-stu-id="cc018-133">Valid values are</span></span><br /><br /> <span data-ttu-id="cc018-134">-   UnicodeFffeTextEncoding: Codificación Unicode BigEndian</span><span class="sxs-lookup"><span data-stu-id="cc018-134">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding</span></span><br /><span data-ttu-id="cc018-135">-Utf16TextEncoding: Codificación Unicode</span><span class="sxs-lookup"><span data-stu-id="cc018-135">-   Utf16TextEncoding: Unicode encoding</span></span><br /><span data-ttu-id="cc018-136">-Utf8TextEncoding: codificación de 8 bits</span><span class="sxs-lookup"><span data-stu-id="cc018-136">-   Utf8TextEncoding: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="cc018-137">El valor predeterminado es Utf8TextEncoding.</span><span class="sxs-lookup"><span data-stu-id="cc018-137">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="cc018-138">Este atributo es del tipo <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="cc018-138">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cc018-139">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="cc018-139">Child Elements</span></span>  
  
|<span data-ttu-id="cc018-140">Elemento</span><span class="sxs-lookup"><span data-stu-id="cc018-140">Element</span></span>|<span data-ttu-id="cc018-141">Descripción</span><span class="sxs-lookup"><span data-stu-id="cc018-141">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cc018-142">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="cc018-142">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="cc018-143">Define las restricciones en la complejidad de los mensajes SOAP que pueden ser procesados por los puntos de conexión configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="cc018-143">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="cc018-144">Este elemento es del tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="cc018-144">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cc018-145">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="cc018-145">Parent Elements</span></span>  
  
|<span data-ttu-id="cc018-146">Elemento</span><span class="sxs-lookup"><span data-stu-id="cc018-146">Element</span></span>|<span data-ttu-id="cc018-147">Descripción</span><span class="sxs-lookup"><span data-stu-id="cc018-147">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cc018-148">\<binding></span><span class="sxs-lookup"><span data-stu-id="cc018-148">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="cc018-149">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="cc018-149">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cc018-150">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cc018-150">Remarks</span></span>  
 <span data-ttu-id="cc018-151">La codificación es el proceso de transformación de un mensaje en una secuencia de bytes.</span><span class="sxs-lookup"><span data-stu-id="cc018-151">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="cc018-152">La descodificación es el proceso inverso.</span><span class="sxs-lookup"><span data-stu-id="cc018-152">Decoding is the reverse process.</span></span> <span data-ttu-id="cc018-153">Windows Communication Foundation (WCF) incluye tres tipos de codificación para los mensajes SOAP: Texto, binario y mecanismo de optimización de transmisión de mensajes (MTOM).</span><span class="sxs-lookup"><span data-stu-id="cc018-153">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="cc018-154">El elemento `MtomMessageEncoding` especifica la codificación de caracteres y control de versión de mensajes y otros valores usados para los mensajes que utilizan una codificación MTOM (mecanismo de optimización de transmisión de mensajes).</span><span class="sxs-lookup"><span data-stu-id="cc018-154">The `MtomMessageEncoding` element specifies the character encoding and message versioning and other settings used for messages using a Message Transmission Optimization Mechanism (MTOM) encoding.</span></span> <span data-ttu-id="cc018-155">MTOM es una tecnología eficaz para la transmisión de datos binarios en mensajes de WCF.</span><span class="sxs-lookup"><span data-stu-id="cc018-155">MTOM is an efficient technology for transmitting binary data in WCF messages.</span></span> <span data-ttu-id="cc018-156">El codificador MTOM intenta crear una balanza entre la eficacia y la interoperabilidad.</span><span class="sxs-lookup"><span data-stu-id="cc018-156">The MTOM encoder attempts to create a balance between efficiency and interoperability.</span></span> <span data-ttu-id="cc018-157">El codificador MTOM transmite la mayoría del XML en formato de texto, pero optimiza los bloques grandes de datos binarios transmitiéndolos como son, sin convertirlos a su formato codificado base64.</span><span class="sxs-lookup"><span data-stu-id="cc018-157">The MTOM encoding transmits most XML in textual form, but optimizes large blocks of binary data by transmitting them as-is, without conversion to their base64 encoded format.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cc018-158">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cc018-158">Example</span></span>  
  
```xml  
<mtomMessageEncoding maxReadPoolSize="211"
                     maxWritePoolSize="2132"
                     messageVersion="Soap11Addressing10"
                     textEncoding="utf-8" />
```  
  
## <a name="see-also"></a><span data-ttu-id="cc018-159">Vea también</span><span class="sxs-lookup"><span data-stu-id="cc018-159">See also</span></span>

- <xref:System.ServiceModel.Configuration.MtomMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>
- [<span data-ttu-id="cc018-160">Codificación de mensajes</span><span class="sxs-lookup"><span data-stu-id="cc018-160">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)
- [<span data-ttu-id="cc018-161">Elección de un codificador de mensajes</span><span class="sxs-lookup"><span data-stu-id="cc018-161">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="cc018-162">Enlaces</span><span class="sxs-lookup"><span data-stu-id="cc018-162">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="cc018-163">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="cc018-163">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="cc018-164">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="cc018-164">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="cc018-165">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="cc018-165">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
