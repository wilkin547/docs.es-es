---
title: '&lt;roleClaimType&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 69a49deb-6369-41ba-806b-ae8d21fac64b
caps.latest.revision: "4"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: eb46585561ca8a2ab7c69f09d073d38bc1b60646
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltroleclaimtypegt"></a><span data-ttu-id="f5ccf-102">&lt;roleClaimType&gt;</span><span class="sxs-lookup"><span data-stu-id="f5ccf-102">&lt;roleClaimType&gt;</span></span>
<span data-ttu-id="f5ccf-103">Especifica el tipo de notificación que define las notificaciones de tipo de rol de la colección de <xref:System.Security.Claims.ClaimsIdentity> objetos devueltos por la <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> método del controlador de token.</span><span class="sxs-lookup"><span data-stu-id="f5ccf-103">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>  
  
 <span data-ttu-id="f5ccf-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="f5ccf-104">\<system.identityModel></span></span>  
<span data-ttu-id="f5ccf-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="f5ccf-105">\<identityConfiguration></span></span>  
<span data-ttu-id="f5ccf-106">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="f5ccf-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="f5ccf-107">\<add></span><span class="sxs-lookup"><span data-stu-id="f5ccf-107">\<add></span></span>  
<span data-ttu-id="f5ccf-108">\<samlSecurityTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="f5ccf-108">\<samlSecurityTokenRequirement></span></span>  
<span data-ttu-id="f5ccf-109">\<roleClaimType ></span><span class="sxs-lookup"><span data-stu-id="f5ccf-109">\<roleClaimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5ccf-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f5ccf-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f5ccf-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f5ccf-111">Attributes and Elements</span></span>  
 <span data-ttu-id="f5ccf-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f5ccf-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f5ccf-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="f5ccf-113">Attributes</span></span>  
  
|<span data-ttu-id="f5ccf-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="f5ccf-114">Attribute</span></span>|<span data-ttu-id="f5ccf-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="f5ccf-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f5ccf-116">value</span><span class="sxs-lookup"><span data-stu-id="f5ccf-116">value</span></span>|<span data-ttu-id="f5ccf-117">Una cadena que especifica el URI que representa el tipo de notificación de la notificación que se usará para el tipo de notificación de rol.</span><span class="sxs-lookup"><span data-stu-id="f5ccf-117">A string that specifies the URI that represents the claim type of the claim to use for the role claim type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f5ccf-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f5ccf-118">Child Elements</span></span>  
 <span data-ttu-id="f5ccf-119">Ninguna</span><span class="sxs-lookup"><span data-stu-id="f5ccf-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f5ccf-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f5ccf-120">Parent Elements</span></span>  
  
|<span data-ttu-id="f5ccf-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="f5ccf-121">Element</span></span>|<span data-ttu-id="f5ccf-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="f5ccf-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f5ccf-123">\<samlSecurityTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="f5ccf-123">\<samlSecurityTokenRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|<span data-ttu-id="f5ccf-124">Proporciona la configuración para la <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> (clase), el <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> clase o una clase derivada de cualquiera de estas clases.</span><span class="sxs-lookup"><span data-stu-id="f5ccf-124">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f5ccf-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f5ccf-125">Remarks</span></span>  
 <span data-ttu-id="f5ccf-126">El `<roleClaimType>` conjuntos de elementos del <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> propiedad cuando un <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> se inicializa el objeto de configuración.</span><span class="sxs-lookup"><span data-stu-id="f5ccf-126">The `<roleClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f5ccf-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f5ccf-127">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <roleClaimType value="schemas.microsoft.com/ws/2006/04/identity/claims/role" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f5ccf-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="f5ccf-128">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A>
