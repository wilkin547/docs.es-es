---
title: '&lt;security&gt; (elemento) de &lt;ws2007FederationHttpBinding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 826219b4-3a16-45fc-832d-0cd7cbbd3b84
caps.latest.revision: "10"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 79976b015f35bdd71a5f95a018d85c0ba41ce0b2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltsecuritygt-element-of-ltws2007federationhttpbindinggt"></a><span data-ttu-id="77460-102">&lt;security&gt; (elemento) de &lt;ws2007FederationHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="77460-102">&lt;security&gt; element of &lt;ws2007FederationHttpBinding&gt;</span></span>
<span data-ttu-id="77460-103">Define la configuración de seguridad de la [ \<ws2007FederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007federationhttpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="77460-103">Defines the security settings of the [\<ws2007FederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007federationhttpbinding.md) element.</span></span>  
  
 <span data-ttu-id="77460-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="77460-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="77460-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="77460-105">\<bindings></span></span>  
<span data-ttu-id="77460-106">\<ws2007FederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="77460-106">\<ws2007FederationHttpBinding></span></span>  
<span data-ttu-id="77460-107">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="77460-107">\<binding></span></span>  
<span data-ttu-id="77460-108">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="77460-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77460-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="77460-109">Syntax</span></span>  
  
```xml  
<ws2007FederationBinding>  
    <binding >  
        <security mode="None/Message/TransportWithMessageCredential">  
           <message negotiateServiceCredential="Boolean"  
                algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/ Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
                defaultProtectionLevel="none/sign/EncryptAndSign"   
                issuedTokenType="string"   
                issuedKeyType="SymmetricKey/PublicKey"  
           </message>  
        </security>  
    </binding>  
</ws2007FederationBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="77460-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="77460-110">Attributes and Elements</span></span>  
 <span data-ttu-id="77460-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="77460-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="77460-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="77460-112">Attributes</span></span>  
  
|<span data-ttu-id="77460-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="77460-113">Attribute</span></span>|<span data-ttu-id="77460-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="77460-114">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="77460-115">Opcional.</span><span class="sxs-lookup"><span data-stu-id="77460-115">Optional.</span></span> <span data-ttu-id="77460-116">Especifica el tipo de seguridad que se aplica.</span><span class="sxs-lookup"><span data-stu-id="77460-116">Specifies the type of security that is applied.</span></span> <span data-ttu-id="77460-117">El valor predeterminado es `Message`.</span><span class="sxs-lookup"><span data-stu-id="77460-117">The default value is `Message`.</span></span> <span data-ttu-id="77460-118">Este atributo es del tipo <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="77460-118">This attribute is of type <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="77460-119">Atributo de modo</span><span class="sxs-lookup"><span data-stu-id="77460-119">mode Attribute</span></span>  
  
|<span data-ttu-id="77460-120">Valor</span><span class="sxs-lookup"><span data-stu-id="77460-120">Value</span></span>|<span data-ttu-id="77460-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="77460-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="77460-122">Ninguna</span><span class="sxs-lookup"><span data-stu-id="77460-122">None</span></span>|<span data-ttu-id="77460-123">El mensaje SOAP no es seguro durante la transferencia.</span><span class="sxs-lookup"><span data-stu-id="77460-123">The SOAP message is not secure during transfer.</span></span>|  
|<span data-ttu-id="77460-124">Mensaje</span><span class="sxs-lookup"><span data-stu-id="77460-124">Message</span></span>|<span data-ttu-id="77460-125">La integridad, confidencialidad, autenticación de servidor y autenticación del cliente se proporciona mediante la seguridad del mensaje SOAP.</span><span class="sxs-lookup"><span data-stu-id="77460-125">Integrity, confidentiality, server authentication and client authentication are provided using SOAP message security.</span></span> <span data-ttu-id="77460-126">De forma predeterminada, el cuerpo se cifra y firma.</span><span class="sxs-lookup"><span data-stu-id="77460-126">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="77460-127">El servicio se debe configurar con un certificado.</span><span class="sxs-lookup"><span data-stu-id="77460-127">The service must be configured with a certificate.</span></span> <span data-ttu-id="77460-128">La autenticación del cliente está basada en el token emitido al cliente por un servicio del token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="77460-128">Client authentication is based on the token issued to the client by a security token service.</span></span>|  
|<span data-ttu-id="77460-129">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="77460-129">TransportWithMessageCredential</span></span>|<span data-ttu-id="77460-130">HTTPS proporciona integridad, confidencialidad y autenticación del servidor.</span><span class="sxs-lookup"><span data-stu-id="77460-130">Integrity, confidentiality and server authentication are provided by HTTPS.</span></span> <span data-ttu-id="77460-131">El servicio se debe configurar con un certificado.</span><span class="sxs-lookup"><span data-stu-id="77460-131">The service must be configured with a certificate.</span></span> <span data-ttu-id="77460-132">La autenticación del cliente se proporciona por medio de la seguridad del mensaje SOAP y está basada en el token emitido al cliente por un servicio de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="77460-132">Client authentication is provided by means of SOAP message security and is based on the token issued to the client by a security token service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="77460-133">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="77460-133">Child Elements</span></span>  
  
|<span data-ttu-id="77460-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="77460-134">Element</span></span>|<span data-ttu-id="77460-135">Descripción</span><span class="sxs-lookup"><span data-stu-id="77460-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="77460-136">\<mensaje ></span><span class="sxs-lookup"><span data-stu-id="77460-136">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-ws2007httpbinding.md)|<span data-ttu-id="77460-137">Define la configuración de seguridad del nivel del mensaje.</span><span class="sxs-lookup"><span data-stu-id="77460-137">Defines the settings for the message-level security.</span></span> <span data-ttu-id="77460-138">Este elemento es del tipo <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span><span class="sxs-lookup"><span data-stu-id="77460-138">This element is of type <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="77460-139">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="77460-139">Parent Elements</span></span>  
  
|<span data-ttu-id="77460-140">Elemento</span><span class="sxs-lookup"><span data-stu-id="77460-140">Element</span></span>|<span data-ttu-id="77460-141">Descripción</span><span class="sxs-lookup"><span data-stu-id="77460-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="77460-142">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="77460-142">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="77460-143">Define todas las funcionalidades de enlace de la [ \<wsDualHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="77460-143">Defines all binding capabilities of the [\<wsDualHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="77460-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="77460-144">See Also</span></span>  
 <xref:System.ServiceModel.WSFederationHttpSecurity>  
 <xref:System.ServiceModel.WSFederationHttpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>  
 [<span data-ttu-id="77460-145">Cómo: crear un WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="77460-145">How to: Create a WSFederationHttpBinding</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)  
 [<span data-ttu-id="77460-146">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="77460-146">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="77460-147">Al seleccionar un tipo de credencial</span><span class="sxs-lookup"><span data-stu-id="77460-147">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="77460-148">Enlaces</span><span class="sxs-lookup"><span data-stu-id="77460-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="77460-149">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="77460-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="77460-150">Utilización de enlaces para configurar los clientes y servicios de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="77460-150">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="77460-151">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="77460-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
