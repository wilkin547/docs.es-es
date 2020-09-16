---
title: <wsFederationHttpBinding>
ms.date: 03/30/2017
helpviewer_keywords:
- wsFederationBinding element
ms.assetid: 9c3312b4-2137-4e71-bf3f-de1cf8e9be79
ms.openlocfilehash: a57b5ff0b4a8186ffc4c01b5e0824100f265551c
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557286"
---
# \<wsFederationHttpBinding>

<span data-ttu-id="3cb14-101">Define un enlace que admite WS-Federation.</span><span class="sxs-lookup"><span data-stu-id="3cb14-101">Defines a binding that supports WS-Federation.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<wsFederationHttpBinding>**  

## <a name="syntax"></a><span data-ttu-id="3cb14-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3cb14-102">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="3cb14-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3cb14-103">Attributes and Elements</span></span>

<span data-ttu-id="3cb14-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3cb14-104">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="3cb14-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="3cb14-105">Attributes</span></span>

|<span data-ttu-id="3cb14-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="3cb14-106">Attribute</span></span>|<span data-ttu-id="3cb14-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="3cb14-107">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="3cb14-108">bypassProxyOnLocal</span><span class="sxs-lookup"><span data-stu-id="3cb14-108">bypassProxyOnLocal</span></span>|<span data-ttu-id="3cb14-109">Valor de tipo booleano que indica si se omitirá el servidor proxy para las direcciones locales.</span><span class="sxs-lookup"><span data-stu-id="3cb14-109">A Boolean value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="3cb14-110">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="3cb14-110">The default is `false`.</span></span>|
|<span data-ttu-id="3cb14-111">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="3cb14-111">closeTimeout</span></span>|<span data-ttu-id="3cb14-112">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de cierre para completarse.</span><span class="sxs-lookup"><span data-stu-id="3cb14-112">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="3cb14-113">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="3cb14-113">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="3cb14-114">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="3cb14-114">The default is 00:01:00.</span></span>|
|<span data-ttu-id="3cb14-115">hostnameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="3cb14-115">hostnameComparisonMode</span></span>|<span data-ttu-id="3cb14-116">Especifica el modo de comparación de nombres de host HTTP usado para analizar los URI.</span><span class="sxs-lookup"><span data-stu-id="3cb14-116">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="3cb14-117">Este atributo es del tipo <xref:System.ServiceModel.HostNameComparisonMode>, que indica si se va a utilizar el nombre del host para llegar al servicio cuando coincida en el URI.</span><span class="sxs-lookup"><span data-stu-id="3cb14-117">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="3cb14-118">El valor predeterminado es <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, que omite el nombre del host en la coincidencia.</span><span class="sxs-lookup"><span data-stu-id="3cb14-118">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|
|<span data-ttu-id="3cb14-119">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="3cb14-119">maxBufferPoolSize</span></span>|<span data-ttu-id="3cb14-120">Entero que especifica el tamaño máximo del grupo de búferes para este enlace.</span><span class="sxs-lookup"><span data-stu-id="3cb14-120">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="3cb14-121">El valor predeterminado es 524.288 bytes (512x1024).</span><span class="sxs-lookup"><span data-stu-id="3cb14-121">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="3cb14-122">En muchas partes de Windows Communication Foundation (WCF) se utilizan búferes.</span><span class="sxs-lookup"><span data-stu-id="3cb14-122">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="3cb14-123">Crear y destruir búferes cada vez que se usan es caro, y la recolección de elementos no utilizados para los búferes también es cara.</span><span class="sxs-lookup"><span data-stu-id="3cb14-123">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="3cb14-124">Con grupos de búferes, puede tomar un búfer del grupo, usarlo y devolverlo al grupo una vez haya terminado.</span><span class="sxs-lookup"><span data-stu-id="3cb14-124">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="3cb14-125">Así se evita la sobrecarga al crear y destruir búferes.</span><span class="sxs-lookup"><span data-stu-id="3cb14-125">Thus the overhead in creating and destroying buffers is avoided.</span></span>|
|<span data-ttu-id="3cb14-126">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="3cb14-126">maxReceivedMessageSize</span></span>|<span data-ttu-id="3cb14-127">Entero positivo que especifica el tamaño máximo del mensaje, en bytes, incluidos los encabezados, que se puede recibir en un canal configurado con este enlace.</span><span class="sxs-lookup"><span data-stu-id="3cb14-127">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="3cb14-128">El remitente de un mensaje que supere este límite recibirá un error SOAP.</span><span class="sxs-lookup"><span data-stu-id="3cb14-128">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="3cb14-129">El destinatario quita el mensaje y crea una entrada del evento en el registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="3cb14-129">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="3cb14-130">El valor predeterminado es 65536.</span><span class="sxs-lookup"><span data-stu-id="3cb14-130">The default is 65536.</span></span>|
|<span data-ttu-id="3cb14-131">messageEncoding</span><span class="sxs-lookup"><span data-stu-id="3cb14-131">messageEncoding</span></span>|<span data-ttu-id="3cb14-132">Define el codificador utilizado para codificar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="3cb14-132">Defines the encoder used to encode the message.</span></span> <span data-ttu-id="3cb14-133">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="3cb14-133">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="3cb14-134">-Text: usar un codificador de mensajes de texto.</span><span class="sxs-lookup"><span data-stu-id="3cb14-134">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="3cb14-135">-MTOM: usar un codificador del mecanismo de la organización de transmisión de mensajes 1,0 (MTOM).</span><span class="sxs-lookup"><span data-stu-id="3cb14-135">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><br /> <span data-ttu-id="3cb14-136">El valor predeterminado es Text.</span><span class="sxs-lookup"><span data-stu-id="3cb14-136">The default is Text.</span></span><br /><br /> <span data-ttu-id="3cb14-137">Este atributo es del tipo <xref:System.ServiceModel.WSMessageEncoding>.</span><span class="sxs-lookup"><span data-stu-id="3cb14-137">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|
|<span data-ttu-id="3cb14-138">name</span><span class="sxs-lookup"><span data-stu-id="3cb14-138">name</span></span>|<span data-ttu-id="3cb14-139">Cadena que contiene el nombre de configuración del enlace.</span><span class="sxs-lookup"><span data-stu-id="3cb14-139">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="3cb14-140">Este valor debe ser único porque se usa como identificación del enlace.</span><span class="sxs-lookup"><span data-stu-id="3cb14-140">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="3cb14-141">A partir de .NET Framework 4, no es necesario que los enlaces y los comportamientos tengan un nombre.</span><span class="sxs-lookup"><span data-stu-id="3cb14-141">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="3cb14-142">Para obtener más información sobre la configuración predeterminada y los enlaces y comportamientos sin nombre, vea [configuración simplificada](../../../wcf/simplified-configuration.md) y [configuración simplificada para servicios WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="3cb14-142">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|
|<span data-ttu-id="3cb14-143">openTimeout</span><span class="sxs-lookup"><span data-stu-id="3cb14-143">openTimeout</span></span>|<span data-ttu-id="3cb14-144">Valor de la estructura <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de apertura para completarse.</span><span class="sxs-lookup"><span data-stu-id="3cb14-144">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="3cb14-145">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="3cb14-145">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="3cb14-146">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="3cb14-146">The default is 00:01:00.</span></span>|
|<span data-ttu-id="3cb14-147">privacyNoticeAt</span><span class="sxs-lookup"><span data-stu-id="3cb14-147">privacyNoticeAt</span></span>|<span data-ttu-id="3cb14-148">Una cadena que especifica un URI en el que el aviso de privacidad se encuentra.</span><span class="sxs-lookup"><span data-stu-id="3cb14-148">A String that specifies a URI at which the privacy notice is located.</span></span>|
|<span data-ttu-id="3cb14-149">privacyNoticeVersion</span><span class="sxs-lookup"><span data-stu-id="3cb14-149">privacyNoticeVersion</span></span>|<span data-ttu-id="3cb14-150">Un entero que especifica la versión del aviso de privacidad actual.</span><span class="sxs-lookup"><span data-stu-id="3cb14-150">An integer that specifies the version of the current privacy notice.</span></span>|
|<span data-ttu-id="3cb14-151">proxyAddress</span><span class="sxs-lookup"><span data-stu-id="3cb14-151">proxyAddress</span></span>|<span data-ttu-id="3cb14-152">Un URI que especifica la dirección del proxy HTTP.</span><span class="sxs-lookup"><span data-stu-id="3cb14-152">A URI that specifies the address of the HTTP proxy.</span></span> <span data-ttu-id="3cb14-153">Si `useDefaultWebProxy` es `true`, este valor debe ser `null`.</span><span class="sxs-lookup"><span data-stu-id="3cb14-153">If `useDefaultWebProxy` is `true`, this setting must be `null`.</span></span> <span data-ttu-id="3cb14-154">De manera predeterminada, es `null`.</span><span class="sxs-lookup"><span data-stu-id="3cb14-154">The default is `null`.</span></span>|
|<span data-ttu-id="3cb14-155">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="3cb14-155">receiveTimeout</span></span>|<span data-ttu-id="3cb14-156">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de recepción para completarse.</span><span class="sxs-lookup"><span data-stu-id="3cb14-156">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="3cb14-157">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="3cb14-157">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="3cb14-158">El valor predeterminado es 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="3cb14-158">The default is 00:10:00.</span></span>|
|<span data-ttu-id="3cb14-159">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="3cb14-159">sendTimeout</span></span>|<span data-ttu-id="3cb14-160">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de envío para completarse.</span><span class="sxs-lookup"><span data-stu-id="3cb14-160">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="3cb14-161">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="3cb14-161">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="3cb14-162">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="3cb14-162">The default is 00:01:00.</span></span>|
|<span data-ttu-id="3cb14-163">textEncoding</span><span class="sxs-lookup"><span data-stu-id="3cb14-163">textEncoding</span></span>|<span data-ttu-id="3cb14-164">Establece el codificador del juego de caracteres que se va a usar para emitir los mensajes en el enlace.</span><span class="sxs-lookup"><span data-stu-id="3cb14-164">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="3cb14-165">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="3cb14-165">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="3cb14-166">-BigEndianUnicode: codificación Unicode BigEndian.</span><span class="sxs-lookup"><span data-stu-id="3cb14-166">-   BigEndianUnicode: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="3cb14-167">-Unicode: codificación de 16 bits.</span><span class="sxs-lookup"><span data-stu-id="3cb14-167">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="3cb14-168">-UTF8: codificación de 8 bits</span><span class="sxs-lookup"><span data-stu-id="3cb14-168">-   UTF8: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="3cb14-169">El valor predeterminado es UTF8.</span><span class="sxs-lookup"><span data-stu-id="3cb14-169">The default is UTF8.</span></span> <span data-ttu-id="3cb14-170">Este atributo es del tipo <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="3cb14-170">This attribute is of type <xref:System.Text.Encoding>..</span></span>|
|<span data-ttu-id="3cb14-171">transactionFlow</span><span class="sxs-lookup"><span data-stu-id="3cb14-171">transactionFlow</span></span>|<span data-ttu-id="3cb14-172">Valor booleano que especifica si el enlace admite las transacciones WS del flujo.</span><span class="sxs-lookup"><span data-stu-id="3cb14-172">A Boolean value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="3cb14-173">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="3cb14-173">The default is `false`.</span></span>|
|<span data-ttu-id="3cb14-174">useDefaultWebProxy</span><span class="sxs-lookup"><span data-stu-id="3cb14-174">useDefaultWebProxy</span></span>|<span data-ttu-id="3cb14-175">Valor de tipo booleano que indica si se utiliza el proxy HTTP del sistema configurado automáticamente.</span><span class="sxs-lookup"><span data-stu-id="3cb14-175">A Boolean value that indicates whether the system’s auto-configured HTTP proxy is used.</span></span> <span data-ttu-id="3cb14-176">La dirección de proxy debe ser `null` (es decir, sin establecer) si este atributo es `true`.</span><span class="sxs-lookup"><span data-stu-id="3cb14-176">The proxy address must be `null` (that is, not set) if this attribute is `true`.</span></span> <span data-ttu-id="3cb14-177">De manera predeterminada, es `true`.</span><span class="sxs-lookup"><span data-stu-id="3cb14-177">The default is `true`.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="3cb14-178">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3cb14-178">Child Elements</span></span>

|<span data-ttu-id="3cb14-179">Elemento</span><span class="sxs-lookup"><span data-stu-id="3cb14-179">Element</span></span>|<span data-ttu-id="3cb14-180">Descripción</span><span class="sxs-lookup"><span data-stu-id="3cb14-180">Description</span></span>|
|-------------|-----------------|
|[\<security>](security-of-wsfederationhttpbinding.md)|<span data-ttu-id="3cb14-181">Define la configuración de seguridad del mensaje.</span><span class="sxs-lookup"><span data-stu-id="3cb14-181">Defines the security settings for the message.</span></span> <span data-ttu-id="3cb14-182">Este elemento es del tipo <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="3cb14-182">This element is of type <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>.</span></span>|
|[\<readerQuotas>](/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="3cb14-183">Define las restricciones en la complejidad de los mensajes SOAP que pueden ser procesados por los puntos de conexión configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="3cb14-183">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="3cb14-184">Este elemento es del tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="3cb14-184">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|
|[\<reliableSession>](/previous-versions/ms731375(v=vs.90))|<span data-ttu-id="3cb14-185">Especifica si se establecen sesiones confiables entre los puntos de conexión del canal.</span><span class="sxs-lookup"><span data-stu-id="3cb14-185">Specifies if reliable sessions are established between channel endpoints.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="3cb14-186">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3cb14-186">Parent Elements</span></span>

|<span data-ttu-id="3cb14-187">Elemento</span><span class="sxs-lookup"><span data-stu-id="3cb14-187">Element</span></span>|<span data-ttu-id="3cb14-188">Descripción</span><span class="sxs-lookup"><span data-stu-id="3cb14-188">Description</span></span>|
|-------------|-----------------|
|[\<bindings>](bindings.md)|<span data-ttu-id="3cb14-189">Este elemento contiene una colección de enlaces estándar y personalizados.</span><span class="sxs-lookup"><span data-stu-id="3cb14-189">This element holds a collection of standard and custom bindings.</span></span>|

## <a name="remarks"></a><span data-ttu-id="3cb14-190">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3cb14-190">Remarks</span></span>

<span data-ttu-id="3cb14-191">La federación es la capacidad de compartir identidades en varios sistemas para la autenticación y autorización.</span><span class="sxs-lookup"><span data-stu-id="3cb14-191">Federation is the ability to share identities across multiple systems for authentication and authorization.</span></span> <span data-ttu-id="3cb14-192">Estas identidades pueden hacer referencia a usuarios o a equipos.</span><span class="sxs-lookup"><span data-stu-id="3cb14-192">These identities can refer to users or to machines.</span></span> <span data-ttu-id="3cb14-193">El HTTP federado admite la seguridad de SOAP así como la seguridad de modo mixto, pero no permite utilizar únicamente la seguridad de transporte.</span><span class="sxs-lookup"><span data-stu-id="3cb14-193">Federated HTTP supports SOAP security as well as mixed-mode security, but it does not support exclusively using transport security.</span></span> <span data-ttu-id="3cb14-194">Este enlace proporciona compatibilidad con Windows Communication Foundation (WCF) para el protocolo WS-Federation.</span><span class="sxs-lookup"><span data-stu-id="3cb14-194">This binding provides Windows Communication Foundation (WCF) support for the WS-Federation protocol.</span></span> <span data-ttu-id="3cb14-195">Los servicios configurados con este enlace deben utilizar el transporte de HTTP.</span><span class="sxs-lookup"><span data-stu-id="3cb14-195">Services configured with this binding must use the HTTP transport.</span></span>

<span data-ttu-id="3cb14-196">Los enlaces están compuestos de una pila de elementos de enlace.</span><span class="sxs-lookup"><span data-stu-id="3cb14-196">Bindings consist of a stack of binding elements.</span></span> <span data-ttu-id="3cb14-197">La pila de elementos de enlace en</span><span class="sxs-lookup"><span data-stu-id="3cb14-197">The stack of binding elements in</span></span>

<span data-ttu-id="3cb14-198">`wsFederationHttpBinding`es la misma que la que contiene `wsHttpBinding`</span><span class="sxs-lookup"><span data-stu-id="3cb14-198">`wsFederationHttpBinding` is the same as that contained in `wsHttpBinding`</span></span>

<span data-ttu-id="3cb14-199">Cuando [\<security>](security-of-wsfederationhttpbinding.md) se establece en el valor predeterminado de <xref:System.ServiceModel.WSFederationHttpSecurityMode.Message> .</span><span class="sxs-lookup"><span data-stu-id="3cb14-199">when [\<security>](security-of-wsfederationhttpbinding.md) is set to the default value of <xref:System.ServiceModel.WSFederationHttpSecurityMode.Message>.</span></span>

<span data-ttu-id="3cb14-200">`wsFederationHttpBinding`Controla los detalles de la configuración de seguridad del mensaje en [\<message>](message-element-of-wsfederationhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="3cb14-200">The `wsFederationHttpBinding` controls the details of the message security settings in [\<message>](message-element-of-wsfederationhttpbinding.md).</span></span> <span data-ttu-id="3cb14-201">Tenga en cuenta que el [\<security>](security-of-wsfederationhttpbinding.md) elemento proporciona acceso solo cuando la seguridad que usa el enlace no se puede cambiar una vez creado el enlace.</span><span class="sxs-lookup"><span data-stu-id="3cb14-201">Note that the [\<security>](security-of-wsfederationhttpbinding.md) element provides get access only as the security used by the binding cannot be changed once the binding is created.</span></span>

<span data-ttu-id="3cb14-202">`wsFederationHttpBinding`También proporciona un atributo privacyNoticeAt para establecer y recuperar el URI en el que se encuentra el aviso de privacidad.</span><span class="sxs-lookup"><span data-stu-id="3cb14-202">The `wsFederationHttpBinding` also provides a privacyNoticeAt attribute to set and retrieve the URI at which the privacy notice is located.</span></span>

<span data-ttu-id="3cb14-203">Mantener la directiva protegida es especialmente importante en escenarios de federación.</span><span class="sxs-lookup"><span data-stu-id="3cb14-203">Keeping policy secure is especially important in federation scenarios.</span></span> <span data-ttu-id="3cb14-204">Se recomienda utilizar algún formulario de seguridad, como HTTPS, para proteger la directiva de los usuarios malintencionados.</span><span class="sxs-lookup"><span data-stu-id="3cb14-204">The recommendation is to use some form of security, such as HTTPS, to protect the policy from malicious users.</span></span>

<span data-ttu-id="3cb14-205">En los escenarios de federación que utilizan este enlace, la directiva del servicio tiene potencialmente información importante como la clave para utilizar para cifrar el token emitido (SAML), el tipo de demandas para introducir el token, etc.</span><span class="sxs-lookup"><span data-stu-id="3cb14-205">In federation scenarios using this binding, the service policy potentially has important information such as the key to use to encrypt the issued (SAML) token, the type of claims to put in the token, and so forth.</span></span> <span data-ttu-id="3cb14-206">Si esta directiva se manipula, un atacante podría detectar la clave del token emitido que conduce a una modificación posterior, divulgación de información y otros comportamientos malintencionados.</span><span class="sxs-lookup"><span data-stu-id="3cb14-206">If this policy is tampered with, an attacker could discover the key of the issued token leading to further tampering, info disclosure and other malicious behavior.</span></span> <span data-ttu-id="3cb14-207">Para ayudar a evitar esto, la directiva se debe obtener firmemente (utilizando HTTPS, por ejemplo) del servicio.</span><span class="sxs-lookup"><span data-stu-id="3cb14-207">To help prevent this, the policy must be obtained securely (for example using HTTPS) from the service.</span></span>

<span data-ttu-id="3cb14-208">Para obtener más información sobre este enlace, vea [Cómo: crear un WSFederationHttpBinding](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="3cb14-208">For more information on this binding, see [How to: Create a WSFederationHttpBinding](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md).</span></span>

## <a name="example"></a><span data-ttu-id="3cb14-209">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3cb14-209">Example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="3cb14-210">Vea también</span><span class="sxs-lookup"><span data-stu-id="3cb14-210">See also</span></span>

- <xref:System.ServiceModel.WSFederationHttpBinding>
- <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement>
- [<span data-ttu-id="3cb14-211">Procedimiento para crear un WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="3cb14-211">How to: Create a WSFederationHttpBinding</span></span>](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
- [<span data-ttu-id="3cb14-212">Enlaces</span><span class="sxs-lookup"><span data-stu-id="3cb14-212">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="3cb14-213">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="3cb14-213">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="3cb14-214">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="3cb14-214">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
