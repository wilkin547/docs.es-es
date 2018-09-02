---
title: '&lt;mtomMessageEncoding&gt;'
ms.date: 03/30/2017
ms.assetid: 7865d171-cd1e-430a-8421-39cc13541d1b
ms.openlocfilehash: 380aa162d2bb55ac968bdd057a4bb45b2ea6abfe
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43452638"
---
# <a name="ltmtommessageencodinggt"></a><span data-ttu-id="41738-102">&lt;mtomMessageEncoding&gt;</span><span class="sxs-lookup"><span data-stu-id="41738-102">&lt;mtomMessageEncoding&gt;</span></span>
<span data-ttu-id="41738-103">Especifica la codificación y la versión del mensaje utilizada para los mensajes basados en el mecanismo de optimización de la transmisión de mensajes (MTOM) SOAP.</span><span class="sxs-lookup"><span data-stu-id="41738-103">Specifies the encoding and message versioning used for SOAP Message Transmission Optimization Mechanism (MTOM) based messages.</span></span>  
  
 <span data-ttu-id="41738-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="41738-104">\<system.serviceModel></span></span>  
<span data-ttu-id="41738-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="41738-105">\<bindings></span></span>  
<span data-ttu-id="41738-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="41738-106">\<customBinding></span></span>  
<span data-ttu-id="41738-107">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="41738-107">\<binding></span></span>  
<span data-ttu-id="41738-108">\<mtomMessageEncoding ></span><span class="sxs-lookup"><span data-stu-id="41738-108">\<mtomMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41738-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="41738-109">Syntax</span></span>  
  
