---
title: '&lt;webMessageEncoding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 892ca485-e21a-4a44-8e40-633161ef6796
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e6257721f8b85296d4da28cc036c946f6357c11b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltwebmessageencodinggt"></a><span data-ttu-id="cc460-102">&lt;webMessageEncoding&gt;</span><span class="sxs-lookup"><span data-stu-id="cc460-102">&lt;webMessageEncoding&gt;</span></span>
<span data-ttu-id="cc460-103">Habilita texto sin formato XML, las codificaciones de mensajes de JavaScript Object Notation (JSON) y el contenido binario "sin formato" para ser leído y escrito cuando se utiliza en un enlace [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cc460-103">Enables plain-text XML, JavaScript Object Notation (JSON) message encodings and "raw" binary content to be read and written when used in a [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] binding.</span></span>  
  
 <span data-ttu-id="cc460-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="cc460-104">\<system.serviceModel></span></span>  
<span data-ttu-id="cc460-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="cc460-105">\<bindings></span></span>  
<span data-ttu-id="cc460-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="cc460-106">\<customBinding></span></span>  
<span data-ttu-id="cc460-107">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="cc460-107">\<binding></span></span>  
<span data-ttu-id="cc460-108">\<webMessageEncoding ></span><span class="sxs-lookup"><span data-stu-id="cc460-108">\<webMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc460-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cc460-109">Syntax</span></span>  
  
```xml  
<webMessageEncoding   
      maxReadPoolSize="Integer"  
   maxWritePoolSize="Integer"  
  
writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cc460-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="cc460-110">Attributes and Elements</span></span>  
 <span data-ttu-id="cc460-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="cc460-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cc460-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="cc460-112">Attributes</span></span>  
  
|<span data-ttu-id="cc460-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="cc460-113">Attribute</span></span>|<span data-ttu-id="cc460-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="cc460-114">Description</span></span>|  
|---------------|-----------------|  
|`maxReadPoolSize`|<span data-ttu-id="cc460-115">El número de mensajes que se pueden leer simultáneamente sin asignar nuevos lectores.</span><span class="sxs-lookup"><span data-stu-id="cc460-115">The amount of messages that can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="cc460-116">Los tamaños de grupo más grandes hacen que el sistema sea más tolerante a picos de actividad a costa de un espacio de trabajo mayor.</span><span class="sxs-lookup"><span data-stu-id="cc460-116">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="cc460-117">El valor predeterminado es 64 lectores para cada uno de los codificadores internos (texto, JSON, y "sin formato").</span><span class="sxs-lookup"><span data-stu-id="cc460-117">The default is 64 readers for each of the inner encoders (text, JSON, and "raw").</span></span><br /><br /> <span data-ttu-id="cc460-118">Al aumentar este número, se aumenta el consumo de memoria, pero se prepara al codificador para tratar con ráfagas súbitas de mensajes entrantes porque puede utilizar los lectores del grupo ya creados en lugar de tener que crear nuevos.</span><span class="sxs-lookup"><span data-stu-id="cc460-118">Increasing this number increases memory consumption, but prepares the encoder to deal with sudden bursts of incoming messages because it is able to use readers from the pool that are already created instead of creating new ones.</span></span>|  
|`maxWritePoolSize`|<span data-ttu-id="cc460-119">El número de mensajes que se pueden enviar simultáneamente sin asignar nuevos escritores.</span><span class="sxs-lookup"><span data-stu-id="cc460-119">The amount of messages that can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="cc460-120">Los tamaños de grupo más grandes hacen que el sistema sea más tolerante a picos de actividad a costa de un espacio de trabajo mayor.</span><span class="sxs-lookup"><span data-stu-id="cc460-120">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="cc460-121">El valor predeterminado es 16 escritores para cada uno de los codificadores internos (texto, JSON, y "sin formato").</span><span class="sxs-lookup"><span data-stu-id="cc460-121">The default is 16 writers for each of the inner encoders (text, JSON, and "raw").</span></span><br /><br /> <span data-ttu-id="cc460-122">Al aumentar este número, se aumenta el consumo de memoria, pero se prepara al codificador para tratar con ráfagas súbitas de mensajes salientes porque puede utilizar los escritores del grupo ya creados en lugar de tener que crear nuevos.</span><span class="sxs-lookup"><span data-stu-id="cc460-122">Increasing this number increases memory consumption, but prepares the encoder to deal with sudden bursts of outgoing messages because it is able to use writers from the pool that are already created instead of creating new ones.</span></span>|  
|`writeEncoding`|<span data-ttu-id="cc460-123">Especifica el codificador del juego de caracteres que se va a usar para emitir los mensajes en el enlace.</span><span class="sxs-lookup"><span data-stu-id="cc460-123">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="cc460-124">Los valores válidos son:</span><span class="sxs-lookup"><span data-stu-id="cc460-124">Valid values are:</span></span><br /><br /> <span data-ttu-id="cc460-125">-UnicodeFffeTextEncoding: Big-Endian codificación Unicode.</span><span class="sxs-lookup"><span data-stu-id="cc460-125">-   UnicodeFffeTextEncoding: Unicode Big Endian encoding.</span></span><br /><span data-ttu-id="cc460-126">-Utf16TextEncoding: Codificación de Unicode.</span><span class="sxs-lookup"><span data-stu-id="cc460-126">-   Utf16TextEncoding: Unicode encoding.</span></span><br /><span data-ttu-id="cc460-127">-Utf8TextEncoding: codificación de 8 bits.</span><span class="sxs-lookup"><span data-stu-id="cc460-127">-   Utf8TextEncoding: 8-bit encoding.</span></span><br /><br /> <span data-ttu-id="cc460-128">El valor predeterminado es Utf8TextEncoding.</span><span class="sxs-lookup"><span data-stu-id="cc460-128">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="cc460-129">Este atributo es del tipo <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="cc460-129">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cc460-130">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="cc460-130">Child Elements</span></span>  
  
|<span data-ttu-id="cc460-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="cc460-131">Element</span></span>|<span data-ttu-id="cc460-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="cc460-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cc460-133">\<readerQuotas ></span><span class="sxs-lookup"><span data-stu-id="cc460-133">\<readerQuotas></span></span>](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="cc460-134">Define las restricciones en la complejidad de los mensajes SOAP que pueden ser procesados por los puntos de conexión configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="cc460-134">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="cc460-135">Este elemento es del tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="cc460-135">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cc460-136">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="cc460-136">Parent Elements</span></span>  
  
|<span data-ttu-id="cc460-137">Elemento</span><span class="sxs-lookup"><span data-stu-id="cc460-137">Element</span></span>|<span data-ttu-id="cc460-138">Descripción</span><span class="sxs-lookup"><span data-stu-id="cc460-138">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cc460-139">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="cc460-139">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="cc460-140">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="cc460-140">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cc460-141">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cc460-141">Remarks</span></span>  
 <span data-ttu-id="cc460-142">La codificación es el proceso de transformación de un mensaje en una secuencia de bytes.</span><span class="sxs-lookup"><span data-stu-id="cc460-142">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="cc460-143">La descodificación es el proceso inverso.</span><span class="sxs-lookup"><span data-stu-id="cc460-143">Decoding is the reverse process.</span></span> <span data-ttu-id="cc460-144">Estos procesos requieren la especificación de una codificación de caracteres.</span><span class="sxs-lookup"><span data-stu-id="cc460-144">These processes require the specification of a character encoding.</span></span>  
  
 <span data-ttu-id="cc460-145">El elemento `webMessageEncoding` funciona delegando a una serie de codificadores internos para administrar el texto sin formato XML y las codificaciones JSON, así como los datos binarios "sin formato."</span><span class="sxs-lookup"><span data-stu-id="cc460-145">The `webMessageEncoding` element works by delegating to a series of inner encoders to handle the plain-text XML and JSON encodings, and "raw" binary data.</span></span> <span data-ttu-id="cc460-146">Un codificador del mensaje compuesto hace esta delegación.</span><span class="sxs-lookup"><span data-stu-id="cc460-146">This delegation is done by a composite message encoder.</span></span>  
  
 <span data-ttu-id="cc460-147">Este elemento de enlace y su codificador compuesto se utilizan para controlar la codificación en escenarios que no utilizan la mensajería de SOAP utilizada por el elemento `webHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="cc460-147">This binding element and its composite encoder are used to control the encoding in scenarios that do not use SOAP messaging used by the `webHttpBinding` element.</span></span> <span data-ttu-id="cc460-148">Estos escenarios incluyen "Plain Old XML" (POX), Representational State Transfer (REST), Really Simple Syndication (RSS) y Atom syndication, y Asynchronous JavaScript y XML (AJAX).</span><span class="sxs-lookup"><span data-stu-id="cc460-148">These scenarios include "Plain Old XML" (POX), Representational State Transfer (REST), Really Simple Syndication (RSS) and Atom syndication, and Asynchronous JavaScript and XML (AJAX).</span></span> <span data-ttu-id="cc460-149">El codificador del mensaje compuesto no admite SOAP o WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="cc460-149">The composite message encoder does not support SOAP or WS-Addressing.</span></span>  
  
 <span data-ttu-id="cc460-150">El elemento de enlace se puede configurar con una codificación de caracteres de escritura utilizando el atributo `writeEncoding`.</span><span class="sxs-lookup"><span data-stu-id="cc460-150">The binding element can be configured with a write character encoding by using the `writeEncoding` attribute.</span></span> <span data-ttu-id="cc460-151">El valor <xref:System.Text.Encoding> proporcionado especifica el comportamiento en escritura para los casos de texto XML y JSON.</span><span class="sxs-lookup"><span data-stu-id="cc460-151">The supplied <xref:System.Text.Encoding> value specifies the behavior on write for the JSON and Textual XML cases.</span></span> <span data-ttu-id="cc460-152">En lectura, cualquier codificación de mensajes válida y codificación de texto se entenderán.</span><span class="sxs-lookup"><span data-stu-id="cc460-152">On read, any valid message encoding and text encoding is understood.</span></span>  
  
 <span data-ttu-id="cc460-153">`maxReadPoolSize` y `maxWritePoolSize` también se pueden utilizar para establecer el número máximo de lectores y escritores que se van a asignar respectivamente.</span><span class="sxs-lookup"><span data-stu-id="cc460-153">`maxReadPoolSize` and `maxWritePoolSize` can also be used to set the maximum number of readers and writers to be allocated respectively.</span></span> <span data-ttu-id="cc460-154">De forma predeterminada se asignan 64 lectores y 16 escritores.</span><span class="sxs-lookup"><span data-stu-id="cc460-154">By default 64 readers and 16 writers are allocated.</span></span>  
  
 <span data-ttu-id="cc460-155">Restricciones de complejidad predeterminadas también se establecen utilizando el [ \<readerQuotas >](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd) ataques de elemento que se va a proteger contra una clase de denegación de servicio (DOS) que intentan utilizar la complejidad del mensaje para paralizar el proceso de punto de conexión recursos.</span><span class="sxs-lookup"><span data-stu-id="cc460-155">Default complexity constraints are also set using the [\<readerQuotas>](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd) element to protect against a class of denial of service (DOS) attacks that attempt to use message complexity to tie up endpoint processing resources.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cc460-156">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cc460-156">Example</span></span>  
  
```xml  
<webMessageEncoding   
    maxReadPoolSize="256"  
    maxWritePoolSize="128"  
    messageVersion="None"  
    textEncoding="utf-8"   
/>  
```  
  
## <a name="see-also"></a><span data-ttu-id="cc460-157">Vea también</span><span class="sxs-lookup"><span data-stu-id="cc460-157">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WebMessageEncodingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>  
 <xref:System.ServiceModel.Channels.WebMessageEncodingBindingElement>  
 [<span data-ttu-id="cc460-158">Codificación de mensajes</span><span class="sxs-lookup"><span data-stu-id="cc460-158">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)  
 [<span data-ttu-id="cc460-159">Elegir un codificador de mensajes</span><span class="sxs-lookup"><span data-stu-id="cc460-159">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 [<span data-ttu-id="cc460-160">Enlaces</span><span class="sxs-lookup"><span data-stu-id="cc460-160">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="cc460-161">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="cc460-161">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="cc460-162">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="cc460-162">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="cc460-163">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="cc460-163">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
