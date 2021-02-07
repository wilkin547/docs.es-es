---
description: 'Más información acerca de: <nameClaimType>'
title: <nameClaimType>
ms.date: 03/30/2017
ms.assetid: 17514d95-f0f5-4789-8e28-346640dc227c
author: BrucePerlerMS
ms.openlocfilehash: d5bc2f96c2753febdb61c3495b7067c0e31e52d5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99664059"
---
# \<nameClaimType>

<span data-ttu-id="e2cce-102">Establece el tipo de demanda que especifica la <xref:System.Security.Principal.IIdentity.Name%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="e2cce-102">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="e2cce-103">El tipo de demanda se usa para buscar un <xref:System.Security.Claims.Claim> en la colección de <xref:System.Security.Claims.ClaimsIdentity> objetos devueltos por el <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> método de este controlador de token.</span><span class="sxs-lookup"><span data-stu-id="e2cce-103">The claim type is used to search for a <xref:System.Security.Claims.Claim> in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of this token handler.</span></span> <span data-ttu-id="e2cce-104">El valor de la demanda coincidente se establece entonces como el nombre del <xref:System.Security.Principal.IIdentity> generado a partir de este controlador de token.</span><span class="sxs-lookup"><span data-stu-id="e2cce-104">The value of the matching claim is then set as the name of the <xref:System.Security.Principal.IIdentity> generated from this token handler.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<samlSecurityTokenRequirement>**](samlsecuritytokenrequirement.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<nameClaimType>**  
  
## <a name="syntax"></a><span data-ttu-id="e2cce-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e2cce-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e2cce-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e2cce-106">Attributes and Elements</span></span>  

 <span data-ttu-id="e2cce-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e2cce-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e2cce-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="e2cce-108">Attributes</span></span>  
  
|<span data-ttu-id="e2cce-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="e2cce-109">Attribute</span></span>|<span data-ttu-id="e2cce-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="e2cce-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e2cce-111">value</span><span class="sxs-lookup"><span data-stu-id="e2cce-111">value</span></span>|<span data-ttu-id="e2cce-112">Una cadena que especifica el URI que representa el tipo de demanda de la demanda que se va a usar para la <xref:System.Security.Principal.IIdentity.Name%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="e2cce-112">A string that specifies the URI that represents the claim type of the claim to use for the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="e2cce-113">Necesario.</span><span class="sxs-lookup"><span data-stu-id="e2cce-113">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e2cce-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e2cce-114">Child Elements</span></span>  

 <span data-ttu-id="e2cce-115">None</span><span class="sxs-lookup"><span data-stu-id="e2cce-115">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e2cce-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e2cce-116">Parent Elements</span></span>  
  
|<span data-ttu-id="e2cce-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="e2cce-117">Element</span></span>|<span data-ttu-id="e2cce-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="e2cce-118">Description</span></span>|  
|-------------|-----------------|  
|[\<samlSecurityTokenRequirement>](samlsecuritytokenrequirement.md)|<span data-ttu-id="e2cce-119">Proporciona la configuración para la <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> clase, la <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> clase o una clase derivada de cualquiera de estas clases.</span><span class="sxs-lookup"><span data-stu-id="e2cce-119">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e2cce-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e2cce-120">Remarks</span></span>  

 <span data-ttu-id="e2cce-121">El `<nameClaimType>` elemento establece la <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> propiedad cuando <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> se inicializa un objeto a partir de la configuración.</span><span class="sxs-lookup"><span data-stu-id="e2cce-121">The `<nameClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e2cce-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e2cce-122">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <nameClaimType value="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e2cce-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="e2cce-123">See also</span></span>

- <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A>
