---
title: <textMessageEncoding>
ms.date: 03/30/2017
ms.assetid: e6d834d0-356e-45eb-b530-bbefbb9ec3f0
ms.openlocfilehash: e9942ce3ccbec949160ee70dd103d3c1799bd44d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59186308"
---
# <a name="textmessageencoding"></a><span data-ttu-id="28f40-101">\<textMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="28f40-101">\<textMessageEncoding></span></span>
<span data-ttu-id="28f40-102">Especifica la codificación de caracteres y la versión del mensaje utilizadas para los mensajes XML basados en texto.</span><span class="sxs-lookup"><span data-stu-id="28f40-102">Specifies the character encoding and message versioning used for text-based XML messages.</span></span>  
  
 <span data-ttu-id="28f40-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="28f40-103">\<system.serviceModel></span></span>  
<span data-ttu-id="28f40-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="28f40-104">\<bindings></span></span>  
<span data-ttu-id="28f40-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="28f40-105">\<customBinding></span></span>  
<span data-ttu-id="28f40-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="28f40-106">\<binding></span></span>  
<span data-ttu-id="28f40-107">\<textMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="28f40-107">\<textMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28f40-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="28f40-108">Syntax</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="Integer"
                     maxWritePoolSize="Integer"
                     messageVersion="Soap11Addressing10/Soap12Addressing10"
                     writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="28f40-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="28f40-109">Attributes and Elements</span></span>  
 <span data-ttu-id="28f40-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="28f40-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="28f40-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="28f40-111">Attributes</span></span>  
  
|<span data-ttu-id="28f40-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="28f40-112">Attribute</span></span>|<span data-ttu-id="28f40-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="28f40-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="28f40-114">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="28f40-114">maxReadPoolSize</span></span>|<span data-ttu-id="28f40-115">Un entero que especifica cuántos mensajes pueden leerse simultáneamente sin asignar nuevos lectores.</span><span class="sxs-lookup"><span data-stu-id="28f40-115">An integer that specifies how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="28f40-116">Los tamaños de grupo más grandes hacen que el sistema sea más tolerante a picos de actividad a costa de un espacio de trabajo mayor.</span><span class="sxs-lookup"><span data-stu-id="28f40-116">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="28f40-117">El valor predeterminado es 64.</span><span class="sxs-lookup"><span data-stu-id="28f40-117">The default is 64.</span></span>|  
|<span data-ttu-id="28f40-118">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="28f40-118">maxWritePoolSize</span></span>|<span data-ttu-id="28f40-119">Un entero que especifica cuántos mensajes pueden enviarse simultáneamente sin asignar nuevos escritores.</span><span class="sxs-lookup"><span data-stu-id="28f40-119">An integer that specifies how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="28f40-120">Los tamaños de grupo más grandes hacen que el sistema sea más tolerante a picos de actividad a costa de un espacio de trabajo mayor.</span><span class="sxs-lookup"><span data-stu-id="28f40-120">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="28f40-121">El valor predeterminado es 16.</span><span class="sxs-lookup"><span data-stu-id="28f40-121">The default is 16.</span></span>|  
|<span data-ttu-id="28f40-122">messageVersion</span><span class="sxs-lookup"><span data-stu-id="28f40-122">messageVersion</span></span>|<span data-ttu-id="28f40-123">Especifica la versión SOAP de los mensajes enviados utilizando el enlace.</span><span class="sxs-lookup"><span data-stu-id="28f40-123">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="28f40-124">Los valores válidos son</span><span class="sxs-lookup"><span data-stu-id="28f40-124">Valid values are</span></span><br /><br /> <span data-ttu-id="28f40-125">-   Soap11Addressing10</span><span class="sxs-lookup"><span data-stu-id="28f40-125">-   Soap11Addressing10</span></span><br /><span data-ttu-id="28f40-126">-Soap12Addressing10</span><span class="sxs-lookup"><span data-stu-id="28f40-126">-   Soap12Addressing10</span></span><br /><br /> <span data-ttu-id="28f40-127">El valor predeterminado es Soap12Addressing10.</span><span class="sxs-lookup"><span data-stu-id="28f40-127">The default is Soap12Addressing10.</span></span> <span data-ttu-id="28f40-128">Este atributo es del tipo <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="28f40-128">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
|<span data-ttu-id="28f40-129">writeEncoding</span><span class="sxs-lookup"><span data-stu-id="28f40-129">writeEncoding</span></span>|<span data-ttu-id="28f40-130">Especifica el codificador del juego de caracteres que se va a usar para emitir los mensajes en el enlace.</span><span class="sxs-lookup"><span data-stu-id="28f40-130">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="28f40-131">Los valores válidos son</span><span class="sxs-lookup"><span data-stu-id="28f40-131">Valid values are</span></span><br /><br /> <span data-ttu-id="28f40-132">-   UnicodeFffeTextEncoding: Codificación Unicode BigEndian</span><span class="sxs-lookup"><span data-stu-id="28f40-132">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding</span></span><br /><span data-ttu-id="28f40-133">-Utf16TextEncoding: Codificación Unicode</span><span class="sxs-lookup"><span data-stu-id="28f40-133">-   Utf16TextEncoding: Unicode encoding</span></span><br /><span data-ttu-id="28f40-134">-Utf8TextEncoding: codificación de 8 bits</span><span class="sxs-lookup"><span data-stu-id="28f40-134">-   Utf8TextEncoding: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="28f40-135">El valor predeterminado es Utf8TextEncoding.</span><span class="sxs-lookup"><span data-stu-id="28f40-135">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="28f40-136">Este atributo es del tipo <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="28f40-136">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="28f40-137">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="28f40-137">Child Elements</span></span>  
  
