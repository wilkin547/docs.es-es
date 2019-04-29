---
title: <nameClaimType>
ms.date: 03/30/2017
ms.assetid: 17514d95-f0f5-4789-8e28-346640dc227c
author: BrucePerlerMS
ms.openlocfilehash: 5202e162a7eb5fc4e36d6a6c0a2c18af48872a69
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61791604"
---
# <a name="nameclaimtype"></a><span data-ttu-id="42375-101">\<nameClaimType></span><span class="sxs-lookup"><span data-stu-id="42375-101">\<nameClaimType></span></span>
<span data-ttu-id="42375-102">Establece el tipo de notificación que especifica el <xref:System.Security.Principal.IIdentity.Name%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="42375-102">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="42375-103">El tipo de notificación se utiliza para buscar un <xref:System.Security.Claims.Claim> en la colección de <xref:System.Security.Claims.ClaimsIdentity> los objetos devueltos por la <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> método de este controlador de token.</span><span class="sxs-lookup"><span data-stu-id="42375-103">The claim type is used to search for a <xref:System.Security.Claims.Claim> in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of this token handler.</span></span> <span data-ttu-id="42375-104">El valor de la notificación correspondiente, a continuación, se establece como el nombre de la <xref:System.Security.Principal.IIdentity> generado a partir de este controlador de token.</span><span class="sxs-lookup"><span data-stu-id="42375-104">The value of the matching claim is then set as the name of the <xref:System.Security.Principal.IIdentity> generated from this token handler.</span></span>  
  
 <span data-ttu-id="42375-105">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="42375-105">\<system.identityModel></span></span>  
<span data-ttu-id="42375-106">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="42375-106">\<identityConfiguration></span></span>  
<span data-ttu-id="42375-107">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="42375-107">\<securityTokenHandlers></span></span>  
<span data-ttu-id="42375-108">\<add></span><span class="sxs-lookup"><span data-stu-id="42375-108">\<add></span></span>  
<span data-ttu-id="42375-109">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="42375-109">\<samlSecurityTokenRequirement></span></span>  
<span data-ttu-id="42375-110">\<nameClaimType></span><span class="sxs-lookup"><span data-stu-id="42375-110">\<nameClaimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42375-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="42375-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="42375-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="42375-112">Attributes and Elements</span></span>  
 <span data-ttu-id="42375-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="42375-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="42375-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="42375-114">Attributes</span></span>  
  
|<span data-ttu-id="42375-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="42375-115">Attribute</span></span>|<span data-ttu-id="42375-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="42375-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="42375-117">value</span><span class="sxs-lookup"><span data-stu-id="42375-117">value</span></span>|<span data-ttu-id="42375-118">Una cadena que especifica el URI que representa el tipo de notificación de la notificación que se usará para el <xref:System.Security.Principal.IIdentity.Name%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="42375-118">A string that specifies the URI that represents the claim type of the claim to use for the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="42375-119">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="42375-119">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="42375-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="42375-120">Child Elements</span></span>  
 <span data-ttu-id="42375-121">Ninguna</span><span class="sxs-lookup"><span data-stu-id="42375-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="42375-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="42375-122">Parent Elements</span></span>  
  
|<span data-ttu-id="42375-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="42375-123">Element</span></span>|<span data-ttu-id="42375-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="42375-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="42375-125">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="42375-125">\<samlSecurityTokenRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|<span data-ttu-id="42375-126">Proporciona la configuración de la <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> (clase), el <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> clase o una clase derivada de cualquiera de estas clases.</span><span class="sxs-lookup"><span data-stu-id="42375-126">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="42375-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="42375-127">Remarks</span></span>  
 <span data-ttu-id="42375-128">El `<nameClaimType>` conjuntos de elementos del <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> propiedad cuando un <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> se inicializa el objeto de configuración.</span><span class="sxs-lookup"><span data-stu-id="42375-128">The `<nameClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="42375-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="42375-129">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <nameClaimType value="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="42375-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="42375-130">See also</span></span>

- <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A>
