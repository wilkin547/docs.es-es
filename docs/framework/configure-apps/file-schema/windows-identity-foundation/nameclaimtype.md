---
title: <nameClaimType>
ms.date: 03/30/2017
ms.assetid: 17514d95-f0f5-4789-8e28-346640dc227c
author: BrucePerlerMS
ms.openlocfilehash: 47366c5bb2bd9228268fce3ae6e1fb5ad457dab1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942617"
---
# <a name="nameclaimtype"></a><span data-ttu-id="7ec27-101">\<nameClaimType></span><span class="sxs-lookup"><span data-stu-id="7ec27-101">\<nameClaimType></span></span>
<span data-ttu-id="7ec27-102">Establece el tipo de demanda que especifica <xref:System.Security.Principal.IIdentity.Name%2A> la propiedad.</span><span class="sxs-lookup"><span data-stu-id="7ec27-102">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="7ec27-103">El tipo de demanda se usa para buscar un <xref:System.Security.Claims.Claim> en la colección de <xref:System.Security.Claims.ClaimsIdentity> objetos devueltos <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> por el método de este controlador de token.</span><span class="sxs-lookup"><span data-stu-id="7ec27-103">The claim type is used to search for a <xref:System.Security.Claims.Claim> in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of this token handler.</span></span> <span data-ttu-id="7ec27-104">El valor de la demanda coincidente se establece entonces como el nombre del <xref:System.Security.Principal.IIdentity> generado a partir de este controlador de token.</span><span class="sxs-lookup"><span data-stu-id="7ec27-104">The value of the matching claim is then set as the name of the <xref:System.Security.Principal.IIdentity> generated from this token handler.</span></span>  
  
 <span data-ttu-id="7ec27-105">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="7ec27-105">\<system.identityModel></span></span>  
<span data-ttu-id="7ec27-106">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="7ec27-106">\<identityConfiguration></span></span>  
<span data-ttu-id="7ec27-107">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="7ec27-107">\<securityTokenHandlers></span></span>  
<span data-ttu-id="7ec27-108">\<add></span><span class="sxs-lookup"><span data-stu-id="7ec27-108">\<add></span></span>  
<span data-ttu-id="7ec27-109">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="7ec27-109">\<samlSecurityTokenRequirement></span></span>  
<span data-ttu-id="7ec27-110">\<nameClaimType></span><span class="sxs-lookup"><span data-stu-id="7ec27-110">\<nameClaimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ec27-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7ec27-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7ec27-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="7ec27-112">Attributes and Elements</span></span>  
 <span data-ttu-id="7ec27-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="7ec27-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7ec27-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="7ec27-114">Attributes</span></span>  
  
|<span data-ttu-id="7ec27-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="7ec27-115">Attribute</span></span>|<span data-ttu-id="7ec27-116">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="7ec27-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7ec27-117">valor</span><span class="sxs-lookup"><span data-stu-id="7ec27-117">value</span></span>|<span data-ttu-id="7ec27-118">Una cadena que especifica el URI que representa el tipo de demanda de la demanda que se va <xref:System.Security.Principal.IIdentity.Name%2A> a usar para la propiedad.</span><span class="sxs-lookup"><span data-stu-id="7ec27-118">A string that specifies the URI that represents the claim type of the claim to use for the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="7ec27-119">Necesario.</span><span class="sxs-lookup"><span data-stu-id="7ec27-119">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7ec27-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="7ec27-120">Child Elements</span></span>  
 <span data-ttu-id="7ec27-121">None</span><span class="sxs-lookup"><span data-stu-id="7ec27-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7ec27-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="7ec27-122">Parent Elements</span></span>  
  
|<span data-ttu-id="7ec27-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="7ec27-123">Element</span></span>|<span data-ttu-id="7ec27-124">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="7ec27-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7ec27-125">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="7ec27-125">\<samlSecurityTokenRequirement></span></span>](samlsecuritytokenrequirement.md)|<span data-ttu-id="7ec27-126">Proporciona la configuración para <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> la clase, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> la clase o una clase derivada de cualquiera de estas clases.</span><span class="sxs-lookup"><span data-stu-id="7ec27-126">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7ec27-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7ec27-127">Remarks</span></span>  
 <span data-ttu-id="7ec27-128">El `<nameClaimType>` elemento establece la <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> propiedad cuando se <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> Inicializa un objeto a partir de la configuración.</span><span class="sxs-lookup"><span data-stu-id="7ec27-128">The `<nameClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7ec27-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7ec27-129">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <nameClaimType value="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7ec27-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="7ec27-130">See also</span></span>

- <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A>
