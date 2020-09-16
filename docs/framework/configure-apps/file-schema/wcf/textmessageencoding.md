---
title: <textMessageEncoding>
ms.date: 03/30/2017
ms.assetid: e6d834d0-356e-45eb-b530-bbefbb9ec3f0
ms.openlocfilehash: c5cd8e9e2002f44fd9feebdc6bb7ede023de459a
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556452"
---
# \<textMessageEncoding>
<span data-ttu-id="99ae0-101">Especifica la codificación de caracteres y la versión del mensaje utilizadas para los mensajes XML basados en texto.</span><span class="sxs-lookup"><span data-stu-id="99ae0-101">Specifies the character encoding and message versioning used for text-based XML messages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<textMessageEncoding>**  
  
## <a name="syntax"></a><span data-ttu-id="99ae0-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="99ae0-102">Syntax</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="Integer"
                     maxWritePoolSize="Integer"
                     messageVersion="Soap11Addressing10/Soap12Addressing10"
                     writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="99ae0-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="99ae0-103">Attributes and Elements</span></span>  
 <span data-ttu-id="99ae0-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="99ae0-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="99ae0-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="99ae0-105">Attributes</span></span>  
  
|<span data-ttu-id="99ae0-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="99ae0-106">Attribute</span></span>|<span data-ttu-id="99ae0-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="99ae0-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="99ae0-108">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="99ae0-108">maxReadPoolSize</span></span>|<span data-ttu-id="99ae0-109">Un entero que especifica cuántos mensajes pueden leerse simultáneamente sin asignar nuevos lectores.</span><span class="sxs-lookup"><span data-stu-id="99ae0-109">An integer that specifies how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="99ae0-110">Los tamaños de grupo más grandes hacen que el sistema sea más tolerante a picos de actividad a costa de un espacio de trabajo mayor.</span><span class="sxs-lookup"><span data-stu-id="99ae0-110">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="99ae0-111">El valor predeterminado es 64.</span><span class="sxs-lookup"><span data-stu-id="99ae0-111">The default is 64.</span></span>|  
|<span data-ttu-id="99ae0-112">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="99ae0-112">maxWritePoolSize</span></span>|<span data-ttu-id="99ae0-113">Un entero que especifica cuántos mensajes pueden enviarse simultáneamente sin asignar nuevos escritores.</span><span class="sxs-lookup"><span data-stu-id="99ae0-113">An integer that specifies how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="99ae0-114">Los tamaños de grupo más grandes hacen que el sistema sea más tolerante a picos de actividad a costa de un espacio de trabajo mayor.</span><span class="sxs-lookup"><span data-stu-id="99ae0-114">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="99ae0-115">El valor predeterminado es 16.</span><span class="sxs-lookup"><span data-stu-id="99ae0-115">The default is 16.</span></span>|  
|<span data-ttu-id="99ae0-116">messageVersion</span><span class="sxs-lookup"><span data-stu-id="99ae0-116">messageVersion</span></span>|<span data-ttu-id="99ae0-117">Especifica la versión SOAP de los mensajes enviados utilizando el enlace.</span><span class="sxs-lookup"><span data-stu-id="99ae0-117">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="99ae0-118">Los valores válidos son</span><span class="sxs-lookup"><span data-stu-id="99ae0-118">Valid values are</span></span><br /><br /> <span data-ttu-id="99ae0-119">- Soap11Addressing10</span><span class="sxs-lookup"><span data-stu-id="99ae0-119">-   Soap11Addressing10</span></span><br /><span data-ttu-id="99ae0-120">- Soap12Addressing10</span><span class="sxs-lookup"><span data-stu-id="99ae0-120">-   Soap12Addressing10</span></span><br /><span data-ttu-id="99ae0-121">- Soap11</span><span class="sxs-lookup"><span data-stu-id="99ae0-121">-   Soap11</span></span><br /><span data-ttu-id="99ae0-122">-Soap12</span><span class="sxs-lookup"><span data-stu-id="99ae0-122">-  Soap12</span></span><br /><br /><span data-ttu-id="99ae0-123">El valor predeterminado es Soap12Addressing10.</span><span class="sxs-lookup"><span data-stu-id="99ae0-123">The default is Soap12Addressing10.</span></span> <span data-ttu-id="99ae0-124">Este atributo es del tipo <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="99ae0-124">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
|<span data-ttu-id="99ae0-125">writeEncoding</span><span class="sxs-lookup"><span data-stu-id="99ae0-125">writeEncoding</span></span>|<span data-ttu-id="99ae0-126">Especifica el codificador del juego de caracteres que se va a usar para emitir los mensajes en el enlace.</span><span class="sxs-lookup"><span data-stu-id="99ae0-126">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="99ae0-127">Los valores válidos son</span><span class="sxs-lookup"><span data-stu-id="99ae0-127">Valid values are</span></span><br /><br /> <span data-ttu-id="99ae0-128">-UnicodeFffeTextEncoding: codificación Unicode BigEndian</span><span class="sxs-lookup"><span data-stu-id="99ae0-128">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding</span></span><br /><span data-ttu-id="99ae0-129">-Utf16TextEncoding: codificación Unicode</span><span class="sxs-lookup"><span data-stu-id="99ae0-129">-   Utf16TextEncoding: Unicode encoding</span></span><br /><span data-ttu-id="99ae0-130">-Utf8TextEncoding: codificación de 8 bits</span><span class="sxs-lookup"><span data-stu-id="99ae0-130">-   Utf8TextEncoding: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="99ae0-131">El valor predeterminado es Utf8TextEncoding.</span><span class="sxs-lookup"><span data-stu-id="99ae0-131">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="99ae0-132">Este atributo es del tipo <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="99ae0-132">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="99ae0-133">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="99ae0-133">Child Elements</span></span>  
  
