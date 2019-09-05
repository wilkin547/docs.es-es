---
title: <nameClaimType>
ms.date: 03/30/2017
ms.assetid: 17514d95-f0f5-4789-8e28-346640dc227c
author: BrucePerlerMS
ms.openlocfilehash: 4bf8ad2f70499edfc72dd9fcd9a5d8a0aafbbc66
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251937"
---
# <a name="nameclaimtype"></a><span data-ttu-id="aafa2-101">\<nameClaimType></span><span class="sxs-lookup"><span data-stu-id="aafa2-101">\<nameClaimType></span></span>
<span data-ttu-id="aafa2-102">Establece el tipo de demanda que especifica <xref:System.Security.Principal.IIdentity.Name%2A> la propiedad.</span><span class="sxs-lookup"><span data-stu-id="aafa2-102">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="aafa2-103">El tipo de demanda se usa para buscar un <xref:System.Security.Claims.Claim> en la colección de <xref:System.Security.Claims.ClaimsIdentity> objetos devueltos <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> por el método de este controlador de token.</span><span class="sxs-lookup"><span data-stu-id="aafa2-103">The claim type is used to search for a <xref:System.Security.Claims.Claim> in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of this token handler.</span></span> <span data-ttu-id="aafa2-104">El valor de la demanda coincidente se establece entonces como el nombre del <xref:System.Security.Principal.IIdentity> generado a partir de este controlador de token.</span><span class="sxs-lookup"><span data-stu-id="aafa2-104">The value of the matching claim is then set as the name of the <xref:System.Security.Principal.IIdentity> generated from this token handler.</span></span>  
  
<span data-ttu-id="aafa2-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="aafa2-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="aafa2-106">&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="aafa2-106">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="aafa2-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identityConfiguration**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="aafa2-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="aafa2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> securityTokenHandlers**](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="aafa2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="aafa2-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Agregar >** ](add.md)</span><span class="sxs-lookup"><span data-stu-id="aafa2-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)</span></span>\
<span data-ttu-id="aafa2-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> samlSecurityTokenRequirement**](samlsecuritytokenrequirement.md)</span><span class="sxs-lookup"><span data-stu-id="aafa2-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<samlSecurityTokenRequirement>**](samlsecuritytokenrequirement.md)</span></span>\
<span data-ttu-id="aafa2-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> nameClaimType**</span><span class="sxs-lookup"><span data-stu-id="aafa2-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<nameClaimType>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aafa2-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aafa2-112">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add>  
        <samlSecurityTokenRequirement>  
          <nameClaimType value=xs:string>  
          </nameClaimType>  
        </samlSecurityTokenRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aafa2-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="aafa2-113">Attributes and Elements</span></span>  
 <span data-ttu-id="aafa2-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="aafa2-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aafa2-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="aafa2-115">Attributes</span></span>  
  
|<span data-ttu-id="aafa2-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="aafa2-116">Attribute</span></span>|<span data-ttu-id="aafa2-117">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="aafa2-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="aafa2-118">valor</span><span class="sxs-lookup"><span data-stu-id="aafa2-118">value</span></span>|<span data-ttu-id="aafa2-119">Una cadena que especifica el URI que representa el tipo de demanda de la demanda que se va <xref:System.Security.Principal.IIdentity.Name%2A> a usar para la propiedad.</span><span class="sxs-lookup"><span data-stu-id="aafa2-119">A string that specifies the URI that represents the claim type of the claim to use for the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="aafa2-120">Necesario.</span><span class="sxs-lookup"><span data-stu-id="aafa2-120">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="aafa2-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="aafa2-121">Child Elements</span></span>  
 <span data-ttu-id="aafa2-122">None</span><span class="sxs-lookup"><span data-stu-id="aafa2-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="aafa2-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="aafa2-123">Parent Elements</span></span>  
  
|<span data-ttu-id="aafa2-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="aafa2-124">Element</span></span>|<span data-ttu-id="aafa2-125">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="aafa2-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aafa2-126">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="aafa2-126">\<samlSecurityTokenRequirement></span></span>](samlsecuritytokenrequirement.md)|<span data-ttu-id="aafa2-127">Proporciona la configuración para <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> la clase, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> la clase o una clase derivada de cualquiera de estas clases.</span><span class="sxs-lookup"><span data-stu-id="aafa2-127">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aafa2-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="aafa2-128">Remarks</span></span>  
 <span data-ttu-id="aafa2-129">El `<nameClaimType>` elemento establece la <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> propiedad cuando se <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> Inicializa un objeto a partir de la configuración.</span><span class="sxs-lookup"><span data-stu-id="aafa2-129">The `<nameClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aafa2-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="aafa2-130">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <nameClaimType value="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="aafa2-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="aafa2-131">See also</span></span>

- <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A>
