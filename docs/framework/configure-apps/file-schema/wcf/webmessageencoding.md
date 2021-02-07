---
description: 'Más información acerca de: <webMessageEncoding>'
title: <webMessageEncoding>
ms.date: 03/30/2017
ms.assetid: 892ca485-e21a-4a44-8e40-633161ef6796
ms.openlocfilehash: fb52de348ed20963a66081ac78180557f92e5e30
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99682571"
---
# \<webMessageEncoding>

<span data-ttu-id="89ca6-102">Habilita XML de texto sin formato, codificaciones de mensajes de Notación de objetos JavaScript (JSON) y el contenido binario "sin procesar" que se va a leer y escribir cuando se use en un enlace de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="89ca6-102">Enables plain-text XML, JavaScript Object Notation (JSON) message encodings and "raw" binary content to be read and written when used in a Windows Communication Foundation (WCF) binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webMessageEncoding>**  
  
## <a name="syntax"></a><span data-ttu-id="89ca6-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="89ca6-103">Syntax</span></span>  
  
```xml  
<webMessageEncoding maxReadPoolSize="Integer"
                    maxWritePoolSize="Integer"
                    writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="89ca6-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="89ca6-104">Attributes and Elements</span></span>  

 <span data-ttu-id="89ca6-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="89ca6-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="89ca6-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="89ca6-106">Attributes</span></span>  
  
|<span data-ttu-id="89ca6-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="89ca6-107">Attribute</span></span>|<span data-ttu-id="89ca6-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="89ca6-108">Description</span></span>|  
|---------------|-----------------|  
|`maxReadPoolSize`|<span data-ttu-id="89ca6-109">El número de mensajes que se pueden leer simultáneamente sin asignar nuevos lectores.</span><span class="sxs-lookup"><span data-stu-id="89ca6-109">The amount of messages that can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="89ca6-110">Los tamaños de grupo más grandes hacen que el sistema sea más tolerante a picos de actividad a costa de un espacio de trabajo mayor.</span><span class="sxs-lookup"><span data-stu-id="89ca6-110">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="89ca6-111">El valor predeterminado es 64 lectores para cada uno de los codificadores internos (texto, JSON, y "sin formato").</span><span class="sxs-lookup"><span data-stu-id="89ca6-111">The default is 64 readers for each of the inner encoders (text, JSON, and "raw").</span></span><br /><br /> <span data-ttu-id="89ca6-112">Al aumentar este número, se aumenta el consumo de memoria, pero se prepara al codificador para tratar con ráfagas súbitas de mensajes entrantes porque puede utilizar los lectores del grupo ya creados en lugar de tener que crear nuevos.</span><span class="sxs-lookup"><span data-stu-id="89ca6-112">Increasing this number increases memory consumption, but prepares the encoder to deal with sudden bursts of incoming messages because it is able to use readers from the pool that are already created instead of creating new ones.</span></span>|  
|`maxWritePoolSize`|<span data-ttu-id="89ca6-113">El número de mensajes que se pueden enviar simultáneamente sin asignar nuevos escritores.</span><span class="sxs-lookup"><span data-stu-id="89ca6-113">The amount of messages that can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="89ca6-114">Los tamaños de grupo más grandes hacen que el sistema sea más tolerante a picos de actividad a costa de un espacio de trabajo mayor.</span><span class="sxs-lookup"><span data-stu-id="89ca6-114">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="89ca6-115">El valor predeterminado es 16 escritores para cada uno de los codificadores internos (texto, JSON, y "sin formato").</span><span class="sxs-lookup"><span data-stu-id="89ca6-115">The default is 16 writers for each of the inner encoders (text, JSON, and "raw").</span></span><br /><br /> <span data-ttu-id="89ca6-116">Al aumentar este número, se aumenta el consumo de memoria, pero se prepara al codificador para tratar con ráfagas súbitas de mensajes salientes porque puede utilizar los escritores del grupo ya creados en lugar de tener que crear nuevos.</span><span class="sxs-lookup"><span data-stu-id="89ca6-116">Increasing this number increases memory consumption, but prepares the encoder to deal with sudden bursts of outgoing messages because it is able to use writers from the pool that are already created instead of creating new ones.</span></span>|  
|`writeEncoding`|<span data-ttu-id="89ca6-117">Especifica el codificador del juego de caracteres que se va a usar para emitir los mensajes en el enlace.</span><span class="sxs-lookup"><span data-stu-id="89ca6-117">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="89ca6-118">Los valores válidos son:</span><span class="sxs-lookup"><span data-stu-id="89ca6-118">Valid values are:</span></span><br /><br /> <span data-ttu-id="89ca6-119">-UnicodeFffeTextEncoding: codificación Big Endian de Unicode.</span><span class="sxs-lookup"><span data-stu-id="89ca6-119">-   UnicodeFffeTextEncoding: Unicode Big Endian encoding.</span></span><br /><span data-ttu-id="89ca6-120">-Utf16TextEncoding: codificación Unicode.</span><span class="sxs-lookup"><span data-stu-id="89ca6-120">-   Utf16TextEncoding: Unicode encoding.</span></span><br /><span data-ttu-id="89ca6-121">-Utf8TextEncoding: codificación de 8 bits.</span><span class="sxs-lookup"><span data-stu-id="89ca6-121">-   Utf8TextEncoding: 8-bit encoding.</span></span><br /><br /> <span data-ttu-id="89ca6-122">El valor predeterminado es Utf8TextEncoding.</span><span class="sxs-lookup"><span data-stu-id="89ca6-122">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="89ca6-123">Este atributo es del tipo <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="89ca6-123">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="89ca6-124">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="89ca6-124">Child Elements</span></span>  
  
|<span data-ttu-id="89ca6-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="89ca6-125">Element</span></span>|<span data-ttu-id="89ca6-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="89ca6-126">Description</span></span>|  
|-------------|-----------------|  
|[\<readerQuotas>](/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="89ca6-127">Define las restricciones en la complejidad de los mensajes SOAP que pueden ser procesados por los puntos de conexión configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="89ca6-127">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="89ca6-128">Este elemento es del tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="89ca6-128">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="89ca6-129">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="89ca6-129">Parent Elements</span></span>  
  
|<span data-ttu-id="89ca6-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="89ca6-130">Element</span></span>|<span data-ttu-id="89ca6-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="89ca6-131">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="89ca6-132">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="89ca6-132">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="89ca6-133">Observaciones</span><span class="sxs-lookup"><span data-stu-id="89ca6-133">Remarks</span></span>  

 <span data-ttu-id="89ca6-134">La codificación es el proceso de transformación de un mensaje en una secuencia de bytes.</span><span class="sxs-lookup"><span data-stu-id="89ca6-134">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="89ca6-135">La descodificación es el proceso inverso.</span><span class="sxs-lookup"><span data-stu-id="89ca6-135">Decoding is the reverse process.</span></span> <span data-ttu-id="89ca6-136">Estos procesos requieren la especificación de una codificación de caracteres.</span><span class="sxs-lookup"><span data-stu-id="89ca6-136">These processes require the specification of a character encoding.</span></span>  
  
 <span data-ttu-id="89ca6-137">El elemento `webMessageEncoding` funciona delegando a una serie de codificadores internos para administrar el texto sin formato XML y las codificaciones JSON, así como los datos binarios "sin formato."</span><span class="sxs-lookup"><span data-stu-id="89ca6-137">The `webMessageEncoding` element works by delegating to a series of inner encoders to handle the plain-text XML and JSON encodings, and "raw" binary data.</span></span> <span data-ttu-id="89ca6-138">Un codificador del mensaje compuesto hace esta delegación.</span><span class="sxs-lookup"><span data-stu-id="89ca6-138">This delegation is done by a composite message encoder.</span></span>  
  
 <span data-ttu-id="89ca6-139">Este elemento de enlace y su codificador compuesto se utilizan para controlar la codificación en escenarios que no utilizan la mensajería de SOAP utilizada por el elemento `webHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="89ca6-139">This binding element and its composite encoder are used to control the encoding in scenarios that do not use SOAP messaging used by the `webHttpBinding` element.</span></span> <span data-ttu-id="89ca6-140">Estos escenarios incluyen "Plain Old XML" (POX), Representational State Transfer (REST), Really Simple Syndication (RSS) y Atom syndication, y Asynchronous JavaScript y XML (AJAX).</span><span class="sxs-lookup"><span data-stu-id="89ca6-140">These scenarios include "Plain Old XML" (POX), Representational State Transfer (REST), Really Simple Syndication (RSS) and Atom syndication, and Asynchronous JavaScript and XML (AJAX).</span></span> <span data-ttu-id="89ca6-141">El codificador del mensaje compuesto no admite SOAP o WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="89ca6-141">The composite message encoder does not support SOAP or WS-Addressing.</span></span>  
  
 <span data-ttu-id="89ca6-142">El elemento de enlace se puede configurar con una codificación de caracteres de escritura utilizando el atributo `writeEncoding`.</span><span class="sxs-lookup"><span data-stu-id="89ca6-142">The binding element can be configured with a write character encoding by using the `writeEncoding` attribute.</span></span> <span data-ttu-id="89ca6-143">El valor <xref:System.Text.Encoding> proporcionado especifica el comportamiento en escritura para los casos de texto XML y JSON.</span><span class="sxs-lookup"><span data-stu-id="89ca6-143">The supplied <xref:System.Text.Encoding> value specifies the behavior on write for the JSON and Textual XML cases.</span></span> <span data-ttu-id="89ca6-144">En lectura, cualquier codificación de mensajes válida y codificación de texto se entenderán.</span><span class="sxs-lookup"><span data-stu-id="89ca6-144">On read, any valid message encoding and text encoding is understood.</span></span>  
  
 <span data-ttu-id="89ca6-145">`maxReadPoolSize` y `maxWritePoolSize` también se pueden utilizar para establecer el número máximo de lectores y escritores que se van a asignar respectivamente.</span><span class="sxs-lookup"><span data-stu-id="89ca6-145">`maxReadPoolSize` and `maxWritePoolSize` can also be used to set the maximum number of readers and writers to be allocated respectively.</span></span> <span data-ttu-id="89ca6-146">De forma predeterminada se asignan 64 lectores y 16 escritores.</span><span class="sxs-lookup"><span data-stu-id="89ca6-146">By default 64 readers and 16 writers are allocated.</span></span>  
  
 <span data-ttu-id="89ca6-147">Las restricciones de complejidad predeterminadas también se establecen mediante el [\<readerQuotas>](/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100)) elemento para proteger contra una clase de ataques por denegación de servicio (dos) que intentan usar la complejidad del mensaje para asignar recursos de procesamiento del extremo.</span><span class="sxs-lookup"><span data-stu-id="89ca6-147">Default complexity constraints are also set using the [\<readerQuotas>](/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100)) element to protect against a class of denial of service (DOS) attacks that attempt to use message complexity to tie up endpoint processing resources.</span></span>  
  
## <a name="example"></a><span data-ttu-id="89ca6-148">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="89ca6-148">Example</span></span>  
  
```xml  
<webMessageEncoding maxReadPoolSize="256"
                    maxWritePoolSize="128"
                    messageVersion="None"
                    textEncoding="utf-8" />
```  
  
## <a name="see-also"></a><span data-ttu-id="89ca6-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="89ca6-149">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.WebMessageEncodingBindingElement>
- [<span data-ttu-id="89ca6-150">Codificación de mensajes</span><span class="sxs-lookup"><span data-stu-id="89ca6-150">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="89ca6-151">Elección de un codificador de mensajes</span><span class="sxs-lookup"><span data-stu-id="89ca6-151">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="89ca6-152">Enlaces</span><span class="sxs-lookup"><span data-stu-id="89ca6-152">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="89ca6-153">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="89ca6-153">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="89ca6-154">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="89ca6-154">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
