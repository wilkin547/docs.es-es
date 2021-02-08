---
description: 'Más información acerca de: <textMessageEncoding>'
title: <textMessageEncoding>
ms.date: 03/30/2017
ms.assetid: e6d834d0-356e-45eb-b530-bbefbb9ec3f0
ms.openlocfilehash: a8c7820b2e22152850d6d21c5091e328feb7a9f3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786608"
---
# \<textMessageEncoding>

<span data-ttu-id="79c7f-102">Especifica la codificación de caracteres y la versión del mensaje utilizadas para los mensajes XML basados en texto.</span><span class="sxs-lookup"><span data-stu-id="79c7f-102">Specifies the character encoding and message versioning used for text-based XML messages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<textMessageEncoding>**  
  
## <a name="syntax"></a><span data-ttu-id="79c7f-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="79c7f-103">Syntax</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="Integer"
                     maxWritePoolSize="Integer"
                     messageVersion="Soap11Addressing10/Soap12Addressing10"
                     writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="79c7f-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="79c7f-104">Attributes and Elements</span></span>  

 <span data-ttu-id="79c7f-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="79c7f-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="79c7f-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="79c7f-106">Attributes</span></span>  
  
|<span data-ttu-id="79c7f-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="79c7f-107">Attribute</span></span>|<span data-ttu-id="79c7f-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="79c7f-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="79c7f-109">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="79c7f-109">maxReadPoolSize</span></span>|<span data-ttu-id="79c7f-110">Un entero que especifica cuántos mensajes pueden leerse simultáneamente sin asignar nuevos lectores.</span><span class="sxs-lookup"><span data-stu-id="79c7f-110">An integer that specifies how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="79c7f-111">Los tamaños de grupo más grandes hacen que el sistema sea más tolerante a picos de actividad a costa de un espacio de trabajo mayor.</span><span class="sxs-lookup"><span data-stu-id="79c7f-111">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="79c7f-112">El valor predeterminado es 64.</span><span class="sxs-lookup"><span data-stu-id="79c7f-112">The default is 64.</span></span>|  
|<span data-ttu-id="79c7f-113">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="79c7f-113">maxWritePoolSize</span></span>|<span data-ttu-id="79c7f-114">Un entero que especifica cuántos mensajes pueden enviarse simultáneamente sin asignar nuevos escritores.</span><span class="sxs-lookup"><span data-stu-id="79c7f-114">An integer that specifies how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="79c7f-115">Los tamaños de grupo más grandes hacen que el sistema sea más tolerante a picos de actividad a costa de un espacio de trabajo mayor.</span><span class="sxs-lookup"><span data-stu-id="79c7f-115">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="79c7f-116">El valor predeterminado es 16.</span><span class="sxs-lookup"><span data-stu-id="79c7f-116">The default is 16.</span></span>|  
|<span data-ttu-id="79c7f-117">messageVersion</span><span class="sxs-lookup"><span data-stu-id="79c7f-117">messageVersion</span></span>|<span data-ttu-id="79c7f-118">Especifica la versión SOAP de los mensajes enviados utilizando el enlace.</span><span class="sxs-lookup"><span data-stu-id="79c7f-118">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="79c7f-119">Los valores válidos son</span><span class="sxs-lookup"><span data-stu-id="79c7f-119">Valid values are</span></span><br /><br /> <span data-ttu-id="79c7f-120">- Soap11Addressing10</span><span class="sxs-lookup"><span data-stu-id="79c7f-120">-   Soap11Addressing10</span></span><br /><span data-ttu-id="79c7f-121">- Soap12Addressing10</span><span class="sxs-lookup"><span data-stu-id="79c7f-121">-   Soap12Addressing10</span></span><br /><span data-ttu-id="79c7f-122">- Soap11</span><span class="sxs-lookup"><span data-stu-id="79c7f-122">-   Soap11</span></span><br /><span data-ttu-id="79c7f-123">-Soap12</span><span class="sxs-lookup"><span data-stu-id="79c7f-123">-  Soap12</span></span><br /><br /><span data-ttu-id="79c7f-124">El valor predeterminado es Soap12Addressing10.</span><span class="sxs-lookup"><span data-stu-id="79c7f-124">The default is Soap12Addressing10.</span></span> <span data-ttu-id="79c7f-125">Este atributo es del tipo <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="79c7f-125">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
|<span data-ttu-id="79c7f-126">writeEncoding</span><span class="sxs-lookup"><span data-stu-id="79c7f-126">writeEncoding</span></span>|<span data-ttu-id="79c7f-127">Especifica el codificador del juego de caracteres que se va a usar para emitir los mensajes en el enlace.</span><span class="sxs-lookup"><span data-stu-id="79c7f-127">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="79c7f-128">Los valores válidos son</span><span class="sxs-lookup"><span data-stu-id="79c7f-128">Valid values are</span></span><br /><br /> <span data-ttu-id="79c7f-129">-UnicodeFffeTextEncoding: codificación Unicode BigEndian</span><span class="sxs-lookup"><span data-stu-id="79c7f-129">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding</span></span><br /><span data-ttu-id="79c7f-130">-Utf16TextEncoding: codificación Unicode</span><span class="sxs-lookup"><span data-stu-id="79c7f-130">-   Utf16TextEncoding: Unicode encoding</span></span><br /><span data-ttu-id="79c7f-131">-Utf8TextEncoding: codificación de 8 bits</span><span class="sxs-lookup"><span data-stu-id="79c7f-131">-   Utf8TextEncoding: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="79c7f-132">El valor predeterminado es Utf8TextEncoding.</span><span class="sxs-lookup"><span data-stu-id="79c7f-132">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="79c7f-133">Este atributo es del tipo <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="79c7f-133">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="79c7f-134">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="79c7f-134">Child Elements</span></span>  
  
