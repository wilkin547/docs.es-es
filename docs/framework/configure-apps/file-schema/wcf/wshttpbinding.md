---
title: <wsHttpBinding>
description: Define un enlace HTTP seguro, confiable e interoperable adecuado para contratos de servicio no dúplex, que implementa la mensajería WS-Reliable Messaging y WS-Security.
ms.date: 03/30/2017
helpviewer_keywords:
- wsHttpBinding Element
ms.assetid: 0eee8ced-ad68-427d-b95a-97260e98deed
ms.openlocfilehash: d603f699145622cb1b70ecf99ea542572e841eac
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85243989"
---
# \<wsHttpBinding>
<span data-ttu-id="d5789-102">Define un enlace seguro, de confianza e interoperable, adecuado para contratos de servicio no dúplex.</span><span class="sxs-lookup"><span data-stu-id="d5789-102">Defines a secure, reliable, interoperable binding suitable for non-duplex service contracts.</span></span> <span data-ttu-id="d5789-103">El enlace implementa las características siguientes: WS-Reliable Messaging para confiabilidad y WS-Security para la seguridad del mensaje y autenticación.</span><span class="sxs-lookup"><span data-stu-id="d5789-103">The binding implements the following specifications: WS-Reliable Messaging for reliability, and WS-Security for message security and authentication.</span></span> <span data-ttu-id="d5789-104">El transporte es HTTP y la codificación del mensaje es codificación de texto/XML.</span><span class="sxs-lookup"><span data-stu-id="d5789-104">The transport is HTTP, and message encoding is Text/XML encoding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<wsHttpBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="d5789-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d5789-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d5789-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d5789-106">Attributes and Elements</span></span>  
 <span data-ttu-id="d5789-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d5789-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d5789-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="d5789-108">Attributes</span></span>  
  
