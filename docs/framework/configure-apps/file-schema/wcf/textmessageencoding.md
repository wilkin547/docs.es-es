---
title: <textMessageEncoding>
ms.date: 03/30/2017
ms.assetid: e6d834d0-356e-45eb-b530-bbefbb9ec3f0
ms.openlocfilehash: d67d623736f3cbf50568356132a74d2b234fdfd9
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "73736220"
---
# \<textMessageEncoding>
<span data-ttu-id="d2097-101">Especifica la codificación de caracteres y la versión del mensaje utilizadas para los mensajes XML basados en texto.</span><span class="sxs-lookup"><span data-stu-id="d2097-101">Specifies the character encoding and message versioning used for text-based XML messages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<textMessageEncoding>**  
  
## <a name="syntax"></a><span data-ttu-id="d2097-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d2097-102">Syntax</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="Integer"
                     maxWritePoolSize="Integer"
                     messageVersion="Soap11Addressing10/Soap12Addressing10"
                     writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d2097-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d2097-103">Attributes and Elements</span></span>  
 <span data-ttu-id="d2097-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d2097-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d2097-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="d2097-105">Attributes</span></span>  
  
|<span data-ttu-id="d2097-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="d2097-106">Attribute</span></span>|<span data-ttu-id="d2097-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="d2097-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d2097-108">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="d2097-108">maxReadPoolSize</span></span>|<span data-ttu-id="d2097-109">Un entero que especifica cuántos mensajes pueden leerse simultáneamente sin asignar nuevos lectores.</span><span class="sxs-lookup"><span data-stu-id="d2097-109">An integer that specifies how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="d2097-110">Los tamaños de grupo más grandes hacen que el sistema sea más tolerante a picos de actividad a costa de un espacio de trabajo mayor.</span><span class="sxs-lookup"><span data-stu-id="d2097-110">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="d2097-111">El valor predeterminado es 64.</span><span class="sxs-lookup"><span data-stu-id="d2097-111">The default is 64.</span></span>|  
|<span data-ttu-id="d2097-112">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="d2097-112">maxWritePoolSize</span></span>|<span data-ttu-id="d2097-113">Un entero que especifica cuántos mensajes pueden enviarse simultáneamente sin asignar nuevos escritores.</span><span class="sxs-lookup"><span data-stu-id="d2097-113">An integer that specifies how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="d2097-114">Los tamaños de grupo más grandes hacen que el sistema sea más tolerante a picos de actividad a costa de un espacio de trabajo mayor.</span><span class="sxs-lookup"><span data-stu-id="d2097-114">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="d2097-115">El valor predeterminado es 16.</span><span class="sxs-lookup"><span data-stu-id="d2097-115">The default is 16.</span></span>|  
|<span data-ttu-id="d2097-116">messageVersion</span><span class="sxs-lookup"><span data-stu-id="d2097-116">messageVersion</span></span>|<span data-ttu-id="d2097-117">Especifica la versión SOAP de los mensajes enviados utilizando el enlace.</span><span class="sxs-lookup"><span data-stu-id="d2097-117">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="d2097-118">Los valores válidos son</span><span class="sxs-lookup"><span data-stu-id="d2097-118">Valid values are</span></span><br /><br /> <span data-ttu-id="d2097-119">- Soap11Addressing10</span><span class="sxs-lookup"><span data-stu-id="d2097-119">-   Soap11Addressing10</span></span><br /><span data-ttu-id="d2097-120">- Soap12Addressing10</span><span class="sxs-lookup"><span data-stu-id="d2097-120">-   Soap12Addressing10</span></span><br /><span data-ttu-id="d2097-121">- Soap11</span><span class="sxs-lookup"><span data-stu-id="d2097-121">-   Soap11</span></span><br /><span data-ttu-id="d2097-122">-Soap12</span><span class="sxs-lookup"><span data-stu-id="d2097-122">-  Soap12</span></span><br /><br /><span data-ttu-id="d2097-123">El valor predeterminado es Soap12Addressing10.</span><span class="sxs-lookup"><span data-stu-id="d2097-123">The default is Soap12Addressing10.</span></span> <span data-ttu-id="d2097-124">Este atributo es del tipo <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="d2097-124">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
|<span data-ttu-id="d2097-125">writeEncoding</span><span class="sxs-lookup"><span data-stu-id="d2097-125">writeEncoding</span></span>|<span data-ttu-id="d2097-126">Especifica el codificador del juego de caracteres que se va a usar para emitir los mensajes en el enlace.</span><span class="sxs-lookup"><span data-stu-id="d2097-126">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="d2097-127">Los valores válidos son</span><span class="sxs-lookup"><span data-stu-id="d2097-127">Valid values are</span></span><br /><br /> <span data-ttu-id="d2097-128">-UnicodeFffeTextEncoding: codificación Unicode BigEndian</span><span class="sxs-lookup"><span data-stu-id="d2097-128">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding</span></span><br /><span data-ttu-id="d2097-129">-Utf16TextEncoding: codificación Unicode</span><span class="sxs-lookup"><span data-stu-id="d2097-129">-   Utf16TextEncoding: Unicode encoding</span></span><br /><span data-ttu-id="d2097-130">-Utf8TextEncoding: codificación de 8 bits</span><span class="sxs-lookup"><span data-stu-id="d2097-130">-   Utf8TextEncoding: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="d2097-131">El valor predeterminado es Utf8TextEncoding.</span><span class="sxs-lookup"><span data-stu-id="d2097-131">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="d2097-132">Este atributo es del tipo <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="d2097-132">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d2097-133">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d2097-133">Child Elements</span></span>  
  
