---
description: 'Más información acerca de: <wsFederationHttpBinding>'
title: <wsFederationHttpBinding>
ms.date: 03/30/2017
helpviewer_keywords:
- wsFederationBinding element
ms.assetid: 9c3312b4-2137-4e71-bf3f-de1cf8e9be79
ms.openlocfilehash: 1217c4e46fe18ea5df478b8a790be4da33590c92
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99682103"
---
# \<wsFederationHttpBinding>

<span data-ttu-id="07e44-102">Define un enlace que admite WS-Federation.</span><span class="sxs-lookup"><span data-stu-id="07e44-102">Defines a binding that supports WS-Federation.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<wsFederationHttpBinding>**  

## <a name="syntax"></a><span data-ttu-id="07e44-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="07e44-103">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="07e44-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="07e44-104">Attributes and Elements</span></span>

<span data-ttu-id="07e44-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="07e44-105">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="07e44-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="07e44-106">Attributes</span></span>

|<span data-ttu-id="07e44-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="07e44-107">Attribute</span></span>|<span data-ttu-id="07e44-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="07e44-108">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="07e44-109">bypassProxyOnLocal</span><span class="sxs-lookup"><span data-stu-id="07e44-109">bypassProxyOnLocal</span></span>|<span data-ttu-id="07e44-110">Valor de tipo booleano que indica si se omitirá el servidor proxy para las direcciones locales.</span><span class="sxs-lookup"><span data-stu-id="07e44-110">A Boolean value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="07e44-111">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="07e44-111">The default is `false`.</span></span>|
|<span data-ttu-id="07e44-112">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="07e44-112">closeTimeout</span></span>|<span data-ttu-id="07e44-113">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de cierre para completarse.</span><span class="sxs-lookup"><span data-stu-id="07e44-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="07e44-114">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="07e44-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="07e44-115">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="07e44-115">The default is 00:01:00.</span></span>|
|<span data-ttu-id="07e44-116">hostnameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="07e44-116">hostnameComparisonMode</span></span>|<span data-ttu-id="07e44-117">Especifica el modo de comparación de nombres de host HTTP usado para analizar los URI.</span><span class="sxs-lookup"><span data-stu-id="07e44-117">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="07e44-118">Este atributo es del tipo <xref:System.ServiceModel.HostNameComparisonMode>, que indica si se va a utilizar el nombre del host para llegar al servicio cuando coincida en el URI.</span><span class="sxs-lookup"><span data-stu-id="07e44-118">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="07e44-119">El valor predeterminado es <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, que omite el nombre del host en la coincidencia.</span><span class="sxs-lookup"><span data-stu-id="07e44-119">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|
|<span data-ttu-id="07e44-120">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="07e44-120">maxBufferPoolSize</span></span>|<span data-ttu-id="07e44-121">Entero que especifica el tamaño máximo del grupo de búferes para este enlace.</span><span class="sxs-lookup"><span data-stu-id="07e44-121">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="07e44-122">El valor predeterminado es 524.288 bytes (512x1024).</span><span class="sxs-lookup"><span data-stu-id="07e44-122">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="07e44-123">En muchas partes de Windows Communication Foundation (WCF) se utilizan búferes.</span><span class="sxs-lookup"><span data-stu-id="07e44-123">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="07e44-124">Crear y destruir búferes cada vez que se usan es caro, y la recolección de elementos no utilizados para los búferes también es cara.</span><span class="sxs-lookup"><span data-stu-id="07e44-124">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="07e44-125">Con grupos de búferes, puede tomar un búfer del grupo, usarlo y devolverlo al grupo una vez haya terminado.</span><span class="sxs-lookup"><span data-stu-id="07e44-125">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="07e44-126">Así se evita la sobrecarga al crear y destruir búferes.</span><span class="sxs-lookup"><span data-stu-id="07e44-126">Thus the overhead in creating and destroying buffers is avoided.</span></span>|
|<span data-ttu-id="07e44-127">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="07e44-127">maxReceivedMessageSize</span></span>|<span data-ttu-id="07e44-128">Entero positivo que especifica el tamaño máximo del mensaje, en bytes, incluidos los encabezados, que se puede recibir en un canal configurado con este enlace.</span><span class="sxs-lookup"><span data-stu-id="07e44-128">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="07e44-129">El remitente de un mensaje que supere este límite recibirá un error SOAP.</span><span class="sxs-lookup"><span data-stu-id="07e44-129">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="07e44-130">El destinatario quita el mensaje y crea una entrada del evento en el registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="07e44-130">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="07e44-131">El valor predeterminado es 65536.</span><span class="sxs-lookup"><span data-stu-id="07e44-131">The default is 65536.</span></span>|
|<span data-ttu-id="07e44-132">messageEncoding</span><span class="sxs-lookup"><span data-stu-id="07e44-132">messageEncoding</span></span>|<span data-ttu-id="07e44-133">Define el codificador utilizado para codificar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="07e44-133">Defines the encoder used to encode the message.</span></span> <span data-ttu-id="07e44-134">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="07e44-134">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="07e44-135">-Text: usar un codificador de mensajes de texto.</span><span class="sxs-lookup"><span data-stu-id="07e44-135">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="07e44-136">-MTOM: usar un codificador del mecanismo de la organización de transmisión de mensajes 1,0 (MTOM).</span><span class="sxs-lookup"><span data-stu-id="07e44-136">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><br /> <span data-ttu-id="07e44-137">El valor predeterminado es Text.</span><span class="sxs-lookup"><span data-stu-id="07e44-137">The default is Text.</span></span><br /><br /> <span data-ttu-id="07e44-138">Este atributo es del tipo <xref:System.ServiceModel.WSMessageEncoding>.</span><span class="sxs-lookup"><span data-stu-id="07e44-138">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|
|<span data-ttu-id="07e44-139">name</span><span class="sxs-lookup"><span data-stu-id="07e44-139">name</span></span>|<span data-ttu-id="07e44-140">Cadena que contiene el nombre de configuración del enlace.</span><span class="sxs-lookup"><span data-stu-id="07e44-140">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="07e44-141">Este valor debe ser único porque se usa como identificación del enlace.</span><span class="sxs-lookup"><span data-stu-id="07e44-141">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="07e44-142">A partir de .NET Framework 4, no es necesario que los enlaces y los comportamientos tengan un nombre.</span><span class="sxs-lookup"><span data-stu-id="07e44-142">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="07e44-143">Para obtener más información sobre la configuración predeterminada y los enlaces y comportamientos sin nombre, vea [configuración simplificada](../../../wcf/simplified-configuration.md) y [configuración simplificada para servicios WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="07e44-143">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|
|<span data-ttu-id="07e44-144">openTimeout</span><span class="sxs-lookup"><span data-stu-id="07e44-144">openTimeout</span></span>|<span data-ttu-id="07e44-145">Valor de la estructura <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de apertura para completarse.</span><span class="sxs-lookup"><span data-stu-id="07e44-145">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="07e44-146">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="07e44-146">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="07e44-147">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="07e44-147">The default is 00:01:00.</span></span>|
|<span data-ttu-id="07e44-148">privacyNoticeAt</span><span class="sxs-lookup"><span data-stu-id="07e44-148">privacyNoticeAt</span></span>|<span data-ttu-id="07e44-149">Una cadena que especifica un URI en el que el aviso de privacidad se encuentra.</span><span class="sxs-lookup"><span data-stu-id="07e44-149">A String that specifies a URI at which the privacy notice is located.</span></span>|
|<span data-ttu-id="07e44-150">privacyNoticeVersion</span><span class="sxs-lookup"><span data-stu-id="07e44-150">privacyNoticeVersion</span></span>|<span data-ttu-id="07e44-151">Un entero que especifica la versión del aviso de privacidad actual.</span><span class="sxs-lookup"><span data-stu-id="07e44-151">An integer that specifies the version of the current privacy notice.</span></span>|
|<span data-ttu-id="07e44-152">proxyAddress</span><span class="sxs-lookup"><span data-stu-id="07e44-152">proxyAddress</span></span>|<span data-ttu-id="07e44-153">Un URI que especifica la dirección del proxy HTTP.</span><span class="sxs-lookup"><span data-stu-id="07e44-153">A URI that specifies the address of the HTTP proxy.</span></span> <span data-ttu-id="07e44-154">Si `useDefaultWebProxy` es `true`, este valor debe ser `null`.</span><span class="sxs-lookup"><span data-stu-id="07e44-154">If `useDefaultWebProxy` is `true`, this setting must be `null`.</span></span> <span data-ttu-id="07e44-155">De manera predeterminada, es `null`.</span><span class="sxs-lookup"><span data-stu-id="07e44-155">The default is `null`.</span></span>|
|<span data-ttu-id="07e44-156">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="07e44-156">receiveTimeout</span></span>|<span data-ttu-id="07e44-157">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de recepción para completarse.</span><span class="sxs-lookup"><span data-stu-id="07e44-157">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="07e44-158">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="07e44-158">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="07e44-159">El valor predeterminado es 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="07e44-159">The default is 00:10:00.</span></span>|
|<span data-ttu-id="07e44-160">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="07e44-160">sendTimeout</span></span>|<span data-ttu-id="07e44-161">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de envío para completarse.</span><span class="sxs-lookup"><span data-stu-id="07e44-161">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="07e44-162">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="07e44-162">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="07e44-163">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="07e44-163">The default is 00:01:00.</span></span>|
|<span data-ttu-id="07e44-164">textEncoding</span><span class="sxs-lookup"><span data-stu-id="07e44-164">textEncoding</span></span>|<span data-ttu-id="07e44-165">Establece el codificador del juego de caracteres que se va a usar para emitir los mensajes en el enlace.</span><span class="sxs-lookup"><span data-stu-id="07e44-165">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="07e44-166">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="07e44-166">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="07e44-167">-BigEndianUnicode: codificación Unicode BigEndian.</span><span class="sxs-lookup"><span data-stu-id="07e44-167">-   BigEndianUnicode: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="07e44-168">-Unicode: codificación de 16 bits.</span><span class="sxs-lookup"><span data-stu-id="07e44-168">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="07e44-169">-UTF8: codificación de 8 bits</span><span class="sxs-lookup"><span data-stu-id="07e44-169">-   UTF8: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="07e44-170">El valor predeterminado es UTF8.</span><span class="sxs-lookup"><span data-stu-id="07e44-170">The default is UTF8.</span></span> <span data-ttu-id="07e44-171">Este atributo es del tipo <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="07e44-171">This attribute is of type <xref:System.Text.Encoding>..</span></span>|
|<span data-ttu-id="07e44-172">transactionFlow</span><span class="sxs-lookup"><span data-stu-id="07e44-172">transactionFlow</span></span>|<span data-ttu-id="07e44-173">Valor booleano que especifica si el enlace admite las transacciones WS del flujo.</span><span class="sxs-lookup"><span data-stu-id="07e44-173">A Boolean value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="07e44-174">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="07e44-174">The default is `false`.</span></span>|
|<span data-ttu-id="07e44-175">useDefaultWebProxy</span><span class="sxs-lookup"><span data-stu-id="07e44-175">useDefaultWebProxy</span></span>|<span data-ttu-id="07e44-176">Valor de tipo booleano que indica si se utiliza el proxy HTTP del sistema configurado automáticamente.</span><span class="sxs-lookup"><span data-stu-id="07e44-176">A Boolean value that indicates whether the system’s auto-configured HTTP proxy is used.</span></span> <span data-ttu-id="07e44-177">La dirección de proxy debe ser `null` (es decir, sin establecer) si este atributo es `true`.</span><span class="sxs-lookup"><span data-stu-id="07e44-177">The proxy address must be `null` (that is, not set) if this attribute is `true`.</span></span> <span data-ttu-id="07e44-178">De manera predeterminada, es `true`.</span><span class="sxs-lookup"><span data-stu-id="07e44-178">The default is `true`.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="07e44-179">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="07e44-179">Child Elements</span></span>

|<span data-ttu-id="07e44-180">Elemento</span><span class="sxs-lookup"><span data-stu-id="07e44-180">Element</span></span>|<span data-ttu-id="07e44-181">Descripción</span><span class="sxs-lookup"><span data-stu-id="07e44-181">Description</span></span>|
|-------------|-----------------|
|[\<security>](security-of-wsfederationhttpbinding.md)|<span data-ttu-id="07e44-182">Define la configuración de seguridad del mensaje.</span><span class="sxs-lookup"><span data-stu-id="07e44-182">Defines the security settings for the message.</span></span> <span data-ttu-id="07e44-183">Este elemento es del tipo <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="07e44-183">This element is of type <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>.</span></span>|
|[\<readerQuotas>](/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="07e44-184">Define las restricciones en la complejidad de los mensajes SOAP que pueden ser procesados por los puntos de conexión configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="07e44-184">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="07e44-185">Este elemento es del tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="07e44-185">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|
|[\<reliableSession>](/previous-versions/ms731375(v=vs.90))|<span data-ttu-id="07e44-186">Especifica si se establecen sesiones confiables entre los puntos de conexión del canal.</span><span class="sxs-lookup"><span data-stu-id="07e44-186">Specifies if reliable sessions are established between channel endpoints.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="07e44-187">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="07e44-187">Parent Elements</span></span>

|<span data-ttu-id="07e44-188">Elemento</span><span class="sxs-lookup"><span data-stu-id="07e44-188">Element</span></span>|<span data-ttu-id="07e44-189">Descripción</span><span class="sxs-lookup"><span data-stu-id="07e44-189">Description</span></span>|
|-------------|-----------------|
|[\<bindings>](bindings.md)|<span data-ttu-id="07e44-190">Este elemento contiene una colección de enlaces estándar y personalizados.</span><span class="sxs-lookup"><span data-stu-id="07e44-190">This element holds a collection of standard and custom bindings.</span></span>|

## <a name="remarks"></a><span data-ttu-id="07e44-191">Observaciones</span><span class="sxs-lookup"><span data-stu-id="07e44-191">Remarks</span></span>

<span data-ttu-id="07e44-192">La federación es la capacidad de compartir identidades en varios sistemas para la autenticación y autorización.</span><span class="sxs-lookup"><span data-stu-id="07e44-192">Federation is the ability to share identities across multiple systems for authentication and authorization.</span></span> <span data-ttu-id="07e44-193">Estas identidades pueden hacer referencia a usuarios o a equipos.</span><span class="sxs-lookup"><span data-stu-id="07e44-193">These identities can refer to users or to machines.</span></span> <span data-ttu-id="07e44-194">El HTTP federado admite la seguridad de SOAP así como la seguridad de modo mixto, pero no permite utilizar únicamente la seguridad de transporte.</span><span class="sxs-lookup"><span data-stu-id="07e44-194">Federated HTTP supports SOAP security as well as mixed-mode security, but it does not support exclusively using transport security.</span></span> <span data-ttu-id="07e44-195">Este enlace proporciona compatibilidad con Windows Communication Foundation (WCF) para el protocolo WS-Federation.</span><span class="sxs-lookup"><span data-stu-id="07e44-195">This binding provides Windows Communication Foundation (WCF) support for the WS-Federation protocol.</span></span> <span data-ttu-id="07e44-196">Los servicios configurados con este enlace deben utilizar el transporte de HTTP.</span><span class="sxs-lookup"><span data-stu-id="07e44-196">Services configured with this binding must use the HTTP transport.</span></span>

<span data-ttu-id="07e44-197">Los enlaces están compuestos de una pila de elementos de enlace.</span><span class="sxs-lookup"><span data-stu-id="07e44-197">Bindings consist of a stack of binding elements.</span></span> <span data-ttu-id="07e44-198">La pila de elementos de enlace en</span><span class="sxs-lookup"><span data-stu-id="07e44-198">The stack of binding elements in</span></span>

<span data-ttu-id="07e44-199">`wsFederationHttpBinding`es la misma que la que contiene `wsHttpBinding`</span><span class="sxs-lookup"><span data-stu-id="07e44-199">`wsFederationHttpBinding` is the same as that contained in `wsHttpBinding`</span></span>

<span data-ttu-id="07e44-200">Cuando [\<security>](security-of-wsfederationhttpbinding.md) se establece en el valor predeterminado de <xref:System.ServiceModel.WSFederationHttpSecurityMode.Message> .</span><span class="sxs-lookup"><span data-stu-id="07e44-200">when [\<security>](security-of-wsfederationhttpbinding.md) is set to the default value of <xref:System.ServiceModel.WSFederationHttpSecurityMode.Message>.</span></span>

<span data-ttu-id="07e44-201">`wsFederationHttpBinding`Controla los detalles de la configuración de seguridad del mensaje en [\<message>](message-element-of-wsfederationhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="07e44-201">The `wsFederationHttpBinding` controls the details of the message security settings in [\<message>](message-element-of-wsfederationhttpbinding.md).</span></span> <span data-ttu-id="07e44-202">Tenga en cuenta que el [\<security>](security-of-wsfederationhttpbinding.md) elemento proporciona acceso solo cuando la seguridad que usa el enlace no se puede cambiar una vez creado el enlace.</span><span class="sxs-lookup"><span data-stu-id="07e44-202">Note that the [\<security>](security-of-wsfederationhttpbinding.md) element provides get access only as the security used by the binding cannot be changed once the binding is created.</span></span>

<span data-ttu-id="07e44-203">`wsFederationHttpBinding`También proporciona un atributo privacyNoticeAt para establecer y recuperar el URI en el que se encuentra el aviso de privacidad.</span><span class="sxs-lookup"><span data-stu-id="07e44-203">The `wsFederationHttpBinding` also provides a privacyNoticeAt attribute to set and retrieve the URI at which the privacy notice is located.</span></span>

<span data-ttu-id="07e44-204">Mantener la directiva protegida es especialmente importante en escenarios de federación.</span><span class="sxs-lookup"><span data-stu-id="07e44-204">Keeping policy secure is especially important in federation scenarios.</span></span> <span data-ttu-id="07e44-205">Se recomienda utilizar algún formulario de seguridad, como HTTPS, para proteger la directiva de los usuarios malintencionados.</span><span class="sxs-lookup"><span data-stu-id="07e44-205">The recommendation is to use some form of security, such as HTTPS, to protect the policy from malicious users.</span></span>

<span data-ttu-id="07e44-206">En los escenarios de federación que utilizan este enlace, la directiva del servicio tiene potencialmente información importante como la clave para utilizar para cifrar el token emitido (SAML), el tipo de demandas para introducir el token, etc.</span><span class="sxs-lookup"><span data-stu-id="07e44-206">In federation scenarios using this binding, the service policy potentially has important information such as the key to use to encrypt the issued (SAML) token, the type of claims to put in the token, and so forth.</span></span> <span data-ttu-id="07e44-207">Si esta directiva se manipula, un atacante podría detectar la clave del token emitido que conduce a una modificación posterior, divulgación de información y otros comportamientos malintencionados.</span><span class="sxs-lookup"><span data-stu-id="07e44-207">If this policy is tampered with, an attacker could discover the key of the issued token leading to further tampering, info disclosure and other malicious behavior.</span></span> <span data-ttu-id="07e44-208">Para ayudar a evitar esto, la directiva se debe obtener firmemente (utilizando HTTPS, por ejemplo) del servicio.</span><span class="sxs-lookup"><span data-stu-id="07e44-208">To help prevent this, the policy must be obtained securely (for example using HTTPS) from the service.</span></span>

<span data-ttu-id="07e44-209">Para obtener más información sobre este enlace, vea [Cómo: crear un WSFederationHttpBinding](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="07e44-209">For more information on this binding, see [How to: Create a WSFederationHttpBinding](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md).</span></span>

## <a name="example"></a><span data-ttu-id="07e44-210">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="07e44-210">Example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="07e44-211">Vea también</span><span class="sxs-lookup"><span data-stu-id="07e44-211">See also</span></span>

- <xref:System.ServiceModel.WSFederationHttpBinding>
- <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement>
- [<span data-ttu-id="07e44-212">Procedimiento para crear un WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="07e44-212">How to: Create a WSFederationHttpBinding</span></span>](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
- [<span data-ttu-id="07e44-213">Enlaces</span><span class="sxs-lookup"><span data-stu-id="07e44-213">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="07e44-214">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="07e44-214">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="07e44-215">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="07e44-215">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