|<span data-ttu-id="d5789-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="d5789-109">Attribute</span></span>|<span data-ttu-id="d5789-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="d5789-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d5789-111">allowCookies</span><span class="sxs-lookup"><span data-stu-id="d5789-111">allowCookies</span></span>|<span data-ttu-id="d5789-112">Valor de tipo booleano que indica si el cliente acepta las cookies y las propaga en solicitudes futuras.</span><span class="sxs-lookup"><span data-stu-id="d5789-112">A Boolean value that indicates whether the client accepts cookies and propagates them on future requests.</span></span> <span data-ttu-id="d5789-113">El valor predeterminado es false.</span><span class="sxs-lookup"><span data-stu-id="d5789-113">The default is false.</span></span><br /><br /> <span data-ttu-id="d5789-114">Puede utilizar esta propiedad al interactuar con los servicios Web ASMX que utilizan cookies.</span><span class="sxs-lookup"><span data-stu-id="d5789-114">You can use this property when you interact with ASMX Web services that use cookies.</span></span> <span data-ttu-id="d5789-115">De esta manera, puede estar seguro de que las cookies devueltas del servidor se copian automáticamente en todas las solicitudes de cliente futuras para ese servicio.</span><span class="sxs-lookup"><span data-stu-id="d5789-115">In this way, you can be sure that the cookies returned from the server are automatically copied to all future client requests for that service.</span></span>|  
|<span data-ttu-id="d5789-116">bypassProxyOnLocal</span><span class="sxs-lookup"><span data-stu-id="d5789-116">bypassProxyOnLocal</span></span>|<span data-ttu-id="d5789-117">Valor de tipo booleano que indica si se omitirá el servidor proxy para las direcciones locales.</span><span class="sxs-lookup"><span data-stu-id="d5789-117">A Boolean value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="d5789-118">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="d5789-118">The default is `false`.</span></span>|  
|<span data-ttu-id="d5789-119">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="d5789-119">closeTimeout</span></span>|<span data-ttu-id="d5789-120">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de cierre para completarse.</span><span class="sxs-lookup"><span data-stu-id="d5789-120">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="d5789-121">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="d5789-121">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="d5789-122">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="d5789-122">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="d5789-123">hostnameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="d5789-123">hostnameComparisonMode</span></span>|<span data-ttu-id="d5789-124">Especifica el modo de comparación de nombres de host HTTP usado para analizar los URI.</span><span class="sxs-lookup"><span data-stu-id="d5789-124">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="d5789-125">Este atributo es del tipo <xref:System.ServiceModel.HostNameComparisonMode>, que indica si se va a utilizar el nombre del host para llegar al servicio cuando coincida en el URI.</span><span class="sxs-lookup"><span data-stu-id="d5789-125">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="d5789-126">El valor predeterminado es <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, que omite el nombre del host en la coincidencia.</span><span class="sxs-lookup"><span data-stu-id="d5789-126">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|  
|<span data-ttu-id="d5789-127">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="d5789-127">maxBufferPoolSize</span></span>|<span data-ttu-id="d5789-128">Entero que especifica el tamaño máximo del grupo de búferes para este enlace.</span><span class="sxs-lookup"><span data-stu-id="d5789-128">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="d5789-129">El valor predeterminado es 524.288 bytes (512x1024).</span><span class="sxs-lookup"><span data-stu-id="d5789-129">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="d5789-130">En muchas partes de Windows Communication Foundation (WCF) se utilizan búferes.</span><span class="sxs-lookup"><span data-stu-id="d5789-130">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="d5789-131">Crear y destruir búferes cada vez que se usan es caro, y la recolección de elementos no utilizados para los búferes también es cara.</span><span class="sxs-lookup"><span data-stu-id="d5789-131">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="d5789-132">Con grupos de búferes, puede tomar un búfer del grupo, usarlo y devolverlo al grupo una vez haya terminado.</span><span class="sxs-lookup"><span data-stu-id="d5789-132">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="d5789-133">Así se evita la sobrecarga al crear y destruir búferes.</span><span class="sxs-lookup"><span data-stu-id="d5789-133">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="d5789-134">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="d5789-134">maxReceivedMessageSize</span></span>|<span data-ttu-id="d5789-135">Entero positivo que especifica el tamaño máximo del mensaje, en bytes, incluidos los encabezados, que se puede recibir en un canal configurado con este enlace.</span><span class="sxs-lookup"><span data-stu-id="d5789-135">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="d5789-136">El remitente de un mensaje que supere este límite recibirá un error SOAP.</span><span class="sxs-lookup"><span data-stu-id="d5789-136">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="d5789-137">El destinatario quita el mensaje y crea una entrada del evento en el registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="d5789-137">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="d5789-138">El valor predeterminado es 65536.</span><span class="sxs-lookup"><span data-stu-id="d5789-138">The default is 65536.</span></span>|  
|<span data-ttu-id="d5789-139">messageEncoding</span><span class="sxs-lookup"><span data-stu-id="d5789-139">messageEncoding</span></span>|<span data-ttu-id="d5789-140">Define el codificador utilizado para codificar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="d5789-140">Defines the encoder used to encode the message.</span></span> <span data-ttu-id="d5789-141">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="d5789-141">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="d5789-142">-Text: usar un codificador de mensajes de texto.</span><span class="sxs-lookup"><span data-stu-id="d5789-142">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="d5789-143">-MTOM: usar un codificador del mecanismo de la organización de transmisión de mensajes 1,0 (MTOM).</span><span class="sxs-lookup"><span data-stu-id="d5789-143">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><span data-ttu-id="d5789-144">-El valor predeterminado es texto.</span><span class="sxs-lookup"><span data-stu-id="d5789-144">-   The default is Text.</span></span><br /><br /> <span data-ttu-id="d5789-145">Este atributo es del tipo <xref:System.ServiceModel.WSMessageEncoding>.</span><span class="sxs-lookup"><span data-stu-id="d5789-145">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|  
|<span data-ttu-id="d5789-146">name</span><span class="sxs-lookup"><span data-stu-id="d5789-146">name</span></span>|<span data-ttu-id="d5789-147">Cadena que contiene el nombre de configuración del enlace.</span><span class="sxs-lookup"><span data-stu-id="d5789-147">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="d5789-148">Este valor debe ser único porque se usa como identificación del enlace.</span><span class="sxs-lookup"><span data-stu-id="d5789-148">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="d5789-149">A partir de .NET Framework 4, no es necesario que los enlaces y los comportamientos tengan un nombre.</span><span class="sxs-lookup"><span data-stu-id="d5789-149">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="d5789-150">Para obtener más información sobre la configuración predeterminada y los enlaces y comportamientos sin nombre, vea [configuración simplificada](../../../wcf/simplified-configuration.md) y [configuración simplificada para servicios WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="d5789-150">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|<span data-ttu-id="d5789-151">openTimeout</span><span class="sxs-lookup"><span data-stu-id="d5789-151">openTimeout</span></span>|<span data-ttu-id="d5789-152">Valor de la estructura <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de apertura para completarse.</span><span class="sxs-lookup"><span data-stu-id="d5789-152">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="d5789-153">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="d5789-153">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="d5789-154">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="d5789-154">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="d5789-155">proxyAddress</span><span class="sxs-lookup"><span data-stu-id="d5789-155">proxyAddress</span></span>|<span data-ttu-id="d5789-156">Un URI que especifica la dirección del proxy HTTP.</span><span class="sxs-lookup"><span data-stu-id="d5789-156">A URI that specifies the address of the HTTP proxy.</span></span> <span data-ttu-id="d5789-157">Si `useSystemWebProxy` es `true`, este valor debe ser `null`.</span><span class="sxs-lookup"><span data-stu-id="d5789-157">If `useSystemWebProxy` is `true`, this setting must be `null`.</span></span> <span data-ttu-id="d5789-158">De manera predeterminada, es `null`.</span><span class="sxs-lookup"><span data-stu-id="d5789-158">The default is `null`.</span></span>|  
|<span data-ttu-id="d5789-159">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="d5789-159">receiveTimeout</span></span>|<span data-ttu-id="d5789-160">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de recepción para completarse.</span><span class="sxs-lookup"><span data-stu-id="d5789-160">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="d5789-161">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="d5789-161">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="d5789-162">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="d5789-162">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="d5789-163">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="d5789-163">sendTimeout</span></span>|<span data-ttu-id="d5789-164">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de envío para completarse.</span><span class="sxs-lookup"><span data-stu-id="d5789-164">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="d5789-165">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="d5789-165">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="d5789-166">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="d5789-166">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="d5789-167">textEncoding</span><span class="sxs-lookup"><span data-stu-id="d5789-167">textEncoding</span></span>|<span data-ttu-id="d5789-168">Especifica el codificador del juego de caracteres que se va a usar para emitir los mensajes en el enlace.</span><span class="sxs-lookup"><span data-stu-id="d5789-168">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="d5789-169">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="d5789-169">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="d5789-170">-UnicodeFffeTextEncoding: codificación Unicode BigEndian.</span><span class="sxs-lookup"><span data-stu-id="d5789-170">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="d5789-171">-Utf16TextEncoding: codificación de 16 bits.</span><span class="sxs-lookup"><span data-stu-id="d5789-171">-   Utf16TextEncoding: 16-bit encoding.</span></span><br /><span data-ttu-id="d5789-172">-Utf8TextEncoding: codificación de 8 bits.</span><span class="sxs-lookup"><span data-stu-id="d5789-172">-   Utf8TextEncoding: 8-bit encoding.</span></span><br /><br /> <span data-ttu-id="d5789-173">El valor predeterminado es Utf8TextEncoding.</span><span class="sxs-lookup"><span data-stu-id="d5789-173">The default is Utf8TextEncoding.</span></span><br /><br /> <span data-ttu-id="d5789-174">Este atributo es del tipo <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="d5789-174">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|<span data-ttu-id="d5789-175">transactionFlow</span><span class="sxs-lookup"><span data-stu-id="d5789-175">transactionFlow</span></span>|<span data-ttu-id="d5789-176">Valor booleano que especifica si el enlace admite las transacciones WS del flujo.</span><span class="sxs-lookup"><span data-stu-id="d5789-176">A Boolean value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="d5789-177">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="d5789-177">The default is `false`.</span></span>|  
|<span data-ttu-id="d5789-178">useDefaultWebProxy</span><span class="sxs-lookup"><span data-stu-id="d5789-178">useDefaultWebProxy</span></span>|<span data-ttu-id="d5789-179">Valor de tipo booleano que especifica si se utiliza el proxy HTTP del sistema configurado automáticamente.</span><span class="sxs-lookup"><span data-stu-id="d5789-179">A Boolean value that specifies whether the system’s auto-configured HTTP proxy is used.</span></span> <span data-ttu-id="d5789-180">De manera predeterminada, es `true`.</span><span class="sxs-lookup"><span data-stu-id="d5789-180">The default is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d5789-181">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d5789-181">Child Elements</span></span>  
  
|<span data-ttu-id="d5789-182">Elemento</span><span class="sxs-lookup"><span data-stu-id="d5789-182">Element</span></span>|<span data-ttu-id="d5789-183">Descripción</span><span class="sxs-lookup"><span data-stu-id="d5789-183">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-wshttpbinding.md)|<span data-ttu-id="d5789-184">Define la configuración de seguridad del enlace.</span><span class="sxs-lookup"><span data-stu-id="d5789-184">Defines the security settings for the binding.</span></span> <span data-ttu-id="d5789-185">Este elemento es del tipo <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="d5789-185">This element is of type <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>.</span></span>|  
|[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="d5789-186">Define las restricciones en la complejidad de los mensajes SOAP que pueden ser procesados por los puntos de conexión configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="d5789-186">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="d5789-187">Este elemento es del tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="d5789-187">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))|<span data-ttu-id="d5789-188">Especifica si se establecen sesiones confiables entre los puntos de conexión del canal.</span><span class="sxs-lookup"><span data-stu-id="d5789-188">Specifies if reliable sessions are established between channel endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d5789-189">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d5789-189">Parent Elements</span></span>  
  
