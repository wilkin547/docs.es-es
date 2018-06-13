---
title: '&lt;roleClaimType&gt;'
ms.date: 03/30/2017
ms.assetid: 69a49deb-6369-41ba-806b-ae8d21fac64b
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 909df1bd6054d9737f91c30c3c6b2d68b932281c
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32755193"
---
# <a name="ltroleclaimtypegt"></a><span data-ttu-id="f2293-102">&lt;roleClaimType&gt;</span><span class="sxs-lookup"><span data-stu-id="f2293-102">&lt;roleClaimType&gt;</span></span>
<span data-ttu-id="f2293-103">Especifica el tipo de notificación que define las notificaciones de tipo de rol de la colección de <xref:System.Security.Claims.ClaimsIdentity> objetos devueltos por la <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> método del controlador de token.</span><span class="sxs-lookup"><span data-stu-id="f2293-103">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>  
  
 <span data-ttu-id="f2293-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="f2293-104">\<system.identityModel></span></span>  
<span data-ttu-id="f2293-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="f2293-105">\<identityConfiguration></span></span>  
<span data-ttu-id="f2293-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="f2293-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="f2293-107">\<add></span><span class="sxs-lookup"><span data-stu-id="f2293-107">\<add></span></span>  
<span data-ttu-id="f2293-108">\<samlSecurityTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="f2293-108">\<samlSecurityTokenRequirement></span></span>  
<span data-ttu-id="f2293-109">\<roleClaimType ></span><span class="sxs-lookup"><span data-stu-id="f2293-109">\<roleClaimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2293-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f2293-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f2293-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f2293-111">Attributes and Elements</span></span>  
 <span data-ttu-id="f2293-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f2293-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f2293-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="f2293-113">Attributes</span></span>  
  
|<span data-ttu-id="f2293-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="f2293-114">Attribute</span></span>|<span data-ttu-id="f2293-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="f2293-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f2293-116">value</span><span class="sxs-lookup"><span data-stu-id="f2293-116">value</span></span>|<span data-ttu-id="f2293-117">Una cadena que especifica el URI que representa el tipo de notificación de la notificación que se usará para el tipo de notificación de rol.</span><span class="sxs-lookup"><span data-stu-id="f2293-117">A string that specifies the URI that represents the claim type of the claim to use for the role claim type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f2293-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f2293-118">Child Elements</span></span>  
 <span data-ttu-id="f2293-119">Ninguna</span><span class="sxs-lookup"><span data-stu-id="f2293-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f2293-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f2293-120">Parent Elements</span></span>  
  
|<span data-ttu-id="f2293-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="f2293-121">Element</span></span>|<span data-ttu-id="f2293-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="f2293-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f2293-123">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="f2293-123">\<samlSecurityTokenRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|<span data-ttu-id="f2293-124">Proporciona la configuración para la <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> (clase), el <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> clase o una clase derivada de cualquiera de estas clases.</span><span class="sxs-lookup"><span data-stu-id="f2293-124">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f2293-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f2293-125">Remarks</span></span>  
 <span data-ttu-id="f2293-126">El `<roleClaimType>` conjuntos de elementos del <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> propiedad cuando un <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> se inicializa el objeto de configuración.</span><span class="sxs-lookup"><span data-stu-id="f2293-126">The `<roleClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f2293-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f2293-127">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <roleClaimType value="schemas.microsoft.com/ws/2006/04/identity/claims/role" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f2293-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="f2293-128">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A>
