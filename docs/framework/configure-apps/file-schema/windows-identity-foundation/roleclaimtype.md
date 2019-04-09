---
title: <roleClaimType>
ms.date: 03/30/2017
ms.assetid: 69a49deb-6369-41ba-806b-ae8d21fac64b
author: BrucePerlerMS
ms.openlocfilehash: 8c7b7c9b42ac72b878aed4e12298dc3655f1e707
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59115601"
---
# <a name="roleclaimtype"></a><span data-ttu-id="d22b5-101">\<roleClaimType></span><span class="sxs-lookup"><span data-stu-id="d22b5-101">\<roleClaimType></span></span>
<span data-ttu-id="d22b5-102">Especifica el tipo de notificación que define las notificaciones de tipo de rol en la colección de <xref:System.Security.Claims.ClaimsIdentity> los objetos devueltos por la <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> método del controlador de token.</span><span class="sxs-lookup"><span data-stu-id="d22b5-102">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>  
  
 <span data-ttu-id="d22b5-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="d22b5-103">\<system.identityModel></span></span>  
<span data-ttu-id="d22b5-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="d22b5-104">\<identityConfiguration></span></span>  
<span data-ttu-id="d22b5-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="d22b5-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="d22b5-106">\<add></span><span class="sxs-lookup"><span data-stu-id="d22b5-106">\<add></span></span>  
<span data-ttu-id="d22b5-107">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="d22b5-107">\<samlSecurityTokenRequirement></span></span>  
<span data-ttu-id="d22b5-108">\<roleClaimType></span><span class="sxs-lookup"><span data-stu-id="d22b5-108">\<roleClaimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d22b5-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d22b5-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d22b5-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d22b5-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d22b5-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d22b5-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d22b5-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="d22b5-112">Attributes</span></span>  
  
|<span data-ttu-id="d22b5-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="d22b5-113">Attribute</span></span>|<span data-ttu-id="d22b5-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="d22b5-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d22b5-115">value</span><span class="sxs-lookup"><span data-stu-id="d22b5-115">value</span></span>|<span data-ttu-id="d22b5-116">Una cadena que especifica el URI que representa el tipo de notificación de la notificación que se usará para el tipo de notificación de rol.</span><span class="sxs-lookup"><span data-stu-id="d22b5-116">A string that specifies the URI that represents the claim type of the claim to use for the role claim type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d22b5-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d22b5-117">Child Elements</span></span>  
 <span data-ttu-id="d22b5-118">Ninguna</span><span class="sxs-lookup"><span data-stu-id="d22b5-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d22b5-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d22b5-119">Parent Elements</span></span>  
  
|<span data-ttu-id="d22b5-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="d22b5-120">Element</span></span>|<span data-ttu-id="d22b5-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="d22b5-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d22b5-122">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="d22b5-122">\<samlSecurityTokenRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|<span data-ttu-id="d22b5-123">Proporciona la configuración de la <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> (clase), el <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> clase o una clase derivada de cualquiera de estas clases.</span><span class="sxs-lookup"><span data-stu-id="d22b5-123">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d22b5-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d22b5-124">Remarks</span></span>  
 <span data-ttu-id="d22b5-125">El `<roleClaimType>` conjuntos de elementos del <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> propiedad cuando un <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> se inicializa el objeto de configuración.</span><span class="sxs-lookup"><span data-stu-id="d22b5-125">The `<roleClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d22b5-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d22b5-126">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <roleClaimType value="schemas.microsoft.com/ws/2006/04/identity/claims/role" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d22b5-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="d22b5-127">See also</span></span>

- <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A>
