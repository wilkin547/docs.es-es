---
title: <roleClaimType>
ms.date: 03/30/2017
ms.assetid: 69a49deb-6369-41ba-806b-ae8d21fac64b
author: BrucePerlerMS
ms.openlocfilehash: 36d727f97597df816779da1c1f7ed5da1a1697f2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164940"
---
# \<roleClaimType>

<span data-ttu-id="1bd66-101">Especifica el tipo de notificación que define las notificaciones de tipo de rol en la colección de <xref:System.Security.Claims.ClaimsIdentity> objetos devuelta por el <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> método del controlador de token.</span><span class="sxs-lookup"><span data-stu-id="1bd66-101">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<samlSecurityTokenRequirement>**](samlsecuritytokenrequirement.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<roleClaimType>**  
  
## <a name="syntax"></a><span data-ttu-id="1bd66-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1bd66-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1bd66-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="1bd66-103">Attributes and Elements</span></span>  

 <span data-ttu-id="1bd66-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="1bd66-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1bd66-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="1bd66-105">Attributes</span></span>  
  
|<span data-ttu-id="1bd66-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="1bd66-106">Attribute</span></span>|<span data-ttu-id="1bd66-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="1bd66-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1bd66-108">value</span><span class="sxs-lookup"><span data-stu-id="1bd66-108">value</span></span>|<span data-ttu-id="1bd66-109">Una cadena que especifica el URI que representa el tipo de demanda de la demanda que se va a usar para el tipo de notificaciones de rol.</span><span class="sxs-lookup"><span data-stu-id="1bd66-109">A string that specifies the URI that represents the claim type of the claim to use for the role claim type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1bd66-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="1bd66-110">Child Elements</span></span>  

 <span data-ttu-id="1bd66-111">None</span><span class="sxs-lookup"><span data-stu-id="1bd66-111">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1bd66-112">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="1bd66-112">Parent Elements</span></span>  
  
|<span data-ttu-id="1bd66-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="1bd66-113">Element</span></span>|<span data-ttu-id="1bd66-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="1bd66-114">Description</span></span>|  
|-------------|-----------------|  
|[\<samlSecurityTokenRequirement>](samlsecuritytokenrequirement.md)|<span data-ttu-id="1bd66-115">Proporciona la configuración para la <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> clase, la <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> clase o una clase derivada de cualquiera de estas clases.</span><span class="sxs-lookup"><span data-stu-id="1bd66-115">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1bd66-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1bd66-116">Remarks</span></span>  

 <span data-ttu-id="1bd66-117">El `<roleClaimType>` elemento establece la <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> propiedad cuando <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> se inicializa un objeto a partir de la configuración.</span><span class="sxs-lookup"><span data-stu-id="1bd66-117">The `<roleClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1bd66-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1bd66-118">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <roleClaimType value="schemas.microsoft.com/ws/2006/04/identity/claims/role" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1bd66-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1bd66-119">See also</span></span>

- <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A>
