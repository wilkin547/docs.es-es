---
title: <nameClaimType>
ms.date: 03/30/2017
ms.assetid: 17514d95-f0f5-4789-8e28-346640dc227c
author: BrucePerlerMS
ms.openlocfilehash: 4ffc19366d91e4a14ee0f931d7009ede390cc097
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91165031"
---
# \<nameClaimType>

<span data-ttu-id="42ded-101">Establece el tipo de demanda que especifica la <xref:System.Security.Principal.IIdentity.Name%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="42ded-101">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="42ded-102">El tipo de demanda se usa para buscar un <xref:System.Security.Claims.Claim> en la colección de <xref:System.Security.Claims.ClaimsIdentity> objetos devueltos por el <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> método de este controlador de token.</span><span class="sxs-lookup"><span data-stu-id="42ded-102">The claim type is used to search for a <xref:System.Security.Claims.Claim> in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of this token handler.</span></span> <span data-ttu-id="42ded-103">El valor de la demanda coincidente se establece entonces como el nombre del <xref:System.Security.Principal.IIdentity> generado a partir de este controlador de token.</span><span class="sxs-lookup"><span data-stu-id="42ded-103">The value of the matching claim is then set as the name of the <xref:System.Security.Principal.IIdentity> generated from this token handler.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<samlSecurityTokenRequirement>**](samlsecuritytokenrequirement.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<nameClaimType>**  
  
## <a name="syntax"></a><span data-ttu-id="42ded-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="42ded-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="42ded-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="42ded-105">Attributes and Elements</span></span>  

 <span data-ttu-id="42ded-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="42ded-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="42ded-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="42ded-107">Attributes</span></span>  
  
|<span data-ttu-id="42ded-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="42ded-108">Attribute</span></span>|<span data-ttu-id="42ded-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="42ded-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="42ded-110">value</span><span class="sxs-lookup"><span data-stu-id="42ded-110">value</span></span>|<span data-ttu-id="42ded-111">Una cadena que especifica el URI que representa el tipo de demanda de la demanda que se va a usar para la <xref:System.Security.Principal.IIdentity.Name%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="42ded-111">A string that specifies the URI that represents the claim type of the claim to use for the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="42ded-112">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="42ded-112">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="42ded-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="42ded-113">Child Elements</span></span>  

 <span data-ttu-id="42ded-114">None</span><span class="sxs-lookup"><span data-stu-id="42ded-114">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="42ded-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="42ded-115">Parent Elements</span></span>  
  
|<span data-ttu-id="42ded-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="42ded-116">Element</span></span>|<span data-ttu-id="42ded-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="42ded-117">Description</span></span>|  
|-------------|-----------------|  
|[\<samlSecurityTokenRequirement>](samlsecuritytokenrequirement.md)|<span data-ttu-id="42ded-118">Proporciona la configuración para la <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> clase, la <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> clase o una clase derivada de cualquiera de estas clases.</span><span class="sxs-lookup"><span data-stu-id="42ded-118">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="42ded-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="42ded-119">Remarks</span></span>  

 <span data-ttu-id="42ded-120">El `<nameClaimType>` elemento establece la <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> propiedad cuando <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> se inicializa un objeto a partir de la configuración.</span><span class="sxs-lookup"><span data-stu-id="42ded-120">The `<nameClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="42ded-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="42ded-121">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <nameClaimType value="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="42ded-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="42ded-122">See also</span></span>

- <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A>
