---
title: <audienceUris>
ms.date: 03/30/2017
ms.assetid: 7a3d8515-d756-4afe-a22d-07cbe2217ee3
author: BrucePerlerMS
ms.openlocfilehash: 003221ed4dc7f4ccf72d2e0d3a91265e13172813
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941953"
---
# <a name="audienceuris"></a><span data-ttu-id="b8cb1-101">\<audienceUris></span><span class="sxs-lookup"><span data-stu-id="b8cb1-101">\<audienceUris></span></span>
<span data-ttu-id="b8cb1-102">Especifica el conjunto de URI que son identificadores aceptables del usuario de confianza (RP).</span><span class="sxs-lookup"><span data-stu-id="b8cb1-102">Specifies the set of URIs that are acceptable identifiers of the relying party (RP).</span></span> <span data-ttu-id="b8cb1-103">No se aceptarán tokens a menos que estén en el ámbito de uno de los URI de audiencia permitidos.</span><span class="sxs-lookup"><span data-stu-id="b8cb1-103">Tokens will not be accepted unless they are scoped for one of the allowed audience URIs.</span></span>  
  
 <span data-ttu-id="b8cb1-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="b8cb1-104">\<system.identityModel></span></span>  
<span data-ttu-id="b8cb1-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="b8cb1-105">\<identityConfiguration></span></span>  
<span data-ttu-id="b8cb1-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="b8cb1-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="b8cb1-107">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="b8cb1-107">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="b8cb1-108">\<audienceUris></span><span class="sxs-lookup"><span data-stu-id="b8cb1-108">\<audienceUris></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8cb1-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b8cb1-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b8cb1-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b8cb1-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b8cb1-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b8cb1-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b8cb1-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="b8cb1-112">Attributes</span></span>  
  
|<span data-ttu-id="b8cb1-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="b8cb1-113">Attribute</span></span>|<span data-ttu-id="b8cb1-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="b8cb1-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b8cb1-115">modo</span><span class="sxs-lookup"><span data-stu-id="b8cb1-115">mode</span></span>|<span data-ttu-id="b8cb1-116"><xref:System.IdentityModel.Selectors.AudienceUriMode> Valor que especifica si la restricción de audiencia debe aplicarse a un token de entrada.</span><span class="sxs-lookup"><span data-stu-id="b8cb1-116">An <xref:System.IdentityModel.Selectors.AudienceUriMode> value that specifies whether the audience restriction should be applied to an incoming token.</span></span> <span data-ttu-id="b8cb1-117">Los valores posibles son "always", "Never" y "BearerKeyOnly".</span><span class="sxs-lookup"><span data-stu-id="b8cb1-117">The possible values are "Always", "Never", and "BearerKeyOnly".</span></span> <span data-ttu-id="b8cb1-118">El valor predeterminado es "always".</span><span class="sxs-lookup"><span data-stu-id="b8cb1-118">The default is "Always".</span></span> <span data-ttu-id="b8cb1-119">Opcional.</span><span class="sxs-lookup"><span data-stu-id="b8cb1-119">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b8cb1-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b8cb1-120">Child Elements</span></span>  
  
|<span data-ttu-id="b8cb1-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="b8cb1-121">Element</span></span>|<span data-ttu-id="b8cb1-122">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="b8cb1-122">Description</span></span>|  
|-------------|-----------------|  
|`<add value=xs:string>`|<span data-ttu-id="b8cb1-123">Agrega el URI especificado por el `value` atributo a la colección audienceUris.</span><span class="sxs-lookup"><span data-stu-id="b8cb1-123">Adds the URI specified by the `value` attribute to the audienceUris collection.</span></span> <span data-ttu-id="b8cb1-124">El atributo `value` es necesario.</span><span class="sxs-lookup"><span data-stu-id="b8cb1-124">The `value` attribute is required.</span></span> <span data-ttu-id="b8cb1-125">El URI distingue entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="b8cb1-125">The URI is case-sensitive.</span></span>|  
|`<clear>`|<span data-ttu-id="b8cb1-126">Borra la colección audienceUris.</span><span class="sxs-lookup"><span data-stu-id="b8cb1-126">Clears the audienceUris collection.</span></span> <span data-ttu-id="b8cb1-127">Todos los identificadores se quitan de la colección.</span><span class="sxs-lookup"><span data-stu-id="b8cb1-127">All identifiers are removed from the collection.</span></span>|  
|`<remove value=xs:string>`|<span data-ttu-id="b8cb1-128">Quita el URI especificado por el `value` atributo de la colección audienceUris.</span><span class="sxs-lookup"><span data-stu-id="b8cb1-128">Removes the URI specified by the `value` attribute from the audienceUris collection.</span></span> <span data-ttu-id="b8cb1-129">El atributo `value` es necesario.</span><span class="sxs-lookup"><span data-stu-id="b8cb1-129">The `value` attribute is required.</span></span> <span data-ttu-id="b8cb1-130">El URI distingue entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="b8cb1-130">The URI is case-sensitive.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b8cb1-131">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b8cb1-131">Parent Elements</span></span>  
  
