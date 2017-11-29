---
title: '&lt;allowedAudienceUris&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0f4dc73d-d95d-4193-9755-7df4cf2b8e1c
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b48449df95e9cf927cad805043c7419ec8c13be6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltallowedaudienceurisgt"></a><span data-ttu-id="68c23-102">&lt;allowedAudienceUris&gt;</span><span class="sxs-lookup"><span data-stu-id="68c23-102">&lt;allowedAudienceUris&gt;</span></span>
<span data-ttu-id="68c23-103">Representa una colección de los URI de destino para los que el token de seguridad <xref:System.IdentityModel.Tokens.SamlSecurityToken> se puede destinar con el fin de que una instancia de <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> lo considere válido.</span><span class="sxs-lookup"><span data-stu-id="68c23-103">Represents a collection of target URIs for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span>  
  
 <span data-ttu-id="68c23-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="68c23-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="68c23-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="68c23-105">\<behaviors></span></span>  
<span data-ttu-id="68c23-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="68c23-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="68c23-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="68c23-107">\<behavior></span></span>  
<span data-ttu-id="68c23-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="68c23-108">\<serviceCredentials></span></span>  
<span data-ttu-id="68c23-109">\<issuedTokenAuthentication ></span><span class="sxs-lookup"><span data-stu-id="68c23-109">\<issuedTokenAuthentication></span></span>  
<span data-ttu-id="68c23-110">\<allowedAudienceUris ></span><span class="sxs-lookup"><span data-stu-id="68c23-110">\<allowedAudienceUris></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68c23-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="68c23-111">Syntax</span></span>  
  
```xml  
<allowedAudienceUris>  
      <add allowedAudienceUri="String"/>  
</allowedAudienceUris>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="68c23-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="68c23-112">Attributes and Elements</span></span>  
 <span data-ttu-id="68c23-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="68c23-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="68c23-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="68c23-114">Attributes</span></span>  
 <span data-ttu-id="68c23-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="68c23-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="68c23-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="68c23-116">Child Elements</span></span>  
  
|<span data-ttu-id="68c23-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="68c23-117">Element</span></span>|<span data-ttu-id="68c23-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="68c23-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="68c23-119">\<add></span><span class="sxs-lookup"><span data-stu-id="68c23-119">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-allowedaudienceuris.md)|<span data-ttu-id="68c23-120">Agrega un URI de destino para el que el token de seguridad <xref:System.IdentityModel.Tokens.SamlSecurityToken> se puede destinar con el fin de que una instancia de <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> lo considere válido.</span><span class="sxs-lookup"><span data-stu-id="68c23-120">Adds a target Uri for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="68c23-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="68c23-121">Parent Elements</span></span>  
  
|<span data-ttu-id="68c23-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="68c23-122">Element</span></span>|<span data-ttu-id="68c23-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="68c23-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="68c23-124">\<issuedTokenAuthentication ></span><span class="sxs-lookup"><span data-stu-id="68c23-124">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="68c23-125">Especifica un token emitido como una credencial del servicio.</span><span class="sxs-lookup"><span data-stu-id="68c23-125">Specifies a token issued as a service credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="68c23-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="68c23-126">Remarks</span></span>  
 <span data-ttu-id="68c23-127">Debería utilizar esta colección en una aplicación federada que utilice un servicio de token seguro (STS) que emita tokens de seguridad <xref:System.IdentityModel.Tokens.SamlSecurityToken>.</span><span class="sxs-lookup"><span data-stu-id="68c23-127">You should use this collection in a federated application that utilizes a security token service (STS) that issues <xref:System.IdentityModel.Tokens.SamlSecurityToken> security tokens.</span></span> <span data-ttu-id="68c23-128">Cuando el STS emite el token de seguridad, puede especificar el URI de los servicios Web para el que está dirigido el token de seguridad mediante la agregación de una <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> al token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="68c23-128">When the STS issues the security token, it can specify the URI of the Web services for which the security token is intended by adding a <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> to the security token.</span></span> <span data-ttu-id="68c23-129">Eso le permite al <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> del servicio Web del destinatario comprobar que el token de seguridad emitido está dirigido a este servicio Web especificando que esta comprobación debería tener lugar haciendo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="68c23-129">That allows the <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> for the recipient Web service to verify that the issued security token is intended for this Web service by specifying that this check should happen by doing the following:</span></span>  
  
-   <span data-ttu-id="68c23-130">Establezca el atributo `audienceUriMode` de `<issuedTokenAuthentication>` en <xref:System.IdentityModel.Selectors.AudienceUriMode.Always> o <xref:System.IdentityModel.Selectors.AudienceUriMode.BearerKeyOnly>.</span><span class="sxs-lookup"><span data-stu-id="68c23-130">Set the `audienceUriMode` attribute of `<issuedTokenAuthentication>` to <xref:System.IdentityModel.Selectors.AudienceUriMode.Always> or <xref:System.IdentityModel.Selectors.AudienceUriMode.BearerKeyOnly>.</span></span>  
  
-   <span data-ttu-id="68c23-131">Especifique el conjunto de identificadores URI válidos, agregando los URI a esta colección.</span><span class="sxs-lookup"><span data-stu-id="68c23-131">Specify the set of valid URIs, by adding the URIs to this collection.</span></span>  
  
 <span data-ttu-id="68c23-132">Para obtener más información, consulta <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span><span class="sxs-lookup"><span data-stu-id="68c23-132">For more information, see <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span></span>  
  
 <span data-ttu-id="68c23-133">Para obtener más información sobre el uso de este elemento de configuración, consulte [Cómo: configurar las credenciales en un servicio de federación](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span><span class="sxs-lookup"><span data-stu-id="68c23-133">For more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68c23-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="68c23-134">See Also</span></span>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.AllowedAudienceUris%2A>  
 <xref:System.ServiceModel.Configuration.AllowedAudienceUriElementCollection>  
 <xref:System.ServiceModel.Configuration.AllowedAudienceUriElement>  
 <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.AllowedAudienceUris%2A>  
 [<span data-ttu-id="68c23-135">\<issuedTokenAuthentication ></span><span class="sxs-lookup"><span data-stu-id="68c23-135">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)  
 [<span data-ttu-id="68c23-136">\<add></span><span class="sxs-lookup"><span data-stu-id="68c23-136">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-allowedaudienceuris.md)  
 [<span data-ttu-id="68c23-137">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="68c23-137">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="68c23-138">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="68c23-138">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="68c23-139">Cómo: configurar las credenciales en un servicio de federación</span><span class="sxs-lookup"><span data-stu-id="68c23-139">How to: Configure Credentials on a Federation Service</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
