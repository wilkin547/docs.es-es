---
title: <textMessageEncoding>
ms.date: 03/30/2017
ms.assetid: e6d834d0-356e-45eb-b530-bbefbb9ec3f0
ms.openlocfilehash: d67d623736f3cbf50568356132a74d2b234fdfd9
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73736220"
---
# <a name="textmessageencoding"></a><span data-ttu-id="8c443-101">\<textMessageEncoding ></span><span class="sxs-lookup"><span data-stu-id="8c443-101">\<textMessageEncoding></span></span>
<span data-ttu-id="8c443-102">Especifica la codificación de caracteres y la versión del mensaje utilizadas para los mensajes XML basados en texto.</span><span class="sxs-lookup"><span data-stu-id="8c443-102">Specifies the character encoding and message versioning used for text-based XML messages.</span></span>  
  
<span data-ttu-id="8c443-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8c443-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8c443-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="8c443-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="8c443-105">&nbsp;&nbsp;&nbsp;&nbsp;\<[**enlaces**](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="8c443-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="8c443-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**customBinding**](custombinding.md) ></span><span class="sxs-lookup"><span data-stu-id="8c443-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="8c443-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**enlace** ></span><span class="sxs-lookup"><span data-stu-id="8c443-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="8c443-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<textMessageEncoding >**</span><span class="sxs-lookup"><span data-stu-id="8c443-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<textMessageEncoding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c443-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8c443-109">Syntax</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="Integer"
                     maxWritePoolSize="Integer"
                     messageVersion="Soap11Addressing10/Soap12Addressing10"
                     writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8c443-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="8c443-110">Attributes and Elements</span></span>  
 <span data-ttu-id="8c443-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="8c443-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8c443-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="8c443-112">Attributes</span></span>  
  
|<span data-ttu-id="8c443-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="8c443-113">Attribute</span></span>|<span data-ttu-id="8c443-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="8c443-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8c443-115">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="8c443-115">maxReadPoolSize</span></span>|<span data-ttu-id="8c443-116">Un entero que especifica cuántos mensajes pueden leerse simultáneamente sin asignar nuevos lectores.</span><span class="sxs-lookup"><span data-stu-id="8c443-116">An integer that specifies how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="8c443-117">Los tamaños de grupo más grandes hacen que el sistema sea más tolerante a picos de actividad a costa de un espacio de trabajo mayor.</span><span class="sxs-lookup"><span data-stu-id="8c443-117">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="8c443-118">El valor predeterminado es 64.</span><span class="sxs-lookup"><span data-stu-id="8c443-118">The default is 64.</span></span>|  
|<span data-ttu-id="8c443-119">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="8c443-119">maxWritePoolSize</span></span>|<span data-ttu-id="8c443-120">Un entero que especifica cuántos mensajes pueden enviarse simultáneamente sin asignar nuevos escritores.</span><span class="sxs-lookup"><span data-stu-id="8c443-120">An integer that specifies how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="8c443-121">Los tamaños de grupo más grandes hacen que el sistema sea más tolerante a picos de actividad a costa de un espacio de trabajo mayor.</span><span class="sxs-lookup"><span data-stu-id="8c443-121">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="8c443-122">El valor predeterminado es 16.</span><span class="sxs-lookup"><span data-stu-id="8c443-122">The default is 16.</span></span>|  
|<span data-ttu-id="8c443-123">messageVersion</span><span class="sxs-lookup"><span data-stu-id="8c443-123">messageVersion</span></span>|<span data-ttu-id="8c443-124">Especifica la versión SOAP de los mensajes enviados utilizando el enlace.</span><span class="sxs-lookup"><span data-stu-id="8c443-124">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="8c443-125">Los valores válidos son</span><span class="sxs-lookup"><span data-stu-id="8c443-125">Valid values are</span></span><br /><br /> <span data-ttu-id="8c443-126">- Soap11Addressing10</span><span class="sxs-lookup"><span data-stu-id="8c443-126">-   Soap11Addressing10</span></span><br /><span data-ttu-id="8c443-127">- Soap12Addressing10</span><span class="sxs-lookup"><span data-stu-id="8c443-127">-   Soap12Addressing10</span></span><br /><span data-ttu-id="8c443-128">- Soap11</span><span class="sxs-lookup"><span data-stu-id="8c443-128">-   Soap11</span></span><br /><span data-ttu-id="8c443-129">-Soap12</span><span class="sxs-lookup"><span data-stu-id="8c443-129">-  Soap12</span></span><br /><br /><span data-ttu-id="8c443-130">El valor predeterminado es Soap12Addressing10.</span><span class="sxs-lookup"><span data-stu-id="8c443-130">The default is Soap12Addressing10.</span></span> <span data-ttu-id="8c443-131">Este atributo es del tipo <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="8c443-131">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
|<span data-ttu-id="8c443-132">writeEncoding</span><span class="sxs-lookup"><span data-stu-id="8c443-132">writeEncoding</span></span>|<span data-ttu-id="8c443-133">Especifica el codificador del juego de caracteres que se va a usar para emitir los mensajes en el enlace.</span><span class="sxs-lookup"><span data-stu-id="8c443-133">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="8c443-134">Los valores válidos son</span><span class="sxs-lookup"><span data-stu-id="8c443-134">Valid values are</span></span><br /><br /> <span data-ttu-id="8c443-135">-UnicodeFffeTextEncoding: codificación Unicode BigEndian</span><span class="sxs-lookup"><span data-stu-id="8c443-135">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding</span></span><br /><span data-ttu-id="8c443-136">-Utf16TextEncoding: codificación Unicode</span><span class="sxs-lookup"><span data-stu-id="8c443-136">-   Utf16TextEncoding: Unicode encoding</span></span><br /><span data-ttu-id="8c443-137">-Utf8TextEncoding: codificación de 8 bits</span><span class="sxs-lookup"><span data-stu-id="8c443-137">-   Utf8TextEncoding: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="8c443-138">El valor predeterminado es Utf8TextEncoding.</span><span class="sxs-lookup"><span data-stu-id="8c443-138">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="8c443-139">Este atributo es del tipo <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="8c443-139">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8c443-140">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="8c443-140">Child Elements</span></span>  
  