|<span data-ttu-id="d2097-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="d2097-134">Element</span></span>|<span data-ttu-id="d2097-135">Descripción</span><span class="sxs-lookup"><span data-stu-id="d2097-135">Description</span></span>|  
|-------------|-----------------|  
|[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="d2097-136">Define las restricciones en la complejidad de los mensajes SOAP que pueden ser procesados por los puntos de conexión configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="d2097-136">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="d2097-137">Este elemento es del tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="d2097-137">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d2097-138">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d2097-138">Parent Elements</span></span>  
  
|<span data-ttu-id="d2097-139">Elemento</span><span class="sxs-lookup"><span data-stu-id="d2097-139">Element</span></span>|<span data-ttu-id="d2097-140">Descripción</span><span class="sxs-lookup"><span data-stu-id="d2097-140">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="d2097-141">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="d2097-141">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d2097-142">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d2097-142">Remarks</span></span>  
 <span data-ttu-id="d2097-143">La codificación es el proceso de transformación de un mensaje en una secuencia de bytes.</span><span class="sxs-lookup"><span data-stu-id="d2097-143">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="d2097-144">La descodificación es el proceso inverso.</span><span class="sxs-lookup"><span data-stu-id="d2097-144">Decoding is the reverse process.</span></span> <span data-ttu-id="d2097-145">Windows Communication Foundation (WCF) incluye tres tipos de codificación para los mensajes SOAP: Texto, Binario y Mecanismo de optimización de transmisión del mensaje (MTOM).</span><span class="sxs-lookup"><span data-stu-id="d2097-145">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="d2097-146">La codificación de texto representada por el elemento `textMessageEncoding` es el codificador más interoperable, pero el menos eficaz para los mensajes XML.</span><span class="sxs-lookup"><span data-stu-id="d2097-146">The text encoding represented by the `textMessageEncoding` element is the most interoperable, but the least efficient encoder for XML messages.</span></span>  <span data-ttu-id="d2097-147">El codificador de texto crea mensajes basados en texto en la conexión.</span><span class="sxs-lookup"><span data-stu-id="d2097-147">The text encoder creates text-based messages on the wire.</span></span> <span data-ttu-id="d2097-148">Los mensajes generados por este codificador son adecuados para la interoperabilidad basada en WS - \*.</span><span class="sxs-lookup"><span data-stu-id="d2097-148">Messages produced by this encoder are suitable for WS-\* based interop.</span></span> <span data-ttu-id="d2097-149">Un servicio web o un cliente de servicios web, por lo general, pueden entender XML textual.</span><span class="sxs-lookup"><span data-stu-id="d2097-149">Web service or Web service client can generally understand textual XML.</span></span> <span data-ttu-id="d2097-150">Sin embargo, transmitir bloques grandes de datos binarios como texto es el método menos eficaz para codificar mensajes XML.</span><span class="sxs-lookup"><span data-stu-id="d2097-150">However, transmitting large blocks of binary data as text is the least efficient method for encoding XML messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d2097-151">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d2097-151">Example</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="211"
                     maxWritePoolSize="2132"
                     messageVersion="Soap12Addressing10"
                     textEncoding="utf-8" />
```  
  
## <a name="see-also"></a><span data-ttu-id="d2097-152">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d2097-152">See also</span></span>

- <xref:System.ServiceModel.Configuration.TextMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>
- [<span data-ttu-id="d2097-153">Elección de un codificador de mensajes</span><span class="sxs-lookup"><span data-stu-id="d2097-153">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="d2097-154">Codificación de mensajes</span><span class="sxs-lookup"><span data-stu-id="d2097-154">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="d2097-155">Enlaces</span><span class="sxs-lookup"><span data-stu-id="d2097-155">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="d2097-156">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="d2097-156">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="d2097-157">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="d2097-157">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
