---
title: '&lt;binaryMessageEncoding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e4ae3cd4-6b67-4ce1-af4b-9400e0a38dba
caps.latest.revision: "14"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 11d819d5d6302da309dd3e4ce674110c8419978f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltbinarymessageencodinggt"></a><span data-ttu-id="a0abf-102">&lt;binaryMessageEncoding&gt;</span><span class="sxs-lookup"><span data-stu-id="a0abf-102">&lt;binaryMessageEncoding&gt;</span></span>
<span data-ttu-id="a0abf-103">Define un codificador del mensaje binario que codifica los mensajes de la Windows Communication Foundation (WCF) en binario en la conexión.</span><span class="sxs-lookup"><span data-stu-id="a0abf-103">Defines a binary message encoder that encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span>  
  
 <span data-ttu-id="a0abf-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="a0abf-104">\<system.serviceModel></span></span>  
<span data-ttu-id="a0abf-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="a0abf-105">\<bindings></span></span>  
<span data-ttu-id="a0abf-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="a0abf-106">\<customBinding></span></span>  
<span data-ttu-id="a0abf-107">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="a0abf-107">\<binding></span></span>  
<span data-ttu-id="a0abf-108">\<binaryMessageEncoding ></span><span class="sxs-lookup"><span data-stu-id="a0abf-108">\<binaryMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0abf-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a0abf-109">Syntax</span></span>  
  
