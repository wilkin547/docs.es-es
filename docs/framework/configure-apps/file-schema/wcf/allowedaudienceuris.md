---
title: <allowedAudienceUris>
ms.date: 03/30/2017
ms.assetid: 0f4dc73d-d95d-4193-9755-7df4cf2b8e1c
ms.openlocfilehash: 03888600a89d72f5216c8c8cac21c9da96879ba8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919977"
---
# <a name="allowedaudienceuris"></a><span data-ttu-id="132ae-101">\<allowedAudienceUris></span><span class="sxs-lookup"><span data-stu-id="132ae-101">\<allowedAudienceUris></span></span>
<span data-ttu-id="132ae-102">Representa una colección de los URI de destino para los que el token de seguridad <xref:System.IdentityModel.Tokens.SamlSecurityToken> se puede destinar con el fin de que una instancia de <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> lo considere válido.</span><span class="sxs-lookup"><span data-stu-id="132ae-102">Represents a collection of target URIs for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span>  
  
 <span data-ttu-id="132ae-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="132ae-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="132ae-104">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="132ae-104">\<behaviors></span></span>  
<span data-ttu-id="132ae-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="132ae-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="132ae-106">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="132ae-106">\<behavior></span></span>  
<span data-ttu-id="132ae-107">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="132ae-107">\<serviceCredentials></span></span>  
<span data-ttu-id="132ae-108">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="132ae-108">\<issuedTokenAuthentication></span></span>  
<span data-ttu-id="132ae-109">\<allowedAudienceUris></span><span class="sxs-lookup"><span data-stu-id="132ae-109">\<allowedAudienceUris></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="132ae-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="132ae-110">Syntax</span></span>  
  
```xml  
<allowedAudienceUris>
  <add allowedAudienceUri="String" />
</allowedAudienceUris>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="132ae-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="132ae-111">Attributes and Elements</span></span>  
 <span data-ttu-id="132ae-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="132ae-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="132ae-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="132ae-113">Attributes</span></span>  
 <span data-ttu-id="132ae-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="132ae-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="132ae-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="132ae-115">Child Elements</span></span>  
  
|<span data-ttu-id="132ae-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="132ae-116">Element</span></span>|<span data-ttu-id="132ae-117">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="132ae-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="132ae-118">\<add></span><span class="sxs-lookup"><span data-stu-id="132ae-118">\<add></span></span>](add-of-allowedaudienceuris.md)|<span data-ttu-id="132ae-119">Agrega un URI de destino para el que el token de seguridad <xref:System.IdentityModel.Tokens.SamlSecurityToken> se puede destinar con el fin de que una instancia de <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> lo considere válido.</span><span class="sxs-lookup"><span data-stu-id="132ae-119">Adds a target Uri for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="132ae-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="132ae-120">Parent Elements</span></span>  
  
|<span data-ttu-id="132ae-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="132ae-121">Element</span></span>|<span data-ttu-id="132ae-122">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="132ae-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="132ae-123">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="132ae-123">\<issuedTokenAuthentication></span></span>](issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="132ae-124">Especifica un token emitido como una credencial del servicio.</span><span class="sxs-lookup"><span data-stu-id="132ae-124">Specifies a token issued as a service credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="132ae-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="132ae-125">Remarks</span></span>  
 <span data-ttu-id="132ae-126">Debería utilizar esta colección en una aplicación federada que utilice un servicio de token seguro (STS) que emita tokens de seguridad <xref:System.IdentityModel.Tokens.SamlSecurityToken>.</span><span class="sxs-lookup"><span data-stu-id="132ae-126">You should use this collection in a federated application that utilizes a security token service (STS) that issues <xref:System.IdentityModel.Tokens.SamlSecurityToken> security tokens.</span></span> <span data-ttu-id="132ae-127">Cuando el STS emite el token de seguridad, puede especificar el URI de los servicios Web para el que está dirigido el token de seguridad mediante la agregación de una <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> al token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="132ae-127">When the STS issues the security token, it can specify the URI of the Web services for which the security token is intended by adding a <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> to the security token.</span></span> <span data-ttu-id="132ae-128">Eso le permite al <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> del servicio Web del destinatario comprobar que el token de seguridad emitido está dirigido a este servicio Web especificando que esta comprobación debería tener lugar haciendo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="132ae-128">That allows the <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> for the recipient Web service to verify that the issued security token is intended for this Web service by specifying that this check should happen by doing the following:</span></span>  
  
- <span data-ttu-id="132ae-129">Establezca el atributo `audienceUriMode` de `<issuedTokenAuthentication>` en <xref:System.IdentityModel.Selectors.AudienceUriMode.Always> o <xref:System.IdentityModel.Selectors.AudienceUriMode.BearerKeyOnly>.</span><span class="sxs-lookup"><span data-stu-id="132ae-129">Set the `audienceUriMode` attribute of `<issuedTokenAuthentication>` to <xref:System.IdentityModel.Selectors.AudienceUriMode.Always> or <xref:System.IdentityModel.Selectors.AudienceUriMode.BearerKeyOnly>.</span></span>  
  
- <span data-ttu-id="132ae-130">Especifique el conjunto de identificadores URI válidos, agregando los URI a esta colección.</span><span class="sxs-lookup"><span data-stu-id="132ae-130">Specify the set of valid URIs, by adding the URIs to this collection.</span></span>  
  
 <span data-ttu-id="132ae-131">Para obtener más información, consulta <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span><span class="sxs-lookup"><span data-stu-id="132ae-131">For more information, see <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span></span>  
  
 <span data-ttu-id="132ae-132">Para obtener más información sobre el uso de este elemento [de configuración, vea cómo: Configure las credenciales](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)en un servicio de Federación.</span><span class="sxs-lookup"><span data-stu-id="132ae-132">For more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="132ae-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="132ae-133">See also</span></span>

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.AllowedAudienceUris%2A>
- <xref:System.ServiceModel.Configuration.AllowedAudienceUriElementCollection>
- <xref:System.ServiceModel.Configuration.AllowedAudienceUriElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.AllowedAudienceUris%2A>
- [<span data-ttu-id="132ae-134">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="132ae-134">\<issuedTokenAuthentication></span></span>](issuedtokenauthentication-of-servicecredentials.md)
- [<span data-ttu-id="132ae-135">\<add></span><span class="sxs-lookup"><span data-stu-id="132ae-135">\<add></span></span>](add-of-allowedaudienceuris.md)
- [<span data-ttu-id="132ae-136">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="132ae-136">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="132ae-137">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="132ae-137">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="132ae-138">Procedimientos: Configurar credenciales en un Servicio de federación</span><span class="sxs-lookup"><span data-stu-id="132ae-138">How to: Configure Credentials on a Federation Service</span></span>](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
