---
title: '&lt;udpBinding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fa291901-8340-45c6-9c44-5d9281c70bc3
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6f43462ac42c59407ae90f2d342a445a688e1b26
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltudpbindinggt"></a><span data-ttu-id="63ab6-102">&lt;udpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="63ab6-102">&lt;udpBinding&gt;</span></span>
<span data-ttu-id="63ab6-103">Un elemento de configuración usado para configurar el enlace <xref:System.ServiceModel.UdpBinding>.</span><span class="sxs-lookup"><span data-stu-id="63ab6-103">A configuration element used to configure the <xref:System.ServiceModel.UdpBinding> binding.</span></span>  
  
 <span data-ttu-id="63ab6-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="63ab6-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="63ab6-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="63ab6-105">\<bindings></span></span>  
<span data-ttu-id="63ab6-106">\<udpBinding ></span><span class="sxs-lookup"><span data-stu-id="63ab6-106">\<udpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63ab6-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="63ab6-107">Syntax</span></span>  
  
```xml  
<udpBinding>  
   <binding   
       closeTimeout="TimeSpan"   
       duplicateMessageHistoryLength="Integer"  
       maxBufferPoolSize="Integer"  
       maxBufferSize="Integer"       maxPendingMessagesTotalSize="Integer"  
       maxReceivedMessageSize="Integer"       maxRetransmitCount="Integer"  
       multicastInterfaceId="Integer"  
              name="string"   
       openTimeout="TimeSpan"   
       receiveTimeout="TimeSpan"  
       sendTimeout="TimeSpan"  
       textEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding"  
       timeToLive="TimeSpan">  
       <readerQuotas   
            maxArrayLength="Integer"  
            maxBytesPerRead="Integer"  
            maxDepth="Integer"             maxNameTableCharCount="Integer"                maxStringContentLength="Integer" />  
   </binding>  
</basicHttpBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="63ab6-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="63ab6-108">Attributes and Elements</span></span>  
 <span data-ttu-id="63ab6-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="63ab6-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="63ab6-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="63ab6-110">Attributes</span></span>  
  
|<span data-ttu-id="63ab6-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="63ab6-111">Attribute</span></span>|<span data-ttu-id="63ab6-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="63ab6-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="63ab6-113">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de cierre para completarse.</span><span class="sxs-lookup"><span data-stu-id="63ab6-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="63ab6-114">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="63ab6-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="63ab6-115">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="63ab6-115">The default is 00:01:00.</span></span>|  
|`duplicateMessageHistoryLength`|<span data-ttu-id="63ab6-116">Un valor entero que especifica la longitud duplicada del historial de mensajes.</span><span class="sxs-lookup"><span data-stu-id="63ab6-116">An integer value that specifies the duplicate message history length.</span></span>|  
|`maxBufferPoolSize`|<span data-ttu-id="63ab6-117">Un valor entero que especifica la cantidad de memoria máxima que se asigna para el uso realizado por el administrador de los búferes que reciben los mensajes del canal.</span><span class="sxs-lookup"><span data-stu-id="63ab6-117">An integer value that specifies the maximum amount of memory that is allocated for use by the manager of the message buffers that receive messages from the channel.</span></span> <span data-ttu-id="63ab6-118">El valor predeterminado es 524288 (0x80000) bytes.</span><span class="sxs-lookup"><span data-stu-id="63ab6-118">The default value is 524288 (0x80000) bytes.</span></span>|  
|`maxBufferSize`|<span data-ttu-id="63ab6-119">Un valor entero que especifica el tamaño máximo, en bytes, de un búfer que almacena los mensajes mientras se procesan para un extremo configurado con este enlace.</span><span class="sxs-lookup"><span data-stu-id="63ab6-119">An integer value that specifies the maximum size, in bytes, of a buffer that stores messages while they are processed for an endpoint configured with this binding.</span></span> <span data-ttu-id="63ab6-120">El valor predeterminado es 65.536 bytes.</span><span class="sxs-lookup"><span data-stu-id="63ab6-120">The default value is 65,536 bytes.</span></span>|  
|`maxPendingMessagesTotalSize`|<span data-ttu-id="63ab6-121">Valor entero que especifica el número máximo de mensajes que se han recibido pero que todavía no se han quitado de la cola de entrada para una instancia del canal individual.</span><span class="sxs-lookup"><span data-stu-id="63ab6-121">An integer value that specifies the maximum number of messages that are received but not yet removed from the input queue for an individual channel instance.</span></span>|  
|`maxReceivedMessageSize`|<span data-ttu-id="63ab6-122">Un entero positivo que define el tamaño máximo del mensaje, en bytes, incluidos los encabezados, para un mensaje que se puede recibir en un canal configurado con este enlace.</span><span class="sxs-lookup"><span data-stu-id="63ab6-122">A positive integer that defines the maximum message size, in bytes, including headers, for a message that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="63ab6-123">El remitente recibe un error SOAP cuando el mensaje es demasiado grande para el receptor.</span><span class="sxs-lookup"><span data-stu-id="63ab6-123">The sender receives a SOAP fault if the message is too large for the receiver.</span></span> <span data-ttu-id="63ab6-124">El destinatario quita el mensaje y crea una entrada del evento en el registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="63ab6-124">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="63ab6-125">El valor predeterminado es 65.536 bytes.</span><span class="sxs-lookup"><span data-stu-id="63ab6-125">The default is 65,536 bytes.</span></span>|  
|`maxRetransmitCount`|<span data-ttu-id="63ab6-126">Valor entero de que especifica el número máximo de mensajes de retransmisión.</span><span class="sxs-lookup"><span data-stu-id="63ab6-126">An integer value that specifies the maximum number of retransmit messages.</span></span>|  
|`multicastInterfaceId`|<span data-ttu-id="63ab6-127">Valor entero que especifica el identificador de la interfaz de multidifusión.</span><span class="sxs-lookup"><span data-stu-id="63ab6-127">An integer value that specifies the multicast interface ID.</span></span>|  
|`name`|<span data-ttu-id="63ab6-128">Cadena que contiene el nombre de configuración del enlace.</span><span class="sxs-lookup"><span data-stu-id="63ab6-128">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="63ab6-129">Este valor debe ser único porque se usa como identificación del enlace.</span><span class="sxs-lookup"><span data-stu-id="63ab6-129">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="63ab6-130">Cada enlace tiene los atributos `name` y `namespace` que, juntos, lo identifican de forma exclusiva en los metadatos del servicio.</span><span class="sxs-lookup"><span data-stu-id="63ab6-130">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="63ab6-131">Además, este nombre es único entre los enlaces del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="63ab6-131">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="63ab6-132">A partir de [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], no es necesario que los enlaces y los comportamientos tengan nombre.</span><span class="sxs-lookup"><span data-stu-id="63ab6-132">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="63ab6-133">Para obtener más información acerca de la configuración predeterminada y enlaces anónimos y los comportamientos, consulte [configuración simplificada](../../../../../docs/framework/wcf/simplified-configuration.md) y [configuración simplificada para los servicios WCF](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="63ab6-133">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="63ab6-134">Valor de la estructura <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de apertura para completarse.</span><span class="sxs-lookup"><span data-stu-id="63ab6-134">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="63ab6-135">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="63ab6-135">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="63ab6-136">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="63ab6-136">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="63ab6-137">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de recepción para completarse.</span><span class="sxs-lookup"><span data-stu-id="63ab6-137">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="63ab6-138">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="63ab6-138">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="63ab6-139">El valor predeterminado es 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="63ab6-139">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="63ab6-140">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de envío para completarse.</span><span class="sxs-lookup"><span data-stu-id="63ab6-140">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="63ab6-141">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="63ab6-141">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="63ab6-142">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="63ab6-142">The default is 00:01:00.</span></span>|  
|`textEncoding`|<span data-ttu-id="63ab6-143">Establece el codificador del juego de caracteres que se va a usar para emitir los mensajes en el enlace.</span><span class="sxs-lookup"><span data-stu-id="63ab6-143">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="63ab6-144">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="63ab6-144">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="63ab6-145">-BigEndianUnicode: Codificación Unicode BigEndian.</span><span class="sxs-lookup"><span data-stu-id="63ab6-145">-   BigEndianUnicode: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="63ab6-146">-Unicode: codificación de 16 bits.</span><span class="sxs-lookup"><span data-stu-id="63ab6-146">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="63ab6-147">-UTF8: codificación de 8 bits</span><span class="sxs-lookup"><span data-stu-id="63ab6-147">-   UTF8: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="63ab6-148">El valor predeterminado es UTF8.</span><span class="sxs-lookup"><span data-stu-id="63ab6-148">The default is UTF8.</span></span> <span data-ttu-id="63ab6-149">Este atributo es del tipo <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="63ab6-149">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|`timeToLive`|<span data-ttu-id="63ab6-150">Valor timespan que especifica el período de vida para el enlace.</span><span class="sxs-lookup"><span data-stu-id="63ab6-150">A timespan value that specifies the time to live for the binding.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="63ab6-151">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="63ab6-151">Child Elements</span></span>  
  
|<span data-ttu-id="63ab6-152">Elemento</span><span class="sxs-lookup"><span data-stu-id="63ab6-152">Element</span></span>|<span data-ttu-id="63ab6-153">Descripción</span><span class="sxs-lookup"><span data-stu-id="63ab6-153">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="63ab6-154">\<readerQuotas ></span><span class="sxs-lookup"><span data-stu-id="63ab6-154">\<readerQuotas></span></span>](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="63ab6-155">Define las restricciones en la complejidad de los mensajes SOAP que pueden ser procesados por los puntos de conexión configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="63ab6-155">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="63ab6-156">Este elemento es del tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="63ab6-156">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="63ab6-157">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="63ab6-157">Parent Elements</span></span>  
  
|<span data-ttu-id="63ab6-158">Elemento</span><span class="sxs-lookup"><span data-stu-id="63ab6-158">Element</span></span>|<span data-ttu-id="63ab6-159">Descripción</span><span class="sxs-lookup"><span data-stu-id="63ab6-159">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="63ab6-160">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="63ab6-160">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="63ab6-161">Este elemento contiene una colección de enlaces estándar y personalizados.</span><span class="sxs-lookup"><span data-stu-id="63ab6-161">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="63ab6-162">Comentarios</span><span class="sxs-lookup"><span data-stu-id="63ab6-162">Remarks</span></span>  
 <span data-ttu-id="63ab6-163">El UdpBinding permite que los servicios de WCF se comuniquen sobre el transporte UDP.</span><span class="sxs-lookup"><span data-stu-id="63ab6-163">The UdpBinding allows WCF services to communicate over the UDP transport.</span></span> <span data-ttu-id="63ab6-164">Permite intercambios de mensajes "desencadenar y omitir" donde un cliente envía un mensaje a un servicio y no espera ninguna respuesta.</span><span class="sxs-lookup"><span data-stu-id="63ab6-164">It allows for "fire and forget" message exchanges where a client sends a message to a service and expects no response back.</span></span>  
  
## <a name="example"></a><span data-ttu-id="63ab6-165">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="63ab6-165">Example</span></span>  
 <span data-ttu-id="63ab6-166">En el ejemplo siguiente se muestra cómo configurar <xref:System.ServiceModel.UdpBinding> con el elemento <`udpBinding`>.</span><span class="sxs-lookup"><span data-stu-id="63ab6-166">The following example shows how to configure the <xref:System.ServiceModel.UdpBinding> using the <`udpBinding`> element.</span></span>  
  
```xml  
<udpBinding>  
        <binding  closeTimeout="00:10:00"  
                   duplicateMessageHistoryLength="100"  
                   maxBufferPoolSize="100"  
                   maxPendingMessagesTotalSize="100000"  
                   maxReceivedMessageSize="65536"  
                    maxRetransmitCount="10"  
                   multicastInterfaceId="00000"  
                   name="myUdpBinding"  
                   openTimeout="00:10:00"  
                   receiveTimeout="00:10:00"  
                   sendTimeout="00:10:00"  
                   textEncoding="utf-8"  
                   timeToLive="00:10:00"  
          <readerQuotas/>   
        </binding>  
      </udpBinding>  
```  
  
## <a name="see-also"></a><span data-ttu-id="63ab6-167">Vea también</span><span class="sxs-lookup"><span data-stu-id="63ab6-167">See Also</span></span>  
 <xref:System.ServiceModel.Channels.Binding>  
 <xref:System.ServiceModel.Channels.BindingElement>  
 <xref:System.ServiceModel.BasicHttpBinding>  
 <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>  
 [<span data-ttu-id="63ab6-168">Enlaces</span><span class="sxs-lookup"><span data-stu-id="63ab6-168">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="63ab6-169">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="63ab6-169">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="63ab6-170">Utilización de enlaces para configurar los clientes y servicios de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="63ab6-170">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="63ab6-171">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="63ab6-171">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
