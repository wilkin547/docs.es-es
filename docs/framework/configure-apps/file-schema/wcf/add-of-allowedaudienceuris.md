---
description: 'Más información sobre: <add> de <allowedAudienceUris>'
title: <add> de <allowedAudienceUris>
ms.date: 03/30/2017
ms.assetid: 4e7b7637-e0ea-4a91-988f-6b6ef28d9fc3
ms.openlocfilehash: caa61da0ee7e00691213b95e31c943f5d81eea32
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99782212"
---
# <a name="add-of-allowedaudienceuris"></a><span data-ttu-id="d09fe-103">\<add> de \<allowedAudienceUris></span><span class="sxs-lookup"><span data-stu-id="d09fe-103">\<add> of \<allowedAudienceUris></span></span>

<span data-ttu-id="d09fe-104">Agrega un URI de destino para el que el token de seguridad <xref:System.IdentityModel.Tokens.SamlSecurityToken> se puede destinar con el fin de que una instancia de <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> lo considere válido.</span><span class="sxs-lookup"><span data-stu-id="d09fe-104">Adds a target Uri for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenAuthentication>**](issuedtokenauthentication-of-servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<allowedAudienceUris>**](allowedaudienceuris.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="d09fe-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d09fe-105">Syntax</span></span>  
  
```xml  
<allowedAudienceUris>
  <add allowedAudienceUri="String" />
</allowedAudienceUris>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d09fe-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d09fe-106">Attributes and Elements</span></span>  

 <span data-ttu-id="d09fe-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d09fe-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d09fe-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="d09fe-108">Attributes</span></span>  
  
|<span data-ttu-id="d09fe-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="d09fe-109">Attribute</span></span>|<span data-ttu-id="d09fe-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="d09fe-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d09fe-111">allowedAudienceUri</span><span class="sxs-lookup"><span data-stu-id="d09fe-111">allowedAudienceUri</span></span>|<span data-ttu-id="d09fe-112">Cadena que contiene un URI de destino para el que el token de seguridad <xref:System.IdentityModel.Tokens.SamlSecurityToken> se puede destinar con el fin de que una instancia de <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> lo considere válido.</span><span class="sxs-lookup"><span data-stu-id="d09fe-112">A string that contains a target Uri for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d09fe-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d09fe-113">Child Elements</span></span>  

 <span data-ttu-id="d09fe-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="d09fe-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d09fe-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d09fe-115">Parent Elements</span></span>  
  
|<span data-ttu-id="d09fe-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="d09fe-116">Element</span></span>|<span data-ttu-id="d09fe-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="d09fe-117">Description</span></span>|  
|-------------|-----------------|  
|[\<allowedAudienceUris>](allowedaudienceuris.md)|<span data-ttu-id="d09fe-118">Representa una colección de los URI de destino para los que el token de seguridad <xref:System.IdentityModel.Tokens.SamlSecurityToken> se puede destinar con el fin de que una instancia de <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> lo considere válido.</span><span class="sxs-lookup"><span data-stu-id="d09fe-118">Represents a collection of target URIs for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d09fe-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d09fe-119">Remarks</span></span>  

 <span data-ttu-id="d09fe-120">Debería utilizar esta colección en una aplicación federada que utilice un servicio de token seguro (STS) que emita tokens de seguridad <xref:System.IdentityModel.Tokens.SamlSecurityToken>.</span><span class="sxs-lookup"><span data-stu-id="d09fe-120">You should use this collection in a federated application that utilizes a security token service (STS) that issues <xref:System.IdentityModel.Tokens.SamlSecurityToken> security tokens.</span></span> <span data-ttu-id="d09fe-121">Cuando el STS emite el token de seguridad, puede especificar el URI de los servicios Web para el que está dirigido el token de seguridad mediante la agregación de una <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> al token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="d09fe-121">When the STS issues the security token, it can specify the URI of the Web services for which the security token is intended by adding a <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> to the security token.</span></span> <span data-ttu-id="d09fe-122">Eso le permite al <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> del servicio Web del destinatario comprobar que el token de seguridad emitido está dirigido a este servicio Web especificando que esta comprobación debería tener lugar haciendo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d09fe-122">That allows the <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> for the recipient Web service to verify that the issued security token is intended for this Web service by specifying that this check should happen by doing the following:</span></span>  
  
- <span data-ttu-id="d09fe-123">Establezca el atributo `audienceUriMode` de `<issuedTokenAuthentication>` en <xref:System.IdentityModel.Selectors.AudienceUriMode.Always> o <xref:System.IdentityModel.Selectors.AudienceUriMode.BearerKeyOnly>.</span><span class="sxs-lookup"><span data-stu-id="d09fe-123">Set the `audienceUriMode` attribute of `<issuedTokenAuthentication>` to <xref:System.IdentityModel.Selectors.AudienceUriMode.Always> or <xref:System.IdentityModel.Selectors.AudienceUriMode.BearerKeyOnly>.</span></span>  
  
- <span data-ttu-id="d09fe-124">Especifique el conjunto de identificadores URI válidos, agregando los URI a esta colección.</span><span class="sxs-lookup"><span data-stu-id="d09fe-124">Specify the set of valid URIs, by adding the URIs to this collection.</span></span>  
  
 <span data-ttu-id="d09fe-125">Para obtener más información, vea <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span><span class="sxs-lookup"><span data-stu-id="d09fe-125">For more information, see <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span></span>  
  
 <span data-ttu-id="d09fe-126">Para obtener más información sobre el uso de este elemento de configuración, consulte [Cómo: configurar credenciales en un servicio de Federación](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span><span class="sxs-lookup"><span data-stu-id="d09fe-126">For more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d09fe-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="d09fe-127">See also</span></span>

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.AllowedAudienceUris%2A>
- <xref:System.ServiceModel.Configuration.AllowedAudienceUriElementCollection>
- <xref:System.ServiceModel.Configuration.AllowedAudienceUriElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.AllowedAudienceUris%2A>
- [\<allowedAudienceUris>](allowedaudienceuris.md)
- [\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md)
- [<span data-ttu-id="d09fe-128">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="d09fe-128">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="d09fe-129">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="d09fe-129">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="d09fe-130">Procedimiento para configurar las credenciales en un servicio de federación</span><span class="sxs-lookup"><span data-stu-id="d09fe-130">How to: Configure Credentials on a Federation Service</span></span>](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
