---
title: <wsFederationHttpBinding>
ms.date: 03/30/2017
helpviewer_keywords:
- wsFederationBinding element
ms.assetid: 9c3312b4-2137-4e71-bf3f-de1cf8e9be79
ms.openlocfilehash: 8ed8f62f9415ed556a61ca53f27442a9355d8d7c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698855"
---
# <a name="wsfederationhttpbinding"></a><span data-ttu-id="31045-101">\<wsFederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="31045-101">\<wsFederationHttpBinding></span></span>

<span data-ttu-id="31045-102">Define un enlace que admite WS-Federation.</span><span class="sxs-lookup"><span data-stu-id="31045-102">Defines a binding that supports WS-Federation.</span></span>

<span data-ttu-id="31045-103">\<system.ServiceModel>\\</span><span class="sxs-lookup"><span data-stu-id="31045-103">\<system.ServiceModel>\\</span></span>
<span data-ttu-id="31045-104">\<bindings>\\</span><span class="sxs-lookup"><span data-stu-id="31045-104">\<bindings>\\</span></span>
<span data-ttu-id="31045-105">wsFederationBinding element</span><span class="sxs-lookup"><span data-stu-id="31045-105">wsFederationBinding element</span></span>

## <a name="syntax"></a><span data-ttu-id="31045-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="31045-106">Syntax</span></span>

