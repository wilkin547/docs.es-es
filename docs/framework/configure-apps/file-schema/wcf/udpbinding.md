---
title: <udpBinding>
ms.date: 03/30/2017
ms.assetid: fa291901-8340-45c6-9c44-5d9281c70bc3
ms.openlocfilehash: 7fa72d233d6489ab6a2c534f69c66a55a22d0f59
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74429832"
---
# <a name="udpbinding"></a><span data-ttu-id="559d4-101">\<udpBinding ></span><span class="sxs-lookup"><span data-stu-id="559d4-101">\<udpBinding></span></span>
<span data-ttu-id="559d4-102">Un elemento de configuración usado para configurar el enlace <xref:System.ServiceModel.UdpBinding>.</span><span class="sxs-lookup"><span data-stu-id="559d4-102">A configuration element used to configure the <xref:System.ServiceModel.UdpBinding> binding.</span></span>  
  
<span data-ttu-id="559d4-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="559d4-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="559d4-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="559d4-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="559d4-105">&nbsp;&nbsp;&nbsp;&nbsp;\<[**enlaces**](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="559d4-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="559d4-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<udpBinding >**</span><span class="sxs-lookup"><span data-stu-id="559d4-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<udpBinding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="559d4-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="559d4-107">Syntax</span></span>  
  
```xml  
<udpBinding>
  <binding closeTimeout="TimeSpan"
           duplicateMessageHistoryLength="Integer"
           maxBufferPoolSize="Integer"
           maxBufferSize="Integer"
           maxPendingMessagesTotalSize="Integer"
           maxReceivedMessageSize="Integer"
           maxRetransmitCount="Integer"
           multicastInterfaceId="Integer"
           name="String"
           openTimeout="TimeSpan"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan"
           textEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding"
           timeToLive="TimeSpan">
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</basicHttpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="559d4-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="559d4-108">Attributes and Elements</span></span>  
 <span data-ttu-id="559d4-109">En las secciones siguientes se describen atributos, elementos secundarios y elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="559d4-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="559d4-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="559d4-110">Attributes</span></span>  
  
|<span data-ttu-id="559d4-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="559d4-111">Attribute</span></span>|<span data-ttu-id="559d4-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="559d4-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="559d4-113">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de cierre para completarse.</span><span class="sxs-lookup"><span data-stu-id="559d4-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="559d4-114">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="559d4-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="559d4-115">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="559d4-115">The default is 00:01:00.</span></span>|  
|`duplicateMessageHistoryLength`|<span data-ttu-id="559d4-116">Un valor entero que especifica la longitud duplicada del historial de mensajes.</span><span class="sxs-lookup"><span data-stu-id="559d4-116">An integer value that specifies the duplicate message history length.</span></span>|  
|`maxBufferPoolSize`|<span data-ttu-id="559d4-117">Un valor entero que especifica la cantidad de memoria máxima que se asigna para el uso realizado por el administrador de los búferes que reciben los mensajes del canal.</span><span class="sxs-lookup"><span data-stu-id="559d4-117">An integer value that specifies the maximum amount of memory that is allocated for use by the manager of the message buffers that receive messages from the channel.</span></span> <span data-ttu-id="559d4-118">El valor predeterminado es 524288 (0x80000) bytes.</span><span class="sxs-lookup"><span data-stu-id="559d4-118">The default value is 524288 (0x80000) bytes.</span></span>|  
|`maxBufferSize`|<span data-ttu-id="559d4-119">Un valor entero que especifica el tamaño máximo, en bytes, de un búfer que almacena los mensajes mientras se procesan para un extremo configurado con este enlace.</span><span class="sxs-lookup"><span data-stu-id="559d4-119">An integer value that specifies the maximum size, in bytes, of a buffer that stores messages while they are processed for an endpoint configured with this binding.</span></span> <span data-ttu-id="559d4-120">El valor predeterminado es 65.536 bytes.</span><span class="sxs-lookup"><span data-stu-id="559d4-120">The default value is 65,536 bytes.</span></span>|  
|`maxPendingMessagesTotalSize`|<span data-ttu-id="559d4-121">Valor entero que especifica el número máximo de mensajes que se han recibido pero que todavía no se han quitado de la cola de entrada para una instancia del canal individual.</span><span class="sxs-lookup"><span data-stu-id="559d4-121">An integer value that specifies the maximum number of messages that are received but not yet removed from the input queue for an individual channel instance.</span></span>|  
|`maxReceivedMessageSize`|<span data-ttu-id="559d4-122">Un entero positivo que define el tamaño máximo del mensaje, en bytes, incluidos los encabezados, para un mensaje que se puede recibir en un canal configurado con este enlace.</span><span class="sxs-lookup"><span data-stu-id="559d4-122">A positive integer that defines the maximum message size, in bytes, including headers, for a message that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="559d4-123">El remitente recibe un error SOAP cuando el mensaje es demasiado grande para el receptor.</span><span class="sxs-lookup"><span data-stu-id="559d4-123">The sender receives a SOAP fault if the message is too large for the receiver.</span></span> <span data-ttu-id="559d4-124">El destinatario quita el mensaje y crea una entrada del evento en el registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="559d4-124">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="559d4-125">El valor predeterminado es 65.536 bytes.</span><span class="sxs-lookup"><span data-stu-id="559d4-125">The default is 65,536 bytes.</span></span>|  
|`maxRetransmitCount`|<span data-ttu-id="559d4-126">Valor entero de que especifica el número máximo de mensajes de retransmisión.</span><span class="sxs-lookup"><span data-stu-id="559d4-126">An integer value that specifies the maximum number of retransmit messages.</span></span>|  
|`multicastInterfaceId`|<span data-ttu-id="559d4-127">Valor entero que especifica el identificador de la interfaz de multidifusión.</span><span class="sxs-lookup"><span data-stu-id="559d4-127">An integer value that specifies the multicast interface ID.</span></span>|  
|`name`|<span data-ttu-id="559d4-128">Cadena que contiene el nombre de configuración del enlace.</span><span class="sxs-lookup"><span data-stu-id="559d4-128">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="559d4-129">Este valor debe ser único porque se usa como identificación del enlace.</span><span class="sxs-lookup"><span data-stu-id="559d4-129">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="559d4-130">A partir de .NET Framework 4, no es necesario que los enlaces y los comportamientos tengan un nombre.</span><span class="sxs-lookup"><span data-stu-id="559d4-130">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="559d4-131">Para obtener más información sobre la configuración predeterminada y los enlaces y comportamientos sin nombre, vea [configuración simplificada](../../../wcf/simplified-configuration.md) y [configuración simplificada para servicios WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="559d4-131">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="559d4-132">Valor de la estructura <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de apertura para completarse.</span><span class="sxs-lookup"><span data-stu-id="559d4-132">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="559d4-133">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="559d4-133">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="559d4-134">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="559d4-134">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="559d4-135">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de recepción para completarse.</span><span class="sxs-lookup"><span data-stu-id="559d4-135">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="559d4-136">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="559d4-136">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="559d4-137">El valor predeterminado es 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="559d4-137">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="559d4-138">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de envío para completarse.</span><span class="sxs-lookup"><span data-stu-id="559d4-138">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="559d4-139">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="559d4-139">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="559d4-140">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="559d4-140">The default is 00:01:00.</span></span>|  
|`textEncoding`|<span data-ttu-id="559d4-141">Establece el codificador del juego de caracteres que se va a usar para emitir los mensajes en el enlace.</span><span class="sxs-lookup"><span data-stu-id="559d4-141">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="559d4-142">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="559d4-142">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="559d4-143">-BigEndianUnicode: codificación Unicode BigEndian.</span><span class="sxs-lookup"><span data-stu-id="559d4-143">-   BigEndianUnicode: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="559d4-144">-Unicode: codificación de 16 bits.</span><span class="sxs-lookup"><span data-stu-id="559d4-144">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="559d4-145">-UTF8: codificación de 8 bits</span><span class="sxs-lookup"><span data-stu-id="559d4-145">-   UTF8: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="559d4-146">El valor predeterminado es UTF8.</span><span class="sxs-lookup"><span data-stu-id="559d4-146">The default is UTF8.</span></span> <span data-ttu-id="559d4-147">Este atributo es del tipo <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="559d4-147">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|`timeToLive`|<span data-ttu-id="559d4-148">Valor timespan que especifica el período de vida para el enlace.</span><span class="sxs-lookup"><span data-stu-id="559d4-148">A timespan value that specifies the time to live for the binding.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="559d4-149">Elemento secundario</span><span class="sxs-lookup"><span data-stu-id="559d4-149">Child Elements</span></span>  
  
|<span data-ttu-id="559d4-150">Elemento</span><span class="sxs-lookup"><span data-stu-id="559d4-150">Element</span></span>|<span data-ttu-id="559d4-151">Descripción</span><span class="sxs-lookup"><span data-stu-id="559d4-151">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="559d4-152">[\<readerQuotas >](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="559d4-152">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="559d4-153">Define las restricciones en la complejidad de los mensajes SOAP que pueden ser procesados por los puntos de conexión configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="559d4-153">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="559d4-154">Este elemento es del tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="559d4-154">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="559d4-155">Elemento principal</span><span class="sxs-lookup"><span data-stu-id="559d4-155">Parent Elements</span></span>  
  
|<span data-ttu-id="559d4-156">Elemento</span><span class="sxs-lookup"><span data-stu-id="559d4-156">Element</span></span>|<span data-ttu-id="559d4-157">Descripción</span><span class="sxs-lookup"><span data-stu-id="559d4-157">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="559d4-158">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="559d4-158">\<bindings></span></span>](bindings.md)|<span data-ttu-id="559d4-159">Este elemento contiene una colección de enlaces estándar y personalizados.</span><span class="sxs-lookup"><span data-stu-id="559d4-159">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="559d4-160">Comentarios</span><span class="sxs-lookup"><span data-stu-id="559d4-160">Remarks</span></span>  
 <span data-ttu-id="559d4-161">El UdpBinding permite que los servicios de WCF se comuniquen sobre el transporte UDP.</span><span class="sxs-lookup"><span data-stu-id="559d4-161">The UdpBinding allows WCF services to communicate over the UDP transport.</span></span> <span data-ttu-id="559d4-162">Permite intercambios de mensajes "desencadenar y olvidar", donde un cliente envía un mensaje a un servicio y no espera ninguna respuesta.</span><span class="sxs-lookup"><span data-stu-id="559d4-162">It allows for "fire and forget" message exchanges where a client sends a message to a service and expects no response back.</span></span>  
  
## <a name="example"></a><span data-ttu-id="559d4-163">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="559d4-163">Example</span></span>  
 <span data-ttu-id="559d4-164">En el ejemplo siguiente se muestra cómo configurar el <xref:System.ServiceModel.UdpBinding> mediante el < elemento`udpBinding`>.</span><span class="sxs-lookup"><span data-stu-id="559d4-164">The following example shows how to configure the <xref:System.ServiceModel.UdpBinding> using the <`udpBinding`> element.</span></span>  
  
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
            timeToLive="00:10:00">
    <readerQuotas />
  </binding>
</udpBinding>
```  
  
## <a name="see-also"></a><span data-ttu-id="559d4-165">Vea también</span><span class="sxs-lookup"><span data-stu-id="559d4-165">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>
- [<span data-ttu-id="559d4-166">Enlaces</span><span class="sxs-lookup"><span data-stu-id="559d4-166">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="559d4-167">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="559d4-167">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="559d4-168">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="559d4-168">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="559d4-169">\<> de enlace</span><span class="sxs-lookup"><span data-stu-id="559d4-169">\<binding></span></span>](bindings.md)
