---
title: '&lt;textMessageEncoding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e6d834d0-356e-45eb-b530-bbefbb9ec3f0
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5ac17ead3c7054f0125527e3992fe865624770a9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="lttextmessageencodinggt"></a><span data-ttu-id="9587f-102">&lt;textMessageEncoding&gt;</span><span class="sxs-lookup"><span data-stu-id="9587f-102">&lt;textMessageEncoding&gt;</span></span>
<span data-ttu-id="9587f-103">Especifica la codificación de caracteres y la versión del mensaje utilizadas para los mensajes XML basados en texto.</span><span class="sxs-lookup"><span data-stu-id="9587f-103">Specifies the character encoding and message versioning used for text-based XML messages.</span></span>  
  
 <span data-ttu-id="9587f-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="9587f-104">\<system.serviceModel></span></span>  
<span data-ttu-id="9587f-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="9587f-105">\<bindings></span></span>  
<span data-ttu-id="9587f-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="9587f-106">\<customBinding></span></span>  
<span data-ttu-id="9587f-107">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="9587f-107">\<binding></span></span>  
<span data-ttu-id="9587f-108">\<textMessageEncoding ></span><span class="sxs-lookup"><span data-stu-id="9587f-108">\<textMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9587f-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9587f-109">Syntax</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="Integer"  
   maxWritePoolSize="Integer"  
   messageVersion="Soap11Addressing10/Soap12Addressing10"  
      writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9587f-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9587f-110">Attributes and Elements</span></span>  
 <span data-ttu-id="9587f-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9587f-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9587f-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="9587f-112">Attributes</span></span>  
  
|<span data-ttu-id="9587f-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="9587f-113">Attribute</span></span>|<span data-ttu-id="9587f-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="9587f-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9587f-115">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="9587f-115">maxReadPoolSize</span></span>|<span data-ttu-id="9587f-116">Un entero que especifica cuántos mensajes pueden leerse simultáneamente sin asignar nuevos lectores.</span><span class="sxs-lookup"><span data-stu-id="9587f-116">An integer that specifies how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="9587f-117">Los tamaños de grupo más grandes hacen que el sistema sea más tolerante a picos de actividad a costa de un espacio de trabajo mayor.</span><span class="sxs-lookup"><span data-stu-id="9587f-117">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="9587f-118">El valor predeterminado es 64.</span><span class="sxs-lookup"><span data-stu-id="9587f-118">The default is 64.</span></span>|  
|<span data-ttu-id="9587f-119">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="9587f-119">maxWritePoolSize</span></span>|<span data-ttu-id="9587f-120">Un entero que especifica cuántos mensajes pueden enviarse simultáneamente sin asignar nuevos escritores.</span><span class="sxs-lookup"><span data-stu-id="9587f-120">An integer that specifies how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="9587f-121">Los tamaños de grupo más grandes hacen que el sistema sea más tolerante a picos de actividad a costa de un espacio de trabajo mayor.</span><span class="sxs-lookup"><span data-stu-id="9587f-121">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="9587f-122">El valor predeterminado es 16.</span><span class="sxs-lookup"><span data-stu-id="9587f-122">The default is 16.</span></span>|  
|<span data-ttu-id="9587f-123">messageVersion</span><span class="sxs-lookup"><span data-stu-id="9587f-123">messageVersion</span></span>|<span data-ttu-id="9587f-124">Especifica la versión SOAP de los mensajes enviados utilizando el enlace.</span><span class="sxs-lookup"><span data-stu-id="9587f-124">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="9587f-125">Los valores válidos son</span><span class="sxs-lookup"><span data-stu-id="9587f-125">Valid values are</span></span><br /><br /> <span data-ttu-id="9587f-126">-Soap11Addressing10</span><span class="sxs-lookup"><span data-stu-id="9587f-126">-   Soap11Addressing10</span></span><br /><span data-ttu-id="9587f-127">-Soap12Addressing10</span><span class="sxs-lookup"><span data-stu-id="9587f-127">-   Soap12Addressing10</span></span><br /><br /> <span data-ttu-id="9587f-128">El valor predeterminado es Soap12Addressing10.</span><span class="sxs-lookup"><span data-stu-id="9587f-128">The default is Soap12Addressing10.</span></span> <span data-ttu-id="9587f-129">Este atributo es del tipo <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="9587f-129">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
|<span data-ttu-id="9587f-130">writeEncoding</span><span class="sxs-lookup"><span data-stu-id="9587f-130">writeEncoding</span></span>|<span data-ttu-id="9587f-131">Especifica el codificador del juego de caracteres que se va a usar para emitir los mensajes en el enlace.</span><span class="sxs-lookup"><span data-stu-id="9587f-131">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="9587f-132">Los valores válidos son</span><span class="sxs-lookup"><span data-stu-id="9587f-132">Valid values are</span></span><br /><br /> <span data-ttu-id="9587f-133">-UnicodeFffeTextEncoding: Codificación de Unicode BigEndian</span><span class="sxs-lookup"><span data-stu-id="9587f-133">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding</span></span><br /><span data-ttu-id="9587f-134">-Utf16TextEncoding: Codificación de Unicode</span><span class="sxs-lookup"><span data-stu-id="9587f-134">-   Utf16TextEncoding: Unicode encoding</span></span><br /><span data-ttu-id="9587f-135">-Utf8TextEncoding: codificación de 8 bits</span><span class="sxs-lookup"><span data-stu-id="9587f-135">-   Utf8TextEncoding: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="9587f-136">El valor predeterminado es Utf8TextEncoding.</span><span class="sxs-lookup"><span data-stu-id="9587f-136">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="9587f-137">Este atributo es del tipo <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="9587f-137">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9587f-138">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9587f-138">Child Elements</span></span>  
  
