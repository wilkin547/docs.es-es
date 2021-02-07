---
description: 'Más información acerca de: <mtomMessageEncoding>'
title: <mtomMessageEncoding>
ms.date: 03/30/2017
ms.assetid: 7865d171-cd1e-430a-8421-39cc13541d1b
ms.openlocfilehash: 37ac0be5f3de84a4c310b8ec2a09ed6f3c4def56
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99684118"
---
# \<mtomMessageEncoding>

<span data-ttu-id="258a9-102">Especifica la codificación y la versión del mensaje utilizada para los mensajes basados en el mecanismo de optimización de la transmisión de mensajes (MTOM) SOAP.</span><span class="sxs-lookup"><span data-stu-id="258a9-102">Specifies the encoding and message versioning used for SOAP Message Transmission Optimization Mechanism (MTOM) based messages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mtomMessageEncoding>**  
  
## <a name="syntax"></a><span data-ttu-id="258a9-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="258a9-103">Syntax</span></span>  
  
```xml  
<mtomMessageEncoding maxBufferSize="Integer"
                     maxReadPoolSize="Integer"
                     maxWritePoolSize="Integer"
                     messageVersion="Soap11Addressing1/Soap12Addressing10"
                     writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="258a9-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="258a9-104">Attributes and Elements</span></span>  

 <span data-ttu-id="258a9-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="258a9-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="258a9-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="258a9-106">Attributes</span></span>  
  
|<span data-ttu-id="258a9-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="258a9-107">Attribute</span></span>|<span data-ttu-id="258a9-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="258a9-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="258a9-109">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="258a9-109">maxBufferSize</span></span>|<span data-ttu-id="258a9-110">Un entero que especifica el tamaño máximo del búfer que se puede utilizar.</span><span class="sxs-lookup"><span data-stu-id="258a9-110">An integer that specifies the maximum size of the buffer that can be used.</span></span>|  
|<span data-ttu-id="258a9-111">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="258a9-111">maxReadPoolSize</span></span>|<span data-ttu-id="258a9-112">Un entero que especifica cuántos mensajes pueden leerse simultáneamente sin asignar nuevos lectores.</span><span class="sxs-lookup"><span data-stu-id="258a9-112">An integer that specifies how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="258a9-113">Los tamaños de grupo más grandes hacen que el sistema sea más tolerante a picos de actividad a costa de un espacio de trabajo mayor.</span><span class="sxs-lookup"><span data-stu-id="258a9-113">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="258a9-114">El valor predeterminado es 64.</span><span class="sxs-lookup"><span data-stu-id="258a9-114">The default is 64.</span></span>|  
|<span data-ttu-id="258a9-115">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="258a9-115">maxWritePoolSize</span></span>|<span data-ttu-id="258a9-116">Un entero que especifica cuántos mensajes pueden enviarse simultáneamente sin asignar nuevos escritores.</span><span class="sxs-lookup"><span data-stu-id="258a9-116">An integer that specifies how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="258a9-117">Los tamaños de grupo más grandes hacen que el sistema sea más tolerante a picos de actividad a costa de un espacio de trabajo mayor.</span><span class="sxs-lookup"><span data-stu-id="258a9-117">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="258a9-118">El valor predeterminado es 16.</span><span class="sxs-lookup"><span data-stu-id="258a9-118">The default is 16.</span></span>|  
|<span data-ttu-id="258a9-119">messageVersion</span><span class="sxs-lookup"><span data-stu-id="258a9-119">messageVersion</span></span>|<span data-ttu-id="258a9-120">Especifica la versión SOAP de los mensajes enviados utilizando el enlace.</span><span class="sxs-lookup"><span data-stu-id="258a9-120">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="258a9-121">Los valores válidos son</span><span class="sxs-lookup"><span data-stu-id="258a9-121">Valid values are</span></span><br /><br /> <span data-ttu-id="258a9-122">- Soap11Addressing1</span><span class="sxs-lookup"><span data-stu-id="258a9-122">-   Soap11Addressing1</span></span><br /><span data-ttu-id="258a9-123">- Soap12Addressing10</span><span class="sxs-lookup"><span data-stu-id="258a9-123">-   Soap12Addressing10</span></span><br /><br /> <span data-ttu-id="258a9-124">El valor predeterminado es Soap12Addressing10.</span><span class="sxs-lookup"><span data-stu-id="258a9-124">The default is Soap12Addressing10.</span></span> <span data-ttu-id="258a9-125">Este atributo es del tipo <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="258a9-125">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
|<span data-ttu-id="258a9-126">writeEncoding</span><span class="sxs-lookup"><span data-stu-id="258a9-126">writeEncoding</span></span>|<span data-ttu-id="258a9-127">Especifica el codificador del juego de caracteres que se va a usar para emitir los mensajes en el enlace.</span><span class="sxs-lookup"><span data-stu-id="258a9-127">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="258a9-128">Los valores válidos son</span><span class="sxs-lookup"><span data-stu-id="258a9-128">Valid values are</span></span><br /><br /> <span data-ttu-id="258a9-129">-UnicodeFffeTextEncoding: codificación Unicode BigEndian</span><span class="sxs-lookup"><span data-stu-id="258a9-129">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding</span></span><br /><span data-ttu-id="258a9-130">-Utf16TextEncoding: codificación Unicode</span><span class="sxs-lookup"><span data-stu-id="258a9-130">-   Utf16TextEncoding: Unicode encoding</span></span><br /><span data-ttu-id="258a9-131">-Utf8TextEncoding: codificación de 8 bits</span><span class="sxs-lookup"><span data-stu-id="258a9-131">-   Utf8TextEncoding: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="258a9-132">El valor predeterminado es Utf8TextEncoding.</span><span class="sxs-lookup"><span data-stu-id="258a9-132">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="258a9-133">Este atributo es del tipo <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="258a9-133">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="258a9-134">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="258a9-134">Child Elements</span></span>  
  
|<span data-ttu-id="258a9-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="258a9-135">Element</span></span>|<span data-ttu-id="258a9-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="258a9-136">Description</span></span>|  
|-------------|-----------------|  
|[\<readerQuotas>](/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="258a9-137">Define las restricciones en la complejidad de los mensajes SOAP que pueden ser procesados por los puntos de conexión configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="258a9-137">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="258a9-138">Este elemento es del tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="258a9-138">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="258a9-139">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="258a9-139">Parent Elements</span></span>  
  
|<span data-ttu-id="258a9-140">Elemento</span><span class="sxs-lookup"><span data-stu-id="258a9-140">Element</span></span>|<span data-ttu-id="258a9-141">Descripción</span><span class="sxs-lookup"><span data-stu-id="258a9-141">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="258a9-142">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="258a9-142">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="258a9-143">Observaciones</span><span class="sxs-lookup"><span data-stu-id="258a9-143">Remarks</span></span>  

 <span data-ttu-id="258a9-144">La codificación es el proceso de transformación de un mensaje en una secuencia de bytes.</span><span class="sxs-lookup"><span data-stu-id="258a9-144">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="258a9-145">La descodificación es el proceso inverso.</span><span class="sxs-lookup"><span data-stu-id="258a9-145">Decoding is the reverse process.</span></span> <span data-ttu-id="258a9-146">Windows Communication Foundation (WCF) incluye tres tipos de codificación para los mensajes SOAP: Texto, Binario y Mecanismo de optimización de transmisión del mensaje (MTOM).</span><span class="sxs-lookup"><span data-stu-id="258a9-146">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="258a9-147">El elemento `MtomMessageEncoding` especifica la codificación de caracteres y control de versión de mensajes y otros valores usados para los mensajes que utilizan una codificación MTOM (mecanismo de optimización de transmisión de mensajes).</span><span class="sxs-lookup"><span data-stu-id="258a9-147">The `MtomMessageEncoding` element specifies the character encoding and message versioning and other settings used for messages using a Message Transmission Optimization Mechanism (MTOM) encoding.</span></span> <span data-ttu-id="258a9-148">MTOM es una tecnología eficaz para la transmisión de datos binarios en mensajes de WCF.</span><span class="sxs-lookup"><span data-stu-id="258a9-148">MTOM is an efficient technology for transmitting binary data in WCF messages.</span></span> <span data-ttu-id="258a9-149">El codificador MTOM intenta crear una balanza entre la eficacia y la interoperabilidad.</span><span class="sxs-lookup"><span data-stu-id="258a9-149">The MTOM encoder attempts to create a balance between efficiency and interoperability.</span></span> <span data-ttu-id="258a9-150">El codificador MTOM transmite la mayoría del XML en formato de texto, pero optimiza los bloques grandes de datos binarios transmitiéndolos como son, sin convertirlos a su formato codificado base64.</span><span class="sxs-lookup"><span data-stu-id="258a9-150">The MTOM encoding transmits most XML in textual form, but optimizes large blocks of binary data by transmitting them as-is, without conversion to their base64 encoded format.</span></span>  
  
## <a name="example"></a><span data-ttu-id="258a9-151">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="258a9-151">Example</span></span>  
  
```xml  
<mtomMessageEncoding maxReadPoolSize="211"
                     maxWritePoolSize="2132"
                     messageVersion="Soap11Addressing10"
                     textEncoding="utf-8" />
```  
  
## <a name="see-also"></a><span data-ttu-id="258a9-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="258a9-152">See also</span></span>

- <xref:System.ServiceModel.Configuration.MtomMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>
- [<span data-ttu-id="258a9-153">Codificación de mensajes</span><span class="sxs-lookup"><span data-stu-id="258a9-153">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="258a9-154">Elección de un codificador de mensajes</span><span class="sxs-lookup"><span data-stu-id="258a9-154">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="258a9-155">Enlaces</span><span class="sxs-lookup"><span data-stu-id="258a9-155">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="258a9-156">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="258a9-156">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="258a9-157">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="258a9-157">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