```xml  
<mtomMessageEncoding   
   maxBufferSize="Integer"  
      maxReadPoolSize="Integer"  
   maxWritePoolSize="Integer"  
   messageVersion="Soap11Addressing1/Soap12Addressing10"  
      writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="41738-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="41738-110">Attributes and Elements</span></span>  
 <span data-ttu-id="41738-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="41738-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="41738-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="41738-112">Attributes</span></span>  
  
|<span data-ttu-id="41738-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="41738-113">Attribute</span></span>|<span data-ttu-id="41738-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="41738-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="41738-115">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="41738-115">maxBufferSize</span></span>|<span data-ttu-id="41738-116">Un entero que especifica el tamaño máximo del búfer que se puede utilizar.</span><span class="sxs-lookup"><span data-stu-id="41738-116">An integer that specifies the maximum size of the buffer that can be used.</span></span>|  
|<span data-ttu-id="41738-117">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="41738-117">maxReadPoolSize</span></span>|<span data-ttu-id="41738-118">Un entero que especifica cuántos mensajes pueden leerse simultáneamente sin asignar nuevos lectores.</span><span class="sxs-lookup"><span data-stu-id="41738-118">An integer that specifies how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="41738-119">Los tamaños de grupo más grandes hacen que el sistema sea más tolerante a picos de actividad a costa de un espacio de trabajo mayor.</span><span class="sxs-lookup"><span data-stu-id="41738-119">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="41738-120">El valor predeterminado es 64.</span><span class="sxs-lookup"><span data-stu-id="41738-120">The default is 64.</span></span>|  
|<span data-ttu-id="41738-121">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="41738-121">maxWritePoolSize</span></span>|<span data-ttu-id="41738-122">Un entero que especifica cuántos mensajes pueden enviarse simultáneamente sin asignar nuevos escritores.</span><span class="sxs-lookup"><span data-stu-id="41738-122">An integer that specifies how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="41738-123">Los tamaños de grupo más grandes hacen que el sistema sea más tolerante a picos de actividad a costa de un espacio de trabajo mayor.</span><span class="sxs-lookup"><span data-stu-id="41738-123">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="41738-124">El valor predeterminado es 16.</span><span class="sxs-lookup"><span data-stu-id="41738-124">The default is 16.</span></span>|  
|<span data-ttu-id="41738-125">messageVersion</span><span class="sxs-lookup"><span data-stu-id="41738-125">messageVersion</span></span>|<span data-ttu-id="41738-126">Especifica la versión SOAP de los mensajes enviados utilizando el enlace.</span><span class="sxs-lookup"><span data-stu-id="41738-126">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="41738-127">Los valores válidos son</span><span class="sxs-lookup"><span data-stu-id="41738-127">Valid values are</span></span><br /><br /> <span data-ttu-id="41738-128">-Soap11Addressing1</span><span class="sxs-lookup"><span data-stu-id="41738-128">-   Soap11Addressing1</span></span><br /><span data-ttu-id="41738-129">-Soap12Addressing10</span><span class="sxs-lookup"><span data-stu-id="41738-129">-   Soap12Addressing10</span></span><br /><br /> <span data-ttu-id="41738-130">El valor predeterminado es Soap12Addressing10.</span><span class="sxs-lookup"><span data-stu-id="41738-130">The default is Soap12Addressing10.</span></span> <span data-ttu-id="41738-131">Este atributo es del tipo <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="41738-131">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
|<span data-ttu-id="41738-132">writeEncoding</span><span class="sxs-lookup"><span data-stu-id="41738-132">writeEncoding</span></span>|<span data-ttu-id="41738-133">Especifica el codificador del juego de caracteres que se va a usar para emitir los mensajes en el enlace.</span><span class="sxs-lookup"><span data-stu-id="41738-133">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="41738-134">Los valores válidos son</span><span class="sxs-lookup"><span data-stu-id="41738-134">Valid values are</span></span><br /><br /> <span data-ttu-id="41738-135">-UnicodeFffeTextEncoding: Codificación de Unicode BigEndian</span><span class="sxs-lookup"><span data-stu-id="41738-135">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding</span></span><br /><span data-ttu-id="41738-136">-Utf16TextEncoding: Codificación de Unicode</span><span class="sxs-lookup"><span data-stu-id="41738-136">-   Utf16TextEncoding: Unicode encoding</span></span><br /><span data-ttu-id="41738-137">-Utf8TextEncoding: codificación de 8 bits</span><span class="sxs-lookup"><span data-stu-id="41738-137">-   Utf8TextEncoding: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="41738-138">El valor predeterminado es Utf8TextEncoding.</span><span class="sxs-lookup"><span data-stu-id="41738-138">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="41738-139">Este atributo es del tipo <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="41738-139">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="41738-140">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="41738-140">Child Elements</span></span>  
  
|<span data-ttu-id="41738-141">Elemento</span><span class="sxs-lookup"><span data-stu-id="41738-141">Element</span></span>|<span data-ttu-id="41738-142">Descripción</span><span class="sxs-lookup"><span data-stu-id="41738-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="41738-143">\<readerQuotas></span><span class="sxs-lookup"><span data-stu-id="41738-143">\<readerQuotas></span></span>](https://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="41738-144">Define las restricciones en la complejidad de los mensajes SOAP que pueden ser procesados por los puntos de conexión configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="41738-144">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="41738-145">Este elemento es del tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="41738-145">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="41738-146">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="41738-146">Parent Elements</span></span>  
  
|<span data-ttu-id="41738-147">Elemento</span><span class="sxs-lookup"><span data-stu-id="41738-147">Element</span></span>|<span data-ttu-id="41738-148">Descripción</span><span class="sxs-lookup"><span data-stu-id="41738-148">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="41738-149">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="41738-149">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="41738-150">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="41738-150">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="41738-151">Comentarios</span><span class="sxs-lookup"><span data-stu-id="41738-151">Remarks</span></span>  
 <span data-ttu-id="41738-152">La codificación es el proceso de transformación de un mensaje en una secuencia de bytes.</span><span class="sxs-lookup"><span data-stu-id="41738-152">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="41738-153">La descodificación es el proceso inverso.</span><span class="sxs-lookup"><span data-stu-id="41738-153">Decoding is the reverse process.</span></span> <span data-ttu-id="41738-154">Windows Communication Foundation (WCF) incluye tres tipos de codificación para los mensajes SOAP: Texto, Binario y Mecanismo de optimización de transmisión del mensaje (MTOM).</span><span class="sxs-lookup"><span data-stu-id="41738-154">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="41738-155">El elemento `MtomMessageEncoding` especifica la codificación de caracteres y control de versión de mensajes y otros valores usados para los mensajes que utilizan una codificación MTOM (mecanismo de optimización de transmisión de mensajes).</span><span class="sxs-lookup"><span data-stu-id="41738-155">The `MtomMessageEncoding` element specifies the character encoding and message versioning and other settings used for messages using a Message Transmission Optimization Mechanism (MTOM) encoding.</span></span> <span data-ttu-id="41738-156">MTOM es una tecnología eficaz para la transmisión de datos binarios en mensajes de WCF.</span><span class="sxs-lookup"><span data-stu-id="41738-156">MTOM is an efficient technology for transmitting binary data in WCF messages.</span></span> <span data-ttu-id="41738-157">El codificador MTOM intenta crear una balanza entre la eficacia y la interoperabilidad.</span><span class="sxs-lookup"><span data-stu-id="41738-157">The MTOM encoder attempts to create a balance between efficiency and interoperability.</span></span> <span data-ttu-id="41738-158">El codificador MTOM transmite la mayoría del XML en formato de texto, pero optimiza los bloques grandes de datos binarios transmitiéndolos como son, sin convertirlos a su formato codificado base64.</span><span class="sxs-lookup"><span data-stu-id="41738-158">The MTOM encoding transmits most XML in textual form, but optimizes large blocks of binary data by transmitting them as-is, without conversion to their base64 encoded format.</span></span>  
  
## <a name="example"></a><span data-ttu-id="41738-159">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="41738-159">Example</span></span>  
  
```xml  
<mtomMessageEncoding maxReadPoolSize="211"  
    maxWritePoolSize="2132"  
    messageVersion="Soap11Addressing10"  
    textEncoding="utf-8" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="41738-160">Vea también</span><span class="sxs-lookup"><span data-stu-id="41738-160">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.MtomMessageEncodingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>  
 <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>  
 [<span data-ttu-id="41738-161">Codificación de mensajes</span><span class="sxs-lookup"><span data-stu-id="41738-161">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)  
 [<span data-ttu-id="41738-162">Elección de un codificador de mensajes</span><span class="sxs-lookup"><span data-stu-id="41738-162">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 [<span data-ttu-id="41738-163">Enlaces</span><span class="sxs-lookup"><span data-stu-id="41738-163">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="41738-164">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="41738-164">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="41738-165">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="41738-165">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="41738-166">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="41738-166">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
