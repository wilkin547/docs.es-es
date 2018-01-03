---
title: '&lt;customBinding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9da4f960-f64e-4d8a-894d-2b09eba5ce4b
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1659e6352fa195bae56b764c80a08dee56b4c9e5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltcustombindinggt"></a><span data-ttu-id="f5b6a-102">&lt;customBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="f5b6a-102">&lt;customBinding&gt;</span></span>
<span data-ttu-id="f5b6a-103">Proporciona el control completo sobre la pila de la mensajería para el usuario.</span><span class="sxs-lookup"><span data-stu-id="f5b6a-103">Provides full control over the messaging stack for the user.</span></span>  
  
 <span data-ttu-id="f5b6a-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="f5b6a-104">\<system.serviceModel></span></span>  
<span data-ttu-id="f5b6a-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="f5b6a-105">\<bindings></span></span>  
<span data-ttu-id="f5b6a-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="f5b6a-106">\<customBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5b6a-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f5b6a-107">Syntax</span></span>  
  
```xml  
<customBinding>  
    <binding name="string"  
        closeTimeout="TimeSpan"  
        openTimeout="TimeSpan"   
        receiveTimeout="TimeSpan"  
        sendTimeout="TimeSpan"  
       <compositeDuplex clientBaseAddress="Uri"/>  
       <reliableSession acknowledgementInterval="TimeSpan"  
           advancedFlowControl="Boolean"   
           bufferedMessagesQuota="Integer"  
           inactivityTimeout="TimeSpan"  
           maxPendingChannels="Integer"  
           maxRetryCount="Integer"   
           ordered="Boolean" />  
       <pnrpPeerResolver />  
       <windowsStreamSecurity protectionLevel="None/Sign/EncryptAndSign"/>  
       <sslStreamSecurity requireClientCertificate="Boolean" />  
              <transactionFlow transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004"/>  
       <security   
          defaultAlgorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
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
  
<security   
      defaultAlgorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
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
<security   
   defaultAlgorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/ Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
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
   <GenericIssuedTokenParameters>   
      <LocalIssuerIssuedTokenParameters keyType=" SymmeticKey/PublicKey"  
        keySize="Integer"  
        tokenType="String" />  
     <IssuedTokenParametersEndpointAddress address="URI"  
        bindingConfiguration="String"  
        binding="String" />  
     <IssuedTokenClient localIssuerChannelBehaviors="String"  
        cacheIssuedTokens="Boolean"  
        maxIssuedTokenCachingTime="TimeSpan"  
        keyEntropyMode="ClientEntropy/ServerEntropy/CombinedEntropy" />  
     <IssuedTokenClientBehavior issuerAddress="String"  
        behaviorConfiguration="String" />  
     <IssuedTokenClientBehavior address="URI"  
        bindingConfiguration="String"  
        binding="String" />  
   </GenericIssuedTokenParameters>   
</security>  
</binding>  
</customBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f5b6a-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f5b6a-108">Attributes and Elements</span></span>  
 <span data-ttu-id="f5b6a-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f5b6a-109">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f5b6a-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="f5b6a-110">Attributes</span></span>  
  
|<span data-ttu-id="f5b6a-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="f5b6a-111">Attribute</span></span>|<span data-ttu-id="f5b6a-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="f5b6a-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f5b6a-113">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="f5b6a-113">closeTimeout</span></span>|<span data-ttu-id="f5b6a-114">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de cierre para completarse.</span><span class="sxs-lookup"><span data-stu-id="f5b6a-114">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="f5b6a-115">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="f5b6a-115">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="f5b6a-116">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="f5b6a-116">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="f5b6a-117">name</span><span class="sxs-lookup"><span data-stu-id="f5b6a-117">name</span></span>|<span data-ttu-id="f5b6a-118">Cadena que contiene el nombre de configuración del enlace.</span><span class="sxs-lookup"><span data-stu-id="f5b6a-118">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="f5b6a-119">Este valor es una cadena definida por el usuario que actúa como cadena de identificación para el enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="f5b6a-119">This value is a user-defined string that acts as the identification string for the custom binding.</span></span> <span data-ttu-id="f5b6a-120">A partir de [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], no es necesario que los enlaces y los comportamientos tengan nombre.</span><span class="sxs-lookup"><span data-stu-id="f5b6a-120">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="f5b6a-121">Para obtener más información acerca de la configuración predeterminada y enlaces anónimos y los comportamientos, consulte [configuración simplificada](../../../../../docs/framework/wcf/simplified-configuration.md) y [configuración simplificada para los servicios WCF](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="f5b6a-121">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|<span data-ttu-id="f5b6a-122">openTimeout</span><span class="sxs-lookup"><span data-stu-id="f5b6a-122">openTimeout</span></span>|<span data-ttu-id="f5b6a-123">Valor de la estructura <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de apertura para completarse.</span><span class="sxs-lookup"><span data-stu-id="f5b6a-123">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="f5b6a-124">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="f5b6a-124">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="f5b6a-125">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="f5b6a-125">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="f5b6a-126">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="f5b6a-126">receiveTimeout</span></span>|<span data-ttu-id="f5b6a-127">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de recepción para completarse.</span><span class="sxs-lookup"><span data-stu-id="f5b6a-127">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="f5b6a-128">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="f5b6a-128">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="f5b6a-129">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="f5b6a-129">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="f5b6a-130">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="f5b6a-130">sendTimeout</span></span>|<span data-ttu-id="f5b6a-131">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de envío para completarse.</span><span class="sxs-lookup"><span data-stu-id="f5b6a-131">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="f5b6a-132">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="f5b6a-132">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="f5b6a-133">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="f5b6a-133">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f5b6a-134">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f5b6a-134">Child Elements</span></span>  
  
|<span data-ttu-id="f5b6a-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="f5b6a-135">Element</span></span>|<span data-ttu-id="f5b6a-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="f5b6a-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f5b6a-137">\<compositeDuplex ></span><span class="sxs-lookup"><span data-stu-id="f5b6a-137">\<compositeDuplex></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md)|<span data-ttu-id="f5b6a-138">Especifica la mensajería bidireccional para el enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="f5b6a-138">Specifies two-way messaging to the custom binding.</span></span> <span data-ttu-id="f5b6a-139">Se usa con los transportes que no permiten comunicaciones dúplex de manera nativa, como, por ejemplo, HTTP.</span><span class="sxs-lookup"><span data-stu-id="f5b6a-139">It is used with transports that do not allow duplex communications natively, for example, HTTP.</span></span> <span data-ttu-id="f5b6a-140">TCP, en cambio, permite comunicaciones dúplex de manera nativa y no requiere el uso de este elemento de enlace para que el servicio devuelva los mensajes a un cliente.</span><span class="sxs-lookup"><span data-stu-id="f5b6a-140">TCP, by contrast, allows duplex communications natively, and does not require the use of this binding element for the service to send messages back to a client.</span></span><br /><br /> <span data-ttu-id="f5b6a-141">El cliente debe exponer una dirección para que el servicio haga contacto y establezca una conexión.</span><span class="sxs-lookup"><span data-stu-id="f5b6a-141">The client must expose an address for the service to make contact and establish a connection.</span></span> <span data-ttu-id="f5b6a-142">El atributo `ClientBaseAddress` proporciona esta dirección del cliente.</span><span class="sxs-lookup"><span data-stu-id="f5b6a-142">This client address is provided by the `ClientBaseAddress` attribute.</span></span><br /><br /> <span data-ttu-id="f5b6a-143">Este elemento es del tipo <xref:System.ServiceModel.Configuration.CompositeDuplexElement>.</span><span class="sxs-lookup"><span data-stu-id="f5b6a-143">This element is of type <xref:System.ServiceModel.Configuration.CompositeDuplexElement>.</span></span>|  
|[<span data-ttu-id="f5b6a-144">\<pnrpPeerResolver ></span><span class="sxs-lookup"><span data-stu-id="f5b6a-144">\<pnrpPeerResolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/pnrppeerresolver.md)|<span data-ttu-id="f5b6a-145">Especifica una resolución de nombre de mismo nivel de protocolo de resolución de nombres de mismo nivel (PNRP).</span><span class="sxs-lookup"><span data-stu-id="f5b6a-145">Specifies a Peer Name Resolution Protocol (PNRP) peer name resolver.</span></span> <span data-ttu-id="f5b6a-146">Este elemento es del tipo <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>.</span><span class="sxs-lookup"><span data-stu-id="f5b6a-146">This element is of type <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>.</span></span>|  
|[<span data-ttu-id="f5b6a-147">\<reliableSession ></span><span class="sxs-lookup"><span data-stu-id="f5b6a-147">\<reliableSession></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/reliablesession.md)|<span data-ttu-id="f5b6a-148">Especifica el valor para la mensajería de confianza de WS.</span><span class="sxs-lookup"><span data-stu-id="f5b6a-148">Specifies the setting for WS-Reliable Messaging.</span></span> <span data-ttu-id="f5b6a-149">Cuando este elemento se agrega a un enlace personalizado, el canal resultante puede admitir las convicciones de la entrega exactamente una vez.</span><span class="sxs-lookup"><span data-stu-id="f5b6a-149">When this element is added to a custom binding, the resulting channel can support exactly-once delivery assurances.</span></span> <span data-ttu-id="f5b6a-150">Este elemento es del tipo <xref:System.ServiceModel.Configuration.ReliableSessionElement>.</span><span class="sxs-lookup"><span data-stu-id="f5b6a-150">This element is of type <xref:System.ServiceModel.Configuration.ReliableSessionElement>.</span></span>|  
|[<span data-ttu-id="f5b6a-151">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="f5b6a-151">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)|<span data-ttu-id="f5b6a-152">Especifica las opciones de seguridad del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="f5b6a-152">Specifies the options for security of the custom binding.</span></span> <span data-ttu-id="f5b6a-153">Este elemento es del tipo <xref:System.ServiceModel.Configuration.SecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="f5b6a-153">This element is of type <xref:System.ServiceModel.Configuration.SecurityElement>.</span></span>|  
|[<span data-ttu-id="f5b6a-154">\<sslStreamSecurity ></span><span class="sxs-lookup"><span data-stu-id="f5b6a-154">\<sslStreamSecurity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md)|<span data-ttu-id="f5b6a-155">Especifica la configuración de seguridad para un enlace de secuencia SSL.</span><span class="sxs-lookup"><span data-stu-id="f5b6a-155">Specifies the security settings for a SSL stream binding.</span></span> <span data-ttu-id="f5b6a-156">Este elemento es del tipo <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="f5b6a-156">This element is of type <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>.</span></span>|  
|[<span data-ttu-id="f5b6a-157">\<transactionFlow ></span><span class="sxs-lookup"><span data-stu-id="f5b6a-157">\<transactionFlow></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transactionflow.md)|<span data-ttu-id="f5b6a-158">Especifica que el enlace soporta el flujo de transacción, y el protocolo que va a ser utilizado por el atributo `transactionProtocol`.</span><span class="sxs-lookup"><span data-stu-id="f5b6a-158">Specifies that the binding supports transaction flow, and the protocol to be used by the `transactionProtocol` attribute.</span></span> <span data-ttu-id="f5b6a-159">Este elemento es del tipo <xref:System.ServiceModel.Configuration.TransactionFlowElement>.</span><span class="sxs-lookup"><span data-stu-id="f5b6a-159">This element is of type <xref:System.ServiceModel.Configuration.TransactionFlowElement>.</span></span>|  
|[<span data-ttu-id="f5b6a-160">\<inicial de windowsStreamSecurity ></span><span class="sxs-lookup"><span data-stu-id="f5b6a-160">\<windowsStreamSecurity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/windowsstreamsecurity.md)|<span data-ttu-id="f5b6a-161">Especifica las opciones de seguridad de transmisión del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="f5b6a-161">Specifies the options for streaming security of the custom binding.</span></span> <span data-ttu-id="f5b6a-162">Este elemento es del tipo <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="f5b6a-162">This element is of type <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f5b6a-163">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f5b6a-163">Parent Elements</span></span>  
  
|<span data-ttu-id="f5b6a-164">Elemento</span><span class="sxs-lookup"><span data-stu-id="f5b6a-164">Element</span></span>|<span data-ttu-id="f5b6a-165">Descripción</span><span class="sxs-lookup"><span data-stu-id="f5b6a-165">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f5b6a-166">enlaces</span><span class="sxs-lookup"><span data-stu-id="f5b6a-166">bindings</span></span>|<span data-ttu-id="f5b6a-167">Contiene todos los enlaces para las aplicaciones de Windows Communication Foundation.</span><span class="sxs-lookup"><span data-stu-id="f5b6a-167">Contains all bindings for Windows Communication Foundation applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f5b6a-168">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f5b6a-168">Remarks</span></span>  
 <span data-ttu-id="f5b6a-169">Los enlaces personalizados proporcionan el control completo sobre la pila de mensajería WCF.</span><span class="sxs-lookup"><span data-stu-id="f5b6a-169">Custom bindings provide full control over the WCF messaging stack.</span></span> <span data-ttu-id="f5b6a-170">Los enlaces diseñados especialmente se pueden crear agregando los elementos de configuración para las entidades concretas.</span><span class="sxs-lookup"><span data-stu-id="f5b6a-170">Special tailored bindings can be created my adding the configuration elements for specific entities.</span></span> <span data-ttu-id="f5b6a-171">Por ejemplo, el usuario puede combinar la sección `httpsTransport`, sección `reliableSession` y la sección `security` para crear https fiables y seguros basados en el enlace.</span><span class="sxs-lookup"><span data-stu-id="f5b6a-171">For example, the user can combine the `httpsTransport` section, `reliableSession` section and the `security` section to create a reliable and secure https based binding.</span></span>  
  
 <span data-ttu-id="f5b6a-172">Un enlace individual define la pila de mensajes mediante la especificación de los elementos de configuración para los elementos de la pila en el orden que aparecen en la pila.</span><span class="sxs-lookup"><span data-stu-id="f5b6a-172">An individual binding defines the message stack by specifying the configuration elements for the stack elements in the order they appear on the stack.</span></span> <span data-ttu-id="f5b6a-173">Cada elemento define y configura un elemento de la pila.</span><span class="sxs-lookup"><span data-stu-id="f5b6a-173">Each element defines and configures the one element of the stack.</span></span> <span data-ttu-id="f5b6a-174">Debe haber un único elemento de transporte en cada enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="f5b6a-174">There must be one and only one transport element in each custom binding.</span></span> <span data-ttu-id="f5b6a-175">Sin este elemento, la pila de la mensajería está incompleta.</span><span class="sxs-lookup"><span data-stu-id="f5b6a-175">Without this element, the messaging stack is incomplete.</span></span>  
  
 <span data-ttu-id="f5b6a-176">El orden de aparición de los elementos en la pila es importante, porque es el orden en el que las operaciones se aplican al mensaje.</span><span class="sxs-lookup"><span data-stu-id="f5b6a-176">The order in which elements appear in the stack matters, because it is the order in which operations are applied to the message.</span></span> <span data-ttu-id="f5b6a-177">El orden recomendado de elementos de pila es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="f5b6a-177">The recommended order of stack elements is the following:</span></span>  
  
1.  <span data-ttu-id="f5b6a-178">Transacciones (opcional)</span><span class="sxs-lookup"><span data-stu-id="f5b6a-178">Transactions (optional)</span></span>  
  
2.  <span data-ttu-id="f5b6a-179">Mensajería de confianza (opcional)</span><span class="sxs-lookup"><span data-stu-id="f5b6a-179">Reliable Messaging (optional)</span></span>  
  
3.  <span data-ttu-id="f5b6a-180">Seguridad (opcional)</span><span class="sxs-lookup"><span data-stu-id="f5b6a-180">Security (optional)</span></span>  
  
4.  <span data-ttu-id="f5b6a-181">Transporte</span><span class="sxs-lookup"><span data-stu-id="f5b6a-181">Transport</span></span>  
  
5.  <span data-ttu-id="f5b6a-182">Codificador (opcional)</span><span class="sxs-lookup"><span data-stu-id="f5b6a-182">Encoder (optional)</span></span>  
  
 <span data-ttu-id="f5b6a-183">Utilice un enlace personalizado cuando uno de los enlaces proporcionados por el sistema no cumpla los requisitos del servicio.</span><span class="sxs-lookup"><span data-stu-id="f5b6a-183">Use a custom binding when one of the system-provided bindings does not meet the requirements of your service.</span></span> <span data-ttu-id="f5b6a-184">Se pudo utilizar un enlace personalizado, por ejemplo, para habilitar el uso de un nuevo transporte o un nuevo codificador en un extremo de servicio.</span><span class="sxs-lookup"><span data-stu-id="f5b6a-184">A custom binding could be used, for example, to enable the use of a new transport or a new encoder at a service endpoint.</span></span>  
  
 <span data-ttu-id="f5b6a-185">Un enlace personalizado se construye utilizando uno de <xref:System.ServiceModel.Channels.CustomBinding.%23ctor%2A> de una colección de elementos de enlace que se apilan en un orden específico:</span><span class="sxs-lookup"><span data-stu-id="f5b6a-185">A custom binding is constructed using one of the <xref:System.ServiceModel.Channels.CustomBinding.%23ctor%2A> from a collection of binding elements that are "stacked" in a specific order:</span></span>  
  
-   <span data-ttu-id="f5b6a-186">En la parte superior hay un <xref:System.ServiceModel.Channels.TransactionFlowBindingElement> opcional que permite el flujo de transacciones.</span><span class="sxs-lookup"><span data-stu-id="f5b6a-186">At the top is an optional <xref:System.ServiceModel.Channels.TransactionFlowBindingElement> that allows flowing transactions.</span></span>  
  
-   <span data-ttu-id="f5b6a-187">A continuación hay un <xref:System.ServiceModel.Channels.ReliableSessionBindingElement> opcional que proporciona una sesión y un mecanismo de orden, como se define en la especificación WS-ReliableMessaging.</span><span class="sxs-lookup"><span data-stu-id="f5b6a-187">Next is an optional <xref:System.ServiceModel.Channels.ReliableSessionBindingElement> that provides a session and ordering mechanism as defined in the WS-ReliableMessaging specification.</span></span> <span data-ttu-id="f5b6a-188">Esta noción de sesión puede cruzar SOAP y transportar intermediarios.</span><span class="sxs-lookup"><span data-stu-id="f5b6a-188">This notion of a session can cross SOAP and transport intermediaries.</span></span>  
  
-   <span data-ttu-id="f5b6a-189">A continuación hay un elemento de enlace de seguridad opcional que proporciona las características de seguridad como la autorización, autenticación, protección y confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="f5b6a-189">Next is an optional security binding element that provides security features like authorization, authentication, protection, and confidentiality.</span></span> <span data-ttu-id="f5b6a-190">[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] proporciona los elementos de enlace de seguridad siguientes:</span><span class="sxs-lookup"><span data-stu-id="f5b6a-190">The following security binding elements are provided by [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]:</span></span>  
  
    -   <xref:System.ServiceModel.Channels.SecurityBindingElement>  
  
    -   <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>  
  
    -   <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>  
  
    -   <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>  
  
-   <span data-ttu-id="f5b6a-191">A continuación están los modelos de mensaje opcionales especificados por elementos de enlace:</span><span class="sxs-lookup"><span data-stu-id="f5b6a-191">Next are the optional message-patterns specified by binding elements:</span></span>  
  
-   <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>  
  
-   <span data-ttu-id="f5b6a-192">Luego están las actualizaciones de transporte opcionales/elementos de enlace de el transporte opcional actualiza/los elementos de enlace auxiliares:</span><span class="sxs-lookup"><span data-stu-id="f5b6a-192">Next are the optional transport upgrades/helpers binding elements:</span></span>  
  
    -   <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>  
  
    -   <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>  
  
    -   <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>  
  
-   <span data-ttu-id="f5b6a-193">A continuación hay un elemento de enlace de codificación del mensaje requerido.</span><span class="sxs-lookup"><span data-stu-id="f5b6a-193">Next is a required message encoding binding element.</span></span> <span data-ttu-id="f5b6a-194">Puede utilizar su propio transporte o utilizar uno de los siguientes enlaces de codificación del mensaje:</span><span class="sxs-lookup"><span data-stu-id="f5b6a-194">You can use your own transport or use one of the following message encoding bindings:</span></span>  
  
    -   <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>  
  
    -   <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>  
  
    -   <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>  
  
-   <span data-ttu-id="f5b6a-195">En la parte inferior hay un elemento de transporte necesario.</span><span class="sxs-lookup"><span data-stu-id="f5b6a-195">At the bottom is a required transport element.</span></span> <span data-ttu-id="f5b6a-196">Puede usar su propio transporte o uno de los elementos de enlace de transporte proporcionados por [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="f5b6a-196">You can use your own transport or use one of transport binding elements provided by [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]:</span></span>  
  
    -   <xref:System.ServiceModel.Channels.TcpTransportBindingElement>  
  
    -   <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>  
  
    -   <xref:System.ServiceModel.Channels.HttpTransportBindingElement>  
  
    -   <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>  
  
    -   <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>  
  
    -   <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBindingElement>  
  
    -   <xref:System.ServiceModel.Channels.PeerTransportBindingElement>  
  
 <span data-ttu-id="f5b6a-197">La tabla siguiente resume las opciones de cada nivel.</span><span class="sxs-lookup"><span data-stu-id="f5b6a-197">The following table summarizes the options for each layer.</span></span>  
  
|<span data-ttu-id="f5b6a-198">Capa</span><span class="sxs-lookup"><span data-stu-id="f5b6a-198">Layer</span></span>|<span data-ttu-id="f5b6a-199">Opciones</span><span class="sxs-lookup"><span data-stu-id="f5b6a-199">Options</span></span>|<span data-ttu-id="f5b6a-200">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="f5b6a-200">Required</span></span>|  
|-----------|-------------|--------------|  
|<span data-ttu-id="f5b6a-201">Flujo de transacciones</span><span class="sxs-lookup"><span data-stu-id="f5b6a-201">Transaction Flow</span></span>|<xref:System.ServiceModel.Channels.TransactionFlowBindingElement>|<span data-ttu-id="f5b6a-202">No</span><span class="sxs-lookup"><span data-stu-id="f5b6a-202">No</span></span>|  
|<span data-ttu-id="f5b6a-203">Confiabilidad</span><span class="sxs-lookup"><span data-stu-id="f5b6a-203">Reliability</span></span>|<xref:System.ServiceModel.Channels.ReliableSessionBindingElement>|<span data-ttu-id="f5b6a-204">No</span><span class="sxs-lookup"><span data-stu-id="f5b6a-204">No</span></span>|  
|<span data-ttu-id="f5b6a-205">Seguridad</span><span class="sxs-lookup"><span data-stu-id="f5b6a-205">Security</span></span>|<span data-ttu-id="f5b6a-206">Simétrico, Asimétrico, Nivel de transporte</span><span class="sxs-lookup"><span data-stu-id="f5b6a-206">Symmetric, Asymmetric, Transport-Level</span></span>|<span data-ttu-id="f5b6a-207">No</span><span class="sxs-lookup"><span data-stu-id="f5b6a-207">No</span></span>|  
|<span data-ttu-id="f5b6a-208">Cambiar forma</span><span class="sxs-lookup"><span data-stu-id="f5b6a-208">Shape Change</span></span>|<xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>|<span data-ttu-id="f5b6a-209">No</span><span class="sxs-lookup"><span data-stu-id="f5b6a-209">No</span></span>|  
|<span data-ttu-id="f5b6a-210">Actualizaciones de transporte</span><span class="sxs-lookup"><span data-stu-id="f5b6a-210">Transport Upgrades</span></span>|<span data-ttu-id="f5b6a-211">Secuencia de SSL, secuencia de Windows, Resolución del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="f5b6a-211">SSL stream, Windows stream, Peer Resolver</span></span>|<span data-ttu-id="f5b6a-212">No</span><span class="sxs-lookup"><span data-stu-id="f5b6a-212">No</span></span>|  
|<span data-ttu-id="f5b6a-213">Codificación</span><span class="sxs-lookup"><span data-stu-id="f5b6a-213">Encoding</span></span>|<span data-ttu-id="f5b6a-214">Texto, binario, MTOM, personalizado</span><span class="sxs-lookup"><span data-stu-id="f5b6a-214">Text, Binary, MTOM, Custom</span></span>|<span data-ttu-id="f5b6a-215">Sí</span><span class="sxs-lookup"><span data-stu-id="f5b6a-215">Yes</span></span>|  
|<span data-ttu-id="f5b6a-216">Transporte</span><span class="sxs-lookup"><span data-stu-id="f5b6a-216">Transport</span></span>|<span data-ttu-id="f5b6a-217">TCP, canalizaciones con nombre, http, HTTPS, versiones de MSMQ, personalizado</span><span class="sxs-lookup"><span data-stu-id="f5b6a-217">TCP, Named Pipes, HTTP, HTTPS, flavors of MSMQ, Custom</span></span>|<span data-ttu-id="f5b6a-218">Sí</span><span class="sxs-lookup"><span data-stu-id="f5b6a-218">Yes</span></span>|  
  
 <span data-ttu-id="f5b6a-219">Además, puede definir sus propios elementos de enlace e insertarlos entre cualquiera de las capas definidas anteriores.</span><span class="sxs-lookup"><span data-stu-id="f5b6a-219">In addition, you can define your own binding elements and insert them between any of the preceding defined layers.</span></span>  
  
 <span data-ttu-id="f5b6a-220">Para obtener información sobre cómo utilizar un enlace personalizado para modificar un enlace proporcionado por el sistema, consulte [Cómo: personalizar un enlace proporcionados](../../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md).</span><span class="sxs-lookup"><span data-stu-id="f5b6a-220">For a discussion on how to use a custom binding to modify a system-provided binding, see [How to: Customize a System-Provided Binding](../../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md).</span></span>  
  
1.  
  
## <a name="see-also"></a><span data-ttu-id="f5b6a-221">Vea también</span><span class="sxs-lookup"><span data-stu-id="f5b6a-221">See Also</span></span>  
 <xref:System.ServiceModel.Channels.Binding>  
 <xref:System.ServiceModel.Channels.BindingElement>  
 <xref:System.ServiceModel.Configuration.BindingsSection>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="f5b6a-222">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="f5b6a-222">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)  
 [<span data-ttu-id="f5b6a-223">Enlaces</span><span class="sxs-lookup"><span data-stu-id="f5b6a-223">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="f5b6a-224">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="f5b6a-224">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="f5b6a-225">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="f5b6a-225">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="f5b6a-226">Elemento customBinding</span><span class="sxs-lookup"><span data-stu-id="f5b6a-226">customBinding Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="f5b6a-227">Enlaces</span><span class="sxs-lookup"><span data-stu-id="f5b6a-227">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="f5b6a-228">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="f5b6a-228">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="f5b6a-229">Utilización de enlaces para configurar los clientes y servicios de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="f5b6a-229">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)
