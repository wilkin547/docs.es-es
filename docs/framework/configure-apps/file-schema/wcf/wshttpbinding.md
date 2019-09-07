---
title: <wsHttpBinding>
ms.date: 03/30/2017
helpviewer_keywords:
- wsHttpBinding Element
ms.assetid: 0eee8ced-ad68-427d-b95a-97260e98deed
ms.openlocfilehash: fc86a97ebae160f5bf2c8fcb2df9295ed7803963
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399014"
---
# <a name="wshttpbinding"></a><span data-ttu-id="64a88-101">\<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="64a88-101">\<wsHttpBinding></span></span>
<span data-ttu-id="64a88-102">Define un enlace seguro, de confianza e interoperable, adecuado para contratos de servicio no dúplex.</span><span class="sxs-lookup"><span data-stu-id="64a88-102">Defines a secure, reliable, interoperable binding suitable for non-duplex service contracts.</span></span> <span data-ttu-id="64a88-103">El enlace implementa las siguientes especificaciones: WS-Reliable Messaging para confiabilidad y WS-Security para la seguridad y autenticación de mensajes.</span><span class="sxs-lookup"><span data-stu-id="64a88-103">The binding implements the following specifications: WS-Reliable Messaging for reliability, and WS-Security for message security and authentication.</span></span> <span data-ttu-id="64a88-104">El transporte es HTTP y la codificación del mensaje es codificación de texto/XML.</span><span class="sxs-lookup"><span data-stu-id="64a88-104">The transport is HTTP, and message encoding is Text/XML encoding.</span></span>  
  
<span data-ttu-id="64a88-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="64a88-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="64a88-106">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="64a88-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="64a88-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de enlaces**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="64a88-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="64a88-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<wsHttpBinding >**</span><span class="sxs-lookup"><span data-stu-id="64a88-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<wsHttpBinding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64a88-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="64a88-109">Syntax</span></span>  
  
