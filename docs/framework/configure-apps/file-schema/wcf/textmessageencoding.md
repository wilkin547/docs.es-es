---
title: '&lt;textMessageEncoding&gt;'
ms.date: 03/30/2017
ms.assetid: e6d834d0-356e-45eb-b530-bbefbb9ec3f0
ms.openlocfilehash: 0ee50a4b5adeede2dd531ba734ac9fb420f3b713
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54150245"
---
# <a name="lttextmessageencodinggt"></a><span data-ttu-id="5efe4-102">&lt;textMessageEncoding&gt;</span><span class="sxs-lookup"><span data-stu-id="5efe4-102">&lt;textMessageEncoding&gt;</span></span>
<span data-ttu-id="5efe4-103">Especifica la codificación de caracteres y la versión del mensaje utilizadas para los mensajes XML basados en texto.</span><span class="sxs-lookup"><span data-stu-id="5efe4-103">Specifies the character encoding and message versioning used for text-based XML messages.</span></span>  
  
 <span data-ttu-id="5efe4-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="5efe4-104">\<system.serviceModel></span></span>  
<span data-ttu-id="5efe4-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="5efe4-105">\<bindings></span></span>  
<span data-ttu-id="5efe4-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="5efe4-106">\<customBinding></span></span>  
<span data-ttu-id="5efe4-107">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="5efe4-107">\<binding></span></span>  
<span data-ttu-id="5efe4-108">\<textMessageEncoding ></span><span class="sxs-lookup"><span data-stu-id="5efe4-108">\<textMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5efe4-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5efe4-109">Syntax</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="Integer"
                     maxWritePoolSize="Integer"
                     messageVersion="Soap11Addressing10/Soap12Addressing10"
                     writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5efe4-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5efe4-110">Attributes and Elements</span></span>  
 <span data-ttu-id="5efe4-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5efe4-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5efe4-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="5efe4-112">Attributes</span></span>  
  
|<span data-ttu-id="5efe4-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="5efe4-113">Attribute</span></span>|<span data-ttu-id="5efe4-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="5efe4-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5efe4-115">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="5efe4-115">maxReadPoolSize</span></span>|<span data-ttu-id="5efe4-116">Un entero que especifica cuántos mensajes pueden leerse simultáneamente sin asignar nuevos lectores.</span><span class="sxs-lookup"><span data-stu-id="5efe4-116">An integer that specifies how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="5efe4-117">Los tamaños de grupo más grandes hacen que el sistema sea más tolerante a picos de actividad a costa de un espacio de trabajo mayor.</span><span class="sxs-lookup"><span data-stu-id="5efe4-117">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="5efe4-118">El valor predeterminado es 64.</span><span class="sxs-lookup"><span data-stu-id="5efe4-118">The default is 64.</span></span>|  
|<span data-ttu-id="5efe4-119">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="5efe4-119">maxWritePoolSize</span></span>|<span data-ttu-id="5efe4-120">Un entero que especifica cuántos mensajes pueden enviarse simultáneamente sin asignar nuevos escritores.</span><span class="sxs-lookup"><span data-stu-id="5efe4-120">An integer that specifies how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="5efe4-121">Los tamaños de grupo más grandes hacen que el sistema sea más tolerante a picos de actividad a costa de un espacio de trabajo mayor.</span><span class="sxs-lookup"><span data-stu-id="5efe4-121">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="5efe4-122">El valor predeterminado es 16.</span><span class="sxs-lookup"><span data-stu-id="5efe4-122">The default is 16.</span></span>|  
|<span data-ttu-id="5efe4-123">messageVersion</span><span class="sxs-lookup"><span data-stu-id="5efe4-123">messageVersion</span></span>|<span data-ttu-id="5efe4-124">Especifica la versión SOAP de los mensajes enviados utilizando el enlace.</span><span class="sxs-lookup"><span data-stu-id="5efe4-124">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="5efe4-125">Los valores válidos son</span><span class="sxs-lookup"><span data-stu-id="5efe4-125">Valid values are</span></span><br /><br /> <span data-ttu-id="5efe4-126">-Soap11Addressing10</span><span class="sxs-lookup"><span data-stu-id="5efe4-126">-   Soap11Addressing10</span></span><br /><span data-ttu-id="5efe4-127">-Soap12Addressing10</span><span class="sxs-lookup"><span data-stu-id="5efe4-127">-   Soap12Addressing10</span></span><br /><br /> <span data-ttu-id="5efe4-128">El valor predeterminado es Soap12Addressing10.</span><span class="sxs-lookup"><span data-stu-id="5efe4-128">The default is Soap12Addressing10.</span></span> <span data-ttu-id="5efe4-129">Este atributo es del tipo <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="5efe4-129">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
|<span data-ttu-id="5efe4-130">writeEncoding</span><span class="sxs-lookup"><span data-stu-id="5efe4-130">writeEncoding</span></span>|<span data-ttu-id="5efe4-131">Especifica el codificador del juego de caracteres que se va a usar para emitir los mensajes en el enlace.</span><span class="sxs-lookup"><span data-stu-id="5efe4-131">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="5efe4-132">Los valores válidos son</span><span class="sxs-lookup"><span data-stu-id="5efe4-132">Valid values are</span></span><br /><br /> <span data-ttu-id="5efe4-133">-UnicodeFffeTextEncoding: Codificación Unicode BigEndian</span><span class="sxs-lookup"><span data-stu-id="5efe4-133">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding</span></span><br /><span data-ttu-id="5efe4-134">-Utf16TextEncoding: Codificación Unicode</span><span class="sxs-lookup"><span data-stu-id="5efe4-134">-   Utf16TextEncoding: Unicode encoding</span></span><br /><span data-ttu-id="5efe4-135">-Utf8TextEncoding: codificación de 8 bits</span><span class="sxs-lookup"><span data-stu-id="5efe4-135">-   Utf8TextEncoding: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="5efe4-136">El valor predeterminado es Utf8TextEncoding.</span><span class="sxs-lookup"><span data-stu-id="5efe4-136">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="5efe4-137">Este atributo es del tipo <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="5efe4-137">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5efe4-138">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5efe4-138">Child Elements</span></span>  
  