|<span data-ttu-id="b8cb1-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="b8cb1-132">Element</span></span>|<span data-ttu-id="b8cb1-133">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="b8cb1-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b8cb1-134">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="b8cb1-134">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="b8cb1-135">Proporciona la configuración para una colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="b8cb1-135">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b8cb1-136">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b8cb1-136">Remarks</span></span>  
 <span data-ttu-id="b8cb1-137">De forma predeterminada, la colección está vacía; Use `<add>`los `<clear>`elementos, `<remove>` y para modificar la colección.</span><span class="sxs-lookup"><span data-stu-id="b8cb1-137">By default, the collection is empty; use `<add>`, `<clear>`, and `<remove>` elements to modify the collection.</span></span> <span data-ttu-id="b8cb1-138"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>los <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> objetos y usan los valores de la colección de URI de audiencia para configurar las restricciones de <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> URI de audiencia permitidas en los objetos.</span><span class="sxs-lookup"><span data-stu-id="b8cb1-138"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> and <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> objects use the values in the audience URI collection to configure any allowed audience URI restrictions in <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> objects.</span></span>  
  
 <span data-ttu-id="b8cb1-139">El elemento se representa mediante la <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> clase. `<audienceUris>`</span><span class="sxs-lookup"><span data-stu-id="b8cb1-139">The `<audienceUris>` element is represented by the <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> class.</span></span> <span data-ttu-id="b8cb1-140">Una dirección URI individual agregada a la colección se representa <xref:System.IdentityModel.Configuration.AudienceUriElement> mediante la clase.</span><span class="sxs-lookup"><span data-stu-id="b8cb1-140">An individual URI added to the collection is represented by the <xref:System.IdentityModel.Configuration.AudienceUriElement> class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b8cb1-141">El uso del `<audienceUris>` elemento como elemento secundario [ \<del elemento > identityConfiguration](identityconfiguration.md) está en desuso, pero todavía se admite por compatibilidad con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="b8cb1-141">The use of the `<audienceUris>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="b8cb1-142">La `<securityTokenHandlerConfiguration>` configuración del elemento invalida la `<identityConfiguration>` del elemento.</span><span class="sxs-lookup"><span data-stu-id="b8cb1-142">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8cb1-143">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b8cb1-143">Example</span></span>  
 <span data-ttu-id="b8cb1-144">El siguiente XML muestra cómo configurar los URI de audiencia aceptables para una aplicación.</span><span class="sxs-lookup"><span data-stu-id="b8cb1-144">The following XML shows how to configure the acceptable audience URIs for an application.</span></span> <span data-ttu-id="b8cb1-145">En este ejemplo se configura un URI único.</span><span class="sxs-lookup"><span data-stu-id="b8cb1-145">This example configures a single URI.</span></span> <span data-ttu-id="b8cb1-146">Se aceptarán los tokens con ámbito para este URI; se rechazarán todos los demás.</span><span class="sxs-lookup"><span data-stu-id="b8cb1-146">Tokens scoped for this URI will be accepted, all others will be rejected.</span></span>  
  
```xml  
<audienceUris>  
  <add value="http://localhost:19851/"/>  
</audienceUris>  
```
