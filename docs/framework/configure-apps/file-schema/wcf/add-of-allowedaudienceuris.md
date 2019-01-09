---
title: '&lt;add&gt; de &lt;allowedAudienceUris&gt;'
ms.date: 03/30/2017
ms.assetid: 4e7b7637-e0ea-4a91-988f-6b6ef28d9fc3
ms.openlocfilehash: 5428b41cadebbb38716789fa0e275c244fe74311
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54146247"
---
# <a name="ltaddgt-of-ltallowedaudienceurisgt"></a><span data-ttu-id="bbb4f-102">&lt;add&gt; de &lt;allowedAudienceUris&gt;</span><span class="sxs-lookup"><span data-stu-id="bbb4f-102">&lt;add&gt; of &lt;allowedAudienceUris&gt;</span></span>
<span data-ttu-id="bbb4f-103">Agrega un URI de destino para el que el token de seguridad <xref:System.IdentityModel.Tokens.SamlSecurityToken> se puede destinar con el fin de que una instancia de <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> lo considere válido.</span><span class="sxs-lookup"><span data-stu-id="bbb4f-103">Adds a target Uri for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span>  
  
 <span data-ttu-id="bbb4f-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="bbb4f-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="bbb4f-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="bbb4f-105">\<behaviors></span></span>  
<span data-ttu-id="bbb4f-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="bbb4f-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="bbb4f-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="bbb4f-107">\<behavior></span></span>  
<span data-ttu-id="bbb4f-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="bbb4f-108">\<serviceCredentials></span></span>  
<span data-ttu-id="bbb4f-109">\<issuedTokenAuthentication ></span><span class="sxs-lookup"><span data-stu-id="bbb4f-109">\<issuedTokenAuthentication></span></span>  
<span data-ttu-id="bbb4f-110">\<allowedAudienceUris ></span><span class="sxs-lookup"><span data-stu-id="bbb4f-110">\<allowedAudienceUris></span></span>  
<span data-ttu-id="bbb4f-111">\<Agregar > elemento para \<allowedAudienceUris ></span><span class="sxs-lookup"><span data-stu-id="bbb4f-111">\<add> element for \<allowedAudienceUris></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bbb4f-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bbb4f-112">Syntax</span></span>  
  
