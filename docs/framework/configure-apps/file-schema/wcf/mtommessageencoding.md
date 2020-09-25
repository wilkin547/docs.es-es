---
title: <mtomMessageEncoding>
ms.date: 03/30/2017
ms.assetid: 7865d171-cd1e-430a-8421-39cc13541d1b
ms.openlocfilehash: 76b83381849b8519c1b758ef52c6d5c3f682f9b7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204637"
---
# \<mtomMessageEncoding>

<span data-ttu-id="369bf-101">Especifica la codificación y la versión del mensaje utilizada para los mensajes basados en el mecanismo de optimización de la transmisión de mensajes (MTOM) SOAP.</span><span class="sxs-lookup"><span data-stu-id="369bf-101">Specifies the encoding and message versioning used for SOAP Message Transmission Optimization Mechanism (MTOM) based messages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mtomMessageEncoding>**  
  
## <a name="syntax"></a><span data-ttu-id="369bf-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="369bf-102">Syntax</span></span>  
  
```xml  
<mtomMessageEncoding maxBufferSize="Integer"
                     maxReadPoolSize="Integer"
                     maxWritePoolSize="Integer"
                     messageVersion="Soap11Addressing1/Soap12Addressing10"
                     writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="369bf-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="369bf-103">Attributes and Elements</span></span>  

 <span data-ttu-id="369bf-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="369bf-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="369bf-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="369bf-105">Attributes</span></span>  
  
|<span data-ttu-id="369bf-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="369bf-106">Attribute</span></span>|<span data-ttu-id="369bf-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="369bf-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="369bf-108">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="369bf-108">maxBufferSize</span></span>|<span data-ttu-id="369bf-109">Un entero que especifica el tamaño máximo del búfer que se puede utilizar.</span><span class="sxs-lookup"><span data-stu-id="369bf-109">An integer that specifies the maximum size of the buffer that can be used.</span></span>|  
|<span data-ttu-id="369bf-110">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="369bf-110">maxReadPoolSize</span></span>|<span data-ttu-id="369bf-111">Un entero que especifica cuántos mensajes pueden leerse simultáneamente sin asignar nuevos lectores.</span><span class="sxs-lookup"><span data-stu-id="369bf-111">An integer that specifies how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="369bf-112">Los tamaños de grupo más grandes hacen que el sistema sea más tolerante a picos de actividad a costa de un espacio de trabajo mayor.</span><span class="sxs-lookup"><span data-stu-id="369bf-112">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="369bf-113">El valor predeterminado es 64.</span><span class="sxs-lookup"><span data-stu-id="369bf-113">The default is 64.</span></span>|  
|<span data-ttu-id="369bf-114">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="369bf-114">maxWritePoolSize</span></span>|<span data-ttu-id="369bf-115">Un entero que especifica cuántos mensajes pueden enviarse simultáneamente sin asignar nuevos escritores.</span><span class="sxs-lookup"><span data-stu-id="369bf-115">An integer that specifies how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="369bf-116">Los tamaños de grupo más grandes hacen que el sistema sea más tolerante a picos de actividad a costa de un espacio de trabajo mayor.</span><span class="sxs-lookup"><span data-stu-id="369bf-116">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="369bf-117">El valor predeterminado es 16.</span><span class="sxs-lookup"><span data-stu-id="369bf-117">The default is 16.</span></span>|  
|<span data-ttu-id="369bf-118">messageVersion</span><span class="sxs-lookup"><span data-stu-id="369bf-118">messageVersion</span></span>|<span data-ttu-id="369bf-119">Especifica la versión SOAP de los mensajes enviados utilizando el enlace.</span><span class="sxs-lookup"><span data-stu-id="369bf-119">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="369bf-120">Los valores válidos son</span><span class="sxs-lookup"><span data-stu-id="369bf-120">Valid values are</span></span><br /><br /> <span data-ttu-id="369bf-121">- Soap11Addressing1</span><span class="sxs-lookup"><span data-stu-id="369bf-121">-   Soap11Addressing1</span></span><br /><span data-ttu-id="369bf-122">- Soap12Addressing10</span><span class="sxs-lookup"><span data-stu-id="369bf-122">-   Soap12Addressing10</span></span><br /><br /> <span data-ttu-id="369bf-123">El valor predeterminado es Soap12Addressing10.</span><span class="sxs-lookup"><span data-stu-id="369bf-123">The default is Soap12Addressing10.</span></span> <span data-ttu-id="369bf-124">Este atributo es del tipo <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="369bf-124">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
|<span data-ttu-id="369bf-125">writeEncoding</span><span class="sxs-lookup"><span data-stu-id="369bf-125">writeEncoding</span></span>|<span data-ttu-id="369bf-126">Especifica el codificador del juego de caracteres que se va a usar para emitir los mensajes en el enlace.</span><span class="sxs-lookup"><span data-stu-id="369bf-126">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="369bf-127">Los valores válidos son</span><span class="sxs-lookup"><span data-stu-id="369bf-127">Valid values are</span></span><br /><br /> <span data-ttu-id="369bf-128">-UnicodeFffeTextEncoding: codificación Unicode BigEndian</span><span class="sxs-lookup"><span data-stu-id="369bf-128">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding</span></span><br /><span data-ttu-id="369bf-129">-Utf16TextEncoding: codificación Unicode</span><span class="sxs-lookup"><span data-stu-id="369bf-129">-   Utf16TextEncoding: Unicode encoding</span></span><br /><span data-ttu-id="369bf-130">-Utf8TextEncoding: codificación de 8 bits</span><span class="sxs-lookup"><span data-stu-id="369bf-130">-   Utf8TextEncoding: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="369bf-131">El valor predeterminado es Utf8TextEncoding.</span><span class="sxs-lookup"><span data-stu-id="369bf-131">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="369bf-132">Este atributo es del tipo <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="369bf-132">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="369bf-133">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="369bf-133">Child Elements</span></span>  
  
|<span data-ttu-id="369bf-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="369bf-134">Element</span></span>|<span data-ttu-id="369bf-135">Descripción</span><span class="sxs-lookup"><span data-stu-id="369bf-135">Description</span></span>|  
|-------------|-----------------|  
|[\<readerQuotas>](/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="369bf-136">Define las restricciones en la complejidad de los mensajes SOAP que pueden ser procesados por los puntos de conexión configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="369bf-136">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="369bf-137">Este elemento es del tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="369bf-137">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="369bf-138">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="369bf-138">Parent Elements</span></span>  
  
|<span data-ttu-id="369bf-139">Elemento</span><span class="sxs-lookup"><span data-stu-id="369bf-139">Element</span></span>|<span data-ttu-id="369bf-140">Descripción</span><span class="sxs-lookup"><span data-stu-id="369bf-140">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="369bf-141">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="369bf-141">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="369bf-142">Observaciones</span><span class="sxs-lookup"><span data-stu-id="369bf-142">Remarks</span></span>  

 <span data-ttu-id="369bf-143">La codificación es el proceso de transformación de un mensaje en una secuencia de bytes.</span><span class="sxs-lookup"><span data-stu-id="369bf-143">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="369bf-144">La descodificación es el proceso inverso.</span><span class="sxs-lookup"><span data-stu-id="369bf-144">Decoding is the reverse process.</span></span> <span data-ttu-id="369bf-145">Windows Communication Foundation (WCF) incluye tres tipos de codificación para los mensajes SOAP: Texto, Binario y Mecanismo de optimización de transmisión del mensaje (MTOM).</span><span class="sxs-lookup"><span data-stu-id="369bf-145">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="369bf-146">El elemento `MtomMessageEncoding` especifica la codificación de caracteres y control de versión de mensajes y otros valores usados para los mensajes que utilizan una codificación MTOM (mecanismo de optimización de transmisión de mensajes).</span><span class="sxs-lookup"><span data-stu-id="369bf-146">The `MtomMessageEncoding` element specifies the character encoding and message versioning and other settings used for messages using a Message Transmission Optimization Mechanism (MTOM) encoding.</span></span> <span data-ttu-id="369bf-147">MTOM es una tecnología eficaz para la transmisión de datos binarios en mensajes de WCF.</span><span class="sxs-lookup"><span data-stu-id="369bf-147">MTOM is an efficient technology for transmitting binary data in WCF messages.</span></span> <span data-ttu-id="369bf-148">El codificador MTOM intenta crear una balanza entre la eficacia y la interoperabilidad.</span><span class="sxs-lookup"><span data-stu-id="369bf-148">The MTOM encoder attempts to create a balance between efficiency and interoperability.</span></span> <span data-ttu-id="369bf-149">El codificador MTOM transmite la mayoría del XML en formato de texto, pero optimiza los bloques grandes de datos binarios transmitiéndolos como son, sin convertirlos a su formato codificado base64.</span><span class="sxs-lookup"><span data-stu-id="369bf-149">The MTOM encoding transmits most XML in textual form, but optimizes large blocks of binary data by transmitting them as-is, without conversion to their base64 encoded format.</span></span>  
  
## <a name="example"></a><span data-ttu-id="369bf-150">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="369bf-150">Example</span></span>  
  
```xml  
<mtomMessageEncoding maxReadPoolSize="211"
                     maxWritePoolSize="2132"
                     messageVersion="Soap11Addressing10"
                     textEncoding="utf-8" />
```  
  
## <a name="see-also"></a><span data-ttu-id="369bf-151">Consulte también</span><span class="sxs-lookup"><span data-stu-id="369bf-151">See also</span></span>

- <xref:System.ServiceModel.Configuration.MtomMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>
- [<span data-ttu-id="369bf-152">Codificación de mensajes</span><span class="sxs-lookup"><span data-stu-id="369bf-152">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="369bf-153">Elección de un codificador de mensajes</span><span class="sxs-lookup"><span data-stu-id="369bf-153">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="369bf-154">Enlaces</span><span class="sxs-lookup"><span data-stu-id="369bf-154">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="369bf-155">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="369bf-155">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="369bf-156">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="369bf-156">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