|<span data-ttu-id="d5789-190">Elemento</span><span class="sxs-lookup"><span data-stu-id="d5789-190">Element</span></span>|<span data-ttu-id="d5789-191">Descripción</span><span class="sxs-lookup"><span data-stu-id="d5789-191">Description</span></span>|  
|-------------|-----------------|  
|[\<bindings>](bindings.md)|<span data-ttu-id="d5789-192">Este elemento contiene una colección de enlaces estándar y personalizados.</span><span class="sxs-lookup"><span data-stu-id="d5789-192">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d5789-193">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d5789-193">Remarks</span></span>  
 <span data-ttu-id="d5789-194">La clase `WSHttpBinding` es similar a la clase `BasicHttpBinding` pero proporciona más características de servicios Web.</span><span class="sxs-lookup"><span data-stu-id="d5789-194">The `WSHttpBinding` is similar to the `BasicHttpBinding` but provides more Web service features.</span></span> <span data-ttu-id="d5789-195">Utiliza el transporte HTTP y proporciona seguridad para mensajes, como BasicHttpBinding, pero también proporciona transacciones, mensajería confiable y WS-Addressing, habilitada de forma predeterminada o disponible mediante un valor de control único.</span><span class="sxs-lookup"><span data-stu-id="d5789-195">It uses the HTTP transport and provides message security, as does BasicHttpBinding, but it also provides transactions, reliable messaging, and WS-Addressing, either enabled by default or available through a single control setting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d5789-196">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d5789-196">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d5789-197">Vea también</span><span class="sxs-lookup"><span data-stu-id="d5789-197">See also</span></span>

- <xref:System.ServiceModel.WSHttpBinding>
- <xref:System.ServiceModel.Configuration.WSHttpBindingElement>
- [<span data-ttu-id="d5789-198">Enlaces</span><span class="sxs-lookup"><span data-stu-id="d5789-198">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="d5789-199">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="d5789-199">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="d5789-200">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="d5789-200">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
