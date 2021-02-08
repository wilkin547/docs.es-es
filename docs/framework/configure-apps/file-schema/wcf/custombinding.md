---
description: 'Más información acerca de: <customBinding>'
title: <customBinding>
ms.date: 03/30/2017
ms.assetid: 9da4f960-f64e-4d8a-894d-2b09eba5ce4b
ms.openlocfilehash: a4d297750d107648aa10b349c6febc1a8929a30b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803950"
---
# \<customBinding>

<span data-ttu-id="088b5-102">Proporciona el control completo sobre la pila de la mensajería para el usuario.</span><span class="sxs-lookup"><span data-stu-id="088b5-102">Provides full control over the messaging stack for the user.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customBinding>**  

## <a name="syntax"></a><span data-ttu-id="088b5-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="088b5-103">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="088b5-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="088b5-104">Attributes and Elements</span></span>

<span data-ttu-id="088b5-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="088b5-105">The following sections describe attributes, child elements, and parent elements</span></span>

### <a name="attributes"></a><span data-ttu-id="088b5-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="088b5-106">Attributes</span></span>

|<span data-ttu-id="088b5-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="088b5-107">Attribute</span></span>|<span data-ttu-id="088b5-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="088b5-108">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="088b5-109">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="088b5-109">closeTimeout</span></span>|<span data-ttu-id="088b5-110">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de cierre para completarse.</span><span class="sxs-lookup"><span data-stu-id="088b5-110">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="088b5-111">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="088b5-111">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="088b5-112">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="088b5-112">The default is 00:01:00.</span></span>|
|<span data-ttu-id="088b5-113">name</span><span class="sxs-lookup"><span data-stu-id="088b5-113">name</span></span>|<span data-ttu-id="088b5-114">Cadena que contiene el nombre de configuración del enlace.</span><span class="sxs-lookup"><span data-stu-id="088b5-114">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="088b5-115">Este valor es una cadena definida por el usuario que actúa como cadena de identificación para el enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="088b5-115">This value is a user-defined string that acts as the identification string for the custom binding.</span></span> <span data-ttu-id="088b5-116">A partir de .NET Framework 4, no es necesario que los enlaces y los comportamientos tengan un nombre.</span><span class="sxs-lookup"><span data-stu-id="088b5-116">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="088b5-117">Para obtener más información sobre la configuración predeterminada y los enlaces y comportamientos sin nombre, vea [configuración simplificada](../../../wcf/simplified-configuration.md) y [configuración simplificada para servicios WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="088b5-117">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|
|<span data-ttu-id="088b5-118">openTimeout</span><span class="sxs-lookup"><span data-stu-id="088b5-118">openTimeout</span></span>|<span data-ttu-id="088b5-119">Valor de la estructura <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de apertura para completarse.</span><span class="sxs-lookup"><span data-stu-id="088b5-119">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="088b5-120">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="088b5-120">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="088b5-121">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="088b5-121">The default is 00:01:00.</span></span>|
|<span data-ttu-id="088b5-122">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="088b5-122">receiveTimeout</span></span>|<span data-ttu-id="088b5-123">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de recepción para completarse.</span><span class="sxs-lookup"><span data-stu-id="088b5-123">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="088b5-124">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="088b5-124">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="088b5-125">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="088b5-125">The default is 00:01:00.</span></span>|
|<span data-ttu-id="088b5-126">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="088b5-126">sendTimeout</span></span>|<span data-ttu-id="088b5-127">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de envío para completarse.</span><span class="sxs-lookup"><span data-stu-id="088b5-127">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="088b5-128">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="088b5-128">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="088b5-129">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="088b5-129">The default is 00:01:00.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="088b5-130">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="088b5-130">Child Elements</span></span>

|<span data-ttu-id="088b5-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="088b5-131">Element</span></span>|<span data-ttu-id="088b5-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="088b5-132">Description</span></span>|
|-------------|-----------------|
|[\<compositeDuplex>](compositeduplex.md)|<span data-ttu-id="088b5-133">Especifica la mensajería bidireccional para el enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="088b5-133">Specifies two-way messaging to the custom binding.</span></span> <span data-ttu-id="088b5-134">Se usa con los transportes que no permiten comunicaciones dúplex de manera nativa, como, por ejemplo, HTTP.</span><span class="sxs-lookup"><span data-stu-id="088b5-134">It is used with transports that do not allow duplex communications natively, for example, HTTP.</span></span> <span data-ttu-id="088b5-135">TCP, en cambio, permite comunicaciones dúplex de manera nativa y no requiere el uso de este elemento de enlace para que el servicio devuelva los mensajes a un cliente.</span><span class="sxs-lookup"><span data-stu-id="088b5-135">TCP, by contrast, allows duplex communications natively, and does not require the use of this binding element for the service to send messages back to a client.</span></span><br /><br /> <span data-ttu-id="088b5-136">El cliente debe exponer una dirección para que el servicio haga contacto y establezca una conexión.</span><span class="sxs-lookup"><span data-stu-id="088b5-136">The client must expose an address for the service to make contact and establish a connection.</span></span> <span data-ttu-id="088b5-137">El atributo `ClientBaseAddress` proporciona esta dirección del cliente.</span><span class="sxs-lookup"><span data-stu-id="088b5-137">This client address is provided by the `ClientBaseAddress` attribute.</span></span><br /><br /> <span data-ttu-id="088b5-138">Este elemento es del tipo <xref:System.ServiceModel.Configuration.CompositeDuplexElement>.</span><span class="sxs-lookup"><span data-stu-id="088b5-138">This element is of type <xref:System.ServiceModel.Configuration.CompositeDuplexElement>.</span></span>|
|[\<pnrpPeerResolver>](pnrppeerresolver.md)|<span data-ttu-id="088b5-139">Especifica una resolución de nombre de mismo nivel de protocolo de resolución de nombres de mismo nivel (PNRP).</span><span class="sxs-lookup"><span data-stu-id="088b5-139">Specifies a Peer Name Resolution Protocol (PNRP) peer name resolver.</span></span> <span data-ttu-id="088b5-140">Este elemento es del tipo <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>.</span><span class="sxs-lookup"><span data-stu-id="088b5-140">This element is of type <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>.</span></span>|
|[\<reliableSession>](reliablesession.md)|<span data-ttu-id="088b5-141">Especifica el valor para la mensajería de confianza de WS.</span><span class="sxs-lookup"><span data-stu-id="088b5-141">Specifies the setting for WS-Reliable Messaging.</span></span> <span data-ttu-id="088b5-142">Cuando este elemento se agrega a un enlace personalizado, el canal resultante puede admitir las convicciones de la entrega exactamente una vez.</span><span class="sxs-lookup"><span data-stu-id="088b5-142">When this element is added to a custom binding, the resulting channel can support exactly-once delivery assurances.</span></span> <span data-ttu-id="088b5-143">Este elemento es del tipo <xref:System.ServiceModel.Configuration.ReliableSessionElement>.</span><span class="sxs-lookup"><span data-stu-id="088b5-143">This element is of type <xref:System.ServiceModel.Configuration.ReliableSessionElement>.</span></span>|
|[\<security>](security-of-custombinding.md)|<span data-ttu-id="088b5-144">Especifica las opciones de seguridad del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="088b5-144">Specifies the options for security of the custom binding.</span></span> <span data-ttu-id="088b5-145">Este elemento es del tipo <xref:System.ServiceModel.Configuration.SecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="088b5-145">This element is of type <xref:System.ServiceModel.Configuration.SecurityElement>.</span></span>|
|[\<sslStreamSecurity>](sslstreamsecurity.md)|<span data-ttu-id="088b5-146">Especifica la configuración de seguridad para un enlace de secuencia SSL.</span><span class="sxs-lookup"><span data-stu-id="088b5-146">Specifies the security settings for a SSL stream binding.</span></span> <span data-ttu-id="088b5-147">Este elemento es del tipo <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="088b5-147">This element is of type <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>.</span></span>|
|[\<transactionFlow>](transactionflow.md)|<span data-ttu-id="088b5-148">Especifica que el enlace soporta el flujo de transacción, y el protocolo que va a ser utilizado por el atributo `transactionProtocol`.</span><span class="sxs-lookup"><span data-stu-id="088b5-148">Specifies that the binding supports transaction flow, and the protocol to be used by the `transactionProtocol` attribute.</span></span> <span data-ttu-id="088b5-149">Este elemento es del tipo <xref:System.ServiceModel.Configuration.TransactionFlowElement>.</span><span class="sxs-lookup"><span data-stu-id="088b5-149">This element is of type <xref:System.ServiceModel.Configuration.TransactionFlowElement>.</span></span>|
|[\<windowsStreamSecurity>](windowsstreamsecurity.md)|<span data-ttu-id="088b5-150">Especifica las opciones de seguridad de transmisión del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="088b5-150">Specifies the options for streaming security of the custom binding.</span></span> <span data-ttu-id="088b5-151">Este elemento es del tipo <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="088b5-151">This element is of type <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="088b5-152">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="088b5-152">Parent Elements</span></span>

|<span data-ttu-id="088b5-153">Elemento</span><span class="sxs-lookup"><span data-stu-id="088b5-153">Element</span></span>|<span data-ttu-id="088b5-154">Descripción</span><span class="sxs-lookup"><span data-stu-id="088b5-154">Description</span></span>|
|-------------|-----------------|
|<span data-ttu-id="088b5-155">enlaces</span><span class="sxs-lookup"><span data-stu-id="088b5-155">bindings</span></span>|<span data-ttu-id="088b5-156">Contiene todos los enlaces para las aplicaciones de Windows Communication Foundation.</span><span class="sxs-lookup"><span data-stu-id="088b5-156">Contains all bindings for Windows Communication Foundation applications.</span></span>|

## <a name="remarks"></a><span data-ttu-id="088b5-157">Observaciones</span><span class="sxs-lookup"><span data-stu-id="088b5-157">Remarks</span></span>

<span data-ttu-id="088b5-158">Los enlaces personalizados proporcionan el control completo sobre la pila de mensajería WCF.</span><span class="sxs-lookup"><span data-stu-id="088b5-158">Custom bindings provide full control over the WCF messaging stack.</span></span> <span data-ttu-id="088b5-159">Los enlaces diseñados especialmente se pueden crear agregando los elementos de configuración para las entidades concretas.</span><span class="sxs-lookup"><span data-stu-id="088b5-159">Special tailored bindings can be created my adding the configuration elements for specific entities.</span></span> <span data-ttu-id="088b5-160">Por ejemplo, el usuario puede combinar la sección `httpsTransport`, sección `reliableSession` y la sección `security` para crear https fiables y seguros basados en el enlace.</span><span class="sxs-lookup"><span data-stu-id="088b5-160">For example, the user can combine the `httpsTransport` section, `reliableSession` section and the `security` section to create a reliable and secure https based binding.</span></span>

<span data-ttu-id="088b5-161">Un enlace individual define la pila de mensajes mediante la especificación de los elementos de configuración para los elementos de la pila en el orden que aparecen en la pila.</span><span class="sxs-lookup"><span data-stu-id="088b5-161">An individual binding defines the message stack by specifying the configuration elements for the stack elements in the order they appear on the stack.</span></span> <span data-ttu-id="088b5-162">Cada elemento define y configura un elemento de la pila.</span><span class="sxs-lookup"><span data-stu-id="088b5-162">Each element defines and configures the one element of the stack.</span></span> <span data-ttu-id="088b5-163">Debe haber un único elemento de transporte en cada enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="088b5-163">There must be one and only one transport element in each custom binding.</span></span> <span data-ttu-id="088b5-164">Sin este elemento, la pila de la mensajería está incompleta.</span><span class="sxs-lookup"><span data-stu-id="088b5-164">Without this element, the messaging stack is incomplete.</span></span>

<span data-ttu-id="088b5-165">El orden de aparición de los elementos en la pila es importante, porque es el orden en el que las operaciones se aplican al mensaje.</span><span class="sxs-lookup"><span data-stu-id="088b5-165">The order in which elements appear in the stack matters, because it is the order in which operations are applied to the message.</span></span> <span data-ttu-id="088b5-166">El orden recomendado de elementos de pila es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="088b5-166">The recommended order of stack elements is the following:</span></span>

1. <span data-ttu-id="088b5-167">Transacciones (opcional)</span><span class="sxs-lookup"><span data-stu-id="088b5-167">Transactions (optional)</span></span>

2. <span data-ttu-id="088b5-168">Mensajería de confianza (opcional)</span><span class="sxs-lookup"><span data-stu-id="088b5-168">Reliable Messaging (optional)</span></span>

3. <span data-ttu-id="088b5-169">Seguridad (opcional)</span><span class="sxs-lookup"><span data-stu-id="088b5-169">Security (optional)</span></span>

4. <span data-ttu-id="088b5-170">Transporte</span><span class="sxs-lookup"><span data-stu-id="088b5-170">Transport</span></span>

5. <span data-ttu-id="088b5-171">Codificador (opcional)</span><span class="sxs-lookup"><span data-stu-id="088b5-171">Encoder (optional)</span></span>

<span data-ttu-id="088b5-172">Utilice un enlace personalizado cuando uno de los enlaces proporcionados por el sistema no cumpla los requisitos del servicio.</span><span class="sxs-lookup"><span data-stu-id="088b5-172">Use a custom binding when one of the system-provided bindings does not meet the requirements of your service.</span></span> <span data-ttu-id="088b5-173">Se pudo utilizar un enlace personalizado, por ejemplo, para habilitar el uso de un nuevo transporte o un nuevo codificador en un punto de conexión de servicio.</span><span class="sxs-lookup"><span data-stu-id="088b5-173">A custom binding could be used, for example, to enable the use of a new transport or a new encoder at a service endpoint.</span></span>

<span data-ttu-id="088b5-174">Un enlace personalizado se construye utilizando uno de <xref:System.ServiceModel.Channels.CustomBinding.%23ctor%2A> de una colección de elementos de enlace que se apilan en un orden específico:</span><span class="sxs-lookup"><span data-stu-id="088b5-174">A custom binding is constructed using one of the <xref:System.ServiceModel.Channels.CustomBinding.%23ctor%2A> from a collection of binding elements that are "stacked" in a specific order:</span></span>

- <span data-ttu-id="088b5-175">En la parte superior hay un <xref:System.ServiceModel.Channels.TransactionFlowBindingElement> opcional que permite el flujo de transacciones.</span><span class="sxs-lookup"><span data-stu-id="088b5-175">At the top is an optional <xref:System.ServiceModel.Channels.TransactionFlowBindingElement> that allows flowing transactions.</span></span>

- <span data-ttu-id="088b5-176">A continuación hay un <xref:System.ServiceModel.Channels.ReliableSessionBindingElement> opcional que proporciona una sesión y un mecanismo de orden, como se define en la especificación WS-ReliableMessaging.</span><span class="sxs-lookup"><span data-stu-id="088b5-176">Next is an optional <xref:System.ServiceModel.Channels.ReliableSessionBindingElement> that provides a session and ordering mechanism as defined in the WS-ReliableMessaging specification.</span></span> <span data-ttu-id="088b5-177">Esta noción de sesión puede cruzar SOAP y transportar intermediarios.</span><span class="sxs-lookup"><span data-stu-id="088b5-177">This notion of a session can cross SOAP and transport intermediaries.</span></span>

- <span data-ttu-id="088b5-178">A continuación hay un elemento de enlace de seguridad opcional que proporciona las características de seguridad como la autorización, autenticación, protección y confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="088b5-178">Next is an optional security binding element that provides security features like authorization, authentication, protection, and confidentiality.</span></span> <span data-ttu-id="088b5-179">Windows Communication Foundation (WCF) proporciona los siguientes elementos de enlace de seguridad:</span><span class="sxs-lookup"><span data-stu-id="088b5-179">The following security binding elements are provided by Windows Communication Foundation (WCF):</span></span>

  - <xref:System.ServiceModel.Channels.SecurityBindingElement>

  - <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>

  - <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>

  - <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>

- <span data-ttu-id="088b5-180">A continuación están los modelos de mensaje opcionales especificados por elementos de enlace:</span><span class="sxs-lookup"><span data-stu-id="088b5-180">Next are the optional message-patterns specified by binding elements:</span></span>

- <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>

- <span data-ttu-id="088b5-181">A continuación, se encuentran los elementos de enlace de asistentes/actualizaciones de transporte opcionales: </span><span class="sxs-lookup"><span data-stu-id="088b5-181">Next are the optional transport upgrades/helpers binding elements:</span></span>

  - <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>

  - <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>

  - <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>

- <span data-ttu-id="088b5-182">A continuación hay un elemento de enlace de codificación del mensaje requerido.</span><span class="sxs-lookup"><span data-stu-id="088b5-182">Next is a required message encoding binding element.</span></span> <span data-ttu-id="088b5-183">Puede utilizar su propio transporte o utilizar uno de los siguientes enlaces de codificación del mensaje:</span><span class="sxs-lookup"><span data-stu-id="088b5-183">You can use your own transport or use one of the following message encoding bindings:</span></span>

  - <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>

  - <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>

  - <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>

- <span data-ttu-id="088b5-184">En la parte inferior hay un elemento de transporte necesario.</span><span class="sxs-lookup"><span data-stu-id="088b5-184">At the bottom is a required transport element.</span></span> <span data-ttu-id="088b5-185">Puede utilizar su propio transporte o usar uno de los elementos de enlace de transporte proporcionados por Windows Communication Foundation (WCF):</span><span class="sxs-lookup"><span data-stu-id="088b5-185">You can use your own transport or use one of transport binding elements provided by Windows Communication Foundation (WCF):</span></span>

  - <xref:System.ServiceModel.Channels.TcpTransportBindingElement>

  - <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>

  - <xref:System.ServiceModel.Channels.HttpTransportBindingElement>

  - <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>

  - <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>

  - <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBindingElement>

  - <xref:System.ServiceModel.Channels.PeerTransportBindingElement>

<span data-ttu-id="088b5-186">La tabla siguiente resume las opciones de cada nivel.</span><span class="sxs-lookup"><span data-stu-id="088b5-186">The following table summarizes the options for each layer.</span></span>

|<span data-ttu-id="088b5-187">Nivel</span><span class="sxs-lookup"><span data-stu-id="088b5-187">Layer</span></span>|<span data-ttu-id="088b5-188">Opciones</span><span class="sxs-lookup"><span data-stu-id="088b5-188">Options</span></span>|<span data-ttu-id="088b5-189">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="088b5-189">Required</span></span>|
|-----------|-------------|--------------|
|<span data-ttu-id="088b5-190">Flujo de transacciones</span><span class="sxs-lookup"><span data-stu-id="088b5-190">Transaction Flow</span></span>|<xref:System.ServiceModel.Channels.TransactionFlowBindingElement>|<span data-ttu-id="088b5-191">No</span><span class="sxs-lookup"><span data-stu-id="088b5-191">No</span></span>|
|<span data-ttu-id="088b5-192">Confiabilidad</span><span class="sxs-lookup"><span data-stu-id="088b5-192">Reliability</span></span>|<xref:System.ServiceModel.Channels.ReliableSessionBindingElement>|<span data-ttu-id="088b5-193">No</span><span class="sxs-lookup"><span data-stu-id="088b5-193">No</span></span>|
|<span data-ttu-id="088b5-194">Seguridad</span><span class="sxs-lookup"><span data-stu-id="088b5-194">Security</span></span>|<span data-ttu-id="088b5-195">Simétrico, Asimétrico, Nivel de transporte</span><span class="sxs-lookup"><span data-stu-id="088b5-195">Symmetric, Asymmetric, Transport-Level</span></span>|<span data-ttu-id="088b5-196">No</span><span class="sxs-lookup"><span data-stu-id="088b5-196">No</span></span>|
|<span data-ttu-id="088b5-197">Cambiar forma</span><span class="sxs-lookup"><span data-stu-id="088b5-197">Shape Change</span></span>|<xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>|<span data-ttu-id="088b5-198">No</span><span class="sxs-lookup"><span data-stu-id="088b5-198">No</span></span>|
|<span data-ttu-id="088b5-199">Actualizaciones de transporte</span><span class="sxs-lookup"><span data-stu-id="088b5-199">Transport Upgrades</span></span>|<span data-ttu-id="088b5-200">Secuencia de SSL, secuencia de Windows, Resolución del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="088b5-200">SSL stream, Windows stream, Peer Resolver</span></span>|<span data-ttu-id="088b5-201">No</span><span class="sxs-lookup"><span data-stu-id="088b5-201">No</span></span>|
|<span data-ttu-id="088b5-202">Encoding</span><span class="sxs-lookup"><span data-stu-id="088b5-202">Encoding</span></span>|<span data-ttu-id="088b5-203">Texto, binario, MTOM, personalizado</span><span class="sxs-lookup"><span data-stu-id="088b5-203">Text, Binary, MTOM, Custom</span></span>|<span data-ttu-id="088b5-204">Sí</span><span class="sxs-lookup"><span data-stu-id="088b5-204">Yes</span></span>|
|<span data-ttu-id="088b5-205">Transporte</span><span class="sxs-lookup"><span data-stu-id="088b5-205">Transport</span></span>|<span data-ttu-id="088b5-206">TCP, canalizaciones con nombre, http, HTTPS, versiones de MSMQ, personalizado</span><span class="sxs-lookup"><span data-stu-id="088b5-206">TCP, Named Pipes, HTTP, HTTPS, flavors of MSMQ, Custom</span></span>|<span data-ttu-id="088b5-207">Sí</span><span class="sxs-lookup"><span data-stu-id="088b5-207">Yes</span></span>|

<span data-ttu-id="088b5-208">Además, puede definir sus propios elementos de enlace e insertarlos entre cualquiera de las capas definidas anteriores.</span><span class="sxs-lookup"><span data-stu-id="088b5-208">In addition, you can define your own binding elements and insert them between any of the preceding defined layers.</span></span>

<span data-ttu-id="088b5-209">Para obtener información sobre cómo utilizar un enlace personalizado para modificar un enlace proporcionado por el sistema, consulte [Cómo: personalizar un enlace de System-Provided](../../../wcf/extending/how-to-customize-a-system-provided-binding.md).</span><span class="sxs-lookup"><span data-stu-id="088b5-209">For a discussion on how to use a custom binding to modify a system-provided binding, see [How to: Customize a System-Provided Binding](../../../wcf/extending/how-to-customize-a-system-provided-binding.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="088b5-210">Vea también</span><span class="sxs-lookup"><span data-stu-id="088b5-210">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.Configuration.BindingsSection>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [\<binding>](bindings.md)
- [<span data-ttu-id="088b5-211">Enlaces</span><span class="sxs-lookup"><span data-stu-id="088b5-211">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="088b5-212">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="088b5-212">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="088b5-213">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="088b5-213">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="088b5-214">customBinding (elemento)</span><span class="sxs-lookup"><span data-stu-id="088b5-214">customBinding Element</span></span>](custombinding.md)
- [<span data-ttu-id="088b5-215">Enlaces</span><span class="sxs-lookup"><span data-stu-id="088b5-215">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="088b5-216">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="088b5-216">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="088b5-217">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="088b5-217">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
