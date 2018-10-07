---
title: '&lt;nameClaimType&gt;'
ms.date: 03/30/2017
ms.assetid: 17514d95-f0f5-4789-8e28-346640dc227c
author: BrucePerlerMS
ms.openlocfilehash: bd4033b2edea7450b66c25f446669b3ded65e9af
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2018
ms.locfileid: "48847365"
---
# <a name="ltnameclaimtypegt"></a><span data-ttu-id="c45e2-102">&lt;nameClaimType&gt;</span><span class="sxs-lookup"><span data-stu-id="c45e2-102">&lt;nameClaimType&gt;</span></span>
<span data-ttu-id="c45e2-103">Establece el tipo de notificación que especifica el <xref:System.Security.Principal.IIdentity.Name%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="c45e2-103">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="c45e2-104">El tipo de notificación se utiliza para buscar un <xref:System.Security.Claims.Claim> en la colección de <xref:System.Security.Claims.ClaimsIdentity> los objetos devueltos por la <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> método de este controlador de token.</span><span class="sxs-lookup"><span data-stu-id="c45e2-104">The claim type is used to search for a <xref:System.Security.Claims.Claim> in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of this token handler.</span></span> <span data-ttu-id="c45e2-105">El valor de la notificación correspondiente, a continuación, se establece como el nombre de la <xref:System.Security.Principal.IIdentity> generado a partir de este controlador de token.</span><span class="sxs-lookup"><span data-stu-id="c45e2-105">The value of the matching claim is then set as the name of the <xref:System.Security.Principal.IIdentity> generated from this token handler.</span></span>  
  
 <span data-ttu-id="c45e2-106">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="c45e2-106">\<system.identityModel></span></span>  
<span data-ttu-id="c45e2-107">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="c45e2-107">\<identityConfiguration></span></span>  
<span data-ttu-id="c45e2-108">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="c45e2-108">\<securityTokenHandlers></span></span>  
<span data-ttu-id="c45e2-109">\<add></span><span class="sxs-lookup"><span data-stu-id="c45e2-109">\<add></span></span>  
<span data-ttu-id="c45e2-110">\<samlSecurityTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="c45e2-110">\<samlSecurityTokenRequirement></span></span>  
<span data-ttu-id="c45e2-111">\<nameClaimType ></span><span class="sxs-lookup"><span data-stu-id="c45e2-111">\<nameClaimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c45e2-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c45e2-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c45e2-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c45e2-113">Attributes and Elements</span></span>  
 <span data-ttu-id="c45e2-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c45e2-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c45e2-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="c45e2-115">Attributes</span></span>  
  
|<span data-ttu-id="c45e2-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="c45e2-116">Attribute</span></span>|<span data-ttu-id="c45e2-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="c45e2-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c45e2-118">value</span><span class="sxs-lookup"><span data-stu-id="c45e2-118">value</span></span>|<span data-ttu-id="c45e2-119">Una cadena que especifica el URI que representa el tipo de notificación de la notificación que se usará para el <xref:System.Security.Principal.IIdentity.Name%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="c45e2-119">A string that specifies the URI that represents the claim type of the claim to use for the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="c45e2-120">Requerido.</span><span class="sxs-lookup"><span data-stu-id="c45e2-120">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c45e2-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c45e2-121">Child Elements</span></span>  
 <span data-ttu-id="c45e2-122">Ninguna</span><span class="sxs-lookup"><span data-stu-id="c45e2-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c45e2-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c45e2-123">Parent Elements</span></span>  
  
|<span data-ttu-id="c45e2-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="c45e2-124">Element</span></span>|<span data-ttu-id="c45e2-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="c45e2-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c45e2-126">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="c45e2-126">\<samlSecurityTokenRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|<span data-ttu-id="c45e2-127">Proporciona la configuración de la <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> (clase), el <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> clase o una clase derivada de cualquiera de estas clases.</span><span class="sxs-lookup"><span data-stu-id="c45e2-127">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c45e2-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c45e2-128">Remarks</span></span>  
 <span data-ttu-id="c45e2-129">El `<nameClaimType>` conjuntos de elementos del <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> propiedad cuando un <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> se inicializa el objeto de configuración.</span><span class="sxs-lookup"><span data-stu-id="c45e2-129">The `<nameClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c45e2-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c45e2-130">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <nameClaimType value="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c45e2-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="c45e2-131">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A>
