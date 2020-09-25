---
title: <userNameSecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: 6ec3bac1-b014-49ae-843c-c54518cb709a
author: BrucePerlerMS
ms.openlocfilehash: a49b41c04c8f184188b62e04c3b232bd33752fca
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185527"
---
# \<userNameSecurityTokenHandlerRequirement>

<span data-ttu-id="6e48f-101">Proporciona la configuración para la <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> clase o las clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="6e48f-101">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<userNameSecurityTokenHandlerRequirement>**  
  
## <a name="syntax"></a><span data-ttu-id="6e48f-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6e48f-102">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
        <userNameSecurityTokenHandlerRequirement membershipProviderName=xs:string >  
        </userNameSecurityTokenHandlerRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6e48f-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="6e48f-103">Attributes and Elements</span></span>  

 <span data-ttu-id="6e48f-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="6e48f-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6e48f-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="6e48f-105">Attributes</span></span>  
  
|<span data-ttu-id="6e48f-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="6e48f-106">Attribute</span></span>|<span data-ttu-id="6e48f-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="6e48f-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6e48f-108">membershipProviderName</span><span class="sxs-lookup"><span data-stu-id="6e48f-108">membershipProviderName</span></span>|<span data-ttu-id="6e48f-109">Especifica el <xref:System.Web.Security.MembershipProvider> que debe usar el controlador de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="6e48f-109">Specifies the <xref:System.Web.Security.MembershipProvider> that should be used by the security token handler.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6e48f-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="6e48f-110">Child Elements</span></span>  

 <span data-ttu-id="6e48f-111">None</span><span class="sxs-lookup"><span data-stu-id="6e48f-111">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6e48f-112">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="6e48f-112">Parent Elements</span></span>  
  
|<span data-ttu-id="6e48f-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="6e48f-113">Element</span></span>|<span data-ttu-id="6e48f-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="6e48f-114">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add.md)|<span data-ttu-id="6e48f-115">Agrega el controlador de tokens de seguridad especificado a la colección de controladores de tokens.</span><span class="sxs-lookup"><span data-stu-id="6e48f-115">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6e48f-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6e48f-116">Remarks</span></span>  

 <span data-ttu-id="6e48f-117">El `<userNameSecurityTokenHandlerRequirement>` elemento establece la <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> propiedad cuando <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> se inicializa un objeto a partir de la configuración.</span><span class="sxs-lookup"><span data-stu-id="6e48f-117">The `<userNameSecurityTokenHandlerRequirement>` element sets the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> property when a <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e48f-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6e48f-118">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
    <userNameSecurityTokenHandlerRequirement membershipProviderName="AspNetSqlProvider/>  
</add>  
```
