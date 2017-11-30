---
title: '&lt;nameClaimType&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 17514d95-f0f5-4789-8e28-346640dc227c
caps.latest.revision: "4"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: e910333084aae9e47153cfe3ee4b5cd943a37f71
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="ltnameclaimtypegt"></a><span data-ttu-id="4a77f-102">&lt;nameClaimType&gt;</span><span class="sxs-lookup"><span data-stu-id="4a77f-102">&lt;nameClaimType&gt;</span></span>
<span data-ttu-id="4a77f-103">Establece el tipo de notificación que especifica la <xref:System.Security.Principal.IIdentity.Name%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="4a77f-103">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="4a77f-104">El tipo de notificación se utiliza para buscar un <xref:System.Security.Claims.Claim> en la colección de <xref:System.Security.Claims.ClaimsIdentity> objetos devueltos por la <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> método de este controlador de token.</span><span class="sxs-lookup"><span data-stu-id="4a77f-104">The claim type is used to search for a <xref:System.Security.Claims.Claim> in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of this token handler.</span></span> <span data-ttu-id="4a77f-105">El valor de la notificación correspondiente, a continuación, se establece como el nombre de la <xref:System.Security.Principal.IIdentity> generados a partir de este controlador de token.</span><span class="sxs-lookup"><span data-stu-id="4a77f-105">The value of the matching claim is then set as the name of the <xref:System.Security.Principal.IIdentity> generated from this token handler.</span></span>  
  
 <span data-ttu-id="4a77f-106">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="4a77f-106">\<system.identityModel></span></span>  
<span data-ttu-id="4a77f-107">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="4a77f-107">\<identityConfiguration></span></span>  
<span data-ttu-id="4a77f-108">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="4a77f-108">\<securityTokenHandlers></span></span>  
<span data-ttu-id="4a77f-109">\<add></span><span class="sxs-lookup"><span data-stu-id="4a77f-109">\<add></span></span>  
<span data-ttu-id="4a77f-110">\<samlSecurityTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="4a77f-110">\<samlSecurityTokenRequirement></span></span>  
<span data-ttu-id="4a77f-111">\<nameClaimType ></span><span class="sxs-lookup"><span data-stu-id="4a77f-111">\<nameClaimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a77f-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4a77f-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4a77f-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4a77f-113">Attributes and Elements</span></span>  
 <span data-ttu-id="4a77f-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="4a77f-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4a77f-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="4a77f-115">Attributes</span></span>  
  
|<span data-ttu-id="4a77f-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="4a77f-116">Attribute</span></span>|<span data-ttu-id="4a77f-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="4a77f-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4a77f-118">valor</span><span class="sxs-lookup"><span data-stu-id="4a77f-118">value</span></span>|<span data-ttu-id="4a77f-119">Una cadena que especifica el URI que representa el tipo de notificación de la notificación que se usará para la <xref:System.Security.Principal.IIdentity.Name%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="4a77f-119">A string that specifies the URI that represents the claim type of the claim to use for the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="4a77f-120">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="4a77f-120">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4a77f-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4a77f-121">Child Elements</span></span>  
 <span data-ttu-id="4a77f-122">Ninguna</span><span class="sxs-lookup"><span data-stu-id="4a77f-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4a77f-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4a77f-123">Parent Elements</span></span>  
  
|<span data-ttu-id="4a77f-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="4a77f-124">Element</span></span>|<span data-ttu-id="4a77f-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="4a77f-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4a77f-126">\<samlSecurityTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="4a77f-126">\<samlSecurityTokenRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|<span data-ttu-id="4a77f-127">Proporciona la configuración para la <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> (clase), el <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> clase o una clase derivada de cualquiera de estas clases.</span><span class="sxs-lookup"><span data-stu-id="4a77f-127">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4a77f-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4a77f-128">Remarks</span></span>  
 <span data-ttu-id="4a77f-129">El `<nameClaimType>` conjuntos de elementos del <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> propiedad cuando un <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> se inicializa el objeto de configuración.</span><span class="sxs-lookup"><span data-stu-id="4a77f-129">The `<nameClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4a77f-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4a77f-130">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <nameClaimType value="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4a77f-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="4a77f-131">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A>
