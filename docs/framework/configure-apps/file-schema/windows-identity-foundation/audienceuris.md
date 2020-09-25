---
title: <audienceUris>
ms.date: 03/30/2017
ms.assetid: 7a3d8515-d756-4afe-a22d-07cbe2217ee3
author: BrucePerlerMS
ms.openlocfilehash: c9787d8e0d8d66494bbf2dbd0e24ff39178a4cde
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189908"
---
# \<audienceUris>

<span data-ttu-id="e8d78-101">Especifica el conjunto de URI que son identificadores aceptables del usuario de confianza (RP).</span><span class="sxs-lookup"><span data-stu-id="e8d78-101">Specifies the set of URIs that are acceptable identifiers of the relying party (RP).</span></span> <span data-ttu-id="e8d78-102">Los tokens no se aceptarán a menos que se definan sus ámbitos para uno de los URI de público permitido.</span><span class="sxs-lookup"><span data-stu-id="e8d78-102">Tokens will not be accepted unless they are scoped for one of the allowed audience URIs.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<audienceUris>**  
  
## <a name="syntax"></a><span data-ttu-id="e8d78-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e8d78-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e8d78-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e8d78-104">Attributes and Elements</span></span>  

 <span data-ttu-id="e8d78-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e8d78-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e8d78-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="e8d78-106">Attributes</span></span>  
  
|<span data-ttu-id="e8d78-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="e8d78-107">Attribute</span></span>|<span data-ttu-id="e8d78-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="e8d78-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e8d78-109">mode</span><span class="sxs-lookup"><span data-stu-id="e8d78-109">mode</span></span>|<span data-ttu-id="e8d78-110"><xref:System.IdentityModel.Selectors.AudienceUriMode>Valor que especifica si la restricción de audiencia debe aplicarse a un token de entrada.</span><span class="sxs-lookup"><span data-stu-id="e8d78-110">An <xref:System.IdentityModel.Selectors.AudienceUriMode> value that specifies whether the audience restriction should be applied to an incoming token.</span></span> <span data-ttu-id="e8d78-111">Los valores posibles son "always", "Never" y "BearerKeyOnly".</span><span class="sxs-lookup"><span data-stu-id="e8d78-111">The possible values are "Always", "Never", and "BearerKeyOnly".</span></span> <span data-ttu-id="e8d78-112">El valor predeterminado es "always".</span><span class="sxs-lookup"><span data-stu-id="e8d78-112">The default is "Always".</span></span> <span data-ttu-id="e8d78-113">Opcional.</span><span class="sxs-lookup"><span data-stu-id="e8d78-113">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e8d78-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e8d78-114">Child Elements</span></span>  
  
|<span data-ttu-id="e8d78-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="e8d78-115">Element</span></span>|<span data-ttu-id="e8d78-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="e8d78-116">Description</span></span>|  
|-------------|-----------------|  
|`<add value=xs:string>`|<span data-ttu-id="e8d78-117">Agrega el URI especificado por el `value` atributo a la colección audienceUris.</span><span class="sxs-lookup"><span data-stu-id="e8d78-117">Adds the URI specified by the `value` attribute to the audienceUris collection.</span></span> <span data-ttu-id="e8d78-118">El atributo `value` es necesario.</span><span class="sxs-lookup"><span data-stu-id="e8d78-118">The `value` attribute is required.</span></span> <span data-ttu-id="e8d78-119">El URI distingue entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="e8d78-119">The URI is case-sensitive.</span></span>|  
|`<clear>`|<span data-ttu-id="e8d78-120">Borra la colección audienceUris.</span><span class="sxs-lookup"><span data-stu-id="e8d78-120">Clears the audienceUris collection.</span></span> <span data-ttu-id="e8d78-121">Todos los identificadores se quitan de la colección.</span><span class="sxs-lookup"><span data-stu-id="e8d78-121">All identifiers are removed from the collection.</span></span>|  
|`<remove value=xs:string>`|<span data-ttu-id="e8d78-122">Quita el URI especificado por el `value` atributo de la colección audienceUris.</span><span class="sxs-lookup"><span data-stu-id="e8d78-122">Removes the URI specified by the `value` attribute from the audienceUris collection.</span></span> <span data-ttu-id="e8d78-123">El atributo `value` es necesario.</span><span class="sxs-lookup"><span data-stu-id="e8d78-123">The `value` attribute is required.</span></span> <span data-ttu-id="e8d78-124">El URI distingue entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="e8d78-124">The URI is case-sensitive.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e8d78-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e8d78-125">Parent Elements</span></span>  
  
|<span data-ttu-id="e8d78-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="e8d78-126">Element</span></span>|<span data-ttu-id="e8d78-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="e8d78-127">Description</span></span>|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="e8d78-128">Proporciona la configuración para una colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="e8d78-128">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e8d78-129">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e8d78-129">Remarks</span></span>  

 <span data-ttu-id="e8d78-130">De forma predeterminada, la colección está vacía; Use `<add>` `<clear>` `<remove>` los elementos, y para modificar la colección.</span><span class="sxs-lookup"><span data-stu-id="e8d78-130">By default, the collection is empty; use `<add>`, `<clear>`, and `<remove>` elements to modify the collection.</span></span> <span data-ttu-id="e8d78-131"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> los <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> objetos y usan los valores de la colección de URI de audiencia para configurar las restricciones de URI de audiencia permitidas en los <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> objetos.</span><span class="sxs-lookup"><span data-stu-id="e8d78-131"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> and <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> objects use the values in the audience URI collection to configure any allowed audience URI restrictions in <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> objects.</span></span>  
  
 <span data-ttu-id="e8d78-132">El `<audienceUris>` elemento se representa mediante la <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> clase.</span><span class="sxs-lookup"><span data-stu-id="e8d78-132">The `<audienceUris>` element is represented by the <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> class.</span></span> <span data-ttu-id="e8d78-133">Una dirección URI individual agregada a la colección se representa mediante la <xref:System.IdentityModel.Configuration.AudienceUriElement> clase.</span><span class="sxs-lookup"><span data-stu-id="e8d78-133">An individual URI added to the collection is represented by the <xref:System.IdentityModel.Configuration.AudienceUriElement> class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e8d78-134">El uso del `<audienceUris>` elemento como elemento secundario del elemento está en [\<identityConfiguration>](identityconfiguration.md) desuso, pero todavía se admite por compatibilidad con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="e8d78-134">The use of the `<audienceUris>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="e8d78-135">La configuración del `<securityTokenHandlerConfiguration>` elemento invalida la del `<identityConfiguration>` elemento.</span><span class="sxs-lookup"><span data-stu-id="e8d78-135">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e8d78-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e8d78-136">Example</span></span>  

 <span data-ttu-id="e8d78-137">El siguiente XML muestra cómo configurar los URI de audiencia aceptables para una aplicación.</span><span class="sxs-lookup"><span data-stu-id="e8d78-137">The following XML shows how to configure the acceptable audience URIs for an application.</span></span> <span data-ttu-id="e8d78-138">En este ejemplo se configura un URI único.</span><span class="sxs-lookup"><span data-stu-id="e8d78-138">This example configures a single URI.</span></span> <span data-ttu-id="e8d78-139">Se aceptarán los tokens con ámbito para este URI; se rechazarán todos los demás.</span><span class="sxs-lookup"><span data-stu-id="e8d78-139">Tokens scoped for this URI will be accepted, all others will be rejected.</span></span>  
  
```xml  
<audienceUris>  
  <add value="http://localhost:19851/"/>  
</audienceUris>  
```
