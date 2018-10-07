---
title: '&lt;RoleClaimType&gt;'
ms.date: 03/30/2017
ms.assetid: 69a49deb-6369-41ba-806b-ae8d21fac64b
author: BrucePerlerMS
ms.openlocfilehash: 565bf30d334c62c8132c60f411e89f7b260c54f1
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2018
ms.locfileid: "48841520"
---
# <a name="ltroleclaimtypegt"></a><span data-ttu-id="7003e-102">&lt;RoleClaimType&gt;</span><span class="sxs-lookup"><span data-stu-id="7003e-102">&lt;roleClaimType&gt;</span></span>
<span data-ttu-id="7003e-103">Especifica el tipo de notificación que define las notificaciones de tipo de rol en la colección de <xref:System.Security.Claims.ClaimsIdentity> los objetos devueltos por la <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> método del controlador de token.</span><span class="sxs-lookup"><span data-stu-id="7003e-103">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>  
  
 <span data-ttu-id="7003e-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="7003e-104">\<system.identityModel></span></span>  
<span data-ttu-id="7003e-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="7003e-105">\<identityConfiguration></span></span>  
<span data-ttu-id="7003e-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="7003e-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="7003e-107">\<add></span><span class="sxs-lookup"><span data-stu-id="7003e-107">\<add></span></span>  
<span data-ttu-id="7003e-108">\<samlSecurityTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="7003e-108">\<samlSecurityTokenRequirement></span></span>  
<span data-ttu-id="7003e-109">\<roleClaimType ></span><span class="sxs-lookup"><span data-stu-id="7003e-109">\<roleClaimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7003e-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7003e-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7003e-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="7003e-111">Attributes and Elements</span></span>  
 <span data-ttu-id="7003e-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="7003e-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7003e-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="7003e-113">Attributes</span></span>  
  
|<span data-ttu-id="7003e-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="7003e-114">Attribute</span></span>|<span data-ttu-id="7003e-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="7003e-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7003e-116">value</span><span class="sxs-lookup"><span data-stu-id="7003e-116">value</span></span>|<span data-ttu-id="7003e-117">Una cadena que especifica el URI que representa el tipo de notificación de la notificación que se usará para el tipo de notificación de rol.</span><span class="sxs-lookup"><span data-stu-id="7003e-117">A string that specifies the URI that represents the claim type of the claim to use for the role claim type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7003e-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="7003e-118">Child Elements</span></span>  
 <span data-ttu-id="7003e-119">Ninguna</span><span class="sxs-lookup"><span data-stu-id="7003e-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7003e-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="7003e-120">Parent Elements</span></span>  
  
|<span data-ttu-id="7003e-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="7003e-121">Element</span></span>|<span data-ttu-id="7003e-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="7003e-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7003e-123">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="7003e-123">\<samlSecurityTokenRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|<span data-ttu-id="7003e-124">Proporciona la configuración de la <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> (clase), el <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> clase o una clase derivada de cualquiera de estas clases.</span><span class="sxs-lookup"><span data-stu-id="7003e-124">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7003e-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7003e-125">Remarks</span></span>  
 <span data-ttu-id="7003e-126">El `<roleClaimType>` conjuntos de elementos del <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> propiedad cuando un <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> se inicializa el objeto de configuración.</span><span class="sxs-lookup"><span data-stu-id="7003e-126">The `<roleClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7003e-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7003e-127">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <roleClaimType value="schemas.microsoft.com/ws/2006/04/identity/claims/role" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7003e-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="7003e-128">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A>