```xml  
<binaryMessageEncoding   
      maxReadPoolSize="Integer"  
   maxSessionSize="Integer"   
   maxWritePoolSize="Integer"   messageVersion="Soap11Addressing10/Soap12Addressing10" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a0abf-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a0abf-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a0abf-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a0abf-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a0abf-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="a0abf-112">Attributes</span></span>  
  
|<span data-ttu-id="a0abf-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="a0abf-113">Attribute</span></span>|<span data-ttu-id="a0abf-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="a0abf-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a0abf-115">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="a0abf-115">maxReadPoolSize</span></span>|<span data-ttu-id="a0abf-116">Entero que define cuántos mensajes pueden leerse simultáneamente sin asignar nuevos lectores.</span><span class="sxs-lookup"><span data-stu-id="a0abf-116">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="a0abf-117">Los tamaños de grupo más grandes hacen que el sistema sea más tolerante a picos de actividad a costa de un espacio de trabajo mayor.</span><span class="sxs-lookup"><span data-stu-id="a0abf-117">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="a0abf-118">El valor predeterminado es 64.</span><span class="sxs-lookup"><span data-stu-id="a0abf-118">The default is 64.</span></span>|  
|<span data-ttu-id="a0abf-119">maxSessionSize</span><span class="sxs-lookup"><span data-stu-id="a0abf-119">maxSessionSize</span></span>|<span data-ttu-id="a0abf-120">Un entero positivo que establece el tamaño, en bytes, del búfer utilizado para codificar.</span><span class="sxs-lookup"><span data-stu-id="a0abf-120">A positive integer that sets the size, in bytes, of the buffer used for encoding.</span></span> <span data-ttu-id="a0abf-121">Un búfer mayor aumenta la velocidad de codificación a costa del tamaño del espacio de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a0abf-121">A larger buffer increases encoding speed at the expense of the size of the working set.</span></span> <span data-ttu-id="a0abf-122">El valor predeterminado es 2048.</span><span class="sxs-lookup"><span data-stu-id="a0abf-122">The default is 2048.</span></span>|  
|<span data-ttu-id="a0abf-123">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="a0abf-123">maxWritePoolSize</span></span>|<span data-ttu-id="a0abf-124">Entero que define cuántos mensajes pueden enviarse simultáneamente sin asignar nuevos escritores.</span><span class="sxs-lookup"><span data-stu-id="a0abf-124">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="a0abf-125">Los tamaños de grupo más grandes hacen que el sistema sea más tolerante a picos de actividad a costa de un espacio de trabajo mayor.</span><span class="sxs-lookup"><span data-stu-id="a0abf-125">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="a0abf-126">El valor predeterminado es 16.</span><span class="sxs-lookup"><span data-stu-id="a0abf-126">The default is 16.</span></span>|  
|<span data-ttu-id="a0abf-127">messageVersion</span><span class="sxs-lookup"><span data-stu-id="a0abf-127">messageVersion</span></span>|<span data-ttu-id="a0abf-128">Especifica las versiones del mensaje SOAP y de WS-Addressing que se usan o se esperan.</span><span class="sxs-lookup"><span data-stu-id="a0abf-128">Specifies the SOAP message and WS-Addressing versions that are used or expected.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a0abf-129">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a0abf-129">Child Elements</span></span>  
  
|<span data-ttu-id="a0abf-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="a0abf-130">Element</span></span>|<span data-ttu-id="a0abf-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="a0abf-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a0abf-132">\<readerQuotas ></span><span class="sxs-lookup"><span data-stu-id="a0abf-132">\<readerQuotas></span></span>](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="a0abf-133">Define las restricciones en la complejidad de los mensajes SOAP que pueden ser procesados por los puntos de conexión configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="a0abf-133">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="a0abf-134">Este elemento es del tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="a0abf-134">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a0abf-135">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a0abf-135">Parent Elements</span></span>  
  
|<span data-ttu-id="a0abf-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="a0abf-136">Element</span></span>|<span data-ttu-id="a0abf-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="a0abf-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a0abf-138">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="a0abf-138">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="a0abf-139">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="a0abf-139">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a0abf-140">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a0abf-140">Remarks</span></span>  
 <span data-ttu-id="a0abf-141">La codificación es el proceso de transformación de un mensaje en una secuencia de bytes.</span><span class="sxs-lookup"><span data-stu-id="a0abf-141">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="a0abf-142">La descodificación es el proceso inverso.</span><span class="sxs-lookup"><span data-stu-id="a0abf-142">Decoding is the reverse process.</span></span> <span data-ttu-id="a0abf-143">Windows Communication Foundation (WCF) incluye tres tipos de codificación para los mensajes SOAP: Texto, Binario y Mecanismo de optimización de transmisión del mensaje (MTOM).</span><span class="sxs-lookup"><span data-stu-id="a0abf-143">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="a0abf-144">El elemento `binaryMessageEncoding` especifica el formato binario de .NET para XML y tiene las opciones para especificar la codificación de caracteres, así como la versión de SOAP y WS-Addressing que se va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="a0abf-144">The `binaryMessageEncoding` element specifies the .NET Binary Format for XML and has options to specify the character encoding and the SOAP and WS-Addressing version to be used.</span></span> <span data-ttu-id="a0abf-145">El codificador del mensaje binario codifica los mensajes de Windows Communication Foundation (WCF) en binario en la conexión.</span><span class="sxs-lookup"><span data-stu-id="a0abf-145">The binary message encoder encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span> <span data-ttu-id="a0abf-146">Aunque esta codificación realiza transmisiones muy rápidas de mensajes, la interoperabilidad basada en estándares WS-* se pierde.</span><span class="sxs-lookup"><span data-stu-id="a0abf-146">While this encoding results in very fast transmission of messages, interoperability based on the WS-* standards is lost.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a0abf-147">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a0abf-147">Example</span></span>  
  
```xml  
<binaryMessageEncoding maxReadPoolSize="211"  
   maxWritePoolSize="2132"  
   maxSessionSize="3141" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="a0abf-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="a0abf-148">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.BinaryMessageEncodingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>  
 <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>  
 [<span data-ttu-id="a0abf-149">Codificación de mensajes</span><span class="sxs-lookup"><span data-stu-id="a0abf-149">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)  
 [<span data-ttu-id="a0abf-150">Elegir un codificador de mensajes</span><span class="sxs-lookup"><span data-stu-id="a0abf-150">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 [<span data-ttu-id="a0abf-151">Enlaces</span><span class="sxs-lookup"><span data-stu-id="a0abf-151">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="a0abf-152">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="a0abf-152">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="a0abf-153">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="a0abf-153">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="a0abf-154">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="a0abf-154">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
