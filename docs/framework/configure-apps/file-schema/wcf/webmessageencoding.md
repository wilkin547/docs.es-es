---
title: <webMessageEncoding>
ms.date: 03/30/2017
ms.assetid: 892ca485-e21a-4a44-8e40-633161ef6796
ms.openlocfilehash: a1d776730053cd6af3c930a33e13582a8906c4d7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940396"
---
# <a name="webmessageencoding"></a><span data-ttu-id="9bd42-101">\<webMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="9bd42-101">\<webMessageEncoding></span></span>
<span data-ttu-id="9bd42-102">Habilita XML de texto sin formato, codificaciones de mensajes de Notación de objetos JavaScript (JSON) y el contenido binario "sin procesar" que se va a leer y escribir cuando se use en un enlace de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="9bd42-102">Enables plain-text XML, JavaScript Object Notation (JSON) message encodings and "raw" binary content to be read and written when used in a Windows Communication Foundation (WCF) binding.</span></span>  
  
 <span data-ttu-id="9bd42-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="9bd42-103">\<system.serviceModel></span></span>  
<span data-ttu-id="9bd42-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="9bd42-104">\<bindings></span></span>  
<span data-ttu-id="9bd42-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="9bd42-105">\<customBinding></span></span>  
<span data-ttu-id="9bd42-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="9bd42-106">\<binding></span></span>  
<span data-ttu-id="9bd42-107">\<webMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="9bd42-107">\<webMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9bd42-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9bd42-108">Syntax</span></span>  
  
