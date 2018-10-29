---
title: '&lt;security&gt; (elemento) de &lt;ws2007FederationHttpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 826219b4-3a16-45fc-832d-0cd7cbbd3b84
ms.openlocfilehash: e212e73f03d52bdfcba8559db5ab62288b3ebcc2
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2018
ms.locfileid: "50199232"
---
# <a name="ltsecuritygt-element-of-ltws2007federationhttpbindinggt"></a><span data-ttu-id="b4828-102">&lt;security&gt; (elemento) de &lt;ws2007FederationHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="b4828-102">&lt;security&gt; element of &lt;ws2007FederationHttpBinding&gt;</span></span>
<span data-ttu-id="b4828-103">Define la configuración de seguridad de la [ \<ws2007FederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007federationhttpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="b4828-103">Defines the security settings of the [\<ws2007FederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007federationhttpbinding.md) element.</span></span>  
  
 <span data-ttu-id="b4828-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="b4828-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="b4828-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="b4828-105">\<bindings></span></span>  
<span data-ttu-id="b4828-106">\<ws2007FederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="b4828-106">\<ws2007FederationHttpBinding></span></span>  
<span data-ttu-id="b4828-107">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="b4828-107">\<binding></span></span>  
<span data-ttu-id="b4828-108">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="b4828-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4828-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b4828-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b4828-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b4828-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b4828-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b4828-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b4828-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="b4828-112">Attributes</span></span>  
  
|<span data-ttu-id="b4828-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="b4828-113">Attribute</span></span>|<span data-ttu-id="b4828-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="b4828-114">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="b4828-115">Opcional.</span><span class="sxs-lookup"><span data-stu-id="b4828-115">Optional.</span></span> <span data-ttu-id="b4828-116">Especifica el tipo de seguridad que se aplica.</span><span class="sxs-lookup"><span data-stu-id="b4828-116">Specifies the type of security that is applied.</span></span> <span data-ttu-id="b4828-117">El valor predeterminado es `Message`.</span><span class="sxs-lookup"><span data-stu-id="b4828-117">The default value is `Message`.</span></span> <span data-ttu-id="b4828-118">Este atributo es del tipo <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="b4828-118">This attribute is of type <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="b4828-119">Atributo de modo</span><span class="sxs-lookup"><span data-stu-id="b4828-119">mode Attribute</span></span>  
  
|<span data-ttu-id="b4828-120">Valor</span><span class="sxs-lookup"><span data-stu-id="b4828-120">Value</span></span>|<span data-ttu-id="b4828-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="b4828-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b4828-122">Ninguna</span><span class="sxs-lookup"><span data-stu-id="b4828-122">None</span></span>|<span data-ttu-id="b4828-123">El mensaje SOAP no es seguro durante la transferencia.</span><span class="sxs-lookup"><span data-stu-id="b4828-123">The SOAP message is not secure during transfer.</span></span>|  
|<span data-ttu-id="b4828-124">Mensaje</span><span class="sxs-lookup"><span data-stu-id="b4828-124">Message</span></span>|<span data-ttu-id="b4828-125">La integridad, confidencialidad, autenticación de servidor y autenticación del cliente se proporciona mediante la seguridad del mensaje SOAP.</span><span class="sxs-lookup"><span data-stu-id="b4828-125">Integrity, confidentiality, server authentication and client authentication are provided using SOAP message security.</span></span> <span data-ttu-id="b4828-126">De forma predeterminada, el cuerpo se cifra y firma.</span><span class="sxs-lookup"><span data-stu-id="b4828-126">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="b4828-127">El servicio se debe configurar con un certificado.</span><span class="sxs-lookup"><span data-stu-id="b4828-127">The service must be configured with a certificate.</span></span> <span data-ttu-id="b4828-128">La autenticación del cliente está basada en el token emitido al cliente por un servicio del token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="b4828-128">Client authentication is based on the token issued to the client by a security token service.</span></span>|  
|<span data-ttu-id="b4828-129">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="b4828-129">TransportWithMessageCredential</span></span>|<span data-ttu-id="b4828-130">HTTPS proporciona integridad, confidencialidad y autenticación del servidor.</span><span class="sxs-lookup"><span data-stu-id="b4828-130">Integrity, confidentiality and server authentication are provided by HTTPS.</span></span> <span data-ttu-id="b4828-131">El servicio se debe configurar con un certificado.</span><span class="sxs-lookup"><span data-stu-id="b4828-131">The service must be configured with a certificate.</span></span> <span data-ttu-id="b4828-132">La autenticación del cliente se proporciona por medio de la seguridad del mensaje SOAP y está basada en el token emitido al cliente por un servicio de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="b4828-132">Client authentication is provided by means of SOAP message security and is based on the token issued to the client by a security token service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b4828-133">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b4828-133">Child Elements</span></span>  
  
|<span data-ttu-id="b4828-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="b4828-134">Element</span></span>|<span data-ttu-id="b4828-135">Descripción</span><span class="sxs-lookup"><span data-stu-id="b4828-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b4828-136">\<mensaje ></span><span class="sxs-lookup"><span data-stu-id="b4828-136">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-ws2007httpbinding.md)|<span data-ttu-id="b4828-137">Define la configuración de seguridad del nivel del mensaje.</span><span class="sxs-lookup"><span data-stu-id="b4828-137">Defines the settings for the message-level security.</span></span> <span data-ttu-id="b4828-138">Este elemento es del tipo <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span><span class="sxs-lookup"><span data-stu-id="b4828-138">This element is of type <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b4828-139">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b4828-139">Parent Elements</span></span>  
  
|<span data-ttu-id="b4828-140">Elemento</span><span class="sxs-lookup"><span data-stu-id="b4828-140">Element</span></span>|<span data-ttu-id="b4828-141">Descripción</span><span class="sxs-lookup"><span data-stu-id="b4828-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b4828-142">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="b4828-142">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="b4828-143">Define todas las capacidades de enlace de la [ \<wsDualHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="b4828-143">Defines all binding capabilities of the [\<wsDualHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b4828-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="b4828-144">See Also</span></span>  
 <xref:System.ServiceModel.WSFederationHttpSecurity>  
 <xref:System.ServiceModel.WSFederationHttpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>  
 [<span data-ttu-id="b4828-145">Creación de un WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="b4828-145">How to: Create a WSFederationHttpBinding</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)  
 [<span data-ttu-id="b4828-146">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="b4828-146">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="b4828-147">Selección de tipos de credenciales</span><span class="sxs-lookup"><span data-stu-id="b4828-147">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="b4828-148">Enlaces</span><span class="sxs-lookup"><span data-stu-id="b4828-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="b4828-149">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="b4828-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="b4828-150">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="b4828-150">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="b4828-151">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="b4828-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
