---
title: <textMessageEncoding>
ms.date: 03/30/2017
ms.assetid: e6d834d0-356e-45eb-b530-bbefbb9ec3f0
ms.openlocfilehash: 6485bbd751d6467628f2191c3f5f0c6cc8a3db2f
ms.sourcegitcommit: 01ea420eaa4bf76d5fc47673294c8881379b3369
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2019
ms.locfileid: "55758656"
---
# <a name="textmessageencoding"></a><span data-ttu-id="cdc2b-101">\<textMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="cdc2b-101">\<textMessageEncoding></span></span>
<span data-ttu-id="cdc2b-102">Especifica la codificación de caracteres y la versión del mensaje utilizadas para los mensajes XML basados en texto.</span><span class="sxs-lookup"><span data-stu-id="cdc2b-102">Specifies the character encoding and message versioning used for text-based XML messages.</span></span>  
  
 <span data-ttu-id="cdc2b-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="cdc2b-103">\<system.serviceModel></span></span>  
<span data-ttu-id="cdc2b-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="cdc2b-104">\<bindings></span></span>  
<span data-ttu-id="cdc2b-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="cdc2b-105">\<customBinding></span></span>  
<span data-ttu-id="cdc2b-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="cdc2b-106">\<binding></span></span>  
<span data-ttu-id="cdc2b-107">\<textMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="cdc2b-107">\<textMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cdc2b-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cdc2b-108">Syntax</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="Integer"
                     maxWritePoolSize="Integer"
                     messageVersion="Soap11Addressing10/Soap12Addressing10"
                     writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cdc2b-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="cdc2b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="cdc2b-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="cdc2b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cdc2b-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="cdc2b-111">Attributes</span></span>  
  
|<span data-ttu-id="cdc2b-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="cdc2b-112">Attribute</span></span>|<span data-ttu-id="cdc2b-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="cdc2b-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cdc2b-114">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="cdc2b-114">maxReadPoolSize</span></span>|<span data-ttu-id="cdc2b-115">Un entero que especifica cuántos mensajes pueden leerse simultáneamente sin asignar nuevos lectores.</span><span class="sxs-lookup"><span data-stu-id="cdc2b-115">An integer that specifies how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="cdc2b-116">Los tamaños de grupo más grandes hacen que el sistema sea más tolerante a picos de actividad a costa de un espacio de trabajo mayor.</span><span class="sxs-lookup"><span data-stu-id="cdc2b-116">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="cdc2b-117">El valor predeterminado es 64.</span><span class="sxs-lookup"><span data-stu-id="cdc2b-117">The default is 64.</span></span>|  
|<span data-ttu-id="cdc2b-118">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="cdc2b-118">maxWritePoolSize</span></span>|<span data-ttu-id="cdc2b-119">Un entero que especifica cuántos mensajes pueden enviarse simultáneamente sin asignar nuevos escritores.</span><span class="sxs-lookup"><span data-stu-id="cdc2b-119">An integer that specifies how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="cdc2b-120">Los tamaños de grupo más grandes hacen que el sistema sea más tolerante a picos de actividad a costa de un espacio de trabajo mayor.</span><span class="sxs-lookup"><span data-stu-id="cdc2b-120">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="cdc2b-121">El valor predeterminado es 16.</span><span class="sxs-lookup"><span data-stu-id="cdc2b-121">The default is 16.</span></span>|  
|<span data-ttu-id="cdc2b-122">messageVersion</span><span class="sxs-lookup"><span data-stu-id="cdc2b-122">messageVersion</span></span>|<span data-ttu-id="cdc2b-123">Especifica la versión SOAP de los mensajes enviados utilizando el enlace.</span><span class="sxs-lookup"><span data-stu-id="cdc2b-123">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="cdc2b-124">Los valores válidos son</span><span class="sxs-lookup"><span data-stu-id="cdc2b-124">Valid values are</span></span><br /><br /> <span data-ttu-id="cdc2b-125">-   Soap11Addressing10</span><span class="sxs-lookup"><span data-stu-id="cdc2b-125">-   Soap11Addressing10</span></span><br /><span data-ttu-id="cdc2b-126">-Soap12Addressing10</span><span class="sxs-lookup"><span data-stu-id="cdc2b-126">-   Soap12Addressing10</span></span><br /><br /> <span data-ttu-id="cdc2b-127">El valor predeterminado es Soap12Addressing10.</span><span class="sxs-lookup"><span data-stu-id="cdc2b-127">The default is Soap12Addressing10.</span></span> <span data-ttu-id="cdc2b-128">Este atributo es del tipo <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="cdc2b-128">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
|<span data-ttu-id="cdc2b-129">writeEncoding</span><span class="sxs-lookup"><span data-stu-id="cdc2b-129">writeEncoding</span></span>|<span data-ttu-id="cdc2b-130">Especifica el codificador del juego de caracteres que se va a usar para emitir los mensajes en el enlace.</span><span class="sxs-lookup"><span data-stu-id="cdc2b-130">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="cdc2b-131">Los valores válidos son</span><span class="sxs-lookup"><span data-stu-id="cdc2b-131">Valid values are</span></span><br /><br /> <span data-ttu-id="cdc2b-132">-   UnicodeFffeTextEncoding: Codificación Unicode BigEndian</span><span class="sxs-lookup"><span data-stu-id="cdc2b-132">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding</span></span><br /><span data-ttu-id="cdc2b-133">-Utf16TextEncoding: Codificación Unicode</span><span class="sxs-lookup"><span data-stu-id="cdc2b-133">-   Utf16TextEncoding: Unicode encoding</span></span><br /><span data-ttu-id="cdc2b-134">-Utf8TextEncoding: codificación de 8 bits</span><span class="sxs-lookup"><span data-stu-id="cdc2b-134">-   Utf8TextEncoding: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="cdc2b-135">El valor predeterminado es Utf8TextEncoding.</span><span class="sxs-lookup"><span data-stu-id="cdc2b-135">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="cdc2b-136">Este atributo es del tipo <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="cdc2b-136">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cdc2b-137">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="cdc2b-137">Child Elements</span></span>  
  