```xml  
<webMessageEncoding maxReadPoolSize="Integer"
                    maxWritePoolSize="Integer"
                    writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9bd42-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9bd42-109">Attributes and Elements</span></span>  
 <span data-ttu-id="9bd42-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9bd42-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9bd42-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="9bd42-111">Attributes</span></span>  
  
|<span data-ttu-id="9bd42-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="9bd42-112">Attribute</span></span>|<span data-ttu-id="9bd42-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="9bd42-113">Description</span></span>|  
|---------------|-----------------|  
|`maxReadPoolSize`|<span data-ttu-id="9bd42-114">El número de mensajes que se pueden leer simultáneamente sin asignar nuevos lectores.</span><span class="sxs-lookup"><span data-stu-id="9bd42-114">The amount of messages that can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="9bd42-115">Los tamaños de grupo más grandes hacen que el sistema sea más tolerante a picos de actividad a costa de un espacio de trabajo mayor.</span><span class="sxs-lookup"><span data-stu-id="9bd42-115">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="9bd42-116">El valor predeterminado es 64 lectores para cada uno de los codificadores internos (texto, JSON, y "sin formato").</span><span class="sxs-lookup"><span data-stu-id="9bd42-116">The default is 64 readers for each of the inner encoders (text, JSON, and "raw").</span></span><br /><br /> <span data-ttu-id="9bd42-117">Al aumentar este número, se aumenta el consumo de memoria, pero se prepara al codificador para tratar con ráfagas súbitas de mensajes entrantes porque puede utilizar los lectores del grupo ya creados en lugar de tener que crear nuevos.</span><span class="sxs-lookup"><span data-stu-id="9bd42-117">Increasing this number increases memory consumption, but prepares the encoder to deal with sudden bursts of incoming messages because it is able to use readers from the pool that are already created instead of creating new ones.</span></span>|  
|`maxWritePoolSize`|<span data-ttu-id="9bd42-118">El número de mensajes que se pueden enviar simultáneamente sin asignar nuevos escritores.</span><span class="sxs-lookup"><span data-stu-id="9bd42-118">The amount of messages that can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="9bd42-119">Los tamaños de grupo más grandes hacen que el sistema sea más tolerante a picos de actividad a costa de un espacio de trabajo mayor.</span><span class="sxs-lookup"><span data-stu-id="9bd42-119">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="9bd42-120">El valor predeterminado es 16 escritores para cada uno de los codificadores internos (texto, JSON, y "sin formato").</span><span class="sxs-lookup"><span data-stu-id="9bd42-120">The default is 16 writers for each of the inner encoders (text, JSON, and "raw").</span></span><br /><br /> <span data-ttu-id="9bd42-121">Al aumentar este número, se aumenta el consumo de memoria, pero se prepara al codificador para tratar con ráfagas súbitas de mensajes salientes porque puede utilizar los escritores del grupo ya creados en lugar de tener que crear nuevos.</span><span class="sxs-lookup"><span data-stu-id="9bd42-121">Increasing this number increases memory consumption, but prepares the encoder to deal with sudden bursts of outgoing messages because it is able to use writers from the pool that are already created instead of creating new ones.</span></span>|  
|`writeEncoding`|<span data-ttu-id="9bd42-122">Especifica el codificador del juego de caracteres que se va a usar para emitir los mensajes en el enlace.</span><span class="sxs-lookup"><span data-stu-id="9bd42-122">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="9bd42-123">Los valores válidos son:</span><span class="sxs-lookup"><span data-stu-id="9bd42-123">Valid values are:</span></span><br /><br /> <span data-ttu-id="9bd42-124">UnicodeFffeTextEncoding Codificación Big Endian de Unicode.</span><span class="sxs-lookup"><span data-stu-id="9bd42-124">-   UnicodeFffeTextEncoding: Unicode Big Endian encoding.</span></span><br /><span data-ttu-id="9bd42-125">Utf16TextEncoding Codificación Unicode.</span><span class="sxs-lookup"><span data-stu-id="9bd42-125">-   Utf16TextEncoding: Unicode encoding.</span></span><br /><span data-ttu-id="9bd42-126">Utf8TextEncoding codificación de 8 bits.</span><span class="sxs-lookup"><span data-stu-id="9bd42-126">-   Utf8TextEncoding: 8-bit encoding.</span></span><br /><br /> <span data-ttu-id="9bd42-127">El valor predeterminado es Utf8TextEncoding.</span><span class="sxs-lookup"><span data-stu-id="9bd42-127">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="9bd42-128">Este atributo es del tipo <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="9bd42-128">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9bd42-129">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9bd42-129">Child Elements</span></span>  
  
|<span data-ttu-id="9bd42-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="9bd42-130">Element</span></span>|<span data-ttu-id="9bd42-131">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="9bd42-131">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9bd42-132">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="9bd42-132">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="9bd42-133">Define las restricciones en la complejidad de los mensajes SOAP que pueden ser procesados por los puntos de conexión configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="9bd42-133">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="9bd42-134">Este elemento es del tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="9bd42-134">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9bd42-135">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9bd42-135">Parent Elements</span></span>  
  
|<span data-ttu-id="9bd42-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="9bd42-136">Element</span></span>|<span data-ttu-id="9bd42-137">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="9bd42-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9bd42-138">\<binding></span><span class="sxs-lookup"><span data-stu-id="9bd42-138">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="9bd42-139">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="9bd42-139">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9bd42-140">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9bd42-140">Remarks</span></span>  
 <span data-ttu-id="9bd42-141">La codificación es el proceso de transformación de un mensaje en una secuencia de bytes.</span><span class="sxs-lookup"><span data-stu-id="9bd42-141">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="9bd42-142">La descodificación es el proceso inverso.</span><span class="sxs-lookup"><span data-stu-id="9bd42-142">Decoding is the reverse process.</span></span> <span data-ttu-id="9bd42-143">Estos procesos requieren la especificación de una codificación de caracteres.</span><span class="sxs-lookup"><span data-stu-id="9bd42-143">These processes require the specification of a character encoding.</span></span>  
  
 <span data-ttu-id="9bd42-144">El elemento `webMessageEncoding` funciona delegando a una serie de codificadores internos para administrar el texto sin formato XML y las codificaciones JSON, así como los datos binarios "sin formato."</span><span class="sxs-lookup"><span data-stu-id="9bd42-144">The `webMessageEncoding` element works by delegating to a series of inner encoders to handle the plain-text XML and JSON encodings, and "raw" binary data.</span></span> <span data-ttu-id="9bd42-145">Un codificador del mensaje compuesto hace esta delegación.</span><span class="sxs-lookup"><span data-stu-id="9bd42-145">This delegation is done by a composite message encoder.</span></span>  
  
 <span data-ttu-id="9bd42-146">Este elemento de enlace y su codificador compuesto se utilizan para controlar la codificación en escenarios que no utilizan la mensajería de SOAP utilizada por el elemento `webHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="9bd42-146">This binding element and its composite encoder are used to control the encoding in scenarios that do not use SOAP messaging used by the `webHttpBinding` element.</span></span> <span data-ttu-id="9bd42-147">Estos escenarios incluyen "Plain Old XML" (POX), Representational State Transfer (REST), Really Simple Syndication (RSS) y Atom syndication, y Asynchronous JavaScript y XML (AJAX).</span><span class="sxs-lookup"><span data-stu-id="9bd42-147">These scenarios include "Plain Old XML" (POX), Representational State Transfer (REST), Really Simple Syndication (RSS) and Atom syndication, and Asynchronous JavaScript and XML (AJAX).</span></span> <span data-ttu-id="9bd42-148">El codificador del mensaje compuesto no admite SOAP o WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="9bd42-148">The composite message encoder does not support SOAP or WS-Addressing.</span></span>  
  
 <span data-ttu-id="9bd42-149">El elemento de enlace se puede configurar con una codificación de caracteres de escritura utilizando el atributo `writeEncoding`.</span><span class="sxs-lookup"><span data-stu-id="9bd42-149">The binding element can be configured with a write character encoding by using the `writeEncoding` attribute.</span></span> <span data-ttu-id="9bd42-150">El valor <xref:System.Text.Encoding> proporcionado especifica el comportamiento en escritura para los casos de texto XML y JSON.</span><span class="sxs-lookup"><span data-stu-id="9bd42-150">The supplied <xref:System.Text.Encoding> value specifies the behavior on write for the JSON and Textual XML cases.</span></span> <span data-ttu-id="9bd42-151">En lectura, cualquier codificación de mensajes válida y codificación de texto se entenderán.</span><span class="sxs-lookup"><span data-stu-id="9bd42-151">On read, any valid message encoding and text encoding is understood.</span></span>  
  
 <span data-ttu-id="9bd42-152">`maxReadPoolSize` y `maxWritePoolSize` también se pueden utilizar para establecer el número máximo de lectores y escritores que se van a asignar respectivamente.</span><span class="sxs-lookup"><span data-stu-id="9bd42-152">`maxReadPoolSize` and `maxWritePoolSize` can also be used to set the maximum number of readers and writers to be allocated respectively.</span></span> <span data-ttu-id="9bd42-153">De forma predeterminada se asignan 64 lectores y 16 escritores.</span><span class="sxs-lookup"><span data-stu-id="9bd42-153">By default 64 readers and 16 writers are allocated.</span></span>  
  
 <span data-ttu-id="9bd42-154">Las restricciones de complejidad predeterminadas también se establecen [ \<](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100)) mediante el elemento > de readerQuotas para protegerse contra una clase de ataques por denegación de servicio (dos) que intentan usar la complejidad del mensaje para vincular los recursos de procesamiento del extremo.</span><span class="sxs-lookup"><span data-stu-id="9bd42-154">Default complexity constraints are also set using the [\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100)) element to protect against a class of denial of service (DOS) attacks that attempt to use message complexity to tie up endpoint processing resources.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9bd42-155">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9bd42-155">Example</span></span>  
  
```xml  
<webMessageEncoding maxReadPoolSize="256"
                    maxWritePoolSize="128"
                    messageVersion="None"
                    textEncoding="utf-8" />
```  
  
## <a name="see-also"></a><span data-ttu-id="9bd42-156">Vea también</span><span class="sxs-lookup"><span data-stu-id="9bd42-156">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.WebMessageEncodingBindingElement>
- [<span data-ttu-id="9bd42-157">Codificación de mensajes</span><span class="sxs-lookup"><span data-stu-id="9bd42-157">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="9bd42-158">Elección de un codificador de mensajes</span><span class="sxs-lookup"><span data-stu-id="9bd42-158">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="9bd42-159">Enlaces</span><span class="sxs-lookup"><span data-stu-id="9bd42-159">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="9bd42-160">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="9bd42-160">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="9bd42-161">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="9bd42-161">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="9bd42-162">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="9bd42-162">\<customBinding></span></span>](custombinding.md)
