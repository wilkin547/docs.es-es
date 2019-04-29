---
title: <audienceUris>
ms.date: 03/30/2017
ms.assetid: 7a3d8515-d756-4afe-a22d-07cbe2217ee3
author: BrucePerlerMS
ms.openlocfilehash: 556c444d5e48e27036c4b49338f6e70de7ef5c5d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61750753"
---
# <a name="audienceuris"></a><span data-ttu-id="cae5f-101">\<audienceUris></span><span class="sxs-lookup"><span data-stu-id="cae5f-101">\<audienceUris></span></span>
<span data-ttu-id="cae5f-102">Especifica el conjunto de URI que son aceptables identificadores del usuario de confianza (RP).</span><span class="sxs-lookup"><span data-stu-id="cae5f-102">Specifies the set of URIs that are acceptable identifiers of the relying party (RP).</span></span> <span data-ttu-id="cae5f-103">No se aceptarán tokens a menos que tengan el ámbito de uno de lo URI de público permitido.</span><span class="sxs-lookup"><span data-stu-id="cae5f-103">Tokens will not be accepted unless they are scoped for one of the allowed audience URIs.</span></span>  
  
 <span data-ttu-id="cae5f-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="cae5f-104">\<system.identityModel></span></span>  
<span data-ttu-id="cae5f-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="cae5f-105">\<identityConfiguration></span></span>  
<span data-ttu-id="cae5f-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="cae5f-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="cae5f-107">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="cae5f-107">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="cae5f-108">\<audienceUris></span><span class="sxs-lookup"><span data-stu-id="cae5f-108">\<audienceUris></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cae5f-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cae5f-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cae5f-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="cae5f-110">Attributes and Elements</span></span>  
 <span data-ttu-id="cae5f-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="cae5f-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cae5f-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="cae5f-112">Attributes</span></span>  
  
|<span data-ttu-id="cae5f-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="cae5f-113">Attribute</span></span>|<span data-ttu-id="cae5f-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="cae5f-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cae5f-115">modo</span><span class="sxs-lookup"><span data-stu-id="cae5f-115">mode</span></span>|<span data-ttu-id="cae5f-116">Un <xref:System.IdentityModel.Selectors.AudienceUriMode> valor que especifica si se debe aplicar la restricción de audiencia para un token entrante.</span><span class="sxs-lookup"><span data-stu-id="cae5f-116">An <xref:System.IdentityModel.Selectors.AudienceUriMode> value that specifies whether the audience restriction should be applied to an incoming token.</span></span> <span data-ttu-id="cae5f-117">Los valores posibles son "Siempre", "Nunca" y "BearerKeyOnly".</span><span class="sxs-lookup"><span data-stu-id="cae5f-117">The possible values are "Always", "Never", and "BearerKeyOnly".</span></span> <span data-ttu-id="cae5f-118">El valor predeterminado es "Siempre".</span><span class="sxs-lookup"><span data-stu-id="cae5f-118">The default is "Always".</span></span> <span data-ttu-id="cae5f-119">Opcional.</span><span class="sxs-lookup"><span data-stu-id="cae5f-119">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cae5f-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="cae5f-120">Child Elements</span></span>  
  
