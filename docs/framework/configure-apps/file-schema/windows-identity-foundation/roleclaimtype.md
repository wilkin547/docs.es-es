---
title: '&lt;roleClaimType&gt;'
ms.date: 03/30/2017
ms.assetid: 69a49deb-6369-41ba-806b-ae8d21fac64b
author: BrucePerlerMS
ms.openlocfilehash: 6114a95f3942c367849785ce981858f276c0b8fc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54599951"
---
# <a name="ltroleclaimtypegt"></a><span data-ttu-id="480f2-102">&lt;roleClaimType&gt;</span><span class="sxs-lookup"><span data-stu-id="480f2-102">&lt;roleClaimType&gt;</span></span>
<span data-ttu-id="480f2-103">Especifica el tipo de notificación que define las notificaciones de tipo de rol en la colección de <xref:System.Security.Claims.ClaimsIdentity> los objetos devueltos por la <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> método del controlador de token.</span><span class="sxs-lookup"><span data-stu-id="480f2-103">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>  
  
 <span data-ttu-id="480f2-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="480f2-104">\<system.identityModel></span></span>  
<span data-ttu-id="480f2-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="480f2-105">\<identityConfiguration></span></span>  
<span data-ttu-id="480f2-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="480f2-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="480f2-107">\<add></span><span class="sxs-lookup"><span data-stu-id="480f2-107">\<add></span></span>  
<span data-ttu-id="480f2-108">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="480f2-108">\<samlSecurityTokenRequirement></span></span>  
<span data-ttu-id="480f2-109">\<roleClaimType></span><span class="sxs-lookup"><span data-stu-id="480f2-109">\<roleClaimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="480f2-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="480f2-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="480f2-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="480f2-111">Attributes and Elements</span></span>  
 <span data-ttu-id="480f2-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="480f2-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="480f2-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="480f2-113">Attributes</span></span>  
  
|<span data-ttu-id="480f2-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="480f2-114">Attribute</span></span>|<span data-ttu-id="480f2-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="480f2-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="480f2-116">value</span><span class="sxs-lookup"><span data-stu-id="480f2-116">value</span></span>|<span data-ttu-id="480f2-117">Una cadena que especifica el URI que representa el tipo de notificación de la notificación que se usará para el tipo de notificación de rol.</span><span class="sxs-lookup"><span data-stu-id="480f2-117">A string that specifies the URI that represents the claim type of the claim to use for the role claim type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="480f2-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="480f2-118">Child Elements</span></span>  
 <span data-ttu-id="480f2-119">Ninguna</span><span class="sxs-lookup"><span data-stu-id="480f2-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="480f2-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="480f2-120">Parent Elements</span></span>  
  
|<span data-ttu-id="480f2-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="480f2-121">Element</span></span>|<span data-ttu-id="480f2-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="480f2-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="480f2-123">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="480f2-123">\<samlSecurityTokenRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|<span data-ttu-id="480f2-124">Proporciona la configuración de la <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> (clase), el <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> clase o una clase derivada de cualquiera de estas clases.</span><span class="sxs-lookup"><span data-stu-id="480f2-124">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="480f2-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="480f2-125">Remarks</span></span>  
 <span data-ttu-id="480f2-126">El `<roleClaimType>` conjuntos de elementos del <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> propiedad cuando un <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> se inicializa el objeto de configuración.</span><span class="sxs-lookup"><span data-stu-id="480f2-126">The `<roleClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="480f2-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="480f2-127">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <roleClaimType value="schemas.microsoft.com/ws/2006/04/identity/claims/role" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="480f2-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="480f2-128">See also</span></span>
- <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A>
