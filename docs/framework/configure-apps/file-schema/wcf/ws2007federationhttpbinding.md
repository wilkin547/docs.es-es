---
title: '&lt;ws2007FederationHttpBinding&gt;'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9af4ec79-cdef-457e-9dca-09d5eb821594
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3025eec9c01d325d7d00a7355ff908eb1e19e410
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="ltws2007federationhttpbindinggt"></a><span data-ttu-id="becba-102">&lt;ws2007FederationHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="becba-102">&lt;ws2007FederationHttpBinding&gt;</span></span>
<span data-ttu-id="becba-103">Un enlace seguro e interoperable que deriva de [ \<wsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) y admite la seguridad federada.</span><span class="sxs-lookup"><span data-stu-id="becba-103">A secure and interoperable binding that derives from [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) and supports federated security.</span></span>  
  
 <span data-ttu-id="becba-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="becba-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="becba-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="becba-105">\<bindings></span></span>  
<span data-ttu-id="becba-106">\<ws2007FederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="becba-106">\<ws2007FederationHttpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="becba-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="becba-107">Syntax</span></span>  
  
```xml  
<ws2007FederationHttpBinding>  
    <binding   
        bypassProxyOnLocal="Boolean"  
        closeTimeout="TimeSpan"   
        hostNameComparisonMode="StrongWildcard/Exact/WeakWildcard"  
        maxBufferPoolSize="integer"  
        maxReceivedMessageSize="integer"  
        messageEncoding="Text/Mtom"   
                name="string"  
        openTimeout="TimeSpan"   
        privacyNoticeAt="Uri"  
        privacyNoticeVersion="Integer"  
        proxyAddress="Uri"   
        receiveTimeout="TimeSpan"  
        sendTimeout="TimeSpan"  
        textEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding"  
        transactionFlow="Boolean"  
        useDefaultWebProxy="Boolean">  
        <security mode="None/Message/TransportWithMessageCredential">  
           <message negotiateServiceCredential="Boolean"  
                algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
                issuedTokenType="string"  
                issuedKeyType="SymmetricKey/PublicKey"  
           </message>  
        </security>  
        <reliableSession ordered="Boolean"  
           inactivityTimeout="TimeSpan"  
           enabled="Boolean" />  
       <readerQuotas             maxArrayLength="Integer"            maxBytesPerRead="Integer"            maxDepth="Integer"             maxNameTableCharCount="Integer"                     maxStringContentLength="Integer" />    </binding>  
</ws2007FederationHttpBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="becba-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="becba-108">Attributes and Elements</span></span>  
 <span data-ttu-id="becba-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="becba-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="becba-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="becba-110">Attributes</span></span>  
  
|<span data-ttu-id="becba-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="becba-111">Attribute</span></span>|<span data-ttu-id="becba-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="becba-112">Description</span></span>|  
|---------------|-----------------|  
|`bypassProxyOnLocal`|<span data-ttu-id="becba-113">Un valor que indica si se omitirá el servidor proxy para las direcciones locales.</span><span class="sxs-lookup"><span data-stu-id="becba-113">A value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="becba-114">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="becba-114">The default is `false`.</span></span>|  
|`closeTimeout`|<span data-ttu-id="becba-115">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de cierre para completarse.</span><span class="sxs-lookup"><span data-stu-id="becba-115">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="becba-116">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="becba-116">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="becba-117">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="becba-117">The default is 00:01:00.</span></span>|  
|`hostnameComparisonMode`|<span data-ttu-id="becba-118">Especifica el modo de comparación de nombres de host HTTP usado para analizar los URI.</span><span class="sxs-lookup"><span data-stu-id="becba-118">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="becba-119">Este atributo es del tipo <xref:System.ServiceModel.HostNameComparisonMode>, que indica si se va a utilizar el nombre del host para llegar al servicio cuando coincida en el URI.</span><span class="sxs-lookup"><span data-stu-id="becba-119">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="becba-120">El valor predeterminado es <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, que omite el nombre del host en la coincidencia.</span><span class="sxs-lookup"><span data-stu-id="becba-120">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|  
|`maxBufferPoolSize`|<span data-ttu-id="becba-121">El tamaño máximo del grupo de búferes para este enlace.</span><span class="sxs-lookup"><span data-stu-id="becba-121">The maximum buffer pool size for this binding.</span></span> <span data-ttu-id="becba-122">El valor predeterminado es 524.288 bytes (512x1024).</span><span class="sxs-lookup"><span data-stu-id="becba-122">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="becba-123">Muchas partes de búferes de uso [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="becba-123">Many parts of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] use buffers.</span></span> <span data-ttu-id="becba-124">Crear y destruir búferes cada vez que se usan es caro, y la recolección de elementos no utilizados para los búferes también es cara.</span><span class="sxs-lookup"><span data-stu-id="becba-124">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="becba-125">Con grupos de búferes, puede tomar un búfer del grupo, usarlo y devolverlo al grupo una vez haya terminado.</span><span class="sxs-lookup"><span data-stu-id="becba-125">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="becba-126">Así se evita la sobrecarga al crear y destruir búferes.</span><span class="sxs-lookup"><span data-stu-id="becba-126">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|`maxReceivedMessageSize`|<span data-ttu-id="becba-127">El tamaño máximo del mensaje, en bytes, incluidos los encabezados, que se puede recibir en un canal configurado con este enlace.</span><span class="sxs-lookup"><span data-stu-id="becba-127">The maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="becba-128">El remitente de un mensaje que supera este límite recibe un error SOAP.</span><span class="sxs-lookup"><span data-stu-id="becba-128">The sender of a message that exceeds this limit receives a SOAP fault.</span></span> <span data-ttu-id="becba-129">El destinatario quita el mensaje y crea una entrada del evento en el registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="becba-129">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="becba-130">El valor predeterminado es 65536.</span><span class="sxs-lookup"><span data-stu-id="becba-130">The default is 65536.</span></span>|  
|`messageEncoding`|<span data-ttu-id="becba-131">Define el codificador utilizado para codificar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="becba-131">Defines the encoder used to encode the message.</span></span> <span data-ttu-id="becba-132">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="becba-132">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="becba-133">-Text: Utiliza un codificador de mensajes de texto.</span><span class="sxs-lookup"><span data-stu-id="becba-133">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="becba-134">-Mtom: Usa un codificador Message Transmission organización Mechanism 1.0 (MTOM).</span><span class="sxs-lookup"><span data-stu-id="becba-134">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><br /> <span data-ttu-id="becba-135">El valor predeterminado es Text.</span><span class="sxs-lookup"><span data-stu-id="becba-135">The default is Text.</span></span><br /><br /> <span data-ttu-id="becba-136">Este atributo es del tipo <xref:System.ServiceModel.WSMessageEncoding>.</span><span class="sxs-lookup"><span data-stu-id="becba-136">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|  
|`name`|<span data-ttu-id="becba-137">Nombre de configuración del enlace.</span><span class="sxs-lookup"><span data-stu-id="becba-137">The configuration name of the binding.</span></span> <span data-ttu-id="becba-138">Este valor debe ser único porque se usa como identificación del enlace.</span><span class="sxs-lookup"><span data-stu-id="becba-138">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="becba-139">A partir de [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], no es necesario que los enlaces y los comportamientos tengan nombre.</span><span class="sxs-lookup"><span data-stu-id="becba-139">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="becba-140">Para obtener más información acerca de la configuración predeterminada y enlaces anónimos y los comportamientos, consulte [configuración simplificada](../../../../../docs/framework/wcf/simplified-configuration.md) y [configuración simplificada para los servicios WCF](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="becba-140">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="becba-141">Valor de la estructura <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de apertura para completarse.</span><span class="sxs-lookup"><span data-stu-id="becba-141">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="becba-142">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="becba-142">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="becba-143">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="becba-143">The default is 00:01:00.</span></span>|  
|`privactyNoticeAt`|<span data-ttu-id="becba-144">URI en el que se encuentra el aviso de privacidad.</span><span class="sxs-lookup"><span data-stu-id="becba-144">A URI at which the privacy notice is located.</span></span>|  
|`privactyNoticeVersion`|<span data-ttu-id="becba-145">El número de versión del aviso de privacidad actual.</span><span class="sxs-lookup"><span data-stu-id="becba-145">The version of the current privacy notice.</span></span>|  
|`proxyAddress`|<span data-ttu-id="becba-146">Un URI que especifica la dirección del proxy HTTP.</span><span class="sxs-lookup"><span data-stu-id="becba-146">A URI that specifies the address of the HTTP proxy.</span></span> <span data-ttu-id="becba-147">Si `useDefaultWebProxy` es `true`, este valor debe ser `null`.</span><span class="sxs-lookup"><span data-stu-id="becba-147">If `useDefaultWebProxy` is `true`, this setting must be `null`.</span></span> <span data-ttu-id="becba-148">De manera predeterminada, es `null`.</span><span class="sxs-lookup"><span data-stu-id="becba-148">The default is `null`.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="becba-149">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de recepción para completarse.</span><span class="sxs-lookup"><span data-stu-id="becba-149">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="becba-150">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="becba-150">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="becba-151">El valor predeterminado es 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="becba-151">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="becba-152">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de envío para completarse.</span><span class="sxs-lookup"><span data-stu-id="becba-152">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="becba-153">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="becba-153">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="becba-154">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="becba-154">The default is 00:01:00.</span></span>|  
|`textEncoding`|<span data-ttu-id="becba-155">Establece el codificador del juego de caracteres que se va a usar para emitir los mensajes en el enlace.</span><span class="sxs-lookup"><span data-stu-id="becba-155">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="becba-156">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="becba-156">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="becba-157">-BigEndianUnicode: Big-Endian codificación Unicode.</span><span class="sxs-lookup"><span data-stu-id="becba-157">-   BigEndianUnicode: Unicode Big Endian encoding.</span></span><br /><span data-ttu-id="becba-158">-Unicode: codificación de 16 bits.</span><span class="sxs-lookup"><span data-stu-id="becba-158">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="becba-159">-UTF8: codificación de 8 bits.</span><span class="sxs-lookup"><span data-stu-id="becba-159">-   UTF8: 8-bit encoding.</span></span><br /><br /> <span data-ttu-id="becba-160">El valor predeterminado es UTF8.</span><span class="sxs-lookup"><span data-stu-id="becba-160">The default is UTF8.</span></span> <span data-ttu-id="becba-161">Este atributo es del tipo <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="becba-161">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|`transactionFlow`|<span data-ttu-id="becba-162">Valor que especifica si el enlace admite el flujo de transacciones de WS.</span><span class="sxs-lookup"><span data-stu-id="becba-162">A value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="becba-163">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="becba-163">The default is `false`.</span></span>|  
|`useDefaultWebProxy`|<span data-ttu-id="becba-164">Un valor que indica si se utiliza el proxy HTTP del sistema configurado automáticamente.</span><span class="sxs-lookup"><span data-stu-id="becba-164">A value that indicates whether the system’s auto-configured HTTP proxy is used.</span></span> <span data-ttu-id="becba-165">La dirección de proxy debe ser `null` (es decir, sin establecer) si este atributo es `true`.</span><span class="sxs-lookup"><span data-stu-id="becba-165">The proxy address must be `null` (that is, not set) if this attribute is `true`.</span></span> <span data-ttu-id="becba-166">De manera predeterminada, es `true`.</span><span class="sxs-lookup"><span data-stu-id="becba-166">The default is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="becba-167">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="becba-167">Child Elements</span></span>  
  
|<span data-ttu-id="becba-168">Elemento</span><span class="sxs-lookup"><span data-stu-id="becba-168">Element</span></span>|<span data-ttu-id="becba-169">Descripción</span><span class="sxs-lookup"><span data-stu-id="becba-169">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="becba-170">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="becba-170">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsfederationhttpbinding.md)|<span data-ttu-id="becba-171">Define la configuración de seguridad del mensaje.</span><span class="sxs-lookup"><span data-stu-id="becba-171">Defines the security settings for the message.</span></span> <span data-ttu-id="becba-172">Este elemento es del tipo <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="becba-172">This element is of type <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>.</span></span>|  
|[<span data-ttu-id="becba-173">\<readerQuotas></span><span class="sxs-lookup"><span data-stu-id="becba-173">\<readerQuotas></span></span>](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="becba-174">Define las restricciones en la complejidad de los mensajes SOAP que pueden ser procesados por los puntos de conexión configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="becba-174">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="becba-175">Este elemento es del tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="becba-175">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|[<span data-ttu-id="becba-176">reliableSession</span><span class="sxs-lookup"><span data-stu-id="becba-176">reliableSession</span></span>](http://msdn.microsoft.com/library/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b)|<span data-ttu-id="becba-177">Especifica si se establecen sesiones confiables entre los puntos de conexión del canal.</span><span class="sxs-lookup"><span data-stu-id="becba-177">Specifies whether reliable sessions are established between channel endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="becba-178">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="becba-178">Parent Elements</span></span>  
  
|<span data-ttu-id="becba-179">Elemento</span><span class="sxs-lookup"><span data-stu-id="becba-179">Element</span></span>|<span data-ttu-id="becba-180">Descripción</span><span class="sxs-lookup"><span data-stu-id="becba-180">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="becba-181">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="becba-181">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="becba-182">Este elemento contiene una colección de enlaces estándar y personalizados.</span><span class="sxs-lookup"><span data-stu-id="becba-182">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="becba-183">Comentarios</span><span class="sxs-lookup"><span data-stu-id="becba-183">Remarks</span></span>  
 <span data-ttu-id="becba-184">La federación es la capacidad de compartir identidades en varias empresas o dominios de confianza para la autenticación y autorización.</span><span class="sxs-lookup"><span data-stu-id="becba-184">Federation is the ability to share identities across multiple enterprises or trust domains for authentication and authorization.</span></span> <span data-ttu-id="becba-185">Utiliza el protocolo WS-Trust para asignar la representación de identidad de un dominio de confianza a otro.</span><span class="sxs-lookup"><span data-stu-id="becba-185">It uses the WS-Trust protocol to map the identity representation from one trust domain to another.</span></span> <span data-ttu-id="becba-186">El enlace HTTP federado admite la seguridad de SOAP así como la seguridad de modo mixto, pero no permite la seguridad de transporte.</span><span class="sxs-lookup"><span data-stu-id="becba-186">Federated HTTP binding supports SOAP security as well as mixed-mode security, but it does not support transport security.</span></span> <span data-ttu-id="becba-187">Los servicios configurados con este enlace deben utilizar el transporte de HTTP.</span><span class="sxs-lookup"><span data-stu-id="becba-187">Services configured with this binding must use the HTTP transport.</span></span> <span data-ttu-id="becba-188">Para obtener más información, consulte [ \<wsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="becba-188">For more information, see [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="becba-189">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="becba-189">Example</span></span>  
  
```xml  
<configuration>  
<system.ServiceModel>  
<bindings>  
<ws2007FederationHttpBinding>  
    <binding   
        bypassProxyOnLocal="false"  
        transactionFlow="false"  
        hostNameComparisonMode="WeakWildcard"  
        maxReceivedMessageSize="1000"  
        messageEncoding="Mtom"   
        proxyAddress="http://www.contoso.com"   
        textEncoding="Utf16TextEncoding"  
        useDefaultWebProxy="false">  
        <reliableSession ordered="false"  
            inactivityTimeout="00:02:00" enabled="true" />  
        <security mode="None">  
           <message negotiateServiceCredential="false"  
                algorithmSuite="Aes128"  
                issuedTokenType="http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1"   
                issuedKeyType="PublicKey">  
               <issuer address="http://localhost/Sts" />  
           </message>  
        </security>  
    </binding>  
</ws2007FederationBinding>  
</bindings>  
</system.ServiceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="becba-190">Vea también</span><span class="sxs-lookup"><span data-stu-id="becba-190">See Also</span></span>  
 <xref:System.ServiceModel.WS2007FederationHttpBinding>  
 <xref:System.ServiceModel.Configuration.WS2007FederationHttpBindingElement>  
 [<span data-ttu-id="becba-191">\<wsFederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="becba-191">\<wsFederationHttpBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)  
 [<span data-ttu-id="becba-192">Enlaces</span><span class="sxs-lookup"><span data-stu-id="becba-192">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="becba-193">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="becba-193">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="becba-194">Utilización de enlaces para configurar los clientes y servicios de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="becba-194">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="becba-195">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="becba-195">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