```xml  
<allowedAudienceUris>
  <add allowedAudienceUri="String" />
</allowedAudienceUris>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bbb4f-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="bbb4f-113">Attributes and Elements</span></span>  
 <span data-ttu-id="bbb4f-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="bbb4f-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bbb4f-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="bbb4f-115">Attributes</span></span>  
  
|<span data-ttu-id="bbb4f-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="bbb4f-116">Attribute</span></span>|<span data-ttu-id="bbb4f-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="bbb4f-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bbb4f-118">allowedAudienceUri</span><span class="sxs-lookup"><span data-stu-id="bbb4f-118">allowedAudienceUri</span></span>|<span data-ttu-id="bbb4f-119">Cadena que contiene un URI de destino para el que el token de seguridad <xref:System.IdentityModel.Tokens.SamlSecurityToken> se puede destinar con el fin de que una instancia de <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> lo considere válido.</span><span class="sxs-lookup"><span data-stu-id="bbb4f-119">A string that contains a target Uri for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bbb4f-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="bbb4f-120">Child Elements</span></span>  
 <span data-ttu-id="bbb4f-121">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="bbb4f-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bbb4f-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="bbb4f-122">Parent Elements</span></span>  
  
|<span data-ttu-id="bbb4f-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="bbb4f-123">Element</span></span>|<span data-ttu-id="bbb4f-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="bbb4f-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bbb4f-125">\<allowedAudienceUris ></span><span class="sxs-lookup"><span data-stu-id="bbb4f-125">\<allowedAudienceUris></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/allowedaudienceuris.md)|<span data-ttu-id="bbb4f-126">Representa una colección de los URI de destino para los que el token de seguridad <xref:System.IdentityModel.Tokens.SamlSecurityToken> se puede destinar con el fin de que una instancia de <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> lo considere válido.</span><span class="sxs-lookup"><span data-stu-id="bbb4f-126">Represents a collection of target URIs for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bbb4f-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bbb4f-127">Remarks</span></span>  
 <span data-ttu-id="bbb4f-128">Debería utilizar esta colección en una aplicación federada que utilice un servicio de token seguro (STS) que emita tokens de seguridad <xref:System.IdentityModel.Tokens.SamlSecurityToken>.</span><span class="sxs-lookup"><span data-stu-id="bbb4f-128">You should use this collection in a federated application that utilizes a security token service (STS) that issues <xref:System.IdentityModel.Tokens.SamlSecurityToken> security tokens.</span></span> <span data-ttu-id="bbb4f-129">Cuando el STS emite el token de seguridad, puede especificar el URI de los servicios Web para el que está dirigido el token de seguridad mediante la agregación de una <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> al token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="bbb4f-129">When the STS issues the security token, it can specify the URI of the Web services for which the security token is intended by adding a <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> to the security token.</span></span> <span data-ttu-id="bbb4f-130">Eso le permite al <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> del servicio Web del destinatario comprobar que el token de seguridad emitido está dirigido a este servicio Web especificando que esta comprobación debería tener lugar haciendo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bbb4f-130">That allows the <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> for the recipient Web service to verify that the issued security token is intended for this Web service by specifying that this check should happen by doing the following:</span></span>  
  
-   <span data-ttu-id="bbb4f-131">Establezca el atributo `audienceUriMode` de `<issuedTokenAuthentication>` en <xref:System.IdentityModel.Selectors.AudienceUriMode.Always> o <xref:System.IdentityModel.Selectors.AudienceUriMode.BearerKeyOnly>.</span><span class="sxs-lookup"><span data-stu-id="bbb4f-131">Set the `audienceUriMode` attribute of `<issuedTokenAuthentication>` to <xref:System.IdentityModel.Selectors.AudienceUriMode.Always> or <xref:System.IdentityModel.Selectors.AudienceUriMode.BearerKeyOnly>.</span></span>  
  
-   <span data-ttu-id="bbb4f-132">Especifique el conjunto de identificadores URI válidos, agregando los URI a esta colección.</span><span class="sxs-lookup"><span data-stu-id="bbb4f-132">Specify the set of valid URIs, by adding the URIs to this collection.</span></span>  
  
 <span data-ttu-id="bbb4f-133">Para obtener más información, consulta <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span><span class="sxs-lookup"><span data-stu-id="bbb4f-133">For more information, see <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span></span>  
  
 <span data-ttu-id="bbb4f-134">Para obtener más información sobre el uso de este elemento de configuración, vea [Cómo: Configurar las credenciales en un servicio de federación](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span><span class="sxs-lookup"><span data-stu-id="bbb4f-134">For more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbb4f-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="bbb4f-135">See Also</span></span>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.AllowedAudienceUris%2A>  
 <xref:System.ServiceModel.Configuration.AllowedAudienceUriElementCollection>  
 <xref:System.ServiceModel.Configuration.AllowedAudienceUriElement>  
 <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.AllowedAudienceUris%2A>  
 [<span data-ttu-id="bbb4f-136">\<allowedAudienceUris ></span><span class="sxs-lookup"><span data-stu-id="bbb4f-136">\<allowedAudienceUris></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/allowedaudienceuris.md)  
 [<span data-ttu-id="bbb4f-137">\<issuedTokenAuthentication ></span><span class="sxs-lookup"><span data-stu-id="bbb4f-137">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)  
 [<span data-ttu-id="bbb4f-138">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="bbb4f-138">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="bbb4f-139">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="bbb4f-139">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="bbb4f-140">Cómo: Configurar las credenciales en un servicio de federación</span><span class="sxs-lookup"><span data-stu-id="bbb4f-140">How to: Configure Credentials on a Federation Service</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
