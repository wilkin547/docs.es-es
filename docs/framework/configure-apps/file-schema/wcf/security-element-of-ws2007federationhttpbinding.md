---
title: <security> elemento de <ws2007FederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 826219b4-3a16-45fc-832d-0cd7cbbd3b84
ms.openlocfilehash: b85c54c6507313522286e0c66504cfd0c8afb2b0
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738724"
---
# <a name="security-element-of-ws2007federationhttpbinding"></a><span data-ttu-id="b09db-102">\<elemento de > de seguridad de \<ws2007FederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="b09db-102">\<security> element of \<ws2007FederationHttpBinding></span></span>
<span data-ttu-id="b09db-103">Define la configuración de seguridad del elemento [\<> ws2007FederationHttpBinding](ws2007federationhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="b09db-103">Defines the security settings of the [\<ws2007FederationHttpBinding>](ws2007federationhttpbinding.md) element.</span></span>  
  
<span data-ttu-id="b09db-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b09db-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b09db-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="b09db-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="b09db-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**enlaces**](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="b09db-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="b09db-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<ws2007FederationHttpBinding**](ws2007federationhttpbinding.md) ></span><span class="sxs-lookup"><span data-stu-id="b09db-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007FederationHttpBinding>**](ws2007federationhttpbinding.md)</span></span>\
<span data-ttu-id="b09db-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**enlace** ></span><span class="sxs-lookup"><span data-stu-id="b09db-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="b09db-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**seguridad** ></span><span class="sxs-lookup"><span data-stu-id="b09db-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b09db-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b09db-110">Syntax</span></span>  
  
```xml  
<ws2007FederationBinding>
  <binding>
    <security mode="None/Message/TransportWithMessageCredential">
      <message negotiateServiceCredential="Boolean"
               algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/  Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               defaultProtectionLevel="none/sign/EncryptAndSign"
               issuedTokenType="string"
               issuedKeyType="SymmetricKey/PublicKey">
      </message>
    </security>
  </binding>
</ws2007FederationBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b09db-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b09db-111">Attributes and Elements</span></span>  
 <span data-ttu-id="b09db-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b09db-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b09db-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="b09db-113">Attributes</span></span>  
  
|<span data-ttu-id="b09db-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="b09db-114">Attribute</span></span>|<span data-ttu-id="b09db-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="b09db-115">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="b09db-116">Opcional.</span><span class="sxs-lookup"><span data-stu-id="b09db-116">Optional.</span></span> <span data-ttu-id="b09db-117">Especifica el tipo de seguridad que se aplica.</span><span class="sxs-lookup"><span data-stu-id="b09db-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="b09db-118">El valor predeterminado es `Message`.</span><span class="sxs-lookup"><span data-stu-id="b09db-118">The default value is `Message`.</span></span> <span data-ttu-id="b09db-119">Este atributo es del tipo <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="b09db-119">This attribute is of type <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="b09db-120">Atributo de modo</span><span class="sxs-lookup"><span data-stu-id="b09db-120">mode Attribute</span></span>  
  
|<span data-ttu-id="b09db-121">Valor</span><span class="sxs-lookup"><span data-stu-id="b09db-121">Value</span></span>|<span data-ttu-id="b09db-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="b09db-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b09db-123">Ninguno</span><span class="sxs-lookup"><span data-stu-id="b09db-123">None</span></span>|<span data-ttu-id="b09db-124">El mensaje SOAP no es seguro durante la transferencia.</span><span class="sxs-lookup"><span data-stu-id="b09db-124">The SOAP message is not secure during transfer.</span></span>|  
|<span data-ttu-id="b09db-125">Mensaje</span><span class="sxs-lookup"><span data-stu-id="b09db-125">Message</span></span>|<span data-ttu-id="b09db-126">La integridad, confidencialidad, autenticación de servidor y autenticación del cliente se proporciona mediante la seguridad del mensaje SOAP.</span><span class="sxs-lookup"><span data-stu-id="b09db-126">Integrity, confidentiality, server authentication and client authentication are provided using SOAP message security.</span></span> <span data-ttu-id="b09db-127">De forma predeterminada, el cuerpo se cifra y firma.</span><span class="sxs-lookup"><span data-stu-id="b09db-127">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="b09db-128">El servicio se debe configurar con un certificado.</span><span class="sxs-lookup"><span data-stu-id="b09db-128">The service must be configured with a certificate.</span></span> <span data-ttu-id="b09db-129">La autenticación del cliente está basada en el token emitido al cliente por un servicio del token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="b09db-129">Client authentication is based on the token issued to the client by a security token service.</span></span>|  
|<span data-ttu-id="b09db-130">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="b09db-130">TransportWithMessageCredential</span></span>|<span data-ttu-id="b09db-131">HTTPS proporciona integridad, confidencialidad y autenticación del servidor.</span><span class="sxs-lookup"><span data-stu-id="b09db-131">Integrity, confidentiality and server authentication are provided by HTTPS.</span></span> <span data-ttu-id="b09db-132">El servicio se debe configurar con un certificado.</span><span class="sxs-lookup"><span data-stu-id="b09db-132">The service must be configured with a certificate.</span></span> <span data-ttu-id="b09db-133">La autenticación del cliente se proporciona por medio de la seguridad del mensaje SOAP y está basada en el token emitido al cliente por un servicio de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="b09db-133">Client authentication is provided by means of SOAP message security and is based on the token issued to the client by a security token service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b09db-134">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b09db-134">Child Elements</span></span>  
  
|<span data-ttu-id="b09db-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="b09db-135">Element</span></span>|<span data-ttu-id="b09db-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="b09db-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b09db-137">\<> de mensaje</span><span class="sxs-lookup"><span data-stu-id="b09db-137">\<message></span></span>](message-of-ws2007httpbinding.md)|<span data-ttu-id="b09db-138">Define la configuración de seguridad del nivel del mensaje.</span><span class="sxs-lookup"><span data-stu-id="b09db-138">Defines the settings for the message-level security.</span></span> <span data-ttu-id="b09db-139">Este elemento es del tipo <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span><span class="sxs-lookup"><span data-stu-id="b09db-139">This element is of type <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b09db-140">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b09db-140">Parent Elements</span></span>  
  
|<span data-ttu-id="b09db-141">Elemento</span><span class="sxs-lookup"><span data-stu-id="b09db-141">Element</span></span>|<span data-ttu-id="b09db-142">Descripción</span><span class="sxs-lookup"><span data-stu-id="b09db-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b09db-143">\<> de enlace</span><span class="sxs-lookup"><span data-stu-id="b09db-143">\<binding></span></span>](bindings.md)|<span data-ttu-id="b09db-144">Define todas las funciones de enlace del [\<wsDualHttpBinding >](wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="b09db-144">Defines all binding capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b09db-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="b09db-145">See also</span></span>

- <xref:System.ServiceModel.WSFederationHttpSecurity>
- <xref:System.ServiceModel.WSFederationHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>
- [<span data-ttu-id="b09db-146">Creación de un WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="b09db-146">How to: Create a WSFederationHttpBinding</span></span>](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
- [<span data-ttu-id="b09db-147">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="b09db-147">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="b09db-148">Selección de tipos de credenciales</span><span class="sxs-lookup"><span data-stu-id="b09db-148">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="b09db-149">Enlaces</span><span class="sxs-lookup"><span data-stu-id="b09db-149">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="b09db-150">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="b09db-150">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="b09db-151">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="b09db-151">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="b09db-152">\<> de enlace</span><span class="sxs-lookup"><span data-stu-id="b09db-152">\<binding></span></span>](bindings.md)
