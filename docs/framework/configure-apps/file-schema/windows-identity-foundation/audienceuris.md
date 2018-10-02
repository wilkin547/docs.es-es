---
title: '&lt;audienceUris&gt;'
ms.date: 03/30/2017
ms.assetid: 7a3d8515-d756-4afe-a22d-07cbe2217ee3
author: BrucePerlerMS
ms.openlocfilehash: af138a4da49a48ed43e1bc8f2c2c81c56892feed
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2018
ms.locfileid: "48034485"
---
# <a name="ltaudienceurisgt"></a><span data-ttu-id="47668-102">&lt;audienceUris&gt;</span><span class="sxs-lookup"><span data-stu-id="47668-102">&lt;audienceUris&gt;</span></span>
<span data-ttu-id="47668-103">Especifica el conjunto de URI que son aceptables identificadores del usuario de confianza (RP).</span><span class="sxs-lookup"><span data-stu-id="47668-103">Specifies the set of URIs that are acceptable identifiers of the relying party (RP).</span></span> <span data-ttu-id="47668-104">No se aceptarán tokens a menos que tengan el ámbito de uno de lo URI de público permitido.</span><span class="sxs-lookup"><span data-stu-id="47668-104">Tokens will not be accepted unless they are scoped for one of the allowed audience URIs.</span></span>  
  
 <span data-ttu-id="47668-105">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="47668-105">\<system.identityModel></span></span>  
<span data-ttu-id="47668-106">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="47668-106">\<identityConfiguration></span></span>  
<span data-ttu-id="47668-107">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="47668-107">\<securityTokenHandlers></span></span>  
<span data-ttu-id="47668-108">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="47668-108">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="47668-109">\<audienceUris ></span><span class="sxs-lookup"><span data-stu-id="47668-109">\<audienceUris></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47668-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="47668-110">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <audienceUris mode=xs:string>  
          <add value=xs:string />  
          <clear />  
          <remove value=xs:string />  
        </audienceUris>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="47668-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="47668-111">Attributes and Elements</span></span>  
 <span data-ttu-id="47668-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="47668-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="47668-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="47668-113">Attributes</span></span>  
  
|<span data-ttu-id="47668-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="47668-114">Attribute</span></span>|<span data-ttu-id="47668-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="47668-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="47668-116">modo</span><span class="sxs-lookup"><span data-stu-id="47668-116">mode</span></span>|<span data-ttu-id="47668-117">Un <xref:System.IdentityModel.Selectors.AudienceUriMode> valor que especifica si se debe aplicar la restricción de audiencia para un token entrante.</span><span class="sxs-lookup"><span data-stu-id="47668-117">An <xref:System.IdentityModel.Selectors.AudienceUriMode> value that specifies whether the audience restriction should be applied to an incoming token.</span></span> <span data-ttu-id="47668-118">Los valores posibles son "Siempre", "Nunca" y "BearerKeyOnly".</span><span class="sxs-lookup"><span data-stu-id="47668-118">The possible values are "Always", "Never", and "BearerKeyOnly".</span></span> <span data-ttu-id="47668-119">El valor predeterminado es "Siempre".</span><span class="sxs-lookup"><span data-stu-id="47668-119">The default is "Always".</span></span> <span data-ttu-id="47668-120">Opcional.</span><span class="sxs-lookup"><span data-stu-id="47668-120">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="47668-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="47668-121">Child Elements</span></span>  
  
