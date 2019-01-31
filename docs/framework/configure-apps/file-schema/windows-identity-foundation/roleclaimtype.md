---
title: <roleClaimType>
ms.date: 03/30/2017
ms.assetid: 69a49deb-6369-41ba-806b-ae8d21fac64b
author: BrucePerlerMS
ms.openlocfilehash: 812d44ef947d27b0f73d9dc2172494e89ee56d72
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55270880"
---
# <a name="roleclaimtype"></a><span data-ttu-id="f5a8f-101">\<roleClaimType></span><span class="sxs-lookup"><span data-stu-id="f5a8f-101">\<roleClaimType></span></span>
<span data-ttu-id="f5a8f-102">Especifica el tipo de notificación que define las notificaciones de tipo de rol en la colección de <xref:System.Security.Claims.ClaimsIdentity> los objetos devueltos por la <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> método del controlador de token.</span><span class="sxs-lookup"><span data-stu-id="f5a8f-102">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>  
  
 <span data-ttu-id="f5a8f-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="f5a8f-103">\<system.identityModel></span></span>  
<span data-ttu-id="f5a8f-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="f5a8f-104">\<identityConfiguration></span></span>  
<span data-ttu-id="f5a8f-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="f5a8f-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="f5a8f-106">\<add></span><span class="sxs-lookup"><span data-stu-id="f5a8f-106">\<add></span></span>  
<span data-ttu-id="f5a8f-107">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="f5a8f-107">\<samlSecurityTokenRequirement></span></span>  
<span data-ttu-id="f5a8f-108">\<roleClaimType></span><span class="sxs-lookup"><span data-stu-id="f5a8f-108">\<roleClaimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5a8f-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f5a8f-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f5a8f-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f5a8f-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f5a8f-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f5a8f-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f5a8f-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="f5a8f-112">Attributes</span></span>  
  
|<span data-ttu-id="f5a8f-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="f5a8f-113">Attribute</span></span>|<span data-ttu-id="f5a8f-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="f5a8f-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f5a8f-115">value</span><span class="sxs-lookup"><span data-stu-id="f5a8f-115">value</span></span>|<span data-ttu-id="f5a8f-116">Una cadena que especifica el URI que representa el tipo de notificación de la notificación que se usará para el tipo de notificación de rol.</span><span class="sxs-lookup"><span data-stu-id="f5a8f-116">A string that specifies the URI that represents the claim type of the claim to use for the role claim type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f5a8f-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f5a8f-117">Child Elements</span></span>  
 <span data-ttu-id="f5a8f-118">Ninguna</span><span class="sxs-lookup"><span data-stu-id="f5a8f-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f5a8f-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f5a8f-119">Parent Elements</span></span>  
  
|<span data-ttu-id="f5a8f-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="f5a8f-120">Element</span></span>|<span data-ttu-id="f5a8f-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="f5a8f-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f5a8f-122">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="f5a8f-122">\<samlSecurityTokenRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|<span data-ttu-id="f5a8f-123">Proporciona la configuración de la <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> (clase), el <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> clase o una clase derivada de cualquiera de estas clases.</span><span class="sxs-lookup"><span data-stu-id="f5a8f-123">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f5a8f-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f5a8f-124">Remarks</span></span>  
 <span data-ttu-id="f5a8f-125">El `<roleClaimType>` conjuntos de elementos del <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> propiedad cuando un <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> se inicializa el objeto de configuración.</span><span class="sxs-lookup"><span data-stu-id="f5a8f-125">The `<roleClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f5a8f-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f5a8f-126">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <roleClaimType value="schemas.microsoft.com/ws/2006/04/identity/claims/role" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f5a8f-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="f5a8f-127">See also</span></span>
- <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A>
