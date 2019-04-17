---
title: <textMessageEncoding>
ms.date: 03/30/2017
ms.assetid: e6d834d0-356e-45eb-b530-bbefbb9ec3f0
ms.openlocfilehash: e6e6d1907d89a09a72594a836f2192e9ad9c4290
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2019
ms.locfileid: "59614121"
---
# <a name="textmessageencoding"></a><span data-ttu-id="d4164-101">\<textMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="d4164-101">\<textMessageEncoding></span></span>
<span data-ttu-id="d4164-102">Especifica la codificación de caracteres y la versión del mensaje utilizadas para los mensajes XML basados en texto.</span><span class="sxs-lookup"><span data-stu-id="d4164-102">Specifies the character encoding and message versioning used for text-based XML messages.</span></span>  
  
 <span data-ttu-id="d4164-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="d4164-103">\<system.serviceModel></span></span>  
<span data-ttu-id="d4164-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="d4164-104">\<bindings></span></span>  
<span data-ttu-id="d4164-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="d4164-105">\<customBinding></span></span>  
<span data-ttu-id="d4164-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="d4164-106">\<binding></span></span>  
<span data-ttu-id="d4164-107">\<textMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="d4164-107">\<textMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4164-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d4164-108">Syntax</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="Integer"
                     maxWritePoolSize="Integer"
                     messageVersion="Soap11Addressing10/Soap12Addressing10"
                     writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d4164-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d4164-109">Attributes and Elements</span></span>  
 <span data-ttu-id="d4164-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d4164-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d4164-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="d4164-111">Attributes</span></span>  
  
|<span data-ttu-id="d4164-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="d4164-112">Attribute</span></span>|<span data-ttu-id="d4164-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="d4164-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d4164-114">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="d4164-114">maxReadPoolSize</span></span>|<span data-ttu-id="d4164-115">Un entero que especifica cuántos mensajes pueden leerse simultáneamente sin asignar nuevos lectores.</span><span class="sxs-lookup"><span data-stu-id="d4164-115">An integer that specifies how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="d4164-116">Los tamaños de grupo más grandes hacen que el sistema sea más tolerante a picos de actividad a costa de un espacio de trabajo mayor.</span><span class="sxs-lookup"><span data-stu-id="d4164-116">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="d4164-117">El valor predeterminado es 64.</span><span class="sxs-lookup"><span data-stu-id="d4164-117">The default is 64.</span></span>|  
|<span data-ttu-id="d4164-118">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="d4164-118">maxWritePoolSize</span></span>|<span data-ttu-id="d4164-119">Un entero que especifica cuántos mensajes pueden enviarse simultáneamente sin asignar nuevos escritores.</span><span class="sxs-lookup"><span data-stu-id="d4164-119">An integer that specifies how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="d4164-120">Los tamaños de grupo más grandes hacen que el sistema sea más tolerante a picos de actividad a costa de un espacio de trabajo mayor.</span><span class="sxs-lookup"><span data-stu-id="d4164-120">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="d4164-121">El valor predeterminado es 16.</span><span class="sxs-lookup"><span data-stu-id="d4164-121">The default is 16.</span></span>|  
|<span data-ttu-id="d4164-122">messageVersion</span><span class="sxs-lookup"><span data-stu-id="d4164-122">messageVersion</span></span>|<span data-ttu-id="d4164-123">Especifica la versión SOAP de los mensajes enviados utilizando el enlace.</span><span class="sxs-lookup"><span data-stu-id="d4164-123">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="d4164-124">Los valores válidos son</span><span class="sxs-lookup"><span data-stu-id="d4164-124">Valid values are</span></span><br /><br /> <span data-ttu-id="d4164-125">-   Soap11Addressing10</span><span class="sxs-lookup"><span data-stu-id="d4164-125">-   Soap11Addressing10</span></span><br /><span data-ttu-id="d4164-126">-Soap12Addressing10</span><span class="sxs-lookup"><span data-stu-id="d4164-126">-   Soap12Addressing10</span></span><br /><span data-ttu-id="d4164-127">-Soap11</span><span class="sxs-lookup"><span data-stu-id="d4164-127">-   Soap11</span></span><br /><span data-ttu-id="d4164-128">-Soap12</span><span class="sxs-lookup"><span data-stu-id="d4164-128">-  Soap12</span></span><br /><br /><span data-ttu-id="d4164-129">El valor predeterminado es Soap12Addressing10.</span><span class="sxs-lookup"><span data-stu-id="d4164-129">The default is Soap12Addressing10.</span></span> <span data-ttu-id="d4164-130">Este atributo es del tipo <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="d4164-130">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
|<span data-ttu-id="d4164-131">writeEncoding</span><span class="sxs-lookup"><span data-stu-id="d4164-131">writeEncoding</span></span>|<span data-ttu-id="d4164-132">Especifica el codificador del juego de caracteres que se va a usar para emitir los mensajes en el enlace.</span><span class="sxs-lookup"><span data-stu-id="d4164-132">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="d4164-133">Los valores válidos son</span><span class="sxs-lookup"><span data-stu-id="d4164-133">Valid values are</span></span><br /><br /> <span data-ttu-id="d4164-134">-   UnicodeFffeTextEncoding: Codificación Unicode BigEndian</span><span class="sxs-lookup"><span data-stu-id="d4164-134">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding</span></span><br /><span data-ttu-id="d4164-135">-Utf16TextEncoding: Codificación Unicode</span><span class="sxs-lookup"><span data-stu-id="d4164-135">-   Utf16TextEncoding: Unicode encoding</span></span><br /><span data-ttu-id="d4164-136">-Utf8TextEncoding: codificación de 8 bits</span><span class="sxs-lookup"><span data-stu-id="d4164-136">-   Utf8TextEncoding: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="d4164-137">El valor predeterminado es Utf8TextEncoding.</span><span class="sxs-lookup"><span data-stu-id="d4164-137">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="d4164-138">Este atributo es del tipo <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="d4164-138">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d4164-139">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d4164-139">Child Elements</span></span>  
  
