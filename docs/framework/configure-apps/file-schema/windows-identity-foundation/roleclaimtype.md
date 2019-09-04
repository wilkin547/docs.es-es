---
title: <roleClaimType>
ms.date: 03/30/2017
ms.assetid: 69a49deb-6369-41ba-806b-ae8d21fac64b
author: BrucePerlerMS
ms.openlocfilehash: 0f651377346b1f14a4226128cd5cf7059543adca
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251910"
---
# <a name="roleclaimtype"></a><span data-ttu-id="b89cc-101">\<roleClaimType></span><span class="sxs-lookup"><span data-stu-id="b89cc-101">\<roleClaimType></span></span>
<span data-ttu-id="b89cc-102">Especifica el tipo de notificación que define las notificaciones de tipo de rol <xref:System.Security.Claims.ClaimsIdentity> en la colección de <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> objetos devuelta por el método del controlador de token.</span><span class="sxs-lookup"><span data-stu-id="b89cc-102">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>  
  
<span data-ttu-id="b89cc-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b89cc-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b89cc-104">&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="b89cc-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="b89cc-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identityConfiguration**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="b89cc-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="b89cc-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> securityTokenHandlers**](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="b89cc-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="b89cc-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Agregar >** ](add.md)</span><span class="sxs-lookup"><span data-stu-id="b89cc-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)</span></span>\
<span data-ttu-id="b89cc-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> samlSecurityTokenRequirement**](samlsecuritytokenrequirement.md)</span><span class="sxs-lookup"><span data-stu-id="b89cc-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<samlSecurityTokenRequirement>**](samlsecuritytokenrequirement.md)</span></span>\
<span data-ttu-id="b89cc-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> roleClaimType**</span><span class="sxs-lookup"><span data-stu-id="b89cc-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<roleClaimType>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b89cc-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b89cc-110">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add>  
        <samlSecurityTokenRequirement>  
          <roleClaimType value=xs:string>  
          </roleClaimType>  
        </samlSecurityTokenRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b89cc-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b89cc-111">Attributes and Elements</span></span>  
 <span data-ttu-id="b89cc-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b89cc-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b89cc-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="b89cc-113">Attributes</span></span>  
  
|<span data-ttu-id="b89cc-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="b89cc-114">Attribute</span></span>|<span data-ttu-id="b89cc-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="b89cc-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b89cc-116">valor</span><span class="sxs-lookup"><span data-stu-id="b89cc-116">value</span></span>|<span data-ttu-id="b89cc-117">Una cadena que especifica el URI que representa el tipo de demanda de la demanda que se va a usar para el tipo de notificaciones de rol.</span><span class="sxs-lookup"><span data-stu-id="b89cc-117">A string that specifies the URI that represents the claim type of the claim to use for the role claim type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b89cc-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b89cc-118">Child Elements</span></span>  
 <span data-ttu-id="b89cc-119">None</span><span class="sxs-lookup"><span data-stu-id="b89cc-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b89cc-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b89cc-120">Parent Elements</span></span>  
  
|<span data-ttu-id="b89cc-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="b89cc-121">Element</span></span>|<span data-ttu-id="b89cc-122">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="b89cc-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b89cc-123">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="b89cc-123">\<samlSecurityTokenRequirement></span></span>](samlsecuritytokenrequirement.md)|<span data-ttu-id="b89cc-124">Proporciona la configuración para <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> la clase, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> la clase o una clase derivada de cualquiera de estas clases.</span><span class="sxs-lookup"><span data-stu-id="b89cc-124">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b89cc-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b89cc-125">Remarks</span></span>  
 <span data-ttu-id="b89cc-126">El `<roleClaimType>` elemento establece la <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> propiedad cuando se <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> Inicializa un objeto a partir de la configuración.</span><span class="sxs-lookup"><span data-stu-id="b89cc-126">The `<roleClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b89cc-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b89cc-127">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <roleClaimType value="schemas.microsoft.com/ws/2006/04/identity/claims/role" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b89cc-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="b89cc-128">See also</span></span>

- <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A>