|<span data-ttu-id="5efe4-139">Elemento</span><span class="sxs-lookup"><span data-stu-id="5efe4-139">Element</span></span>|<span data-ttu-id="5efe4-140">Descripción</span><span class="sxs-lookup"><span data-stu-id="5efe4-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5efe4-141">\<readerQuotas></span><span class="sxs-lookup"><span data-stu-id="5efe4-141">\<readerQuotas></span></span>](https://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="5efe4-142">Define las restricciones en la complejidad de los mensajes SOAP que pueden ser procesados por los puntos de conexión configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="5efe4-142">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="5efe4-143">Este elemento es del tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="5efe4-143">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5efe4-144">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5efe4-144">Parent Elements</span></span>  
  
|<span data-ttu-id="5efe4-145">Elemento</span><span class="sxs-lookup"><span data-stu-id="5efe4-145">Element</span></span>|<span data-ttu-id="5efe4-146">Descripción</span><span class="sxs-lookup"><span data-stu-id="5efe4-146">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5efe4-147">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="5efe4-147">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="5efe4-148">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="5efe4-148">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5efe4-149">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5efe4-149">Remarks</span></span>  
 <span data-ttu-id="5efe4-150">La codificación es el proceso de transformación de un mensaje en una secuencia de bytes.</span><span class="sxs-lookup"><span data-stu-id="5efe4-150">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="5efe4-151">La descodificación es el proceso inverso.</span><span class="sxs-lookup"><span data-stu-id="5efe4-151">Decoding is the reverse process.</span></span> <span data-ttu-id="5efe4-152">Windows Communication Foundation (WCF) incluye tres tipos de codificación para los mensajes SOAP: Texto, binario y mecanismo de optimización de transmisión de mensajes (MTOM).</span><span class="sxs-lookup"><span data-stu-id="5efe4-152">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="5efe4-153">La codificación de texto representada por el elemento `textMessageEncoding` es el codificador más interoperable, pero el menos eficaz para los mensajes XML.</span><span class="sxs-lookup"><span data-stu-id="5efe4-153">The text encoding represented by the `textMessageEncoding` element is the most interoperable, but the least efficient encoder for XML messages.</span></span>  <span data-ttu-id="5efe4-154">El codificador de texto crea mensajes basados en texto en la conexión.</span><span class="sxs-lookup"><span data-stu-id="5efe4-154">The text encoder creates text-based messages on the wire.</span></span> <span data-ttu-id="5efe4-155">Los mensajes generados por este codificador son adecuados para la interoperabilidad basada en WS - \*.</span><span class="sxs-lookup"><span data-stu-id="5efe4-155">Messages produced by this encoder are suitable for WS-\* based interop.</span></span> <span data-ttu-id="5efe4-156">Un servicio web o un cliente de servicios web, por lo general, pueden entender XML textual.</span><span class="sxs-lookup"><span data-stu-id="5efe4-156">Web service or Web service client can generally understand textual XML.</span></span> <span data-ttu-id="5efe4-157">Sin embargo, transmitir bloques grandes de datos binarios como texto es el método menos eficaz para codificar mensajes XML.</span><span class="sxs-lookup"><span data-stu-id="5efe4-157">However, transmitting large blocks of binary data as text is the least efficient method for encoding XML messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5efe4-158">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5efe4-158">Example</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="211"
                     maxWritePoolSize="2132"
                     messageVersion="Soap12Addressing10"
                     textEncoding="utf-8" />
```  
  
## <a name="see-also"></a><span data-ttu-id="5efe4-159">Vea también</span><span class="sxs-lookup"><span data-stu-id="5efe4-159">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.TextMessageEncodingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>  
 <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>  
 [<span data-ttu-id="5efe4-160">Elección de un codificador de mensajes</span><span class="sxs-lookup"><span data-stu-id="5efe4-160">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 [<span data-ttu-id="5efe4-161">Codificación de mensajes</span><span class="sxs-lookup"><span data-stu-id="5efe4-161">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)  
 [<span data-ttu-id="5efe4-162">Enlaces</span><span class="sxs-lookup"><span data-stu-id="5efe4-162">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="5efe4-163">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="5efe4-163">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="5efe4-164">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="5efe4-164">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="5efe4-165">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="5efe4-165">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