|<span data-ttu-id="47668-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="47668-122">Element</span></span>|<span data-ttu-id="47668-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="47668-123">Description</span></span>|  
|-------------|-----------------|  
|`<add value=xs:string>`|<span data-ttu-id="47668-124">Agrega el URI especificado por el `value` atributo a la colección de audienceUris.</span><span class="sxs-lookup"><span data-stu-id="47668-124">Adds the URI specified by the `value` attribute to the audienceUris collection.</span></span> <span data-ttu-id="47668-125">El atributo `value` es necesario.</span><span class="sxs-lookup"><span data-stu-id="47668-125">The `value` attribute is required.</span></span> <span data-ttu-id="47668-126">El URI distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="47668-126">The URI is case-sensitive.</span></span>|  
|`<clear>`|<span data-ttu-id="47668-127">Borra la colección de audienceUris.</span><span class="sxs-lookup"><span data-stu-id="47668-127">Clears the audienceUris collection.</span></span> <span data-ttu-id="47668-128">Se quitan todos los identificadores de la colección.</span><span class="sxs-lookup"><span data-stu-id="47668-128">All identifiers are removed from the collection.</span></span>|  
|`<remove value=xs:string>`|<span data-ttu-id="47668-129">Quita el URI especificado por el `value` atributo de la colección de audienceUris.</span><span class="sxs-lookup"><span data-stu-id="47668-129">Removes the URI specified by the `value` attribute from the audienceUris collection.</span></span> <span data-ttu-id="47668-130">El atributo `value` es necesario.</span><span class="sxs-lookup"><span data-stu-id="47668-130">The `value` attribute is required.</span></span> <span data-ttu-id="47668-131">El URI distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="47668-131">The URI is case-sensitive.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="47668-132">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="47668-132">Parent Elements</span></span>  
  
|<span data-ttu-id="47668-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="47668-133">Element</span></span>|<span data-ttu-id="47668-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="47668-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="47668-135">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="47668-135">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="47668-136">Proporciona la configuración para una colección de seguridad controladores de token.</span><span class="sxs-lookup"><span data-stu-id="47668-136">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="47668-137">Comentarios</span><span class="sxs-lookup"><span data-stu-id="47668-137">Remarks</span></span>  
 <span data-ttu-id="47668-138">De forma predeterminada, la colección está vacía; usar `<add>`, `<clear>`, y `<remove>` elementos para modificar la colección.</span><span class="sxs-lookup"><span data-stu-id="47668-138">By default, the collection is empty; use `<add>`, `<clear>`, and `<remove>` elements to modify the collection.</span></span> <span data-ttu-id="47668-139"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> y <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> por los objetos de los valores de la colección de URI de audiencia para configurar cualquiera permiten audiencia las restricciones de URI en <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> objetos.</span><span class="sxs-lookup"><span data-stu-id="47668-139"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> and <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> objects use the values in the audience URI collection to configure any allowed audience URI restrictions in <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> objects.</span></span>  
  
 <span data-ttu-id="47668-140">El `<audienceUris>` elemento representado por la <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> clase.</span><span class="sxs-lookup"><span data-stu-id="47668-140">The `<audienceUris>` element is represented by the <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> class.</span></span> <span data-ttu-id="47668-141">Un URI individual agregado a la colección representado por el <xref:System.IdentityModel.Configuration.AudienceUriElement> clase.</span><span class="sxs-lookup"><span data-stu-id="47668-141">An individual URI added to the collection is represented by the <xref:System.IdentityModel.Configuration.AudienceUriElement> class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="47668-142">El uso de la `<audienceUris>` como un elemento secundario de la [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento en desuso, pero todavía se admite por compatibilidad con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="47668-142">The use of the `<audienceUris>` element as a child element of the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="47668-143">Configuración de la `<securityTokenHandlerConfiguration>` elemento invalidan aquellas establecidas en el `<identityConfiguration>` elemento.</span><span class="sxs-lookup"><span data-stu-id="47668-143">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="47668-144">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="47668-144">Example</span></span>  
 <span data-ttu-id="47668-145">El siguiente XML muestra cómo configurar el URI de audiencia aceptables para una aplicación.</span><span class="sxs-lookup"><span data-stu-id="47668-145">The following XML shows how to configure the acceptable audience URIs for an application.</span></span> <span data-ttu-id="47668-146">Este ejemplo configura un URI único.</span><span class="sxs-lookup"><span data-stu-id="47668-146">This example configures a single URI.</span></span> <span data-ttu-id="47668-147">Se aceptarán tokens con ámbito de este identificador URI, se rechazarán todas las demás.</span><span class="sxs-lookup"><span data-stu-id="47668-147">Tokens scoped for this URI will be accepted, all others will be rejected.</span></span>  
  
```xml  
<audienceUris>  
  <add value="http://localhost:19851/"/>  
</audienceUris>  
```