```xml  
<wsHttpBinding>
  <binding allowCookies="Boolean"
           bypassProxyOnLocal="Boolean"
           closeTimeout="TimeSpan"
           hostNameComparisonMode="StrongWildCard/Exact/WeakWildcard"
           maxBufferPoolSize="integer"
           maxReceivedMessageSize="Integer"
           messageEncoding="Text/Mtom"
           name="string"
           openTimeout="TimeSpan"
           proxyAddress="URI"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan"
           textEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding"
           transactionFlow="Boolean"
           useDefaultWebProxy="Boolean">
    <reliableSession ordered="Boolean"
                     inactivityTimeout="TimeSpan"
                     enabled="Boolean" />
    <security mode="Message/None/Transport/TransportWithCredential">
      <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
                 proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
                 realm="string" />
      <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"
               establishSecurityContext="Boolean"
               negotiateServiceCredential="Boolean" />
    </security>
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</wsHttpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="64a88-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="64a88-110">Attributes and Elements</span></span>  
 <span data-ttu-id="64a88-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="64a88-111">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="64a88-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="64a88-112">Attributes</span></span>  
  
|<span data-ttu-id="64a88-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="64a88-113">Attribute</span></span>|<span data-ttu-id="64a88-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="64a88-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="64a88-115">allowCookies</span><span class="sxs-lookup"><span data-stu-id="64a88-115">allowCookies</span></span>|<span data-ttu-id="64a88-116">Valor de tipo booleano que indica si el cliente acepta las cookies y las propaga en solicitudes futuras.</span><span class="sxs-lookup"><span data-stu-id="64a88-116">A Boolean value that indicates whether the client accepts cookies and propagates them on future requests.</span></span> <span data-ttu-id="64a88-117">El valor predeterminado es false.</span><span class="sxs-lookup"><span data-stu-id="64a88-117">The default is false.</span></span><br /><br /> <span data-ttu-id="64a88-118">Puede utilizar esta propiedad al interactuar con los servicios Web ASMX que utilizan cookies.</span><span class="sxs-lookup"><span data-stu-id="64a88-118">You can use this property when you interact with ASMX Web services that use cookies.</span></span> <span data-ttu-id="64a88-119">De esta manera, puede estar seguro de que las cookies devueltas del servidor se copian automáticamente en todas las solicitudes de cliente futuras para ese servicio.</span><span class="sxs-lookup"><span data-stu-id="64a88-119">In this way, you can be sure that the cookies returned from the server are automatically copied to all future client requests for that service.</span></span>|  
|<span data-ttu-id="64a88-120">bypassProxyOnLocal</span><span class="sxs-lookup"><span data-stu-id="64a88-120">bypassProxyOnLocal</span></span>|<span data-ttu-id="64a88-121">Valor de tipo booleano que indica si se omitirá el servidor proxy para las direcciones locales.</span><span class="sxs-lookup"><span data-stu-id="64a88-121">A Boolean value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="64a88-122">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="64a88-122">The default is `false`.</span></span>|  
|<span data-ttu-id="64a88-123">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="64a88-123">closeTimeout</span></span>|<span data-ttu-id="64a88-124">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de cierre para completarse.</span><span class="sxs-lookup"><span data-stu-id="64a88-124">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="64a88-125">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="64a88-125">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="64a88-126">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="64a88-126">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="64a88-127">hostnameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="64a88-127">hostnameComparisonMode</span></span>|<span data-ttu-id="64a88-128">Especifica el modo de comparación de nombres de host HTTP usado para analizar los URI.</span><span class="sxs-lookup"><span data-stu-id="64a88-128">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="64a88-129">Este atributo es del tipo <xref:System.ServiceModel.HostNameComparisonMode>, que indica si se va a utilizar el nombre del host para llegar al servicio cuando coincida en el URI.</span><span class="sxs-lookup"><span data-stu-id="64a88-129">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="64a88-130">El valor predeterminado es <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, que omite el nombre del host en la coincidencia.</span><span class="sxs-lookup"><span data-stu-id="64a88-130">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|  
|<span data-ttu-id="64a88-131">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="64a88-131">maxBufferPoolSize</span></span>|<span data-ttu-id="64a88-132">Entero que especifica el tamaño máximo del grupo de búferes para este enlace.</span><span class="sxs-lookup"><span data-stu-id="64a88-132">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="64a88-133">El valor predeterminado es 524.288 bytes (512x1024).</span><span class="sxs-lookup"><span data-stu-id="64a88-133">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="64a88-134">En muchas partes de Windows Communication Foundation (WCF) se utilizan búferes.</span><span class="sxs-lookup"><span data-stu-id="64a88-134">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="64a88-135">Crear y destruir búferes cada vez que se usan es caro, y la recolección de elementos no utilizados para los búferes también es cara.</span><span class="sxs-lookup"><span data-stu-id="64a88-135">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="64a88-136">Con grupos de búferes, puede tomar un búfer del grupo, usarlo y devolverlo al grupo una vez haya terminado.</span><span class="sxs-lookup"><span data-stu-id="64a88-136">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="64a88-137">Así se evita la sobrecarga al crear y destruir búferes.</span><span class="sxs-lookup"><span data-stu-id="64a88-137">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="64a88-138">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="64a88-138">maxReceivedMessageSize</span></span>|<span data-ttu-id="64a88-139">Entero positivo que especifica el tamaño máximo del mensaje, en bytes, incluidos los encabezados, que se puede recibir en un canal configurado con este enlace.</span><span class="sxs-lookup"><span data-stu-id="64a88-139">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="64a88-140">El remitente de un mensaje que supere este límite recibirá un error SOAP.</span><span class="sxs-lookup"><span data-stu-id="64a88-140">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="64a88-141">El destinatario quita el mensaje y crea una entrada del evento en el registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="64a88-141">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="64a88-142">El valor predeterminado es 65536.</span><span class="sxs-lookup"><span data-stu-id="64a88-142">The default is 65536.</span></span>|  
|<span data-ttu-id="64a88-143">messageEncoding</span><span class="sxs-lookup"><span data-stu-id="64a88-143">messageEncoding</span></span>|<span data-ttu-id="64a88-144">Define el codificador utilizado para codificar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="64a88-144">Defines the encoder used to encode the message.</span></span> <span data-ttu-id="64a88-145">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="64a88-145">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="64a88-146">Negrita Use un codificador de mensajes de texto.</span><span class="sxs-lookup"><span data-stu-id="64a88-146">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="64a88-147">MTOM Use un codificador del mecanismo de la organización de transmisión de mensajes 1,0 (MTOM).</span><span class="sxs-lookup"><span data-stu-id="64a88-147">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><span data-ttu-id="64a88-148">-El valor predeterminado es texto.</span><span class="sxs-lookup"><span data-stu-id="64a88-148">-   The default is Text.</span></span><br /><br /> <span data-ttu-id="64a88-149">Este atributo es del tipo <xref:System.ServiceModel.WSMessageEncoding>.</span><span class="sxs-lookup"><span data-stu-id="64a88-149">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|  
|<span data-ttu-id="64a88-150">name</span><span class="sxs-lookup"><span data-stu-id="64a88-150">name</span></span>|<span data-ttu-id="64a88-151">Cadena que contiene el nombre de configuración del enlace.</span><span class="sxs-lookup"><span data-stu-id="64a88-151">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="64a88-152">Este valor debe ser único porque se usa como identificación del enlace.</span><span class="sxs-lookup"><span data-stu-id="64a88-152">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="64a88-153">A partir de [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], no es necesario que los enlaces y los comportamientos tengan nombre.</span><span class="sxs-lookup"><span data-stu-id="64a88-153">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="64a88-154">Para obtener más información sobre la configuración predeterminada y los enlaces y comportamientos sin nombre, vea [configuración simplificada](../../../wcf/simplified-configuration.md) y [configuración simplificada para servicios WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="64a88-154">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|<span data-ttu-id="64a88-155">openTimeout</span><span class="sxs-lookup"><span data-stu-id="64a88-155">openTimeout</span></span>|<span data-ttu-id="64a88-156">Valor de la estructura <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de apertura para completarse.</span><span class="sxs-lookup"><span data-stu-id="64a88-156">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="64a88-157">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="64a88-157">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="64a88-158">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="64a88-158">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="64a88-159">proxyAddress</span><span class="sxs-lookup"><span data-stu-id="64a88-159">proxyAddress</span></span>|<span data-ttu-id="64a88-160">Un URI que especifica la dirección del proxy HTTP.</span><span class="sxs-lookup"><span data-stu-id="64a88-160">A URI that specifies the address of the HTTP proxy.</span></span> <span data-ttu-id="64a88-161">Si `useSystemWebProxy` es `true`, este valor debe ser `null`.</span><span class="sxs-lookup"><span data-stu-id="64a88-161">If `useSystemWebProxy` is `true`, this setting must be `null`.</span></span> <span data-ttu-id="64a88-162">El valor predeterminado es `null`.</span><span class="sxs-lookup"><span data-stu-id="64a88-162">The default is `null`.</span></span>|  
|<span data-ttu-id="64a88-163">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="64a88-163">receiveTimeout</span></span>|<span data-ttu-id="64a88-164">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de recepción para completarse.</span><span class="sxs-lookup"><span data-stu-id="64a88-164">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="64a88-165">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="64a88-165">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="64a88-166">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="64a88-166">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="64a88-167">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="64a88-167">sendTimeout</span></span>|<span data-ttu-id="64a88-168">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de envío para completarse.</span><span class="sxs-lookup"><span data-stu-id="64a88-168">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="64a88-169">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="64a88-169">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="64a88-170">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="64a88-170">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="64a88-171">textEncoding</span><span class="sxs-lookup"><span data-stu-id="64a88-171">textEncoding</span></span>|<span data-ttu-id="64a88-172">Especifica el codificador del juego de caracteres que se va a usar para emitir los mensajes en el enlace.</span><span class="sxs-lookup"><span data-stu-id="64a88-172">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="64a88-173">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="64a88-173">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="64a88-174">UnicodeFffeTextEncoding Codificación Unicode BigEndian.</span><span class="sxs-lookup"><span data-stu-id="64a88-174">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="64a88-175">Utf16TextEncoding codificación de 16 bits.</span><span class="sxs-lookup"><span data-stu-id="64a88-175">-   Utf16TextEncoding: 16-bit encoding.</span></span><br /><span data-ttu-id="64a88-176">Utf8TextEncoding codificación de 8 bits.</span><span class="sxs-lookup"><span data-stu-id="64a88-176">-   Utf8TextEncoding: 8-bit encoding.</span></span><br /><br /> <span data-ttu-id="64a88-177">El valor predeterminado es Utf8TextEncoding.</span><span class="sxs-lookup"><span data-stu-id="64a88-177">The default is Utf8TextEncoding.</span></span><br /><br /> <span data-ttu-id="64a88-178">Este atributo es del tipo <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="64a88-178">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|<span data-ttu-id="64a88-179">transactionFlow</span><span class="sxs-lookup"><span data-stu-id="64a88-179">transactionFlow</span></span>|<span data-ttu-id="64a88-180">Valor booleano que especifica si el enlace admite las transacciones WS del flujo.</span><span class="sxs-lookup"><span data-stu-id="64a88-180">A Boolean value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="64a88-181">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="64a88-181">The default is `false`.</span></span>|  
|<span data-ttu-id="64a88-182">useDefaultWebProxy</span><span class="sxs-lookup"><span data-stu-id="64a88-182">useDefaultWebProxy</span></span>|<span data-ttu-id="64a88-183">Valor de tipo booleano que especifica si se utiliza el proxy HTTP del sistema configurado automáticamente.</span><span class="sxs-lookup"><span data-stu-id="64a88-183">A Boolean value that specifies whether the system’s auto-configured HTTP proxy is used.</span></span> <span data-ttu-id="64a88-184">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="64a88-184">The default is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="64a88-185">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="64a88-185">Child Elements</span></span>  
  
|<span data-ttu-id="64a88-186">Elemento</span><span class="sxs-lookup"><span data-stu-id="64a88-186">Element</span></span>|<span data-ttu-id="64a88-187">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="64a88-187">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="64a88-188">\<security></span><span class="sxs-lookup"><span data-stu-id="64a88-188">\<security></span></span>](security-of-wshttpbinding.md)|<span data-ttu-id="64a88-189">Define la configuración de seguridad del enlace.</span><span class="sxs-lookup"><span data-stu-id="64a88-189">Defines the security settings for the binding.</span></span> <span data-ttu-id="64a88-190">Este elemento es del tipo <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="64a88-190">This element is of type <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>.</span></span>|  
|<span data-ttu-id="64a88-191">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="64a88-191">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="64a88-192">Define las restricciones en la complejidad de los mensajes SOAP que pueden ser procesados por los puntos de conexión configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="64a88-192">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="64a88-193">Este elemento es del tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="64a88-193">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|<span data-ttu-id="64a88-194">[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="64a88-194">[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))</span></span>|<span data-ttu-id="64a88-195">Especifica si se establecen sesiones confiables entre los puntos de conexión del canal.</span><span class="sxs-lookup"><span data-stu-id="64a88-195">Specifies if reliable sessions are established between channel endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="64a88-196">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="64a88-196">Parent Elements</span></span>  
  
|<span data-ttu-id="64a88-197">Elemento</span><span class="sxs-lookup"><span data-stu-id="64a88-197">Element</span></span>|<span data-ttu-id="64a88-198">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="64a88-198">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="64a88-199">\<bindings></span><span class="sxs-lookup"><span data-stu-id="64a88-199">\<bindings></span></span>](bindings.md)|<span data-ttu-id="64a88-200">Este elemento contiene una colección de enlaces estándar y personalizados.</span><span class="sxs-lookup"><span data-stu-id="64a88-200">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="64a88-201">Comentarios</span><span class="sxs-lookup"><span data-stu-id="64a88-201">Remarks</span></span>  
 <span data-ttu-id="64a88-202">La clase `WSHttpBinding` es similar a la clase `BasicHttpBinding` pero proporciona más características de servicios Web.</span><span class="sxs-lookup"><span data-stu-id="64a88-202">The `WSHttpBinding` is similar to the `BasicHttpBinding` but provides more Web service features.</span></span> <span data-ttu-id="64a88-203">Utiliza el transporte HTTP y proporciona seguridad para mensajes, como BasicHttpBinding, pero también proporciona transacciones, mensajería confiable y WS-Addressing, habilitada de forma predeterminada o disponible mediante un valor de control único.</span><span class="sxs-lookup"><span data-stu-id="64a88-203">It uses the HTTP transport and provides message security, as does BasicHttpBinding, but it also provides transactions, reliable messaging, and WS-Addressing, either enabled by default or available through a single control setting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="64a88-204">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="64a88-204">Example</span></span>  
  
```xml  
<configuration>
  <system.ServiceModel>
    <bindings>
      <wsHttpBinding>
        <binding closeTimeout="00:00:10"
                 openTimeout="00:00:20"
                 receiveTimeout="00:00:30"
                 sendTimeout="00:00:40"
                 bypassProxyOnLocal="false"
                 transactionFlow="false"
                 hostNameComparisonMode="WeakWildcard"
                 maxReceivedMessageSize="1000"
                 messageEncoding="Mtom"
                 proxyAddress="http://foo/bar"
                 textEncoding="utf-16"
                 useDefaultWebProxy="false">
          <reliableSession ordered="false"
                           inactivityTimeout="00:02:00"
                           enabled="true" />
          <security mode="Transport">
            <transport clientCredentialType="Digest"
                       proxyCredentialType="None"
                       realm="someRealm" />
            <message clientCredentialType="Windows"
                     negotiateServiceCredential="false"
                     algorithmSuite="Aes128"
                     defaultProtectionLevel="None" />
          </security>
        </binding>
      </wsHttpBinding>
    </bindings>
  </system.ServiceModel>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="64a88-205">Vea también</span><span class="sxs-lookup"><span data-stu-id="64a88-205">See also</span></span>

- <xref:System.ServiceModel.WSHttpBinding>
- <xref:System.ServiceModel.Configuration.WSHttpBindingElement>
- [<span data-ttu-id="64a88-206">Enlaces</span><span class="sxs-lookup"><span data-stu-id="64a88-206">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="64a88-207">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="64a88-207">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="64a88-208">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="64a88-208">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="64a88-209">\<binding></span><span class="sxs-lookup"><span data-stu-id="64a88-209">\<binding></span></span>](../../../misc/binding.md)