|<span data-ttu-id="d4164-140">Elemento</span><span class="sxs-lookup"><span data-stu-id="d4164-140">Element</span></span>|<span data-ttu-id="d4164-141">Descripción</span><span class="sxs-lookup"><span data-stu-id="d4164-141">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d4164-142">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="d4164-142">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="d4164-143">Define las restricciones en la complejidad de los mensajes SOAP que pueden ser procesados por los puntos de conexión configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="d4164-143">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="d4164-144">Este elemento es del tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="d4164-144">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d4164-145">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d4164-145">Parent Elements</span></span>  
  
|<span data-ttu-id="d4164-146">Elemento</span><span class="sxs-lookup"><span data-stu-id="d4164-146">Element</span></span>|<span data-ttu-id="d4164-147">Descripción</span><span class="sxs-lookup"><span data-stu-id="d4164-147">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d4164-148">\<binding></span><span class="sxs-lookup"><span data-stu-id="d4164-148">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="d4164-149">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="d4164-149">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d4164-150">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d4164-150">Remarks</span></span>  
 <span data-ttu-id="d4164-151">La codificación es el proceso de transformación de un mensaje en una secuencia de bytes.</span><span class="sxs-lookup"><span data-stu-id="d4164-151">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="d4164-152">La descodificación es el proceso inverso.</span><span class="sxs-lookup"><span data-stu-id="d4164-152">Decoding is the reverse process.</span></span> <span data-ttu-id="d4164-153">Windows Communication Foundation (WCF) incluye tres tipos de codificación para los mensajes SOAP: Texto, binario y mecanismo de optimización de transmisión de mensajes (MTOM).</span><span class="sxs-lookup"><span data-stu-id="d4164-153">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="d4164-154">La codificación de texto representada por el elemento `textMessageEncoding` es el codificador más interoperable, pero el menos eficaz para los mensajes XML.</span><span class="sxs-lookup"><span data-stu-id="d4164-154">The text encoding represented by the `textMessageEncoding` element is the most interoperable, but the least efficient encoder for XML messages.</span></span>  <span data-ttu-id="d4164-155">El codificador de texto crea mensajes basados en texto en la conexión.</span><span class="sxs-lookup"><span data-stu-id="d4164-155">The text encoder creates text-based messages on the wire.</span></span> <span data-ttu-id="d4164-156">Los mensajes generados por este codificador son adecuados para la interoperabilidad basada en WS - \*.</span><span class="sxs-lookup"><span data-stu-id="d4164-156">Messages produced by this encoder are suitable for WS-\* based interop.</span></span> <span data-ttu-id="d4164-157">Un servicio web o un cliente de servicios web, por lo general, pueden entender XML textual.</span><span class="sxs-lookup"><span data-stu-id="d4164-157">Web service or Web service client can generally understand textual XML.</span></span> <span data-ttu-id="d4164-158">Sin embargo, transmitir bloques grandes de datos binarios como texto es el método menos eficaz para codificar mensajes XML.</span><span class="sxs-lookup"><span data-stu-id="d4164-158">However, transmitting large blocks of binary data as text is the least efficient method for encoding XML messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d4164-159">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d4164-159">Example</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="211"
                     maxWritePoolSize="2132"
                     messageVersion="Soap12Addressing10"
                     textEncoding="utf-8" />
```  
  
## <a name="see-also"></a><span data-ttu-id="d4164-160">Vea también</span><span class="sxs-lookup"><span data-stu-id="d4164-160">See also</span></span>

- <xref:System.ServiceModel.Configuration.TextMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>
- [<span data-ttu-id="d4164-161">Elección de un codificador de mensajes</span><span class="sxs-lookup"><span data-stu-id="d4164-161">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="d4164-162">Codificación de mensajes</span><span class="sxs-lookup"><span data-stu-id="d4164-162">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)
- [<span data-ttu-id="d4164-163">Enlaces</span><span class="sxs-lookup"><span data-stu-id="d4164-163">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="d4164-164">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="d4164-164">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="d4164-165">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="d4164-165">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="d4164-166">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="d4164-166">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
