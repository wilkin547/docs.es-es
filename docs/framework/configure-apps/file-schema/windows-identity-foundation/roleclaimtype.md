---
title: <roleClaimType>
ms.date: 03/30/2017
ms.assetid: 69a49deb-6369-41ba-806b-ae8d21fac64b
author: BrucePerlerMS
ms.openlocfilehash: 0ce2e06ee895d09de193bac1fe7038e71794dda4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942540"
---
# <a name="roleclaimtype"></a><span data-ttu-id="f43cb-101">\<roleClaimType></span><span class="sxs-lookup"><span data-stu-id="f43cb-101">\<roleClaimType></span></span>
<span data-ttu-id="f43cb-102">Especifica el tipo de notificación que define las notificaciones de tipo de rol <xref:System.Security.Claims.ClaimsIdentity> en la colección de <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> objetos devuelta por el método del controlador de token.</span><span class="sxs-lookup"><span data-stu-id="f43cb-102">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>  
  
 <span data-ttu-id="f43cb-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="f43cb-103">\<system.identityModel></span></span>  
<span data-ttu-id="f43cb-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="f43cb-104">\<identityConfiguration></span></span>  
<span data-ttu-id="f43cb-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="f43cb-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="f43cb-106">\<add></span><span class="sxs-lookup"><span data-stu-id="f43cb-106">\<add></span></span>  
<span data-ttu-id="f43cb-107">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="f43cb-107">\<samlSecurityTokenRequirement></span></span>  
<span data-ttu-id="f43cb-108">\<roleClaimType></span><span class="sxs-lookup"><span data-stu-id="f43cb-108">\<roleClaimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f43cb-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f43cb-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f43cb-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f43cb-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f43cb-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f43cb-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f43cb-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="f43cb-112">Attributes</span></span>  
  
|<span data-ttu-id="f43cb-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="f43cb-113">Attribute</span></span>|<span data-ttu-id="f43cb-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="f43cb-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f43cb-115">valor</span><span class="sxs-lookup"><span data-stu-id="f43cb-115">value</span></span>|<span data-ttu-id="f43cb-116">Una cadena que especifica el URI que representa el tipo de demanda de la demanda que se va a usar para el tipo de notificaciones de rol.</span><span class="sxs-lookup"><span data-stu-id="f43cb-116">A string that specifies the URI that represents the claim type of the claim to use for the role claim type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f43cb-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f43cb-117">Child Elements</span></span>  
 <span data-ttu-id="f43cb-118">None</span><span class="sxs-lookup"><span data-stu-id="f43cb-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f43cb-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f43cb-119">Parent Elements</span></span>  
  
|<span data-ttu-id="f43cb-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="f43cb-120">Element</span></span>|<span data-ttu-id="f43cb-121">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="f43cb-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f43cb-122">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="f43cb-122">\<samlSecurityTokenRequirement></span></span>](samlsecuritytokenrequirement.md)|<span data-ttu-id="f43cb-123">Proporciona la configuración para <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> la clase, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> la clase o una clase derivada de cualquiera de estas clases.</span><span class="sxs-lookup"><span data-stu-id="f43cb-123">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f43cb-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f43cb-124">Remarks</span></span>  
 <span data-ttu-id="f43cb-125">El `<roleClaimType>` elemento establece la <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> propiedad cuando se <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> Inicializa un objeto a partir de la configuración.</span><span class="sxs-lookup"><span data-stu-id="f43cb-125">The `<roleClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f43cb-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f43cb-126">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <roleClaimType value="schemas.microsoft.com/ws/2006/04/identity/claims/role" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f43cb-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="f43cb-127">See also</span></span>

- <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A>