```xml
<wsFederationHttpBinding>
  <binding bypassProxyOnLocal="Boolean"
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
           textEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/ Utf8TextEncoding"
           transactionFlow="Boolean"
           useDefaultWebProxy="Boolean">
    <security mode="None/Message/TransportWithMessageCredential">
      <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               issuedTokenType="string"
               issuedKeyType="SymmetricKey/PublicKey"
               negotiateServiceCredential="Boolean">
        <claimTypeRequirements>
          <add claimType="URI"
               isOptional="Boolean" />
        </claimTypeRequirements>
        <issuer address="Uri" >
          <headers>
            <add name="String"
                 namespace="String" />
          </headers>
          <identity>
            <certificate encodedValue="String" />
            <certificateReference findValue="String"
                                  isChainIncluded="Boolean"
                                  storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                                  storeLocation="LocalMachine/CurrentUser"
                                  X509FindType="System.Security.Cryptography.X509certificates.X509findtype" />
            <dns value="String" />
            <rsa value="String" />
            <servicePrincipalName value="String" />
            <usePrincipalName value="String" />
          </identity>
        </issuer>
        <issuerMetadata address="String">
          <headers>
            <add name="String"
                 namespace="String" />
          </headers>
          <identity>
            <certificate encodedValue="String" />
            <certificateReference findValue="String"
                                  isChainIncluded="Boolean"
                                  storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                                  storeLocation="LocalMachine/CurrentUser"
                                  x509FindType="System.Security.Cryptography.X509certificates.X509findtype" />
            <dns value="String" />
            <rsa value="String" />
            <servicePrincipalName value="String" />
            <usePrincipalName value="String" />
          </identity>
        </issuerMetadata>
        <tokenRequestParameters>
          <xmlElement>
          </xmlElement>
        </tokenRequestParameters>
      </message>
    </security>
    <reliableSession ordered="Boolean"
                     inactivityTimeout="TimeSpan"
                     enabled="Boolean" />
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</wsFederationBinding>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="31045-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="31045-107">Attributes and Elements</span></span>

<span data-ttu-id="31045-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="31045-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="31045-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="31045-109">Attributes</span></span>

|<span data-ttu-id="31045-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="31045-110">Attribute</span></span>|<span data-ttu-id="31045-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="31045-111">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="31045-112">bypassProxyOnLocal</span><span class="sxs-lookup"><span data-stu-id="31045-112">bypassProxyOnLocal</span></span>|<span data-ttu-id="31045-113">Valor de tipo booleano que indica si se omitirá el servidor proxy para las direcciones locales.</span><span class="sxs-lookup"><span data-stu-id="31045-113">A Boolean value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="31045-114">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="31045-114">The default is `false`.</span></span>|
|<span data-ttu-id="31045-115">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="31045-115">closeTimeout</span></span>|<span data-ttu-id="31045-116">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de cierre para completarse.</span><span class="sxs-lookup"><span data-stu-id="31045-116">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="31045-117">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="31045-117">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="31045-118">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="31045-118">The default is 00:01:00.</span></span>|
|<span data-ttu-id="31045-119">hostnameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="31045-119">hostnameComparisonMode</span></span>|<span data-ttu-id="31045-120">Especifica el modo de comparación de nombres de host HTTP usado para analizar los URI.</span><span class="sxs-lookup"><span data-stu-id="31045-120">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="31045-121">Este atributo es del tipo <xref:System.ServiceModel.HostNameComparisonMode>, que indica si se va a utilizar el nombre del host para llegar al servicio cuando coincida en el URI.</span><span class="sxs-lookup"><span data-stu-id="31045-121">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="31045-122">El valor predeterminado es <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, que omite el nombre del host en la coincidencia.</span><span class="sxs-lookup"><span data-stu-id="31045-122">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|
|<span data-ttu-id="31045-123">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="31045-123">maxBufferPoolSize</span></span>|<span data-ttu-id="31045-124">Entero que especifica el tamaño máximo del grupo de búferes para este enlace.</span><span class="sxs-lookup"><span data-stu-id="31045-124">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="31045-125">El valor predeterminado es 524.288 bytes (512x1024).</span><span class="sxs-lookup"><span data-stu-id="31045-125">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="31045-126">En muchas partes de Windows Communication Foundation (WCF) se utilizan búferes.</span><span class="sxs-lookup"><span data-stu-id="31045-126">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="31045-127">Crear y destruir búferes cada vez que se usan es caro, y la recolección de elementos no utilizados para los búferes también es cara.</span><span class="sxs-lookup"><span data-stu-id="31045-127">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="31045-128">Con grupos de búferes, puede tomar un búfer del grupo, usarlo y devolverlo al grupo una vez haya terminado.</span><span class="sxs-lookup"><span data-stu-id="31045-128">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="31045-129">Así se evita la sobrecarga al crear y destruir búferes.</span><span class="sxs-lookup"><span data-stu-id="31045-129">Thus the overhead in creating and destroying buffers is avoided.</span></span>|
|<span data-ttu-id="31045-130">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="31045-130">maxReceivedMessageSize</span></span>|<span data-ttu-id="31045-131">Entero positivo que especifica el tamaño máximo del mensaje, en bytes, incluidos los encabezados, que se puede recibir en un canal configurado con este enlace.</span><span class="sxs-lookup"><span data-stu-id="31045-131">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="31045-132">El remitente de un mensaje que supere este límite recibirá un error SOAP.</span><span class="sxs-lookup"><span data-stu-id="31045-132">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="31045-133">El destinatario quita el mensaje y crea una entrada del evento en el registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="31045-133">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="31045-134">El valor predeterminado es 65536.</span><span class="sxs-lookup"><span data-stu-id="31045-134">The default is 65536.</span></span>|
|<span data-ttu-id="31045-135">messageEncoding</span><span class="sxs-lookup"><span data-stu-id="31045-135">messageEncoding</span></span>|<span data-ttu-id="31045-136">Define el codificador utilizado para codificar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="31045-136">Defines the encoder used to encode the message.</span></span> <span data-ttu-id="31045-137">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="31045-137">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="31045-138">-Texto: Usar un codificador de mensajes de texto.</span><span class="sxs-lookup"><span data-stu-id="31045-138">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="31045-139">-Mtom: Usar un codificador Message Transmission organización Mechanism 1.0 (MTOM).</span><span class="sxs-lookup"><span data-stu-id="31045-139">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><br /> <span data-ttu-id="31045-140">El valor predeterminado es Text.</span><span class="sxs-lookup"><span data-stu-id="31045-140">The default is Text.</span></span><br /><br /> <span data-ttu-id="31045-141">Este atributo es del tipo <xref:System.ServiceModel.WSMessageEncoding>.</span><span class="sxs-lookup"><span data-stu-id="31045-141">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|
|<span data-ttu-id="31045-142">name</span><span class="sxs-lookup"><span data-stu-id="31045-142">name</span></span>|<span data-ttu-id="31045-143">Cadena que contiene el nombre de configuración del enlace.</span><span class="sxs-lookup"><span data-stu-id="31045-143">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="31045-144">Este valor debe ser único porque se usa como identificación del enlace.</span><span class="sxs-lookup"><span data-stu-id="31045-144">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="31045-145">A partir de [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], no es necesario que los enlaces y los comportamientos tengan nombre.</span><span class="sxs-lookup"><span data-stu-id="31045-145">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="31045-146">Para obtener más información acerca de la configuración predeterminada y sin especificar enlaces y comportamientos, consulte [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) y [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="31045-146">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|
|<span data-ttu-id="31045-147">openTimeout</span><span class="sxs-lookup"><span data-stu-id="31045-147">openTimeout</span></span>|<span data-ttu-id="31045-148">Valor de la estructura <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de apertura para completarse.</span><span class="sxs-lookup"><span data-stu-id="31045-148">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="31045-149">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="31045-149">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="31045-150">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="31045-150">The default is 00:01:00.</span></span>|
|<span data-ttu-id="31045-151">privacyNoticeAt</span><span class="sxs-lookup"><span data-stu-id="31045-151">privacyNoticeAt</span></span>|<span data-ttu-id="31045-152">Una cadena que especifica un URI en el que el aviso de privacidad se encuentra.</span><span class="sxs-lookup"><span data-stu-id="31045-152">A String that specifies a URI at which the privacy notice is located.</span></span>|
|<span data-ttu-id="31045-153">privacyNoticeVersion</span><span class="sxs-lookup"><span data-stu-id="31045-153">privacyNoticeVersion</span></span>|<span data-ttu-id="31045-154">Un entero que especifica la versión del aviso de privacidad actual.</span><span class="sxs-lookup"><span data-stu-id="31045-154">An integer that specifies the version of the current privacy notice.</span></span>|
|<span data-ttu-id="31045-155">proxyAddress</span><span class="sxs-lookup"><span data-stu-id="31045-155">proxyAddress</span></span>|<span data-ttu-id="31045-156">Un URI que especifica la dirección del proxy HTTP.</span><span class="sxs-lookup"><span data-stu-id="31045-156">A URI that specifies the address of the HTTP proxy.</span></span> <span data-ttu-id="31045-157">Si `useDefaultWebProxy` es `true`, este valor debe ser `null`.</span><span class="sxs-lookup"><span data-stu-id="31045-157">If `useDefaultWebProxy` is `true`, this setting must be `null`.</span></span> <span data-ttu-id="31045-158">De manera predeterminada, es `null`.</span><span class="sxs-lookup"><span data-stu-id="31045-158">The default is `null`.</span></span>|
|<span data-ttu-id="31045-159">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="31045-159">receiveTimeout</span></span>|<span data-ttu-id="31045-160">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de recepción para completarse.</span><span class="sxs-lookup"><span data-stu-id="31045-160">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="31045-161">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="31045-161">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="31045-162">El valor predeterminado es 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="31045-162">The default is 00:10:00.</span></span>|
|<span data-ttu-id="31045-163">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="31045-163">sendTimeout</span></span>|<span data-ttu-id="31045-164">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de envío para completarse.</span><span class="sxs-lookup"><span data-stu-id="31045-164">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="31045-165">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="31045-165">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="31045-166">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="31045-166">The default is 00:01:00.</span></span>|
|<span data-ttu-id="31045-167">textEncoding</span><span class="sxs-lookup"><span data-stu-id="31045-167">textEncoding</span></span>|<span data-ttu-id="31045-168">Establece el codificador del juego de caracteres que se va a usar para emitir los mensajes en el enlace.</span><span class="sxs-lookup"><span data-stu-id="31045-168">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="31045-169">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="31045-169">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="31045-170">-   BigEndianUnicode: Codificación Unicode BigEndian.</span><span class="sxs-lookup"><span data-stu-id="31045-170">-   BigEndianUnicode: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="31045-171">-Unicode: codificación de 16 bits.</span><span class="sxs-lookup"><span data-stu-id="31045-171">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="31045-172">-   UTF8: codificación de 8 bits</span><span class="sxs-lookup"><span data-stu-id="31045-172">-   UTF8: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="31045-173">El valor predeterminado es UTF8.</span><span class="sxs-lookup"><span data-stu-id="31045-173">The default is UTF8.</span></span> <span data-ttu-id="31045-174">Este atributo es del tipo <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="31045-174">This attribute is of type <xref:System.Text.Encoding>..</span></span>|
|<span data-ttu-id="31045-175">transactionFlow</span><span class="sxs-lookup"><span data-stu-id="31045-175">transactionFlow</span></span>|<span data-ttu-id="31045-176">Valor booleano que especifica si el enlace admite las transacciones WS del flujo.</span><span class="sxs-lookup"><span data-stu-id="31045-176">A Boolean value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="31045-177">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="31045-177">The default is `false`.</span></span>|
|<span data-ttu-id="31045-178">useDefaultWebProxy</span><span class="sxs-lookup"><span data-stu-id="31045-178">useDefaultWebProxy</span></span>|<span data-ttu-id="31045-179">Valor de tipo booleano que indica si se utiliza el proxy HTTP del sistema configurado automáticamente.</span><span class="sxs-lookup"><span data-stu-id="31045-179">A Boolean value that indicates whether the system’s auto-configured HTTP proxy is used.</span></span> <span data-ttu-id="31045-180">La dirección de proxy debe ser `null` (es decir, sin establecer) si este atributo es `true`.</span><span class="sxs-lookup"><span data-stu-id="31045-180">The proxy address must be `null` (that is, not set) if this attribute is `true`.</span></span> <span data-ttu-id="31045-181">De manera predeterminada, es `true`.</span><span class="sxs-lookup"><span data-stu-id="31045-181">The default is `true`.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="31045-182">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="31045-182">Child Elements</span></span>

|<span data-ttu-id="31045-183">Elemento</span><span class="sxs-lookup"><span data-stu-id="31045-183">Element</span></span>|<span data-ttu-id="31045-184">Descripción</span><span class="sxs-lookup"><span data-stu-id="31045-184">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="31045-185">\<security></span><span class="sxs-lookup"><span data-stu-id="31045-185">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsfederationhttpbinding.md)|<span data-ttu-id="31045-186">Define la configuración de seguridad del mensaje.</span><span class="sxs-lookup"><span data-stu-id="31045-186">Defines the security settings for the message.</span></span> <span data-ttu-id="31045-187">Este elemento es del tipo <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="31045-187">This element is of type <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>.</span></span>|
|<span data-ttu-id="31045-188">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="31045-188">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="31045-189">Define las restricciones en la complejidad de los mensajes SOAP que pueden ser procesados por los puntos de conexión configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="31045-189">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="31045-190">Este elemento es del tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="31045-190">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|
|<span data-ttu-id="31045-191">[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="31045-191">[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))</span></span>|<span data-ttu-id="31045-192">Especifica si se establecen sesiones confiables entre los puntos de conexión del canal.</span><span class="sxs-lookup"><span data-stu-id="31045-192">Specifies if reliable sessions are established between channel endpoints.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="31045-193">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="31045-193">Parent Elements</span></span>

|<span data-ttu-id="31045-194">Elemento</span><span class="sxs-lookup"><span data-stu-id="31045-194">Element</span></span>|<span data-ttu-id="31045-195">Descripción</span><span class="sxs-lookup"><span data-stu-id="31045-195">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="31045-196">\<bindings></span><span class="sxs-lookup"><span data-stu-id="31045-196">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="31045-197">Este elemento contiene una colección de enlaces estándar y personalizados.</span><span class="sxs-lookup"><span data-stu-id="31045-197">This element holds a collection of standard and custom bindings.</span></span>|

## <a name="remarks"></a><span data-ttu-id="31045-198">Comentarios</span><span class="sxs-lookup"><span data-stu-id="31045-198">Remarks</span></span>

<span data-ttu-id="31045-199">La federación es la capacidad de compartir identidades en varios sistemas para la autenticación y autorización.</span><span class="sxs-lookup"><span data-stu-id="31045-199">Federation is the ability to share identities across multiple systems for authentication and authorization.</span></span> <span data-ttu-id="31045-200">Estas identidades pueden hacer referencia a usuarios o a equipos.</span><span class="sxs-lookup"><span data-stu-id="31045-200">These identities can refer to users or to machines.</span></span> <span data-ttu-id="31045-201">El HTTP federado admite la seguridad de SOAP así como la seguridad de modo mixto, pero no permite utilizar únicamente la seguridad de transporte.</span><span class="sxs-lookup"><span data-stu-id="31045-201">Federated HTTP supports SOAP security as well as mixed-mode security, but it does not support exclusively using transport security.</span></span> <span data-ttu-id="31045-202">Este enlace proporciona compatibilidad de Windows Communication Foundation (WCF) para el protocolo WS-Federation.</span><span class="sxs-lookup"><span data-stu-id="31045-202">This binding provides Windows Communication Foundation (WCF) support for the WS-Federation protocol.</span></span> <span data-ttu-id="31045-203">Los servicios configurados con este enlace deben utilizar el transporte de HTTP.</span><span class="sxs-lookup"><span data-stu-id="31045-203">Services configured with this binding must use the HTTP transport.</span></span>

<span data-ttu-id="31045-204">Los enlaces están compuestos de una pila de elementos de enlace.</span><span class="sxs-lookup"><span data-stu-id="31045-204">Bindings consist of a stack of binding elements.</span></span> <span data-ttu-id="31045-205">La pila de elementos de enlace en</span><span class="sxs-lookup"><span data-stu-id="31045-205">The stack of binding elements in</span></span>

<span data-ttu-id="31045-206">`wsFederationHttpBinding`es la misma que la que contiene `wsHttpBinding`</span><span class="sxs-lookup"><span data-stu-id="31045-206">`wsFederationHttpBinding` is the same as that contained in `wsHttpBinding`</span></span>

<span data-ttu-id="31045-207">Cuando [ \<seguridad >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsfederationhttpbinding.md) se establece en el valor predeterminado de <xref:System.ServiceModel.WSFederationHttpSecurityMode.Message>.</span><span class="sxs-lookup"><span data-stu-id="31045-207">when [\<security>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsfederationhttpbinding.md) is set to the default value of <xref:System.ServiceModel.WSFederationHttpSecurityMode.Message>.</span></span>

<span data-ttu-id="31045-208">El `wsFederationHttpBinding` controla los detalles de la configuración de seguridad de mensaje en [ \<mensaje >](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-wsfederationhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="31045-208">The `wsFederationHttpBinding` controls the details of the message security settings in [\<message>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-wsfederationhttpbinding.md).</span></span> <span data-ttu-id="31045-209">Tenga en cuenta que el [ \<seguridad >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsfederationhttpbinding.md) elemento proporciona acceso sólo cuando la seguridad utilizada por el enlace no se puede cambiar una vez creado el enlace.</span><span class="sxs-lookup"><span data-stu-id="31045-209">Note that the [\<security>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsfederationhttpbinding.md) element provides get access only as the security used by the binding cannot be changed once the binding is created.</span></span>

<span data-ttu-id="31045-210">El `wsFederationHttpBinding` también proporciona un atributo privacyNoticeAt para establecer y recuperar el URI en el que se encuentra el aviso de privacidad.</span><span class="sxs-lookup"><span data-stu-id="31045-210">The `wsFederationHttpBinding` also provides a privacyNoticeAt attribute to set and retrieve the URI at which the privacy notice is located.</span></span>

<span data-ttu-id="31045-211">Mantener la directiva protegida es especialmente importante en escenarios de federación.</span><span class="sxs-lookup"><span data-stu-id="31045-211">Keeping policy secure is especially important in federation scenarios.</span></span> <span data-ttu-id="31045-212">Se recomienda utilizar algún formulario de seguridad, como HTTPS, para proteger la directiva de los usuarios malintencionados.</span><span class="sxs-lookup"><span data-stu-id="31045-212">The recommendation is to use some form of security, such as HTTPS, to protect the policy from malicious users.</span></span>

<span data-ttu-id="31045-213">En los escenarios de federación que utilizan este enlace, la directiva del servicio tiene potencialmente información importante como la clave para utilizar para cifrar el token emitido (SAML), el tipo de demandas para introducir el token, etc.</span><span class="sxs-lookup"><span data-stu-id="31045-213">In federation scenarios using this binding, the service policy potentially has important information such as the key to use to encrypt the issued (SAML) token, the type of claims to put in the token, and so forth.</span></span> <span data-ttu-id="31045-214">Si esta directiva se manipula, un atacante podría detectar la clave del token emitido que conduce a una modificación posterior, divulgación de información y otros comportamientos malintencionados.</span><span class="sxs-lookup"><span data-stu-id="31045-214">If this policy is tampered with, an attacker could discover the key of the issued token leading to further tampering, info disclosure and other malicious behavior.</span></span> <span data-ttu-id="31045-215">Para ayudar a evitar esto, la directiva se debe obtener firmemente (utilizando HTTPS, por ejemplo) del servicio.</span><span class="sxs-lookup"><span data-stu-id="31045-215">To help prevent this, the policy must be obtained securely (for example using HTTPS) from the service.</span></span>

<span data-ttu-id="31045-216">Para obtener más información sobre este enlace, vea [Cómo: Crear un WSFederationHttpBinding](../../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="31045-216">For more information on this binding, see [How to: Create a WSFederationHttpBinding](../../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md).</span></span>

## <a name="example"></a><span data-ttu-id="31045-217">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="31045-217">Example</span></span>

```xml
<configuration>
  <system.ServiceModel>
    <bindings>
      <wsFederationHttpBinding>
        <binding bypassProxyOnLocal="false"
                 transactionFlow="false"
                 hostNameComparisonMode="WeakWildcard"
                 maxReceivedMessageSize="1000"
                 messageEncoding="Mtom"
                 proxyAddress="http://foo/bar"
                 textEncoding="Utf16TextEncoding"
                 useDefaultWebProxy="false">
          <reliableSession ordered="false"
                           inactivityTimeout="00:02:00"
                           enabled="true" />
          <security mode="None">
            <message negotiateServiceCredential="false"
                     algorithmSuite="Aes128"
                     issuedTokenType="saml"
                     issuedKeyType="PublicKey">
              <issuer address="http://localhost/Sts" />
            </message>
          </security>
        </binding>
      </wsFederationBinding>
    </bindings>
  </system.ServiceModel>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="31045-218">Vea también</span><span class="sxs-lookup"><span data-stu-id="31045-218">See also</span></span>

- <xref:System.ServiceModel.WSFederationHttpBinding>
- <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement>
- [<span data-ttu-id="31045-219">Cómo: Create a WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="31045-219">How to: Create a WSFederationHttpBinding</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
- [<span data-ttu-id="31045-220">Enlaces</span><span class="sxs-lookup"><span data-stu-id="31045-220">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="31045-221">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="31045-221">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="31045-222">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="31045-222">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="31045-223">\<binding></span><span class="sxs-lookup"><span data-stu-id="31045-223">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