|<span data-ttu-id="79c7f-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="79c7f-135">Element</span></span>|<span data-ttu-id="79c7f-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="79c7f-136">Description</span></span>|  
|-------------|-----------------|  
|[\<readerQuotas>](/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="79c7f-137">Define las restricciones en la complejidad de los mensajes SOAP que pueden ser procesados por los puntos de conexión configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="79c7f-137">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="79c7f-138">Este elemento es del tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="79c7f-138">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="79c7f-139">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="79c7f-139">Parent Elements</span></span>  
  
|<span data-ttu-id="79c7f-140">Elemento</span><span class="sxs-lookup"><span data-stu-id="79c7f-140">Element</span></span>|<span data-ttu-id="79c7f-141">Descripción</span><span class="sxs-lookup"><span data-stu-id="79c7f-141">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="79c7f-142">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="79c7f-142">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="79c7f-143">Observaciones</span><span class="sxs-lookup"><span data-stu-id="79c7f-143">Remarks</span></span>  

 <span data-ttu-id="79c7f-144">La codificación es el proceso de transformación de un mensaje en una secuencia de bytes.</span><span class="sxs-lookup"><span data-stu-id="79c7f-144">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="79c7f-145">La descodificación es el proceso inverso.</span><span class="sxs-lookup"><span data-stu-id="79c7f-145">Decoding is the reverse process.</span></span> <span data-ttu-id="79c7f-146">Windows Communication Foundation (WCF) incluye tres tipos de codificación para los mensajes SOAP: Texto, Binario y Mecanismo de optimización de transmisión del mensaje (MTOM).</span><span class="sxs-lookup"><span data-stu-id="79c7f-146">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="79c7f-147">La codificación de texto representada por el elemento `textMessageEncoding` es el codificador más interoperable, pero el menos eficaz para los mensajes XML.</span><span class="sxs-lookup"><span data-stu-id="79c7f-147">The text encoding represented by the `textMessageEncoding` element is the most interoperable, but the least efficient encoder for XML messages.</span></span>  <span data-ttu-id="79c7f-148">El codificador de texto crea mensajes basados en texto en la conexión.</span><span class="sxs-lookup"><span data-stu-id="79c7f-148">The text encoder creates text-based messages on the wire.</span></span> <span data-ttu-id="79c7f-149">Los mensajes generados por este codificador son adecuados para la interoperabilidad basada en WS - \*.</span><span class="sxs-lookup"><span data-stu-id="79c7f-149">Messages produced by this encoder are suitable for WS-\* based interop.</span></span> <span data-ttu-id="79c7f-150">Un servicio web o un cliente de servicios web, por lo general, pueden entender XML textual.</span><span class="sxs-lookup"><span data-stu-id="79c7f-150">Web service or Web service client can generally understand textual XML.</span></span> <span data-ttu-id="79c7f-151">Sin embargo, transmitir bloques grandes de datos binarios como texto es el método menos eficaz para codificar mensajes XML.</span><span class="sxs-lookup"><span data-stu-id="79c7f-151">However, transmitting large blocks of binary data as text is the least efficient method for encoding XML messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="79c7f-152">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="79c7f-152">Example</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="211"
                     maxWritePoolSize="2132"
                     messageVersion="Soap12Addressing10"
                     textEncoding="utf-8" />
```  
  
## <a name="see-also"></a><span data-ttu-id="79c7f-153">Vea también</span><span class="sxs-lookup"><span data-stu-id="79c7f-153">See also</span></span>

- <xref:System.ServiceModel.Configuration.TextMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>
- [<span data-ttu-id="79c7f-154">Elección de un codificador de mensajes</span><span class="sxs-lookup"><span data-stu-id="79c7f-154">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="79c7f-155">Codificación de mensajes</span><span class="sxs-lookup"><span data-stu-id="79c7f-155">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="79c7f-156">Enlaces</span><span class="sxs-lookup"><span data-stu-id="79c7f-156">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="79c7f-157">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="79c7f-157">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="79c7f-158">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="79c7f-158">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
