---
title: <wsFederationHttpBinding>
ms.date: 03/30/2017
helpviewer_keywords:
- wsFederationBinding element
ms.assetid: 9c3312b4-2137-4e71-bf3f-de1cf8e9be79
ms.openlocfilehash: 3c4edc17fd669fbe23ec38ff26a61e867c04c561
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69915071"
---
# <a name="wsfederationhttpbinding"></a><span data-ttu-id="b92f8-101">\<wsFederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="b92f8-101">\<wsFederationHttpBinding></span></span>

<span data-ttu-id="b92f8-102">Define un enlace que admite WS-Federation.</span><span class="sxs-lookup"><span data-stu-id="b92f8-102">Defines a binding that supports WS-Federation.</span></span>

<span data-ttu-id="b92f8-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="b92f8-103">\<system.ServiceModel></span></span>\
<span data-ttu-id="b92f8-104">\<Enlaces > </span><span class="sxs-lookup"><span data-stu-id="b92f8-104">\<bindings></span></span>\
<span data-ttu-id="b92f8-105">wsFederationBinding element</span><span class="sxs-lookup"><span data-stu-id="b92f8-105">wsFederationBinding element</span></span>

## <a name="syntax"></a><span data-ttu-id="b92f8-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b92f8-106">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="b92f8-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b92f8-107">Attributes and Elements</span></span>

<span data-ttu-id="b92f8-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b92f8-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="b92f8-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="b92f8-109">Attributes</span></span>

