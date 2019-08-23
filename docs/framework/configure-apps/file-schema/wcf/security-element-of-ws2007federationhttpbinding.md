---
title: <security>elemento de<ws2007FederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 826219b4-3a16-45fc-832d-0cd7cbbd3b84
ms.openlocfilehash: 61b56ca1fae5c328cda0bbebef4026f0784095a3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936818"
---
# <a name="security-element-of-ws2007federationhttpbinding"></a><span data-ttu-id="3d90a-102">\<elemento Security > de \<ws2007FederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="3d90a-102">\<security> element of \<ws2007FederationHttpBinding></span></span>
<span data-ttu-id="3d90a-103">Define la configuración de seguridad del elemento [ \<> de ws2007FederationHttpBinding](ws2007federationhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="3d90a-103">Defines the security settings of the [\<ws2007FederationHttpBinding>](ws2007federationhttpbinding.md) element.</span></span>  
  
 <span data-ttu-id="3d90a-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="3d90a-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="3d90a-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="3d90a-105">\<bindings></span></span>  
<span data-ttu-id="3d90a-106">\<ws2007FederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="3d90a-106">\<ws2007FederationHttpBinding></span></span>  
<span data-ttu-id="3d90a-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="3d90a-107">\<binding></span></span>  
<span data-ttu-id="3d90a-108">\<> de seguridad</span><span class="sxs-lookup"><span data-stu-id="3d90a-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d90a-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3d90a-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3d90a-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3d90a-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3d90a-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3d90a-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3d90a-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="3d90a-112">Attributes</span></span>  
  
|<span data-ttu-id="3d90a-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="3d90a-113">Attribute</span></span>|<span data-ttu-id="3d90a-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="3d90a-114">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="3d90a-115">Opcional.</span><span class="sxs-lookup"><span data-stu-id="3d90a-115">Optional.</span></span> <span data-ttu-id="3d90a-116">Especifica el tipo de seguridad que se aplica.</span><span class="sxs-lookup"><span data-stu-id="3d90a-116">Specifies the type of security that is applied.</span></span> <span data-ttu-id="3d90a-117">El valor predeterminado es `Message`.</span><span class="sxs-lookup"><span data-stu-id="3d90a-117">The default value is `Message`.</span></span> <span data-ttu-id="3d90a-118">Este atributo es del tipo <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="3d90a-118">This attribute is of type <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="3d90a-119">Atributo de modo</span><span class="sxs-lookup"><span data-stu-id="3d90a-119">mode Attribute</span></span>  
  
|<span data-ttu-id="3d90a-120">Valor</span><span class="sxs-lookup"><span data-stu-id="3d90a-120">Value</span></span>|<span data-ttu-id="3d90a-121">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="3d90a-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3d90a-122">None</span><span class="sxs-lookup"><span data-stu-id="3d90a-122">None</span></span>|<span data-ttu-id="3d90a-123">El mensaje SOAP no es seguro durante la transferencia.</span><span class="sxs-lookup"><span data-stu-id="3d90a-123">The SOAP message is not secure during transfer.</span></span>|  
|<span data-ttu-id="3d90a-124">Message</span><span class="sxs-lookup"><span data-stu-id="3d90a-124">Message</span></span>|<span data-ttu-id="3d90a-125">La integridad, confidencialidad, autenticación de servidor y autenticación del cliente se proporciona mediante la seguridad del mensaje SOAP.</span><span class="sxs-lookup"><span data-stu-id="3d90a-125">Integrity, confidentiality, server authentication and client authentication are provided using SOAP message security.</span></span> <span data-ttu-id="3d90a-126">De forma predeterminada, el cuerpo se cifra y firma.</span><span class="sxs-lookup"><span data-stu-id="3d90a-126">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="3d90a-127">El servicio se debe configurar con un certificado.</span><span class="sxs-lookup"><span data-stu-id="3d90a-127">The service must be configured with a certificate.</span></span> <span data-ttu-id="3d90a-128">La autenticación del cliente está basada en el token emitido al cliente por un servicio del token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="3d90a-128">Client authentication is based on the token issued to the client by a security token service.</span></span>|  
|<span data-ttu-id="3d90a-129">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="3d90a-129">TransportWithMessageCredential</span></span>|<span data-ttu-id="3d90a-130">HTTPS proporciona integridad, confidencialidad y autenticación del servidor.</span><span class="sxs-lookup"><span data-stu-id="3d90a-130">Integrity, confidentiality and server authentication are provided by HTTPS.</span></span> <span data-ttu-id="3d90a-131">El servicio se debe configurar con un certificado.</span><span class="sxs-lookup"><span data-stu-id="3d90a-131">The service must be configured with a certificate.</span></span> <span data-ttu-id="3d90a-132">La autenticación del cliente se proporciona por medio de la seguridad del mensaje SOAP y está basada en el token emitido al cliente por un servicio de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="3d90a-132">Client authentication is provided by means of SOAP message security and is based on the token issued to the client by a security token service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3d90a-133">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3d90a-133">Child Elements</span></span>  
  
|<span data-ttu-id="3d90a-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="3d90a-134">Element</span></span>|<span data-ttu-id="3d90a-135">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="3d90a-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3d90a-136">\<message></span><span class="sxs-lookup"><span data-stu-id="3d90a-136">\<message></span></span>](message-of-ws2007httpbinding.md)|<span data-ttu-id="3d90a-137">Define la configuración de seguridad del nivel del mensaje.</span><span class="sxs-lookup"><span data-stu-id="3d90a-137">Defines the settings for the message-level security.</span></span> <span data-ttu-id="3d90a-138">Este elemento es del tipo <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span><span class="sxs-lookup"><span data-stu-id="3d90a-138">This element is of type <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3d90a-139">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3d90a-139">Parent Elements</span></span>  
  
|<span data-ttu-id="3d90a-140">Elemento</span><span class="sxs-lookup"><span data-stu-id="3d90a-140">Element</span></span>|<span data-ttu-id="3d90a-141">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="3d90a-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3d90a-142">\<binding></span><span class="sxs-lookup"><span data-stu-id="3d90a-142">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="3d90a-143">Define todas las funciones de enlace del [ \<> wsDualHttpBinding](wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="3d90a-143">Defines all binding capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3d90a-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="3d90a-144">See also</span></span>

- <xref:System.ServiceModel.WSFederationHttpSecurity>
- <xref:System.ServiceModel.WSFederationHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>
- [<span data-ttu-id="3d90a-145">Cómo: Creación de un WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="3d90a-145">How to: Create a WSFederationHttpBinding</span></span>](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
- [<span data-ttu-id="3d90a-146">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="3d90a-146">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="3d90a-147">Selección de tipos de credenciales</span><span class="sxs-lookup"><span data-stu-id="3d90a-147">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="3d90a-148">Enlaces</span><span class="sxs-lookup"><span data-stu-id="3d90a-148">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="3d90a-149">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="3d90a-149">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="3d90a-150">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="3d90a-150">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="3d90a-151">\<binding></span><span class="sxs-lookup"><span data-stu-id="3d90a-151">\<binding></span></span>](../../../misc/binding.md)
