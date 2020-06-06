---
title: <wsDualHttpBinding>
ms.date: 03/30/2017
helpviewer_keywords:
- wsDualHttpBinding Element
ms.assetid: fd8ac4e2-5641-473b-9115-73f14ab1c065
ms.openlocfilehash: 01360ae8288b3cb7374597ad77935f634eb0a519
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "74139272"
---
# \<wsDualHttpBinding>
<span data-ttu-id="c7b84-101">Define un enlace seguro, de confianza e interoperable que es apropiado para contratos de servicios dúplex o comunicación a través de los intermediarios de SOAP.</span><span class="sxs-lookup"><span data-stu-id="c7b84-101">Defines a secure, reliable and interoperable binding that is suitable for duplex service contracts or communication through SOAP intermediaries.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<wsDualHttpBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="c7b84-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c7b84-102">Syntax</span></span>  
  
```xml  
<wsDualHttpBinding>
  <binding name="String"
          closeTimeout="TimeSpan"
          openTimeout="TimeSpan"
          receiveTimeout="TimeSpan"
          sendTimeout="TimeSpan"
          bypassProxyOnLocal="Boolean"
          clientBaseAddress="URI"
          transactionFlow="Boolean"
          hostNameComparisonMode="StrongWildCard/Exact/WeakWildcard"
          maxBufferPoolSize="integer"
          maxReceivedMessageSize="Integer"
          messageEncoding="Text/Mtom"
          proxyAddress="URI"
          textEncoding="Unicode/BigEndianUnicode/UTF8"
          useDefaultWebProxy="Boolean">
    <reliableSession ordered="Boolean"
                     inactivityTimeout="TimeSpan" />
    <security mode="None/Message">
      <message clientCredentialType="None/Windows/UserName/Certificate/CardSpace"
               negotiateServiceCredential="Boolean"
               algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15" />
    </security>
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</wsDualHttpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c7b84-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c7b84-103">Attributes and Elements</span></span>  
 <span data-ttu-id="c7b84-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c7b84-104">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c7b84-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="c7b84-105">Attributes</span></span>  
  
|<span data-ttu-id="c7b84-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="c7b84-106">Attribute</span></span>|<span data-ttu-id="c7b84-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="c7b84-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c7b84-108">bypassProxyOnLocal</span><span class="sxs-lookup"><span data-stu-id="c7b84-108">bypassProxyOnLocal</span></span>|<span data-ttu-id="c7b84-109">Valor de tipo booleano que indica si se omitirá el servidor proxy para las direcciones locales.</span><span class="sxs-lookup"><span data-stu-id="c7b84-109">A Boolean value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="c7b84-110">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="c7b84-110">The default is `false`.</span></span>|  
|<span data-ttu-id="c7b84-111">clientBaseAddress</span><span class="sxs-lookup"><span data-stu-id="c7b84-111">clientBaseAddress</span></span>|<span data-ttu-id="c7b84-112">Un URI que establece la dirección base que el cliente escucha para los mensajes de respuesta del servicio.</span><span class="sxs-lookup"><span data-stu-id="c7b84-112">A URI that sets the base address that the client listens to for response messages from the service.</span></span> <span data-ttu-id="c7b84-113">Si se especifica, esta dirección (más una por channelGUID) se utiliza para realizar escuchas.</span><span class="sxs-lookup"><span data-stu-id="c7b84-113">If specified, this address (plus a per-channelGUID) is used for listening.</span></span> <span data-ttu-id="c7b84-114">Si no se especifica el valor, la dirección base de clientes se genera de una manera específica del transporte.</span><span class="sxs-lookup"><span data-stu-id="c7b84-114">If the value is not specified, the client base address is generated in a transport-specific manner.</span></span> <span data-ttu-id="c7b84-115">De manera predeterminada, es `null`.</span><span class="sxs-lookup"><span data-stu-id="c7b84-115">The default is `null`.</span></span>|  
|<span data-ttu-id="c7b84-116">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="c7b84-116">closeTimeout</span></span>|<span data-ttu-id="c7b84-117">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de cierre para completarse.</span><span class="sxs-lookup"><span data-stu-id="c7b84-117">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="c7b84-118">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="c7b84-118">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="c7b84-119">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="c7b84-119">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="c7b84-120">hostnameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="c7b84-120">hostnameComparisonMode</span></span>|<span data-ttu-id="c7b84-121">Especifica el modo de comparación de nombres de host HTTP usado para analizar los URI.</span><span class="sxs-lookup"><span data-stu-id="c7b84-121">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="c7b84-122">Este atributo es del tipo <xref:System.ServiceModel.HostNameComparisonMode>, que indica si se va a utilizar el nombre del host para llegar al servicio cuando coincida en el URI.</span><span class="sxs-lookup"><span data-stu-id="c7b84-122">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="c7b84-123">El valor predeterminado es <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, que omite el nombre del host en la coincidencia.</span><span class="sxs-lookup"><span data-stu-id="c7b84-123">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|  
|<span data-ttu-id="c7b84-124">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="c7b84-124">maxBufferPoolSize</span></span>|<span data-ttu-id="c7b84-125">Entero que especifica el tamaño máximo del grupo de búferes para este enlace.</span><span class="sxs-lookup"><span data-stu-id="c7b84-125">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="c7b84-126">El valor predeterminado es 524.288 bytes (512x1024).</span><span class="sxs-lookup"><span data-stu-id="c7b84-126">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="c7b84-127">En muchas partes de Windows Communication Foundation (WCF) se utilizan búferes.</span><span class="sxs-lookup"><span data-stu-id="c7b84-127">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="c7b84-128">Crear y destruir búferes cada vez que se usan es caro, y la recolección de elementos no utilizados para los búferes también es cara.</span><span class="sxs-lookup"><span data-stu-id="c7b84-128">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="c7b84-129">Con grupos de búferes, puede tomar un búfer del grupo, usarlo y devolverlo al grupo una vez haya terminado.</span><span class="sxs-lookup"><span data-stu-id="c7b84-129">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="c7b84-130">Así se evita la sobrecarga al crear y destruir búferes.</span><span class="sxs-lookup"><span data-stu-id="c7b84-130">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="c7b84-131">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="c7b84-131">maxReceivedMessageSize</span></span>|<span data-ttu-id="c7b84-132">Entero positivo que especifica el tamaño máximo del mensaje, en bytes, incluidos los encabezados, que se puede recibir en un canal configurado con este enlace.</span><span class="sxs-lookup"><span data-stu-id="c7b84-132">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="c7b84-133">El remitente de un mensaje que supere este límite recibirá un error SOAP.</span><span class="sxs-lookup"><span data-stu-id="c7b84-133">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="c7b84-134">El destinatario quita el mensaje y crea una entrada del evento en el registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="c7b84-134">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="c7b84-135">El valor predeterminado es 65536.</span><span class="sxs-lookup"><span data-stu-id="c7b84-135">The default is 65536.</span></span>|  
|<span data-ttu-id="c7b84-136">messageEncoding</span><span class="sxs-lookup"><span data-stu-id="c7b84-136">messageEncoding</span></span>|<span data-ttu-id="c7b84-137">Define el codificador utilizado para codificar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="c7b84-137">Defines the encoder used to encode the message.</span></span> <span data-ttu-id="c7b84-138">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="c7b84-138">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="c7b84-139">-Text: usar un codificador de mensajes de texto.</span><span class="sxs-lookup"><span data-stu-id="c7b84-139">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="c7b84-140">-MTOM: usar un codificador del mecanismo de la organización de transmisión de mensajes 1,0 (MTOM).</span><span class="sxs-lookup"><span data-stu-id="c7b84-140">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><span data-ttu-id="c7b84-141">-El valor predeterminado es texto.</span><span class="sxs-lookup"><span data-stu-id="c7b84-141">-   The default is Text.</span></span><br /><br /> <span data-ttu-id="c7b84-142">Este atributo es del tipo <xref:System.ServiceModel.WSMessageEncoding>.</span><span class="sxs-lookup"><span data-stu-id="c7b84-142">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|  
|<span data-ttu-id="c7b84-143">name</span><span class="sxs-lookup"><span data-stu-id="c7b84-143">name</span></span>|<span data-ttu-id="c7b84-144">Cadena que contiene el nombre de configuración del enlace.</span><span class="sxs-lookup"><span data-stu-id="c7b84-144">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="c7b84-145">Este valor debe ser único porque se usa como identificación del enlace.</span><span class="sxs-lookup"><span data-stu-id="c7b84-145">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="c7b84-146">A partir de .NET Framework 4, no es necesario que los enlaces y los comportamientos tengan un nombre.</span><span class="sxs-lookup"><span data-stu-id="c7b84-146">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="c7b84-147">Para obtener más información sobre la configuración predeterminada y los enlaces y comportamientos sin nombre, vea [configuración simplificada](../../../wcf/simplified-configuration.md) y [configuración simplificada para servicios WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="c7b84-147">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|<span data-ttu-id="c7b84-148">openTimeout</span><span class="sxs-lookup"><span data-stu-id="c7b84-148">openTimeout</span></span>|<span data-ttu-id="c7b84-149">Valor de la estructura <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de apertura para completarse.</span><span class="sxs-lookup"><span data-stu-id="c7b84-149">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="c7b84-150">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="c7b84-150">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="c7b84-151">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="c7b84-151">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="c7b84-152">proxyAddress</span><span class="sxs-lookup"><span data-stu-id="c7b84-152">proxyAddress</span></span>|<span data-ttu-id="c7b84-153">Un URI que especifica la dirección del proxy HTTP.</span><span class="sxs-lookup"><span data-stu-id="c7b84-153">A URI that specifies the address of the HTTP proxy.</span></span> <span data-ttu-id="c7b84-154">Si `useDefaultWebProxy` es `true`, este valor debe ser `null`.</span><span class="sxs-lookup"><span data-stu-id="c7b84-154">If `useDefaultWebProxy` is `true`, this setting must be `null`.</span></span> <span data-ttu-id="c7b84-155">De manera predeterminada, es `null`.</span><span class="sxs-lookup"><span data-stu-id="c7b84-155">The default is `null`.</span></span>|  
|<span data-ttu-id="c7b84-156">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="c7b84-156">receiveTimeout</span></span>|<span data-ttu-id="c7b84-157">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de recepción para completarse.</span><span class="sxs-lookup"><span data-stu-id="c7b84-157">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="c7b84-158">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="c7b84-158">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="c7b84-159">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="c7b84-159">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="c7b84-160">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="c7b84-160">sendTimeout</span></span>|<span data-ttu-id="c7b84-161">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de envío para completarse.</span><span class="sxs-lookup"><span data-stu-id="c7b84-161">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="c7b84-162">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="c7b84-162">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="c7b84-163">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="c7b84-163">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="c7b84-164">textEncoding</span><span class="sxs-lookup"><span data-stu-id="c7b84-164">textEncoding</span></span>|<span data-ttu-id="c7b84-165">Establece el codificador del juego de caracteres que se va a usar para emitir los mensajes en el enlace.</span><span class="sxs-lookup"><span data-stu-id="c7b84-165">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="c7b84-166">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="c7b84-166">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="c7b84-167">-BigEndianUnicode: codificación Unicode BigEndian.</span><span class="sxs-lookup"><span data-stu-id="c7b84-167">-   BigEndianUnicode: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="c7b84-168">-Unicode: codificación de 16 bits.</span><span class="sxs-lookup"><span data-stu-id="c7b84-168">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="c7b84-169">-UTF8: codificación de 8 bits</span><span class="sxs-lookup"><span data-stu-id="c7b84-169">-   UTF8: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="c7b84-170">El valor predeterminado es UTF8.</span><span class="sxs-lookup"><span data-stu-id="c7b84-170">The default is UTF8.</span></span> <span data-ttu-id="c7b84-171">Este atributo es del tipo <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="c7b84-171">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|<span data-ttu-id="c7b84-172">transactionFlow</span><span class="sxs-lookup"><span data-stu-id="c7b84-172">transactionFlow</span></span>|<span data-ttu-id="c7b84-173">Valor booleano que especifica si el enlace admite las transacciones WS del flujo.</span><span class="sxs-lookup"><span data-stu-id="c7b84-173">A Boolean value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="c7b84-174">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="c7b84-174">The default is `false`.</span></span>|  
|<span data-ttu-id="c7b84-175">useDefaultWebProxy</span><span class="sxs-lookup"><span data-stu-id="c7b84-175">useDefaultWebProxy</span></span>|<span data-ttu-id="c7b84-176">Valor de tipo booleano que indica si se utiliza el proxy HTTP del sistema configurado automáticamente.</span><span class="sxs-lookup"><span data-stu-id="c7b84-176">A Boolean value that indicates whether the system’s auto-configured HTTP proxy is used.</span></span> <span data-ttu-id="c7b84-177">La dirección de proxy debe ser `null` (es decir, sin establecer) si este atributo es `true`.</span><span class="sxs-lookup"><span data-stu-id="c7b84-177">The proxy address must be `null` (that is, not set) if this attribute is `true`.</span></span> <span data-ttu-id="c7b84-178">De manera predeterminada, es `true`.</span><span class="sxs-lookup"><span data-stu-id="c7b84-178">The default is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c7b84-179">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c7b84-179">Child Elements</span></span>  
  
|<span data-ttu-id="c7b84-180">Elemento</span><span class="sxs-lookup"><span data-stu-id="c7b84-180">Element</span></span>|<span data-ttu-id="c7b84-181">Descripción</span><span class="sxs-lookup"><span data-stu-id="c7b84-181">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-wsdualhttpbinding.md)|<span data-ttu-id="c7b84-182">Define la configuración de seguridad del enlace.</span><span class="sxs-lookup"><span data-stu-id="c7b84-182">Defines the security settings for the binding.</span></span> <span data-ttu-id="c7b84-183">Este elemento es del tipo <xref:System.ServiceModel.Configuration.WSDualHttpSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="c7b84-183">This element is of type <xref:System.ServiceModel.Configuration.WSDualHttpSecurityElement>.</span></span>|  
|[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="c7b84-184">Define las restricciones en la complejidad de los mensajes SOAP que pueden ser procesados por los puntos de conexión configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="c7b84-184">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="c7b84-185">Este elemento es del tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="c7b84-185">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))|<span data-ttu-id="c7b84-186">Especifica si se establecen sesiones confiables entre los puntos de conexión del canal.</span><span class="sxs-lookup"><span data-stu-id="c7b84-186">Specifies if reliable sessions are established between channel endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c7b84-187">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c7b84-187">Parent Elements</span></span>  
  
|<span data-ttu-id="c7b84-188">Elemento</span><span class="sxs-lookup"><span data-stu-id="c7b84-188">Element</span></span>|<span data-ttu-id="c7b84-189">Descripción</span><span class="sxs-lookup"><span data-stu-id="c7b84-189">Description</span></span>|  
|-------------|-----------------|  
|[\<bindings>](bindings.md)|<span data-ttu-id="c7b84-190">Este elemento contiene una colección de enlaces estándar y personalizados.</span><span class="sxs-lookup"><span data-stu-id="c7b84-190">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c7b84-191">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c7b84-191">Remarks</span></span>  
 <span data-ttu-id="c7b84-192">`WSDualHttpBinding` proporciona la misma compatibilidad para los protocolos de servicio Web que `WSHttpBinding`, pero para el uso con contratos dúplex.</span><span class="sxs-lookup"><span data-stu-id="c7b84-192">The `WSDualHttpBinding` provides the same support for Web Service protocols as the `WSHttpBinding`, but for use with duplex contracts.</span></span> <span data-ttu-id="c7b84-193">`WSDualHttpBinding` solo admite la seguridad de SOAP y requiere mensajería de confianza.</span><span class="sxs-lookup"><span data-stu-id="c7b84-193">`WSDualHttpBinding` only supports SOAP security and requires reliable messaging.</span></span> <span data-ttu-id="c7b84-194">Este enlace requiere que el cliente tenga un URI público que proporciona un extremo de devolución de llamada para el servicio.</span><span class="sxs-lookup"><span data-stu-id="c7b84-194">This binding requires that the client has a public URI that provides a callback endpoint for the service.</span></span> <span data-ttu-id="c7b84-195">Lo proporciona el atributo `clientBaseAddress`.</span><span class="sxs-lookup"><span data-stu-id="c7b84-195">This is provided by the `clientBaseAddress` attribute.</span></span> <span data-ttu-id="c7b84-196">Un enlace dual expone la dirección IP del cliente al servicio.</span><span class="sxs-lookup"><span data-stu-id="c7b84-196">A dual binding exposes the IP address of the client to the service.</span></span> <span data-ttu-id="c7b84-197">El cliente debería utilizar la seguridad para asegurarse de que sólo se conecta a servicios de confianza.</span><span class="sxs-lookup"><span data-stu-id="c7b84-197">The client should use security to ensure that it only connects to services it trusts.</span></span>  
  
 <span data-ttu-id="c7b84-198">Este enlace se puede usar para comunicarse con confianza través de uno o más intermediarios SOAP.</span><span class="sxs-lookup"><span data-stu-id="c7b84-198">This binding can be used to communicate reliably through one or more SOAP intermediaries.</span></span>  
  
 <span data-ttu-id="c7b84-199">De forma predeterminada, este enlace genera una pila en tiempo de ejecución con WS-ReliableMessaging para la fiabilidad, WS-Security para la seguridad de mensajes y autenticación, HTTP para la entrega de mensajes y una codificación de mensaje texto/XML.</span><span class="sxs-lookup"><span data-stu-id="c7b84-199">By default, this binding generates a runtime stack with WS-ReliableMessaging for reliability, WS-Security for message security and authentication, HTTP for message delivery, and a Text/XML message encoding.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7b84-200">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c7b84-200">Example</span></span>  
  
```xml  
<configuration>
  <system.ServiceModel>
    <bindings>
      <wsDualHttpBinding>
        <binding closeTimeout="00:00:10"
                 openTimeout="00:00:20"
                 receiveTimeout="00:00:30"
                 sendTimeout="00:00:40"
                 bypassProxyOnLocal="false"
                 clientBaseAddress="http://localhost:8001/client/"
                 transactionFlow="true"
                 hostNameComparisonMode="WeakWildcard"
                 maxReceivedMessageSize="1000"
                 messageEncoding="Mtom"
                 proxyAddress="http://foo/bar"
                 textEncoding="utf-16"
                 useDefaultWebProxy="false">
          <reliableSession ordered="false"
                           inactivityTimeout="00:02:00" />
          <security mode="None">
            <message clientCredentialType="None"
                     negotiateServiceCredential="false"
                     algorithmSuite="Aes128" />
          </security>
        </binding>
      </wsDualHttpBinding>
    </bindings>
  </system.ServiceModel>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="c7b84-201">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c7b84-201">See also</span></span>

- <xref:System.ServiceModel.WSDualHttpBinding>
- <xref:System.ServiceModel.Configuration.WSDualHttpBindingElement>
- [<span data-ttu-id="c7b84-202">Enlaces</span><span class="sxs-lookup"><span data-stu-id="c7b84-202">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="c7b84-203">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="c7b84-203">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="c7b84-204">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="c7b84-204">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
