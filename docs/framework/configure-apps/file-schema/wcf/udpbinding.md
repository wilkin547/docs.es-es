---
description: 'Más información acerca de: <udpBinding>'
title: <udpBinding>
ms.date: 03/30/2017
ms.assetid: fa291901-8340-45c6-9c44-5d9281c70bc3
ms.openlocfilehash: 33f8f6abaebe24364273ab43e7ef9ade39a969b0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99749225"
---
# \<udpBinding>

<span data-ttu-id="1805d-102">Un elemento de configuración usado para configurar el enlace <xref:System.ServiceModel.UdpBinding>.</span><span class="sxs-lookup"><span data-stu-id="1805d-102">A configuration element used to configure the <xref:System.ServiceModel.UdpBinding> binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<udpBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="1805d-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1805d-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1805d-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="1805d-104">Attributes and Elements</span></span>  

 <span data-ttu-id="1805d-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="1805d-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1805d-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="1805d-106">Attributes</span></span>  
  
|<span data-ttu-id="1805d-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="1805d-107">Attribute</span></span>|<span data-ttu-id="1805d-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="1805d-108">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="1805d-109">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de cierre para completarse.</span><span class="sxs-lookup"><span data-stu-id="1805d-109">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="1805d-110">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="1805d-110">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="1805d-111">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="1805d-111">The default is 00:01:00.</span></span>|  
|`duplicateMessageHistoryLength`|<span data-ttu-id="1805d-112">Un valor entero que especifica la longitud duplicada del historial de mensajes.</span><span class="sxs-lookup"><span data-stu-id="1805d-112">An integer value that specifies the duplicate message history length.</span></span>|  
|`maxBufferPoolSize`|<span data-ttu-id="1805d-113">Un valor entero que especifica la cantidad de memoria máxima que se asigna para el uso realizado por el administrador de los búferes que reciben los mensajes del canal.</span><span class="sxs-lookup"><span data-stu-id="1805d-113">An integer value that specifies the maximum amount of memory that is allocated for use by the manager of the message buffers that receive messages from the channel.</span></span> <span data-ttu-id="1805d-114">El valor predeterminado es 524288 (0x80000) bytes.</span><span class="sxs-lookup"><span data-stu-id="1805d-114">The default value is 524288 (0x80000) bytes.</span></span>|  
|`maxBufferSize`|<span data-ttu-id="1805d-115">Un valor entero que especifica el tamaño máximo, en bytes, de un búfer que almacena los mensajes mientras se procesan para un extremo configurado con este enlace.</span><span class="sxs-lookup"><span data-stu-id="1805d-115">An integer value that specifies the maximum size, in bytes, of a buffer that stores messages while they are processed for an endpoint configured with this binding.</span></span> <span data-ttu-id="1805d-116">El valor predeterminado es 65.536 bytes.</span><span class="sxs-lookup"><span data-stu-id="1805d-116">The default value is 65,536 bytes.</span></span>|  
|`maxPendingMessagesTotalSize`|<span data-ttu-id="1805d-117">Valor entero que especifica el número máximo de mensajes que se han recibido pero que todavía no se han quitado de la cola de entrada para una instancia del canal individual.</span><span class="sxs-lookup"><span data-stu-id="1805d-117">An integer value that specifies the maximum number of messages that are received but not yet removed from the input queue for an individual channel instance.</span></span>|  
|`maxReceivedMessageSize`|<span data-ttu-id="1805d-118">Un entero positivo que define el tamaño máximo del mensaje, en bytes, incluidos los encabezados, para un mensaje que se puede recibir en un canal configurado con este enlace.</span><span class="sxs-lookup"><span data-stu-id="1805d-118">A positive integer that defines the maximum message size, in bytes, including headers, for a message that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="1805d-119">El remitente recibe un error SOAP cuando el mensaje es demasiado grande para el receptor.</span><span class="sxs-lookup"><span data-stu-id="1805d-119">The sender receives a SOAP fault if the message is too large for the receiver.</span></span> <span data-ttu-id="1805d-120">El destinatario quita el mensaje y crea una entrada del evento en el registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="1805d-120">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="1805d-121">The default is 65.536 bytes.</span><span class="sxs-lookup"><span data-stu-id="1805d-121">The default is 65,536 bytes.</span></span>|  
|`maxRetransmitCount`|<span data-ttu-id="1805d-122">Valor entero de que especifica el número máximo de mensajes de retransmisión.</span><span class="sxs-lookup"><span data-stu-id="1805d-122">An integer value that specifies the maximum number of retransmit messages.</span></span>|  
|`multicastInterfaceId`|<span data-ttu-id="1805d-123">Valor entero que especifica el identificador de la interfaz de multidifusión.</span><span class="sxs-lookup"><span data-stu-id="1805d-123">An integer value that specifies the multicast interface ID.</span></span>|  
|`name`|<span data-ttu-id="1805d-124">Cadena que contiene el nombre de configuración del enlace.</span><span class="sxs-lookup"><span data-stu-id="1805d-124">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="1805d-125">Este valor debe ser único porque se usa como identificación del enlace.</span><span class="sxs-lookup"><span data-stu-id="1805d-125">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="1805d-126">A partir de .NET Framework 4, no es necesario que los enlaces y los comportamientos tengan un nombre.</span><span class="sxs-lookup"><span data-stu-id="1805d-126">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="1805d-127">Para obtener más información sobre la configuración predeterminada y los enlaces y comportamientos sin nombre, vea [configuración simplificada](../../../wcf/simplified-configuration.md) y [configuración simplificada para servicios WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="1805d-127">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="1805d-128">Valor de la estructura <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de apertura para completarse.</span><span class="sxs-lookup"><span data-stu-id="1805d-128">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="1805d-129">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="1805d-129">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="1805d-130">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="1805d-130">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="1805d-131">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de recepción para completarse.</span><span class="sxs-lookup"><span data-stu-id="1805d-131">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="1805d-132">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="1805d-132">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="1805d-133">El valor predeterminado es 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="1805d-133">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="1805d-134">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de envío para completarse.</span><span class="sxs-lookup"><span data-stu-id="1805d-134">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="1805d-135">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="1805d-135">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="1805d-136">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="1805d-136">The default is 00:01:00.</span></span>|  
|`textEncoding`|<span data-ttu-id="1805d-137">Establece el codificador del juego de caracteres que se va a usar para emitir los mensajes en el enlace.</span><span class="sxs-lookup"><span data-stu-id="1805d-137">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="1805d-138">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="1805d-138">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="1805d-139">-BigEndianUnicode: codificación Unicode BigEndian.</span><span class="sxs-lookup"><span data-stu-id="1805d-139">-   BigEndianUnicode: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="1805d-140">-Unicode: codificación de 16 bits.</span><span class="sxs-lookup"><span data-stu-id="1805d-140">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="1805d-141">-UTF8: codificación de 8 bits</span><span class="sxs-lookup"><span data-stu-id="1805d-141">-   UTF8: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="1805d-142">El valor predeterminado es UTF8.</span><span class="sxs-lookup"><span data-stu-id="1805d-142">The default is UTF8.</span></span> <span data-ttu-id="1805d-143">Este atributo es del tipo <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="1805d-143">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|`timeToLive`|<span data-ttu-id="1805d-144">Valor timespan que especifica el período de vida para el enlace.</span><span class="sxs-lookup"><span data-stu-id="1805d-144">A timespan value that specifies the time to live for the binding.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1805d-145">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="1805d-145">Child Elements</span></span>  
  
|<span data-ttu-id="1805d-146">Elemento</span><span class="sxs-lookup"><span data-stu-id="1805d-146">Element</span></span>|<span data-ttu-id="1805d-147">Descripción</span><span class="sxs-lookup"><span data-stu-id="1805d-147">Description</span></span>|  
|-------------|-----------------|  
|[\<readerQuotas>](/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="1805d-148">Define las restricciones en la complejidad de los mensajes SOAP que pueden ser procesados por los puntos de conexión configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="1805d-148">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="1805d-149">Este elemento es del tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="1805d-149">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1805d-150">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="1805d-150">Parent Elements</span></span>  
  
|<span data-ttu-id="1805d-151">Elemento</span><span class="sxs-lookup"><span data-stu-id="1805d-151">Element</span></span>|<span data-ttu-id="1805d-152">Descripción</span><span class="sxs-lookup"><span data-stu-id="1805d-152">Description</span></span>|  
|-------------|-----------------|  
|[\<bindings>](bindings.md)|<span data-ttu-id="1805d-153">Este elemento contiene una colección de enlaces estándar y personalizados.</span><span class="sxs-lookup"><span data-stu-id="1805d-153">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1805d-154">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1805d-154">Remarks</span></span>  

 <span data-ttu-id="1805d-155">El UdpBinding permite que los servicios de WCF se comuniquen sobre el transporte UDP.</span><span class="sxs-lookup"><span data-stu-id="1805d-155">The UdpBinding allows WCF services to communicate over the UDP transport.</span></span> <span data-ttu-id="1805d-156">Permite intercambios de mensajes "desencadenar y olvidar", donde un cliente envía un mensaje a un servicio y no espera ninguna respuesta.</span><span class="sxs-lookup"><span data-stu-id="1805d-156">It allows for "fire and forget" message exchanges where a client sends a message to a service and expects no response back.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1805d-157">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1805d-157">Example</span></span>  

 <span data-ttu-id="1805d-158">En el ejemplo siguiente se muestra cómo configurar <xref:System.ServiceModel.UdpBinding> mediante el `udpBinding` elemento> de <.</span><span class="sxs-lookup"><span data-stu-id="1805d-158">The following example shows how to configure the <xref:System.ServiceModel.UdpBinding> using the <`udpBinding`> element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1805d-159">Vea también</span><span class="sxs-lookup"><span data-stu-id="1805d-159">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>
- [<span data-ttu-id="1805d-160">Enlaces</span><span class="sxs-lookup"><span data-stu-id="1805d-160">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="1805d-161">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="1805d-161">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="1805d-162">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="1805d-162">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