|<span data-ttu-id="cae5f-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="cae5f-121">Element</span></span>|<span data-ttu-id="cae5f-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="cae5f-122">Description</span></span>|  
|-------------|-----------------|  
|`<add value=xs:string>`|<span data-ttu-id="cae5f-123">Agrega el URI especificado por el `value` atributo a la colección de audienceUris.</span><span class="sxs-lookup"><span data-stu-id="cae5f-123">Adds the URI specified by the `value` attribute to the audienceUris collection.</span></span> <span data-ttu-id="cae5f-124">El atributo `value` es necesario.</span><span class="sxs-lookup"><span data-stu-id="cae5f-124">The `value` attribute is required.</span></span> <span data-ttu-id="cae5f-125">El URI distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="cae5f-125">The URI is case-sensitive.</span></span>|  
|`<clear>`|<span data-ttu-id="cae5f-126">Borra la colección de audienceUris.</span><span class="sxs-lookup"><span data-stu-id="cae5f-126">Clears the audienceUris collection.</span></span> <span data-ttu-id="cae5f-127">Se quitan todos los identificadores de la colección.</span><span class="sxs-lookup"><span data-stu-id="cae5f-127">All identifiers are removed from the collection.</span></span>|  
|`<remove value=xs:string>`|<span data-ttu-id="cae5f-128">Quita el URI especificado por el `value` atributo de la colección de audienceUris.</span><span class="sxs-lookup"><span data-stu-id="cae5f-128">Removes the URI specified by the `value` attribute from the audienceUris collection.</span></span> <span data-ttu-id="cae5f-129">El atributo `value` es necesario.</span><span class="sxs-lookup"><span data-stu-id="cae5f-129">The `value` attribute is required.</span></span> <span data-ttu-id="cae5f-130">El URI distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="cae5f-130">The URI is case-sensitive.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cae5f-131">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="cae5f-131">Parent Elements</span></span>  
  
|<span data-ttu-id="cae5f-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="cae5f-132">Element</span></span>|<span data-ttu-id="cae5f-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="cae5f-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cae5f-134">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="cae5f-134">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="cae5f-135">Proporciona la configuración para una colección de seguridad controladores de token.</span><span class="sxs-lookup"><span data-stu-id="cae5f-135">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cae5f-136">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cae5f-136">Remarks</span></span>  
 <span data-ttu-id="cae5f-137">De forma predeterminada, la colección está vacía; usar `<add>`, `<clear>`, y `<remove>` elementos para modificar la colección.</span><span class="sxs-lookup"><span data-stu-id="cae5f-137">By default, the collection is empty; use `<add>`, `<clear>`, and `<remove>` elements to modify the collection.</span></span> <span data-ttu-id="cae5f-138"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> y <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> por los objetos de los valores de la colección de URI de audiencia para configurar cualquiera permiten audiencia las restricciones de URI en <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> objetos.</span><span class="sxs-lookup"><span data-stu-id="cae5f-138"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> and <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> objects use the values in the audience URI collection to configure any allowed audience URI restrictions in <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> objects.</span></span>  
  
 <span data-ttu-id="cae5f-139">El `<audienceUris>` elemento representado por la <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> clase.</span><span class="sxs-lookup"><span data-stu-id="cae5f-139">The `<audienceUris>` element is represented by the <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> class.</span></span> <span data-ttu-id="cae5f-140">Un URI individual agregado a la colección representado por el <xref:System.IdentityModel.Configuration.AudienceUriElement> clase.</span><span class="sxs-lookup"><span data-stu-id="cae5f-140">An individual URI added to the collection is represented by the <xref:System.IdentityModel.Configuration.AudienceUriElement> class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cae5f-141">El uso de la `<audienceUris>` como un elemento secundario de la [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento en desuso, pero todavía se admite por compatibilidad con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="cae5f-141">The use of the `<audienceUris>` element as a child element of the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="cae5f-142">Configuración de la `<securityTokenHandlerConfiguration>` elemento invalidan aquellas establecidas en el `<identityConfiguration>` elemento.</span><span class="sxs-lookup"><span data-stu-id="cae5f-142">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cae5f-143">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cae5f-143">Example</span></span>  
 <span data-ttu-id="cae5f-144">El siguiente XML muestra cómo configurar el URI de audiencia aceptables para una aplicación.</span><span class="sxs-lookup"><span data-stu-id="cae5f-144">The following XML shows how to configure the acceptable audience URIs for an application.</span></span> <span data-ttu-id="cae5f-145">Este ejemplo configura un URI único.</span><span class="sxs-lookup"><span data-stu-id="cae5f-145">This example configures a single URI.</span></span> <span data-ttu-id="cae5f-146">Se aceptarán tokens con ámbito de este identificador URI, se rechazarán todas las demás.</span><span class="sxs-lookup"><span data-stu-id="cae5f-146">Tokens scoped for this URI will be accepted, all others will be rejected.</span></span>  
  
```xml  
<audienceUris>  
  <add value="http://localhost:19851/"/>  
</audienceUris>  
```
