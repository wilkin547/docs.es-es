---
title: <audienceUris>
ms.date: 03/30/2017
ms.assetid: 7a3d8515-d756-4afe-a22d-07cbe2217ee3
author: BrucePerlerMS
ms.openlocfilehash: bd04e4ebdf5c58adaeea0ff0ca5993d7d9ce38f1
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252167"
---
# <a name="audienceuris"></a><span data-ttu-id="bf7e8-101">\<audienceUris></span><span class="sxs-lookup"><span data-stu-id="bf7e8-101">\<audienceUris></span></span>
<span data-ttu-id="bf7e8-102">Especifica el conjunto de URI que son identificadores aceptables del usuario de confianza (RP).</span><span class="sxs-lookup"><span data-stu-id="bf7e8-102">Specifies the set of URIs that are acceptable identifiers of the relying party (RP).</span></span> <span data-ttu-id="bf7e8-103">No se aceptarán tokens a menos que estén en el ámbito de uno de los URI de audiencia permitidos.</span><span class="sxs-lookup"><span data-stu-id="bf7e8-103">Tokens will not be accepted unless they are scoped for one of the allowed audience URIs.</span></span>  
  
<span data-ttu-id="bf7e8-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="bf7e8-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="bf7e8-105">&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="bf7e8-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="bf7e8-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identityConfiguration**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="bf7e8-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="bf7e8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> securityTokenHandlers**](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="bf7e8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="bf7e8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> securityTokenHandlerConfiguration**](securitytokenhandlerconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="bf7e8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)</span></span>\
<span data-ttu-id="bf7e8-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> audienceUris**</span><span class="sxs-lookup"><span data-stu-id="bf7e8-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<audienceUris>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf7e8-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bf7e8-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bf7e8-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="bf7e8-111">Attributes and Elements</span></span>  
 <span data-ttu-id="bf7e8-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="bf7e8-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bf7e8-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="bf7e8-113">Attributes</span></span>  
  
|<span data-ttu-id="bf7e8-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="bf7e8-114">Attribute</span></span>|<span data-ttu-id="bf7e8-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="bf7e8-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bf7e8-116">modo</span><span class="sxs-lookup"><span data-stu-id="bf7e8-116">mode</span></span>|<span data-ttu-id="bf7e8-117"><xref:System.IdentityModel.Selectors.AudienceUriMode> Valor que especifica si la restricción de audiencia debe aplicarse a un token de entrada.</span><span class="sxs-lookup"><span data-stu-id="bf7e8-117">An <xref:System.IdentityModel.Selectors.AudienceUriMode> value that specifies whether the audience restriction should be applied to an incoming token.</span></span> <span data-ttu-id="bf7e8-118">Los valores posibles son "always", "Never" y "BearerKeyOnly".</span><span class="sxs-lookup"><span data-stu-id="bf7e8-118">The possible values are "Always", "Never", and "BearerKeyOnly".</span></span> <span data-ttu-id="bf7e8-119">El valor predeterminado es "always".</span><span class="sxs-lookup"><span data-stu-id="bf7e8-119">The default is "Always".</span></span> <span data-ttu-id="bf7e8-120">Opcional.</span><span class="sxs-lookup"><span data-stu-id="bf7e8-120">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bf7e8-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="bf7e8-121">Child Elements</span></span>  
  
|<span data-ttu-id="bf7e8-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="bf7e8-122">Element</span></span>|<span data-ttu-id="bf7e8-123">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="bf7e8-123">Description</span></span>|  
|-------------|-----------------|  
|`<add value=xs:string>`|<span data-ttu-id="bf7e8-124">Agrega el URI especificado por el `value` atributo a la colección audienceUris.</span><span class="sxs-lookup"><span data-stu-id="bf7e8-124">Adds the URI specified by the `value` attribute to the audienceUris collection.</span></span> <span data-ttu-id="bf7e8-125">El atributo `value` es necesario.</span><span class="sxs-lookup"><span data-stu-id="bf7e8-125">The `value` attribute is required.</span></span> <span data-ttu-id="bf7e8-126">El URI distingue entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="bf7e8-126">The URI is case-sensitive.</span></span>|  
|`<clear>`|<span data-ttu-id="bf7e8-127">Borra la colección audienceUris.</span><span class="sxs-lookup"><span data-stu-id="bf7e8-127">Clears the audienceUris collection.</span></span> <span data-ttu-id="bf7e8-128">Todos los identificadores se quitan de la colección.</span><span class="sxs-lookup"><span data-stu-id="bf7e8-128">All identifiers are removed from the collection.</span></span>|  
|`<remove value=xs:string>`|<span data-ttu-id="bf7e8-129">Quita el URI especificado por el `value` atributo de la colección audienceUris.</span><span class="sxs-lookup"><span data-stu-id="bf7e8-129">Removes the URI specified by the `value` attribute from the audienceUris collection.</span></span> <span data-ttu-id="bf7e8-130">El atributo `value` es necesario.</span><span class="sxs-lookup"><span data-stu-id="bf7e8-130">The `value` attribute is required.</span></span> <span data-ttu-id="bf7e8-131">El URI distingue entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="bf7e8-131">The URI is case-sensitive.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bf7e8-132">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="bf7e8-132">Parent Elements</span></span>  
  
|<span data-ttu-id="bf7e8-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="bf7e8-133">Element</span></span>|<span data-ttu-id="bf7e8-134">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="bf7e8-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bf7e8-135">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="bf7e8-135">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="bf7e8-136">Proporciona la configuración para una colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="bf7e8-136">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bf7e8-137">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bf7e8-137">Remarks</span></span>  
 <span data-ttu-id="bf7e8-138">De forma predeterminada, la colección está vacía; Use `<add>`los `<clear>`elementos, `<remove>` y para modificar la colección.</span><span class="sxs-lookup"><span data-stu-id="bf7e8-138">By default, the collection is empty; use `<add>`, `<clear>`, and `<remove>` elements to modify the collection.</span></span> <span data-ttu-id="bf7e8-139"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>los <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> objetos y usan los valores de la colección de URI de audiencia para configurar las restricciones de <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> URI de audiencia permitidas en los objetos.</span><span class="sxs-lookup"><span data-stu-id="bf7e8-139"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> and <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> objects use the values in the audience URI collection to configure any allowed audience URI restrictions in <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> objects.</span></span>  
  
 <span data-ttu-id="bf7e8-140">El elemento se representa mediante la <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> clase. `<audienceUris>`</span><span class="sxs-lookup"><span data-stu-id="bf7e8-140">The `<audienceUris>` element is represented by the <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> class.</span></span> <span data-ttu-id="bf7e8-141">Una dirección URI individual agregada a la colección se representa <xref:System.IdentityModel.Configuration.AudienceUriElement> mediante la clase.</span><span class="sxs-lookup"><span data-stu-id="bf7e8-141">An individual URI added to the collection is represented by the <xref:System.IdentityModel.Configuration.AudienceUriElement> class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bf7e8-142">El uso del `<audienceUris>` elemento como elemento secundario [ \<del elemento > identityConfiguration](identityconfiguration.md) está en desuso, pero todavía se admite por compatibilidad con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="bf7e8-142">The use of the `<audienceUris>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="bf7e8-143">La `<securityTokenHandlerConfiguration>` configuración del elemento invalida la `<identityConfiguration>` del elemento.</span><span class="sxs-lookup"><span data-stu-id="bf7e8-143">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bf7e8-144">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bf7e8-144">Example</span></span>  
 <span data-ttu-id="bf7e8-145">El siguiente XML muestra cómo configurar los URI de audiencia aceptables para una aplicación.</span><span class="sxs-lookup"><span data-stu-id="bf7e8-145">The following XML shows how to configure the acceptable audience URIs for an application.</span></span> <span data-ttu-id="bf7e8-146">En este ejemplo se configura un URI único.</span><span class="sxs-lookup"><span data-stu-id="bf7e8-146">This example configures a single URI.</span></span> <span data-ttu-id="bf7e8-147">Se aceptarán los tokens con ámbito para este URI; se rechazarán todos los demás.</span><span class="sxs-lookup"><span data-stu-id="bf7e8-147">Tokens scoped for this URI will be accepted, all others will be rejected.</span></span>  
  
```xml  
<audienceUris>  
  <add value="http://localhost:19851/"/>  
</audienceUris>  
```