|<span data-ttu-id="9587f-139">Elemento</span><span class="sxs-lookup"><span data-stu-id="9587f-139">Element</span></span>|<span data-ttu-id="9587f-140">Descripción</span><span class="sxs-lookup"><span data-stu-id="9587f-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9587f-141">\<readerQuotas ></span><span class="sxs-lookup"><span data-stu-id="9587f-141">\<readerQuotas></span></span>](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="9587f-142">Define las restricciones en la complejidad de los mensajes SOAP que pueden ser procesados por los puntos de conexión configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="9587f-142">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="9587f-143">Este elemento es del tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="9587f-143">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9587f-144">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9587f-144">Parent Elements</span></span>  
  
|<span data-ttu-id="9587f-145">Elemento</span><span class="sxs-lookup"><span data-stu-id="9587f-145">Element</span></span>|<span data-ttu-id="9587f-146">Descripción</span><span class="sxs-lookup"><span data-stu-id="9587f-146">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9587f-147">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="9587f-147">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="9587f-148">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="9587f-148">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9587f-149">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9587f-149">Remarks</span></span>  
 <span data-ttu-id="9587f-150">La codificación es el proceso de transformación de un mensaje en una secuencia de bytes.</span><span class="sxs-lookup"><span data-stu-id="9587f-150">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="9587f-151">La descodificación es el proceso inverso.</span><span class="sxs-lookup"><span data-stu-id="9587f-151">Decoding is the reverse process.</span></span> <span data-ttu-id="9587f-152">Windows Communication Foundation (WCF) incluye tres tipos de codificación para los mensajes SOAP: Texto, Binario y Mecanismo de optimización de transmisión del mensaje (MTOM).</span><span class="sxs-lookup"><span data-stu-id="9587f-152">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="9587f-153">La codificación de texto representada por el elemento `textMessageEncoding` es el codificador más interoperable, pero el menos eficaz para los mensajes XML.</span><span class="sxs-lookup"><span data-stu-id="9587f-153">The text encoding represented by the `textMessageEncoding` element is the most interoperable, but the least efficient encoder for XML messages.</span></span>  <span data-ttu-id="9587f-154">El codificador de texto crea mensajes basados en texto en la conexión.</span><span class="sxs-lookup"><span data-stu-id="9587f-154">The text encoder creates text-based messages on the wire.</span></span> <span data-ttu-id="9587f-155">Los mensajes generados por este codificador son adecuados para la interoperabilidad basada en WS - *.</span><span class="sxs-lookup"><span data-stu-id="9587f-155">Messages produced by this encoder are suitable for WS-* based interop.</span></span> <span data-ttu-id="9587f-156">Un servicio web o un cliente de servicios web, por lo general, pueden entender XML textual.</span><span class="sxs-lookup"><span data-stu-id="9587f-156">Web service or Web service client can generally understand textual XML.</span></span> <span data-ttu-id="9587f-157">Sin embargo, transmitir bloques grandes de datos binarios como texto es el método menos eficaz para codificar mensajes XML.</span><span class="sxs-lookup"><span data-stu-id="9587f-157">However, transmitting large blocks of binary data as text is the least efficient method for encoding XML messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9587f-158">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9587f-158">Example</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="211"  
    maxWritePoolSize="2132"  
    messageVersion="Soap12Addressing10"  
    textEncoding="utf-8" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="9587f-159">Vea también</span><span class="sxs-lookup"><span data-stu-id="9587f-159">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.TextMessageEncodingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>  
 <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>  
 [<span data-ttu-id="9587f-160">Elección de un codificador de mensajes</span><span class="sxs-lookup"><span data-stu-id="9587f-160">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 [<span data-ttu-id="9587f-161">Codificación de mensajes</span><span class="sxs-lookup"><span data-stu-id="9587f-161">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)  
 [<span data-ttu-id="9587f-162">Enlaces</span><span class="sxs-lookup"><span data-stu-id="9587f-162">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="9587f-163">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="9587f-163">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="9587f-164">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="9587f-164">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="9587f-165">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="9587f-165">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
