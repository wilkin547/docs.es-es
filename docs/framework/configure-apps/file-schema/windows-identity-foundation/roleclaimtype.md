---
title: <roleClaimType>
ms.date: 03/30/2017
ms.assetid: 69a49deb-6369-41ba-806b-ae8d21fac64b
author: BrucePerlerMS
ms.openlocfilehash: 0f651377346b1f14a4226128cd5cf7059543adca
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70251910"
---
# \<roleClaimType>
<span data-ttu-id="3b016-101">Especifica el tipo de notificación que define las notificaciones de tipo de rol en la colección de <xref:System.Security.Claims.ClaimsIdentity> objetos devuelta por el <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> método del controlador de token.</span><span class="sxs-lookup"><span data-stu-id="3b016-101">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<samlSecurityTokenRequirement>**](samlsecuritytokenrequirement.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<roleClaimType>**  
  
## <a name="syntax"></a><span data-ttu-id="3b016-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3b016-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3b016-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3b016-103">Attributes and Elements</span></span>  
 <span data-ttu-id="3b016-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3b016-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3b016-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="3b016-105">Attributes</span></span>  
  
|<span data-ttu-id="3b016-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="3b016-106">Attribute</span></span>|<span data-ttu-id="3b016-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="3b016-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3b016-108">value</span><span class="sxs-lookup"><span data-stu-id="3b016-108">value</span></span>|<span data-ttu-id="3b016-109">Una cadena que especifica el URI que representa el tipo de demanda de la demanda que se va a usar para el tipo de notificaciones de rol.</span><span class="sxs-lookup"><span data-stu-id="3b016-109">A string that specifies the URI that represents the claim type of the claim to use for the role claim type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3b016-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3b016-110">Child Elements</span></span>  
 <span data-ttu-id="3b016-111">None</span><span class="sxs-lookup"><span data-stu-id="3b016-111">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3b016-112">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3b016-112">Parent Elements</span></span>  
  
|<span data-ttu-id="3b016-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="3b016-113">Element</span></span>|<span data-ttu-id="3b016-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="3b016-114">Description</span></span>|  
|-------------|-----------------|  
|[\<samlSecurityTokenRequirement>](samlsecuritytokenrequirement.md)|<span data-ttu-id="3b016-115">Proporciona la configuración para la <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> clase, la <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> clase o una clase derivada de cualquiera de estas clases.</span><span class="sxs-lookup"><span data-stu-id="3b016-115">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3b016-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3b016-116">Remarks</span></span>  
 <span data-ttu-id="3b016-117">El `<roleClaimType>` elemento establece la <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> propiedad cuando <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> se inicializa un objeto a partir de la configuración.</span><span class="sxs-lookup"><span data-stu-id="3b016-117">The `<roleClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3b016-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3b016-118">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <roleClaimType value="schemas.microsoft.com/ws/2006/04/identity/claims/role" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3b016-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3b016-119">See also</span></span>

- <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A>