|<span data-ttu-id="28f40-138">Elemento</span><span class="sxs-lookup"><span data-stu-id="28f40-138">Element</span></span>|<span data-ttu-id="28f40-139">Descripción</span><span class="sxs-lookup"><span data-stu-id="28f40-139">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="28f40-140">\<readerQuotas></span><span class="sxs-lookup"><span data-stu-id="28f40-140">\<readerQuotas></span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="28f40-141">Define las restricciones en la complejidad de los mensajes SOAP que pueden ser procesados por los puntos de conexión configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="28f40-141">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="28f40-142">Este elemento es del tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="28f40-142">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="28f40-143">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="28f40-143">Parent Elements</span></span>  
  
|<span data-ttu-id="28f40-144">Elemento</span><span class="sxs-lookup"><span data-stu-id="28f40-144">Element</span></span>|<span data-ttu-id="28f40-145">Descripción</span><span class="sxs-lookup"><span data-stu-id="28f40-145">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="28f40-146">\<binding></span><span class="sxs-lookup"><span data-stu-id="28f40-146">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="28f40-147">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="28f40-147">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="28f40-148">Comentarios</span><span class="sxs-lookup"><span data-stu-id="28f40-148">Remarks</span></span>  
 <span data-ttu-id="28f40-149">La codificación es el proceso de transformación de un mensaje en una secuencia de bytes.</span><span class="sxs-lookup"><span data-stu-id="28f40-149">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="28f40-150">La descodificación es el proceso inverso.</span><span class="sxs-lookup"><span data-stu-id="28f40-150">Decoding is the reverse process.</span></span> <span data-ttu-id="28f40-151">Windows Communication Foundation (WCF) incluye tres tipos de codificación para los mensajes SOAP: Texto, binario y mecanismo de optimización de transmisión de mensajes (MTOM).</span><span class="sxs-lookup"><span data-stu-id="28f40-151">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="28f40-152">La codificación de texto representada por el elemento `textMessageEncoding` es el codificador más interoperable, pero el menos eficaz para los mensajes XML.</span><span class="sxs-lookup"><span data-stu-id="28f40-152">The text encoding represented by the `textMessageEncoding` element is the most interoperable, but the least efficient encoder for XML messages.</span></span>  <span data-ttu-id="28f40-153">El codificador de texto crea mensajes basados en texto en la conexión.</span><span class="sxs-lookup"><span data-stu-id="28f40-153">The text encoder creates text-based messages on the wire.</span></span> <span data-ttu-id="28f40-154">Los mensajes generados por este codificador son adecuados para la interoperabilidad basada en WS - \*.</span><span class="sxs-lookup"><span data-stu-id="28f40-154">Messages produced by this encoder are suitable for WS-\* based interop.</span></span> <span data-ttu-id="28f40-155">Un servicio web o un cliente de servicios web, por lo general, pueden entender XML textual.</span><span class="sxs-lookup"><span data-stu-id="28f40-155">Web service or Web service client can generally understand textual XML.</span></span> <span data-ttu-id="28f40-156">Sin embargo, transmitir bloques grandes de datos binarios como texto es el método menos eficaz para codificar mensajes XML.</span><span class="sxs-lookup"><span data-stu-id="28f40-156">However, transmitting large blocks of binary data as text is the least efficient method for encoding XML messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="28f40-157">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="28f40-157">Example</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="211"
                     maxWritePoolSize="2132"
                     messageVersion="Soap12Addressing10"
                     textEncoding="utf-8" />
```  
  
## <a name="see-also"></a><span data-ttu-id="28f40-158">Vea también</span><span class="sxs-lookup"><span data-stu-id="28f40-158">See also</span></span>

- <xref:System.ServiceModel.Configuration.TextMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>
- [<span data-ttu-id="28f40-159">Elección de un codificador de mensajes</span><span class="sxs-lookup"><span data-stu-id="28f40-159">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="28f40-160">Codificación de mensajes</span><span class="sxs-lookup"><span data-stu-id="28f40-160">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)
- [<span data-ttu-id="28f40-161">Enlaces</span><span class="sxs-lookup"><span data-stu-id="28f40-161">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="28f40-162">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="28f40-162">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="28f40-163">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="28f40-163">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="28f40-164">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="28f40-164">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