|<span data-ttu-id="99ae0-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="99ae0-134">Element</span></span>|<span data-ttu-id="99ae0-135">Descripción</span><span class="sxs-lookup"><span data-stu-id="99ae0-135">Description</span></span>|  
|-------------|-----------------|  
|[\<readerQuotas>](/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="99ae0-136">Define las restricciones en la complejidad de los mensajes SOAP que pueden ser procesados por los puntos de conexión configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="99ae0-136">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="99ae0-137">Este elemento es del tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="99ae0-137">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="99ae0-138">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="99ae0-138">Parent Elements</span></span>  
  
|<span data-ttu-id="99ae0-139">Elemento</span><span class="sxs-lookup"><span data-stu-id="99ae0-139">Element</span></span>|<span data-ttu-id="99ae0-140">Descripción</span><span class="sxs-lookup"><span data-stu-id="99ae0-140">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="99ae0-141">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="99ae0-141">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="99ae0-142">Comentarios</span><span class="sxs-lookup"><span data-stu-id="99ae0-142">Remarks</span></span>  
 <span data-ttu-id="99ae0-143">La codificación es el proceso de transformación de un mensaje en una secuencia de bytes.</span><span class="sxs-lookup"><span data-stu-id="99ae0-143">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="99ae0-144">La descodificación es el proceso inverso.</span><span class="sxs-lookup"><span data-stu-id="99ae0-144">Decoding is the reverse process.</span></span> <span data-ttu-id="99ae0-145">Windows Communication Foundation (WCF) incluye tres tipos de codificación para los mensajes SOAP: Texto, Binario y Mecanismo de optimización de transmisión del mensaje (MTOM).</span><span class="sxs-lookup"><span data-stu-id="99ae0-145">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="99ae0-146">La codificación de texto representada por el elemento `textMessageEncoding` es el codificador más interoperable, pero el menos eficaz para los mensajes XML.</span><span class="sxs-lookup"><span data-stu-id="99ae0-146">The text encoding represented by the `textMessageEncoding` element is the most interoperable, but the least efficient encoder for XML messages.</span></span>  <span data-ttu-id="99ae0-147">El codificador de texto crea mensajes basados en texto en la conexión.</span><span class="sxs-lookup"><span data-stu-id="99ae0-147">The text encoder creates text-based messages on the wire.</span></span> <span data-ttu-id="99ae0-148">Los mensajes generados por este codificador son adecuados para la interoperabilidad basada en WS - \*.</span><span class="sxs-lookup"><span data-stu-id="99ae0-148">Messages produced by this encoder are suitable for WS-\* based interop.</span></span> <span data-ttu-id="99ae0-149">Un servicio web o un cliente de servicios web, por lo general, pueden entender XML textual.</span><span class="sxs-lookup"><span data-stu-id="99ae0-149">Web service or Web service client can generally understand textual XML.</span></span> <span data-ttu-id="99ae0-150">Sin embargo, transmitir bloques grandes de datos binarios como texto es el método menos eficaz para codificar mensajes XML.</span><span class="sxs-lookup"><span data-stu-id="99ae0-150">However, transmitting large blocks of binary data as text is the least efficient method for encoding XML messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="99ae0-151">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="99ae0-151">Example</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="211"
                     maxWritePoolSize="2132"
                     messageVersion="Soap12Addressing10"
                     textEncoding="utf-8" />
```  
  
## <a name="see-also"></a><span data-ttu-id="99ae0-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="99ae0-152">See also</span></span>

- <xref:System.ServiceModel.Configuration.TextMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>
- [<span data-ttu-id="99ae0-153">Elección de un codificador de mensajes</span><span class="sxs-lookup"><span data-stu-id="99ae0-153">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="99ae0-154">Codificación de mensajes</span><span class="sxs-lookup"><span data-stu-id="99ae0-154">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="99ae0-155">Enlaces</span><span class="sxs-lookup"><span data-stu-id="99ae0-155">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="99ae0-156">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="99ae0-156">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="99ae0-157">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="99ae0-157">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