|<span data-ttu-id="cdc2b-138">Elemento</span><span class="sxs-lookup"><span data-stu-id="cdc2b-138">Element</span></span>|<span data-ttu-id="cdc2b-139">Descripción</span><span class="sxs-lookup"><span data-stu-id="cdc2b-139">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cdc2b-140">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="cdc2b-140">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="cdc2b-141">Define las restricciones en la complejidad de los mensajes SOAP que pueden ser procesados por los puntos de conexión configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="cdc2b-141">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="cdc2b-142">Este elemento es del tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="cdc2b-142">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cdc2b-143">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="cdc2b-143">Parent Elements</span></span>  
  
|<span data-ttu-id="cdc2b-144">Elemento</span><span class="sxs-lookup"><span data-stu-id="cdc2b-144">Element</span></span>|<span data-ttu-id="cdc2b-145">Descripción</span><span class="sxs-lookup"><span data-stu-id="cdc2b-145">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cdc2b-146">\<binding></span><span class="sxs-lookup"><span data-stu-id="cdc2b-146">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="cdc2b-147">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="cdc2b-147">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cdc2b-148">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cdc2b-148">Remarks</span></span>  
 <span data-ttu-id="cdc2b-149">La codificación es el proceso de transformación de un mensaje en una secuencia de bytes.</span><span class="sxs-lookup"><span data-stu-id="cdc2b-149">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="cdc2b-150">La descodificación es el proceso inverso.</span><span class="sxs-lookup"><span data-stu-id="cdc2b-150">Decoding is the reverse process.</span></span> <span data-ttu-id="cdc2b-151">Windows Communication Foundation (WCF) incluye tres tipos de codificación para los mensajes SOAP: Texto, binario y mecanismo de optimización de transmisión de mensajes (MTOM).</span><span class="sxs-lookup"><span data-stu-id="cdc2b-151">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="cdc2b-152">La codificación de texto representada por el elemento `textMessageEncoding` es el codificador más interoperable, pero el menos eficaz para los mensajes XML.</span><span class="sxs-lookup"><span data-stu-id="cdc2b-152">The text encoding represented by the `textMessageEncoding` element is the most interoperable, but the least efficient encoder for XML messages.</span></span>  <span data-ttu-id="cdc2b-153">El codificador de texto crea mensajes basados en texto en la conexión.</span><span class="sxs-lookup"><span data-stu-id="cdc2b-153">The text encoder creates text-based messages on the wire.</span></span> <span data-ttu-id="cdc2b-154">Los mensajes generados por este codificador son adecuados para la interoperabilidad basada en WS - \*.</span><span class="sxs-lookup"><span data-stu-id="cdc2b-154">Messages produced by this encoder are suitable for WS-\* based interop.</span></span> <span data-ttu-id="cdc2b-155">Un servicio web o un cliente de servicios web, por lo general, pueden entender XML textual.</span><span class="sxs-lookup"><span data-stu-id="cdc2b-155">Web service or Web service client can generally understand textual XML.</span></span> <span data-ttu-id="cdc2b-156">Sin embargo, transmitir bloques grandes de datos binarios como texto es el método menos eficaz para codificar mensajes XML.</span><span class="sxs-lookup"><span data-stu-id="cdc2b-156">However, transmitting large blocks of binary data as text is the least efficient method for encoding XML messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cdc2b-157">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cdc2b-157">Example</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="211"
                     maxWritePoolSize="2132"
                     messageVersion="Soap12Addressing10"
                     textEncoding="utf-8" />
```  
  
## <a name="see-also"></a><span data-ttu-id="cdc2b-158">Vea también</span><span class="sxs-lookup"><span data-stu-id="cdc2b-158">See also</span></span>
- <xref:System.ServiceModel.Configuration.TextMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>
- [<span data-ttu-id="cdc2b-159">Elección de un codificador de mensajes</span><span class="sxs-lookup"><span data-stu-id="cdc2b-159">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="cdc2b-160">Codificación de mensajes</span><span class="sxs-lookup"><span data-stu-id="cdc2b-160">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)
- [<span data-ttu-id="cdc2b-161">Enlaces</span><span class="sxs-lookup"><span data-stu-id="cdc2b-161">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="cdc2b-162">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="cdc2b-162">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="cdc2b-163">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="cdc2b-163">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="cdc2b-164">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="cdc2b-164">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