|<span data-ttu-id="8c443-141">Elemento</span><span class="sxs-lookup"><span data-stu-id="8c443-141">Element</span></span>|<span data-ttu-id="8c443-142">Descripción</span><span class="sxs-lookup"><span data-stu-id="8c443-142">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8c443-143">[\<readerQuotas >](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="8c443-143">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="8c443-144">Define las restricciones en la complejidad de los mensajes SOAP que pueden ser procesados por los puntos de conexión configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="8c443-144">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="8c443-145">Este elemento es del tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="8c443-145">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8c443-146">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8c443-146">Parent Elements</span></span>  
  
|<span data-ttu-id="8c443-147">Elemento</span><span class="sxs-lookup"><span data-stu-id="8c443-147">Element</span></span>|<span data-ttu-id="8c443-148">Descripción</span><span class="sxs-lookup"><span data-stu-id="8c443-148">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8c443-149">\<> de enlace</span><span class="sxs-lookup"><span data-stu-id="8c443-149">\<binding></span></span>](bindings.md)|<span data-ttu-id="8c443-150">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="8c443-150">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8c443-151">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8c443-151">Remarks</span></span>  
 <span data-ttu-id="8c443-152">La codificación es el proceso de transformación de un mensaje en una secuencia de bytes.</span><span class="sxs-lookup"><span data-stu-id="8c443-152">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="8c443-153">La descodificación es el proceso inverso.</span><span class="sxs-lookup"><span data-stu-id="8c443-153">Decoding is the reverse process.</span></span> <span data-ttu-id="8c443-154">Windows Communication Foundation (WCF) incluye tres tipos de codificación para los mensajes SOAP: Texto, Binario y Mecanismo de optimización de transmisión del mensaje (MTOM).</span><span class="sxs-lookup"><span data-stu-id="8c443-154">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="8c443-155">La codificación de texto representada por el elemento `textMessageEncoding` es el codificador más interoperable, pero el menos eficaz para los mensajes XML.</span><span class="sxs-lookup"><span data-stu-id="8c443-155">The text encoding represented by the `textMessageEncoding` element is the most interoperable, but the least efficient encoder for XML messages.</span></span>  <span data-ttu-id="8c443-156">El codificador de texto crea mensajes basados en texto en la conexión.</span><span class="sxs-lookup"><span data-stu-id="8c443-156">The text encoder creates text-based messages on the wire.</span></span> <span data-ttu-id="8c443-157">Los mensajes generados por este codificador son adecuados para la interoperabilidad basada en WS - \*.</span><span class="sxs-lookup"><span data-stu-id="8c443-157">Messages produced by this encoder are suitable for WS-\* based interop.</span></span> <span data-ttu-id="8c443-158">Un servicio web o un cliente de servicios web, por lo general, pueden entender XML textual.</span><span class="sxs-lookup"><span data-stu-id="8c443-158">Web service or Web service client can generally understand textual XML.</span></span> <span data-ttu-id="8c443-159">Sin embargo, transmitir bloques grandes de datos binarios como texto es el método menos eficaz para codificar mensajes XML.</span><span class="sxs-lookup"><span data-stu-id="8c443-159">However, transmitting large blocks of binary data as text is the least efficient method for encoding XML messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c443-160">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8c443-160">Example</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="211"
                     maxWritePoolSize="2132"
                     messageVersion="Soap12Addressing10"
                     textEncoding="utf-8" />
```  
  
## <a name="see-also"></a><span data-ttu-id="8c443-161">Vea también</span><span class="sxs-lookup"><span data-stu-id="8c443-161">See also</span></span>

- <xref:System.ServiceModel.Configuration.TextMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>
- [<span data-ttu-id="8c443-162">Elección de un codificador de mensajes</span><span class="sxs-lookup"><span data-stu-id="8c443-162">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="8c443-163">Codificación de mensajes</span><span class="sxs-lookup"><span data-stu-id="8c443-163">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="8c443-164">Enlaces</span><span class="sxs-lookup"><span data-stu-id="8c443-164">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="8c443-165">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="8c443-165">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="8c443-166">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="8c443-166">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="8c443-167">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="8c443-167">\<customBinding></span></span>](custombinding.md)
