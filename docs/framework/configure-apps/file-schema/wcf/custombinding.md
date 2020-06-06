---
title: <customBinding>
ms.date: 03/30/2017
ms.assetid: 9da4f960-f64e-4d8a-894d-2b09eba5ce4b
ms.openlocfilehash: cdaaacf0dfa75209d001f6e8d6ac7175816048aa
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "74140798"
---
# \<customBinding>

<span data-ttu-id="e702b-101">Proporciona el control completo sobre la pila de la mensajería para el usuario.</span><span class="sxs-lookup"><span data-stu-id="e702b-101">Provides full control over the messaging stack for the user.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customBinding>**  

## <a name="syntax"></a><span data-ttu-id="e702b-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e702b-102">Syntax</span></span>

```xml
<customBinding>
  <binding name="String"
           closeTimeout="TimeSpan"
           openTimeout="TimeSpan"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan">
    <compositeDuplex clientBaseAddress="Uri" />
    <reliableSession acknowledgementInterval="TimeSpan"
                     advancedFlowControl="Boolean"
                     bufferedMessagesQuota="Integer"
                     inactivityTimeout="TimeSpan"
                     maxPendingChannels="Integer"
                     maxRetryCount="Integer"
                     ordered="Boolean" />
    <pnrpPeerResolver />
    <windowsStreamSecurity protectionLevel="None/Sign/EncryptAndSign" />
    <sslStreamSecurity requireClientCertificate="Boolean" />
    <transactionFlow transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004" />
    <security defaultAlgorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
              authenticationMode="UserNameForAnonymous"
              contextMode="Cookie"
              defaultProtectionLevel="Sign"
              enableKeyDerivation="false"
              keyEntropyMode="ClientEntropy"
              messageProtectionOrder="SignBeforeEncryptAndEncryptSignature"
              securityVersion="WSSecurityXXX2005">
      <localClientSettings cacheCookies="false"
                           detectReplays="false"
                           maxCookieCachingTime="00:07:24" />
      <localServiceSettings replayCacheSize="9"
                            maxClockSkew="00:00:03"
                            replayWindow="00:07:22.2190000" />
    </security>
    <binaryMessageEncoding maxReadPoolSize="Integer"
                           maxWritePoolSize="Integer"
                           maxSessionSize="Integer" />
    <httpsTransport manualAddressing="Boolean"
                    maxMessageSize="Integer"
                    authenticationScheme="Negotiate"
                    bypassProxyOnLocal="Boolean"
                    hostNameComparisonMode="Exact"
                    mapAddressingHeadersToHttpHeaders="Boolean"
                    proxyaddress="Uri"
                    realm="String"
                    requireClientCertificate="Boolean" />
    <peerTransport manualAddressing="false"
                   maxMessageSize="20002"
                   listenIPAddress="202.10.1.9"
                   messageAuthentication="false"
                   peerNodeAuthenticationMode="None"
                   port="1000" />
    <security defaultAlgorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
              authenticationMode="UserNameForAnonymous"
              bootstrapBindingConfiguration="String"
              bootstrapBindingSectionName="String"
              defaultProtectionLevel="None/Sign/EncryptAndSign"
              requireDerivedKeys="Boolean"
              securityHeaderLayout="Strict/Lax/LaxTimestampFirst/LaxTimestampLast"
              includeTimestamp="Boolean"
              keyEntropyMode="ClientEntropy/ServerEntropy/CombinedEntropy"
              messageProtectionOrder="SignBeforeEncrypt/SignBeforeEncryptAndEncryptSignature/EncryptBeforeSign"
              protectTokens="Boolean"
              requireSecurityContextCancellation="Boolean"
              securityVersion=" WSSecurityJan2004/WSSecurityXXX2005"
              requireSignatureConfirmation="Boolean">
      <localClientSettings cacheCookies="Boolean"
                           detectReplays="Boolean"
                           replayCacheSize="Integer"
                           maxClockSkew="TimeSpan"
                           maxCookieCachingTime="TimeSpan"
                           replayWindow="TimeSpan"
                           sessionKeyRenewalInterval="TimeSpan"
                           sessionKeyRolloverInterval="TimeSpan"
                           reconnectOnTransportFailure="Boolean"
                           timestampValidityDuration="TimeSpan"
                           cookieRenewalThresholdPercentage="Integer" />
      <localServiceSettings detectReplays="Boolean"
                            issuedCookieLifeTime="TimeSpan"
                            maxStatefulNegotiations="Integer"
                            replayCacheSize="Integer"
                            maxClockSkew="TimeSpan"
                            negotiationTimeout="TimeSpan"
                            replayWindow="TimeSpan"
                            inactivityTimeout="TimeSpan"
                            sessionKeyRenewalInterval="TimeSpan"
                            sessionKeyRolloverInterval="TimeSpan"
                            reconnectOnTransportFailure="Boolean"
                            maxConcurrentSessions="Integer"
                            timestampValidityDuration="TimeSpan" />
      <federationParameters trustVersion="WSTrustApr2004/WSTrustFeb2005" />
    </security>
    <security defaultAlgorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
              authenticationMode="UserNameForAnonymous"
              bootstrapBindingConfiguration="String"
              bootstrapBindingSectionName="String"
              defaultProtectionLevel="None/Sign/EncryptAndSign"
              requireDerivedKeys="Boolean"
              securityHeaderLayout="Strict/Lax/LaxTimestampFirst/LaxTimestampLast"
              includeTimestamp="Boolean"
              keyEntropyMode="ClientEntropy/ServerEntropy/CombinedEntropy"
              messageProtectionOrder="SignBeforeEncrypt/SignBeforeEncryptAndEncryptSignature/EncryptBeforeSign"
              protectTokens="Boolean"
              requireSecurityContextCancellation="Boolean"
              securityVersion=" WSSecurityJan2004/WSSecurityXXX2005"
              requireSignatureConfirmation="Boolean" >
      <localClientSettings cacheCookies="Boolean"
                           detectReplays="Boolean"
                           replayCacheSize="Integer"
                           maxClockSkew="TimeSpan"
                           maxCookieCachingTime="TimeSpan"
                           replayWindow="TimeSpan"
                           sessionKeyRenewalInterval="TimeSpan"
                           sessionKeyRolloverInterval="TimeSpan"
                           reconnectOnTransportFailure="Boolean"
                           timestampValidityDuration="TimeSpan"
                           cookieRenewalThresholdPercentage="Integer" />
      <localServiceSettings detectReplays="Boolean"
                           issuedCookieLifeTime="TimeSpan"
                           maxStatefulNegotiations="Integer"
                           replayCacheSize="Integer"
                           maxClockSkew="TimeSpan"
                           negotiationTimeout="TimeSpan"
                           replayWindow="TimeSpan"
                           inactivityTimeout="TimeSpan"
                           sessionKeyRenewalInterval="TimeSpan"
                           sessionKeyRolloverInterval="TimeSpan"
                           reconnectOnTransportFailure="Boolean"
                           maxConcurrentSessions="Integer"
                           timestampValidityDuration="TimeSpan" />
      <federationParameters trustVersion="WSTrustApr2004/WSTrustFeb2005" />
      <genericIssuedTokenParameters>
        <localIssuerIssuedTokenParameters keyType="SymmetricKey/PublicKey"
                                          keySize="Integer"
                                          tokenType="String" />
        <issuedTokenParametersEndpointAddress address="URI"
                                              bindingConfiguration="String"
                                              binding="String" />
        <issuedTokenClient localIssuerChannelBehaviors="String"
                           cacheIssuedTokens="Boolean"
                           maxIssuedTokenCachingTime="TimeSpan"
                           keyEntropyMode="ClientEntropy/ServerEntropy/CombinedEntropy" />
        <issuedTokenClientBehavior issuerAddress="String"
                                   behaviorConfiguration="String" />
        <issuedTokenClientBehavior address="URI"
                                   bindingConfiguration="String"
                                   binding="String" />
      </genericIssuedTokenParameters>
    </security>
  </binding>
</customBinding>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e702b-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e702b-103">Attributes and Elements</span></span>

<span data-ttu-id="e702b-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e702b-104">The following sections describe attributes, child elements, and parent elements</span></span>

### <a name="attributes"></a><span data-ttu-id="e702b-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="e702b-105">Attributes</span></span>

|<span data-ttu-id="e702b-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="e702b-106">Attribute</span></span>|<span data-ttu-id="e702b-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="e702b-107">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="e702b-108">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="e702b-108">closeTimeout</span></span>|<span data-ttu-id="e702b-109">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de cierre para completarse.</span><span class="sxs-lookup"><span data-stu-id="e702b-109">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="e702b-110">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="e702b-110">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="e702b-111">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="e702b-111">The default is 00:01:00.</span></span>|
|<span data-ttu-id="e702b-112">name</span><span class="sxs-lookup"><span data-stu-id="e702b-112">name</span></span>|<span data-ttu-id="e702b-113">Cadena que contiene el nombre de configuración del enlace.</span><span class="sxs-lookup"><span data-stu-id="e702b-113">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="e702b-114">Este valor es una cadena definida por el usuario que actúa como cadena de identificación para el enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="e702b-114">This value is a user-defined string that acts as the identification string for the custom binding.</span></span> <span data-ttu-id="e702b-115">A partir de .NET Framework 4, no es necesario que los enlaces y los comportamientos tengan un nombre.</span><span class="sxs-lookup"><span data-stu-id="e702b-115">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="e702b-116">Para obtener más información sobre la configuración predeterminada y los enlaces y comportamientos sin nombre, vea [configuración simplificada](../../../wcf/simplified-configuration.md) y [configuración simplificada para servicios WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="e702b-116">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|
|<span data-ttu-id="e702b-117">openTimeout</span><span class="sxs-lookup"><span data-stu-id="e702b-117">openTimeout</span></span>|<span data-ttu-id="e702b-118">Valor de la estructura <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de apertura para completarse.</span><span class="sxs-lookup"><span data-stu-id="e702b-118">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="e702b-119">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="e702b-119">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="e702b-120">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="e702b-120">The default is 00:01:00.</span></span>|
|<span data-ttu-id="e702b-121">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="e702b-121">receiveTimeout</span></span>|<span data-ttu-id="e702b-122">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de recepción para completarse.</span><span class="sxs-lookup"><span data-stu-id="e702b-122">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="e702b-123">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="e702b-123">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="e702b-124">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="e702b-124">The default is 00:01:00.</span></span>|
|<span data-ttu-id="e702b-125">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="e702b-125">sendTimeout</span></span>|<span data-ttu-id="e702b-126">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de envío para completarse.</span><span class="sxs-lookup"><span data-stu-id="e702b-126">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="e702b-127">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="e702b-127">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="e702b-128">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="e702b-128">The default is 00:01:00.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="e702b-129">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e702b-129">Child Elements</span></span>

|<span data-ttu-id="e702b-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="e702b-130">Element</span></span>|<span data-ttu-id="e702b-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="e702b-131">Description</span></span>|
|-------------|-----------------|
|[\<compositeDuplex>](compositeduplex.md)|<span data-ttu-id="e702b-132">Especifica la mensajería bidireccional para el enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="e702b-132">Specifies two-way messaging to the custom binding.</span></span> <span data-ttu-id="e702b-133">Se usa con los transportes que no permiten comunicaciones dúplex de manera nativa, como, por ejemplo, HTTP.</span><span class="sxs-lookup"><span data-stu-id="e702b-133">It is used with transports that do not allow duplex communications natively, for example, HTTP.</span></span> <span data-ttu-id="e702b-134">TCP, en cambio, permite comunicaciones dúplex de manera nativa y no requiere el uso de este elemento de enlace para que el servicio devuelva los mensajes a un cliente.</span><span class="sxs-lookup"><span data-stu-id="e702b-134">TCP, by contrast, allows duplex communications natively, and does not require the use of this binding element for the service to send messages back to a client.</span></span><br /><br /> <span data-ttu-id="e702b-135">El cliente debe exponer una dirección para que el servicio haga contacto y establezca una conexión.</span><span class="sxs-lookup"><span data-stu-id="e702b-135">The client must expose an address for the service to make contact and establish a connection.</span></span> <span data-ttu-id="e702b-136">El atributo `ClientBaseAddress` proporciona esta dirección del cliente.</span><span class="sxs-lookup"><span data-stu-id="e702b-136">This client address is provided by the `ClientBaseAddress` attribute.</span></span><br /><br /> <span data-ttu-id="e702b-137">Este elemento es del tipo <xref:System.ServiceModel.Configuration.CompositeDuplexElement>.</span><span class="sxs-lookup"><span data-stu-id="e702b-137">This element is of type <xref:System.ServiceModel.Configuration.CompositeDuplexElement>.</span></span>|
|[\<pnrpPeerResolver>](pnrppeerresolver.md)|<span data-ttu-id="e702b-138">Especifica una resolución de nombre de mismo nivel de protocolo de resolución de nombres de mismo nivel (PNRP).</span><span class="sxs-lookup"><span data-stu-id="e702b-138">Specifies a Peer Name Resolution Protocol (PNRP) peer name resolver.</span></span> <span data-ttu-id="e702b-139">Este elemento es del tipo <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>.</span><span class="sxs-lookup"><span data-stu-id="e702b-139">This element is of type <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>.</span></span>|
|[\<reliableSession>](reliablesession.md)|<span data-ttu-id="e702b-140">Especifica el valor para la mensajería de confianza de WS.</span><span class="sxs-lookup"><span data-stu-id="e702b-140">Specifies the setting for WS-Reliable Messaging.</span></span> <span data-ttu-id="e702b-141">Cuando este elemento se agrega a un enlace personalizado, el canal resultante puede admitir las convicciones de la entrega exactamente una vez.</span><span class="sxs-lookup"><span data-stu-id="e702b-141">When this element is added to a custom binding, the resulting channel can support exactly-once delivery assurances.</span></span> <span data-ttu-id="e702b-142">Este elemento es del tipo <xref:System.ServiceModel.Configuration.ReliableSessionElement>.</span><span class="sxs-lookup"><span data-stu-id="e702b-142">This element is of type <xref:System.ServiceModel.Configuration.ReliableSessionElement>.</span></span>|
|[\<security>](security-of-custombinding.md)|<span data-ttu-id="e702b-143">Especifica las opciones de seguridad del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="e702b-143">Specifies the options for security of the custom binding.</span></span> <span data-ttu-id="e702b-144">Este elemento es del tipo <xref:System.ServiceModel.Configuration.SecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="e702b-144">This element is of type <xref:System.ServiceModel.Configuration.SecurityElement>.</span></span>|
|[\<sslStreamSecurity>](sslstreamsecurity.md)|<span data-ttu-id="e702b-145">Especifica la configuración de seguridad para un enlace de secuencia SSL.</span><span class="sxs-lookup"><span data-stu-id="e702b-145">Specifies the security settings for a SSL stream binding.</span></span> <span data-ttu-id="e702b-146">Este elemento es del tipo <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="e702b-146">This element is of type <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>.</span></span>|
|[\<transactionFlow>](transactionflow.md)|<span data-ttu-id="e702b-147">Especifica que el enlace soporta el flujo de transacción, y el protocolo que va a ser utilizado por el atributo `transactionProtocol`.</span><span class="sxs-lookup"><span data-stu-id="e702b-147">Specifies that the binding supports transaction flow, and the protocol to be used by the `transactionProtocol` attribute.</span></span> <span data-ttu-id="e702b-148">Este elemento es del tipo <xref:System.ServiceModel.Configuration.TransactionFlowElement>.</span><span class="sxs-lookup"><span data-stu-id="e702b-148">This element is of type <xref:System.ServiceModel.Configuration.TransactionFlowElement>.</span></span>|
|[\<windowsStreamSecurity>](windowsstreamsecurity.md)|<span data-ttu-id="e702b-149">Especifica las opciones de seguridad de transmisión del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="e702b-149">Specifies the options for streaming security of the custom binding.</span></span> <span data-ttu-id="e702b-150">Este elemento es del tipo <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="e702b-150">This element is of type <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="e702b-151">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e702b-151">Parent Elements</span></span>

|<span data-ttu-id="e702b-152">Elemento</span><span class="sxs-lookup"><span data-stu-id="e702b-152">Element</span></span>|<span data-ttu-id="e702b-153">Descripción</span><span class="sxs-lookup"><span data-stu-id="e702b-153">Description</span></span>|
|-------------|-----------------|
|<span data-ttu-id="e702b-154">enlaces</span><span class="sxs-lookup"><span data-stu-id="e702b-154">bindings</span></span>|<span data-ttu-id="e702b-155">Contiene todos los enlaces para las aplicaciones de Windows Communication Foundation.</span><span class="sxs-lookup"><span data-stu-id="e702b-155">Contains all bindings for Windows Communication Foundation applications.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e702b-156">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e702b-156">Remarks</span></span>

<span data-ttu-id="e702b-157">Los enlaces personalizados proporcionan el control completo sobre la pila de mensajería WCF.</span><span class="sxs-lookup"><span data-stu-id="e702b-157">Custom bindings provide full control over the WCF messaging stack.</span></span> <span data-ttu-id="e702b-158">Los enlaces diseñados especialmente se pueden crear agregando los elementos de configuración para las entidades concretas.</span><span class="sxs-lookup"><span data-stu-id="e702b-158">Special tailored bindings can be created my adding the configuration elements for specific entities.</span></span> <span data-ttu-id="e702b-159">Por ejemplo, el usuario puede combinar la sección `httpsTransport`, sección `reliableSession` y la sección `security` para crear https fiables y seguros basados en el enlace.</span><span class="sxs-lookup"><span data-stu-id="e702b-159">For example, the user can combine the `httpsTransport` section, `reliableSession` section and the `security` section to create a reliable and secure https based binding.</span></span>

<span data-ttu-id="e702b-160">Un enlace individual define la pila de mensajes mediante la especificación de los elementos de configuración para los elementos de la pila en el orden que aparecen en la pila.</span><span class="sxs-lookup"><span data-stu-id="e702b-160">An individual binding defines the message stack by specifying the configuration elements for the stack elements in the order they appear on the stack.</span></span> <span data-ttu-id="e702b-161">Cada elemento define y configura un elemento de la pila.</span><span class="sxs-lookup"><span data-stu-id="e702b-161">Each element defines and configures the one element of the stack.</span></span> <span data-ttu-id="e702b-162">Debe haber un único elemento de transporte en cada enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="e702b-162">There must be one and only one transport element in each custom binding.</span></span> <span data-ttu-id="e702b-163">Sin este elemento, la pila de la mensajería está incompleta.</span><span class="sxs-lookup"><span data-stu-id="e702b-163">Without this element, the messaging stack is incomplete.</span></span>

<span data-ttu-id="e702b-164">El orden de aparición de los elementos en la pila es importante, porque es el orden en el que las operaciones se aplican al mensaje.</span><span class="sxs-lookup"><span data-stu-id="e702b-164">The order in which elements appear in the stack matters, because it is the order in which operations are applied to the message.</span></span> <span data-ttu-id="e702b-165">El orden recomendado de elementos de pila es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="e702b-165">The recommended order of stack elements is the following:</span></span>

1. <span data-ttu-id="e702b-166">Transacciones (opcional)</span><span class="sxs-lookup"><span data-stu-id="e702b-166">Transactions (optional)</span></span>

2. <span data-ttu-id="e702b-167">Mensajería de confianza (opcional)</span><span class="sxs-lookup"><span data-stu-id="e702b-167">Reliable Messaging (optional)</span></span>

3. <span data-ttu-id="e702b-168">Seguridad (opcional)</span><span class="sxs-lookup"><span data-stu-id="e702b-168">Security (optional)</span></span>

4. <span data-ttu-id="e702b-169">Transporte</span><span class="sxs-lookup"><span data-stu-id="e702b-169">Transport</span></span>

5. <span data-ttu-id="e702b-170">Codificador (opcional)</span><span class="sxs-lookup"><span data-stu-id="e702b-170">Encoder (optional)</span></span>

<span data-ttu-id="e702b-171">Utilice un enlace personalizado cuando uno de los enlaces proporcionados por el sistema no cumpla los requisitos del servicio.</span><span class="sxs-lookup"><span data-stu-id="e702b-171">Use a custom binding when one of the system-provided bindings does not meet the requirements of your service.</span></span> <span data-ttu-id="e702b-172">Se pudo utilizar un enlace personalizado, por ejemplo, para habilitar el uso de un nuevo transporte o un nuevo codificador en un punto de conexión de servicio.</span><span class="sxs-lookup"><span data-stu-id="e702b-172">A custom binding could be used, for example, to enable the use of a new transport or a new encoder at a service endpoint.</span></span>

<span data-ttu-id="e702b-173">Un enlace personalizado se construye utilizando uno de <xref:System.ServiceModel.Channels.CustomBinding.%23ctor%2A> de una colección de elementos de enlace que se apilan en un orden específico:</span><span class="sxs-lookup"><span data-stu-id="e702b-173">A custom binding is constructed using one of the <xref:System.ServiceModel.Channels.CustomBinding.%23ctor%2A> from a collection of binding elements that are "stacked" in a specific order:</span></span>

- <span data-ttu-id="e702b-174">En la parte superior hay un <xref:System.ServiceModel.Channels.TransactionFlowBindingElement> opcional que permite el flujo de transacciones.</span><span class="sxs-lookup"><span data-stu-id="e702b-174">At the top is an optional <xref:System.ServiceModel.Channels.TransactionFlowBindingElement> that allows flowing transactions.</span></span>

- <span data-ttu-id="e702b-175">A continuación hay un <xref:System.ServiceModel.Channels.ReliableSessionBindingElement> opcional que proporciona una sesión y un mecanismo de orden, como se define en la especificación WS-ReliableMessaging.</span><span class="sxs-lookup"><span data-stu-id="e702b-175">Next is an optional <xref:System.ServiceModel.Channels.ReliableSessionBindingElement> that provides a session and ordering mechanism as defined in the WS-ReliableMessaging specification.</span></span> <span data-ttu-id="e702b-176">Esta noción de sesión puede cruzar SOAP y transportar intermediarios.</span><span class="sxs-lookup"><span data-stu-id="e702b-176">This notion of a session can cross SOAP and transport intermediaries.</span></span>

- <span data-ttu-id="e702b-177">A continuación hay un elemento de enlace de seguridad opcional que proporciona las características de seguridad como la autorización, autenticación, protección y confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="e702b-177">Next is an optional security binding element that provides security features like authorization, authentication, protection, and confidentiality.</span></span> <span data-ttu-id="e702b-178">Windows Communication Foundation (WCF) proporciona los siguientes elementos de enlace de seguridad:</span><span class="sxs-lookup"><span data-stu-id="e702b-178">The following security binding elements are provided by Windows Communication Foundation (WCF):</span></span>

  - <xref:System.ServiceModel.Channels.SecurityBindingElement>

  - <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>

  - <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>

  - <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>

- <span data-ttu-id="e702b-179">A continuación están los modelos de mensaje opcionales especificados por elementos de enlace:</span><span class="sxs-lookup"><span data-stu-id="e702b-179">Next are the optional message-patterns specified by binding elements:</span></span>

- <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>

- <span data-ttu-id="e702b-180">A continuación, se encuentran los elementos de enlace de asistentes/actualizaciones de transporte opcionales: </span><span class="sxs-lookup"><span data-stu-id="e702b-180">Next are the optional transport upgrades/helpers binding elements:</span></span>

  - <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>

  - <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>

  - <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>

- <span data-ttu-id="e702b-181">A continuación hay un elemento de enlace de codificación del mensaje requerido.</span><span class="sxs-lookup"><span data-stu-id="e702b-181">Next is a required message encoding binding element.</span></span> <span data-ttu-id="e702b-182">Puede utilizar su propio transporte o utilizar uno de los siguientes enlaces de codificación del mensaje:</span><span class="sxs-lookup"><span data-stu-id="e702b-182">You can use your own transport or use one of the following message encoding bindings:</span></span>

  - <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>

  - <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>

  - <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>

- <span data-ttu-id="e702b-183">En la parte inferior hay un elemento de transporte necesario.</span><span class="sxs-lookup"><span data-stu-id="e702b-183">At the bottom is a required transport element.</span></span> <span data-ttu-id="e702b-184">Puede utilizar su propio transporte o usar uno de los elementos de enlace de transporte proporcionados por Windows Communication Foundation (WCF):</span><span class="sxs-lookup"><span data-stu-id="e702b-184">You can use your own transport or use one of transport binding elements provided by Windows Communication Foundation (WCF):</span></span>

  - <xref:System.ServiceModel.Channels.TcpTransportBindingElement>

  - <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>

  - <xref:System.ServiceModel.Channels.HttpTransportBindingElement>

  - <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>

  - <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>

  - <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBindingElement>

  - <xref:System.ServiceModel.Channels.PeerTransportBindingElement>

<span data-ttu-id="e702b-185">La tabla siguiente resume las opciones de cada nivel.</span><span class="sxs-lookup"><span data-stu-id="e702b-185">The following table summarizes the options for each layer.</span></span>

|<span data-ttu-id="e702b-186">Nivel</span><span class="sxs-lookup"><span data-stu-id="e702b-186">Layer</span></span>|<span data-ttu-id="e702b-187">Opciones</span><span class="sxs-lookup"><span data-stu-id="e702b-187">Options</span></span>|<span data-ttu-id="e702b-188">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="e702b-188">Required</span></span>|
|-----------|-------------|--------------|
|<span data-ttu-id="e702b-189">Flujo de transacciones</span><span class="sxs-lookup"><span data-stu-id="e702b-189">Transaction Flow</span></span>|<xref:System.ServiceModel.Channels.TransactionFlowBindingElement>|<span data-ttu-id="e702b-190">No</span><span class="sxs-lookup"><span data-stu-id="e702b-190">No</span></span>|
|<span data-ttu-id="e702b-191">Confiabilidad</span><span class="sxs-lookup"><span data-stu-id="e702b-191">Reliability</span></span>|<xref:System.ServiceModel.Channels.ReliableSessionBindingElement>|<span data-ttu-id="e702b-192">No</span><span class="sxs-lookup"><span data-stu-id="e702b-192">No</span></span>|
|<span data-ttu-id="e702b-193">Seguridad</span><span class="sxs-lookup"><span data-stu-id="e702b-193">Security</span></span>|<span data-ttu-id="e702b-194">Simétrico, Asimétrico, Nivel de transporte</span><span class="sxs-lookup"><span data-stu-id="e702b-194">Symmetric, Asymmetric, Transport-Level</span></span>|<span data-ttu-id="e702b-195">No</span><span class="sxs-lookup"><span data-stu-id="e702b-195">No</span></span>|
|<span data-ttu-id="e702b-196">Cambiar forma</span><span class="sxs-lookup"><span data-stu-id="e702b-196">Shape Change</span></span>|<xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>|<span data-ttu-id="e702b-197">No</span><span class="sxs-lookup"><span data-stu-id="e702b-197">No</span></span>|
|<span data-ttu-id="e702b-198">Actualizaciones de transporte</span><span class="sxs-lookup"><span data-stu-id="e702b-198">Transport Upgrades</span></span>|<span data-ttu-id="e702b-199">Secuencia de SSL, secuencia de Windows, Resolución del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="e702b-199">SSL stream, Windows stream, Peer Resolver</span></span>|<span data-ttu-id="e702b-200">No</span><span class="sxs-lookup"><span data-stu-id="e702b-200">No</span></span>|
|<span data-ttu-id="e702b-201">Encoding</span><span class="sxs-lookup"><span data-stu-id="e702b-201">Encoding</span></span>|<span data-ttu-id="e702b-202">Texto, binario, MTOM, personalizado</span><span class="sxs-lookup"><span data-stu-id="e702b-202">Text, Binary, MTOM, Custom</span></span>|<span data-ttu-id="e702b-203">Sí</span><span class="sxs-lookup"><span data-stu-id="e702b-203">Yes</span></span>|
|<span data-ttu-id="e702b-204">Transporte</span><span class="sxs-lookup"><span data-stu-id="e702b-204">Transport</span></span>|<span data-ttu-id="e702b-205">TCP, canalizaciones con nombre, http, HTTPS, versiones de MSMQ, personalizado</span><span class="sxs-lookup"><span data-stu-id="e702b-205">TCP, Named Pipes, HTTP, HTTPS, flavors of MSMQ, Custom</span></span>|<span data-ttu-id="e702b-206">Sí</span><span class="sxs-lookup"><span data-stu-id="e702b-206">Yes</span></span>|

<span data-ttu-id="e702b-207">Además, puede definir sus propios elementos de enlace e insertarlos entre cualquiera de las capas definidas anteriores.</span><span class="sxs-lookup"><span data-stu-id="e702b-207">In addition, you can define your own binding elements and insert them between any of the preceding defined layers.</span></span>

<span data-ttu-id="e702b-208">Para obtener información sobre cómo utilizar un enlace personalizado para modificar un enlace proporcionado por el sistema, consulte [Cómo: personalizar un enlace proporcionado por el sistema](../../../wcf/extending/how-to-customize-a-system-provided-binding.md).</span><span class="sxs-lookup"><span data-stu-id="e702b-208">For a discussion on how to use a custom binding to modify a system-provided binding, see [How to: Customize a System-Provided Binding](../../../wcf/extending/how-to-customize-a-system-provided-binding.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e702b-209">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e702b-209">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.Configuration.BindingsSection>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [\<binding>](bindings.md)
- [<span data-ttu-id="e702b-210">Enlaces</span><span class="sxs-lookup"><span data-stu-id="e702b-210">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="e702b-211">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="e702b-211">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="e702b-212">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="e702b-212">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="e702b-213">customBinding (elemento)</span><span class="sxs-lookup"><span data-stu-id="e702b-213">customBinding Element</span></span>](custombinding.md)
- [<span data-ttu-id="e702b-214">Enlaces</span><span class="sxs-lookup"><span data-stu-id="e702b-214">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="e702b-215">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="e702b-215">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="e702b-216">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="e702b-216">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