|<span data-ttu-id="b92f8-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="b92f8-110">Attribute</span></span>|<span data-ttu-id="b92f8-111">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="b92f8-111">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="b92f8-112">bypassProxyOnLocal</span><span class="sxs-lookup"><span data-stu-id="b92f8-112">bypassProxyOnLocal</span></span>|<span data-ttu-id="b92f8-113">Valor de tipo booleano que indica si se omitirá el servidor proxy para las direcciones locales.</span><span class="sxs-lookup"><span data-stu-id="b92f8-113">A Boolean value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="b92f8-114">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="b92f8-114">The default is `false`.</span></span>|
|<span data-ttu-id="b92f8-115">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="b92f8-115">closeTimeout</span></span>|<span data-ttu-id="b92f8-116">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de cierre para completarse.</span><span class="sxs-lookup"><span data-stu-id="b92f8-116">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="b92f8-117">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="b92f8-117">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="b92f8-118">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="b92f8-118">The default is 00:01:00.</span></span>|
|<span data-ttu-id="b92f8-119">hostnameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="b92f8-119">hostnameComparisonMode</span></span>|<span data-ttu-id="b92f8-120">Especifica el modo de comparación de nombres de host HTTP usado para analizar los URI.</span><span class="sxs-lookup"><span data-stu-id="b92f8-120">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="b92f8-121">Este atributo es del tipo <xref:System.ServiceModel.HostNameComparisonMode>, que indica si se va a utilizar el nombre del host para llegar al servicio cuando coincida en el URI.</span><span class="sxs-lookup"><span data-stu-id="b92f8-121">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="b92f8-122">El valor predeterminado es <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, que omite el nombre del host en la coincidencia.</span><span class="sxs-lookup"><span data-stu-id="b92f8-122">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|
|<span data-ttu-id="b92f8-123">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="b92f8-123">maxBufferPoolSize</span></span>|<span data-ttu-id="b92f8-124">Entero que especifica el tamaño máximo del grupo de búferes para este enlace.</span><span class="sxs-lookup"><span data-stu-id="b92f8-124">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="b92f8-125">El valor predeterminado es 524.288 bytes (512x1024).</span><span class="sxs-lookup"><span data-stu-id="b92f8-125">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="b92f8-126">En muchas partes de Windows Communication Foundation (WCF) se utilizan búferes.</span><span class="sxs-lookup"><span data-stu-id="b92f8-126">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="b92f8-127">Crear y destruir búferes cada vez que se usan es caro, y la recolección de elementos no utilizados para los búferes también es cara.</span><span class="sxs-lookup"><span data-stu-id="b92f8-127">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="b92f8-128">Con grupos de búferes, puede tomar un búfer del grupo, usarlo y devolverlo al grupo una vez haya terminado.</span><span class="sxs-lookup"><span data-stu-id="b92f8-128">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="b92f8-129">Así se evita la sobrecarga al crear y destruir búferes.</span><span class="sxs-lookup"><span data-stu-id="b92f8-129">Thus the overhead in creating and destroying buffers is avoided.</span></span>|
|<span data-ttu-id="b92f8-130">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="b92f8-130">maxReceivedMessageSize</span></span>|<span data-ttu-id="b92f8-131">Entero positivo que especifica el tamaño máximo del mensaje, en bytes, incluidos los encabezados, que se puede recibir en un canal configurado con este enlace.</span><span class="sxs-lookup"><span data-stu-id="b92f8-131">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="b92f8-132">El remitente de un mensaje que supere este límite recibirá un error SOAP.</span><span class="sxs-lookup"><span data-stu-id="b92f8-132">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="b92f8-133">El destinatario quita el mensaje y crea una entrada del evento en el registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="b92f8-133">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="b92f8-134">El valor predeterminado es 65536.</span><span class="sxs-lookup"><span data-stu-id="b92f8-134">The default is 65536.</span></span>|
|<span data-ttu-id="b92f8-135">messageEncoding</span><span class="sxs-lookup"><span data-stu-id="b92f8-135">messageEncoding</span></span>|<span data-ttu-id="b92f8-136">Define el codificador utilizado para codificar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="b92f8-136">Defines the encoder used to encode the message.</span></span> <span data-ttu-id="b92f8-137">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="b92f8-137">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="b92f8-138">Negrita Use un codificador de mensajes de texto.</span><span class="sxs-lookup"><span data-stu-id="b92f8-138">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="b92f8-139">MTOM Use un codificador del mecanismo de la organización de transmisión de mensajes 1,0 (MTOM).</span><span class="sxs-lookup"><span data-stu-id="b92f8-139">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><br /> <span data-ttu-id="b92f8-140">El valor predeterminado es Text.</span><span class="sxs-lookup"><span data-stu-id="b92f8-140">The default is Text.</span></span><br /><br /> <span data-ttu-id="b92f8-141">Este atributo es del tipo <xref:System.ServiceModel.WSMessageEncoding>.</span><span class="sxs-lookup"><span data-stu-id="b92f8-141">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|
|<span data-ttu-id="b92f8-142">name</span><span class="sxs-lookup"><span data-stu-id="b92f8-142">name</span></span>|<span data-ttu-id="b92f8-143">Cadena que contiene el nombre de configuración del enlace.</span><span class="sxs-lookup"><span data-stu-id="b92f8-143">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="b92f8-144">Este valor debe ser único porque se usa como identificación del enlace.</span><span class="sxs-lookup"><span data-stu-id="b92f8-144">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="b92f8-145">A partir de [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], no es necesario que los enlaces y los comportamientos tengan nombre.</span><span class="sxs-lookup"><span data-stu-id="b92f8-145">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="b92f8-146">Para obtener más información sobre la configuración predeterminada y los enlaces y comportamientos sin nombre, vea [configuración simplificada](../../../wcf/simplified-configuration.md) y [configuración simplificada para servicios WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="b92f8-146">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|
|<span data-ttu-id="b92f8-147">openTimeout</span><span class="sxs-lookup"><span data-stu-id="b92f8-147">openTimeout</span></span>|<span data-ttu-id="b92f8-148">Valor de la estructura <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de apertura para completarse.</span><span class="sxs-lookup"><span data-stu-id="b92f8-148">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="b92f8-149">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="b92f8-149">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="b92f8-150">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="b92f8-150">The default is 00:01:00.</span></span>|
|<span data-ttu-id="b92f8-151">privacyNoticeAt</span><span class="sxs-lookup"><span data-stu-id="b92f8-151">privacyNoticeAt</span></span>|<span data-ttu-id="b92f8-152">Una cadena que especifica un URI en el que el aviso de privacidad se encuentra.</span><span class="sxs-lookup"><span data-stu-id="b92f8-152">A String that specifies a URI at which the privacy notice is located.</span></span>|
|<span data-ttu-id="b92f8-153">privacyNoticeVersion</span><span class="sxs-lookup"><span data-stu-id="b92f8-153">privacyNoticeVersion</span></span>|<span data-ttu-id="b92f8-154">Un entero que especifica la versión del aviso de privacidad actual.</span><span class="sxs-lookup"><span data-stu-id="b92f8-154">An integer that specifies the version of the current privacy notice.</span></span>|
|<span data-ttu-id="b92f8-155">proxyAddress</span><span class="sxs-lookup"><span data-stu-id="b92f8-155">proxyAddress</span></span>|<span data-ttu-id="b92f8-156">Un URI que especifica la dirección del proxy HTTP.</span><span class="sxs-lookup"><span data-stu-id="b92f8-156">A URI that specifies the address of the HTTP proxy.</span></span> <span data-ttu-id="b92f8-157">Si `useDefaultWebProxy` es `true`, este valor debe ser `null`.</span><span class="sxs-lookup"><span data-stu-id="b92f8-157">If `useDefaultWebProxy` is `true`, this setting must be `null`.</span></span> <span data-ttu-id="b92f8-158">El valor predeterminado es `null`.</span><span class="sxs-lookup"><span data-stu-id="b92f8-158">The default is `null`.</span></span>|
|<span data-ttu-id="b92f8-159">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="b92f8-159">receiveTimeout</span></span>|<span data-ttu-id="b92f8-160">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de recepción para completarse.</span><span class="sxs-lookup"><span data-stu-id="b92f8-160">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="b92f8-161">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="b92f8-161">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="b92f8-162">El valor predeterminado es 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="b92f8-162">The default is 00:10:00.</span></span>|
|<span data-ttu-id="b92f8-163">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="b92f8-163">sendTimeout</span></span>|<span data-ttu-id="b92f8-164">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de envío para completarse.</span><span class="sxs-lookup"><span data-stu-id="b92f8-164">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="b92f8-165">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="b92f8-165">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="b92f8-166">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="b92f8-166">The default is 00:01:00.</span></span>|
|<span data-ttu-id="b92f8-167">textEncoding</span><span class="sxs-lookup"><span data-stu-id="b92f8-167">textEncoding</span></span>|<span data-ttu-id="b92f8-168">Establece el codificador del juego de caracteres que se va a usar para emitir los mensajes en el enlace.</span><span class="sxs-lookup"><span data-stu-id="b92f8-168">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="b92f8-169">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="b92f8-169">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="b92f8-170">-   BigEndianUnicode: Codificación Unicode BigEndian.</span><span class="sxs-lookup"><span data-stu-id="b92f8-170">-   BigEndianUnicode: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="b92f8-171">Unicode codificación de 16 bits.</span><span class="sxs-lookup"><span data-stu-id="b92f8-171">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="b92f8-172">-   UTF8: codificación de 8 bits</span><span class="sxs-lookup"><span data-stu-id="b92f8-172">-   UTF8: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="b92f8-173">El valor predeterminado es UTF8.</span><span class="sxs-lookup"><span data-stu-id="b92f8-173">The default is UTF8.</span></span> <span data-ttu-id="b92f8-174">Este atributo es del tipo <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="b92f8-174">This attribute is of type <xref:System.Text.Encoding>..</span></span>|
|<span data-ttu-id="b92f8-175">transactionFlow</span><span class="sxs-lookup"><span data-stu-id="b92f8-175">transactionFlow</span></span>|<span data-ttu-id="b92f8-176">Valor booleano que especifica si el enlace admite las transacciones WS del flujo.</span><span class="sxs-lookup"><span data-stu-id="b92f8-176">A Boolean value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="b92f8-177">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="b92f8-177">The default is `false`.</span></span>|
|<span data-ttu-id="b92f8-178">useDefaultWebProxy</span><span class="sxs-lookup"><span data-stu-id="b92f8-178">useDefaultWebProxy</span></span>|<span data-ttu-id="b92f8-179">Valor de tipo booleano que indica si se utiliza el proxy HTTP del sistema configurado automáticamente.</span><span class="sxs-lookup"><span data-stu-id="b92f8-179">A Boolean value that indicates whether the system’s auto-configured HTTP proxy is used.</span></span> <span data-ttu-id="b92f8-180">La dirección de proxy debe ser `null` (es decir, sin establecer) si este atributo es `true`.</span><span class="sxs-lookup"><span data-stu-id="b92f8-180">The proxy address must be `null` (that is, not set) if this attribute is `true`.</span></span> <span data-ttu-id="b92f8-181">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="b92f8-181">The default is `true`.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="b92f8-182">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b92f8-182">Child Elements</span></span>

|<span data-ttu-id="b92f8-183">Elemento</span><span class="sxs-lookup"><span data-stu-id="b92f8-183">Element</span></span>|<span data-ttu-id="b92f8-184">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="b92f8-184">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b92f8-185">\<security></span><span class="sxs-lookup"><span data-stu-id="b92f8-185">\<security></span></span>](security-of-wsfederationhttpbinding.md)|<span data-ttu-id="b92f8-186">Define la configuración de seguridad del mensaje.</span><span class="sxs-lookup"><span data-stu-id="b92f8-186">Defines the security settings for the message.</span></span> <span data-ttu-id="b92f8-187">Este elemento es del tipo <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="b92f8-187">This element is of type <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>.</span></span>|
|<span data-ttu-id="b92f8-188">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="b92f8-188">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="b92f8-189">Define las restricciones en la complejidad de los mensajes SOAP que pueden ser procesados por los puntos de conexión configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="b92f8-189">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="b92f8-190">Este elemento es del tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="b92f8-190">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|
|<span data-ttu-id="b92f8-191">[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="b92f8-191">[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))</span></span>|<span data-ttu-id="b92f8-192">Especifica si se establecen sesiones confiables entre los puntos de conexión del canal.</span><span class="sxs-lookup"><span data-stu-id="b92f8-192">Specifies if reliable sessions are established between channel endpoints.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="b92f8-193">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b92f8-193">Parent Elements</span></span>

|<span data-ttu-id="b92f8-194">Elemento</span><span class="sxs-lookup"><span data-stu-id="b92f8-194">Element</span></span>|<span data-ttu-id="b92f8-195">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="b92f8-195">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b92f8-196">\<bindings></span><span class="sxs-lookup"><span data-stu-id="b92f8-196">\<bindings></span></span>](bindings.md)|<span data-ttu-id="b92f8-197">Este elemento contiene una colección de enlaces estándar y personalizados.</span><span class="sxs-lookup"><span data-stu-id="b92f8-197">This element holds a collection of standard and custom bindings.</span></span>|

## <a name="remarks"></a><span data-ttu-id="b92f8-198">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b92f8-198">Remarks</span></span>

<span data-ttu-id="b92f8-199">La federación es la capacidad de compartir identidades en varios sistemas para la autenticación y autorización.</span><span class="sxs-lookup"><span data-stu-id="b92f8-199">Federation is the ability to share identities across multiple systems for authentication and authorization.</span></span> <span data-ttu-id="b92f8-200">Estas identidades pueden hacer referencia a usuarios o a equipos.</span><span class="sxs-lookup"><span data-stu-id="b92f8-200">These identities can refer to users or to machines.</span></span> <span data-ttu-id="b92f8-201">El HTTP federado admite la seguridad de SOAP así como la seguridad de modo mixto, pero no permite utilizar únicamente la seguridad de transporte.</span><span class="sxs-lookup"><span data-stu-id="b92f8-201">Federated HTTP supports SOAP security as well as mixed-mode security, but it does not support exclusively using transport security.</span></span> <span data-ttu-id="b92f8-202">Este enlace proporciona compatibilidad con Windows Communication Foundation (WCF) para el protocolo WS-Federation.</span><span class="sxs-lookup"><span data-stu-id="b92f8-202">This binding provides Windows Communication Foundation (WCF) support for the WS-Federation protocol.</span></span> <span data-ttu-id="b92f8-203">Los servicios configurados con este enlace deben utilizar el transporte de HTTP.</span><span class="sxs-lookup"><span data-stu-id="b92f8-203">Services configured with this binding must use the HTTP transport.</span></span>

<span data-ttu-id="b92f8-204">Los enlaces están compuestos de una pila de elementos de enlace.</span><span class="sxs-lookup"><span data-stu-id="b92f8-204">Bindings consist of a stack of binding elements.</span></span> <span data-ttu-id="b92f8-205">La pila de elementos de enlace en</span><span class="sxs-lookup"><span data-stu-id="b92f8-205">The stack of binding elements in</span></span>

<span data-ttu-id="b92f8-206">`wsFederationHttpBinding`es la misma que la que contiene `wsHttpBinding`</span><span class="sxs-lookup"><span data-stu-id="b92f8-206">`wsFederationHttpBinding` is the same as that contained in `wsHttpBinding`</span></span>

<span data-ttu-id="b92f8-207"><xref:System.ServiceModel.WSFederationHttpSecurityMode.Message>cuando [ \<el > de seguridad](security-of-wsfederationhttpbinding.md) se establece en el valor predeterminado de.</span><span class="sxs-lookup"><span data-stu-id="b92f8-207">when [\<security>](security-of-wsfederationhttpbinding.md) is set to the default value of <xref:System.ServiceModel.WSFederationHttpSecurityMode.Message>.</span></span>

<span data-ttu-id="b92f8-208">Controla los detalles de la configuración de seguridad del mensaje en el [ \<> de mensajes.](message-element-of-wsfederationhttpbinding.md) `wsFederationHttpBinding`</span><span class="sxs-lookup"><span data-stu-id="b92f8-208">The `wsFederationHttpBinding` controls the details of the message security settings in [\<message>](message-element-of-wsfederationhttpbinding.md).</span></span> <span data-ttu-id="b92f8-209">Tenga en cuenta que el elemento de [ \<> de seguridad](security-of-wsfederationhttpbinding.md) proporciona acceso de solo, ya que no se puede cambiar la seguridad utilizada por el enlace una vez creado el enlace.</span><span class="sxs-lookup"><span data-stu-id="b92f8-209">Note that the [\<security>](security-of-wsfederationhttpbinding.md) element provides get access only as the security used by the binding cannot be changed once the binding is created.</span></span>

<span data-ttu-id="b92f8-210">`wsFederationHttpBinding` También proporciona un atributo privacyNoticeAt para establecer y recuperar el URI en el que se encuentra el aviso de privacidad.</span><span class="sxs-lookup"><span data-stu-id="b92f8-210">The `wsFederationHttpBinding` also provides a privacyNoticeAt attribute to set and retrieve the URI at which the privacy notice is located.</span></span>

<span data-ttu-id="b92f8-211">Mantener la directiva protegida es especialmente importante en escenarios de federación.</span><span class="sxs-lookup"><span data-stu-id="b92f8-211">Keeping policy secure is especially important in federation scenarios.</span></span> <span data-ttu-id="b92f8-212">Se recomienda utilizar algún formulario de seguridad, como HTTPS, para proteger la directiva de los usuarios malintencionados.</span><span class="sxs-lookup"><span data-stu-id="b92f8-212">The recommendation is to use some form of security, such as HTTPS, to protect the policy from malicious users.</span></span>

<span data-ttu-id="b92f8-213">En los escenarios de federación que utilizan este enlace, la directiva del servicio tiene potencialmente información importante como la clave para utilizar para cifrar el token emitido (SAML), el tipo de demandas para introducir el token, etc.</span><span class="sxs-lookup"><span data-stu-id="b92f8-213">In federation scenarios using this binding, the service policy potentially has important information such as the key to use to encrypt the issued (SAML) token, the type of claims to put in the token, and so forth.</span></span> <span data-ttu-id="b92f8-214">Si esta directiva se manipula, un atacante podría detectar la clave del token emitido que conduce a una modificación posterior, divulgación de información y otros comportamientos malintencionados.</span><span class="sxs-lookup"><span data-stu-id="b92f8-214">If this policy is tampered with, an attacker could discover the key of the issued token leading to further tampering, info disclosure and other malicious behavior.</span></span> <span data-ttu-id="b92f8-215">Para ayudar a evitar esto, la directiva se debe obtener firmemente (utilizando HTTPS, por ejemplo) del servicio.</span><span class="sxs-lookup"><span data-stu-id="b92f8-215">To help prevent this, the policy must be obtained securely (for example using HTTPS) from the service.</span></span>

<span data-ttu-id="b92f8-216">Para obtener más información sobre este enlace, [vea cómo: Cree un WSFederationHttpBinding](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="b92f8-216">For more information on this binding, see [How to: Create a WSFederationHttpBinding](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md).</span></span>

## <a name="example"></a><span data-ttu-id="b92f8-217">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b92f8-217">Example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="b92f8-218">Vea también</span><span class="sxs-lookup"><span data-stu-id="b92f8-218">See also</span></span>

- <xref:System.ServiceModel.WSFederationHttpBinding>
- <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement>
- [<span data-ttu-id="b92f8-219">Procedimientos: Creación de un WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="b92f8-219">How to: Create a WSFederationHttpBinding</span></span>](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
- [<span data-ttu-id="b92f8-220">Enlaces</span><span class="sxs-lookup"><span data-stu-id="b92f8-220">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="b92f8-221">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="b92f8-221">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="b92f8-222">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="b92f8-222">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="b92f8-223">\<binding></span><span class="sxs-lookup"><span data-stu-id="b92f8-223">\<binding></span></span>](../../../misc/binding.md)
