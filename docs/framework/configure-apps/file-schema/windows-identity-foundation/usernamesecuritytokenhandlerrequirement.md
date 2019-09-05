---
title: <userNameSecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: 6ec3bac1-b014-49ae-843c-c54518cb709a
author: BrucePerlerMS
ms.openlocfilehash: 5863c01e97e7f5fb6fe07c43174c0d6cb7a0a25d
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251746"
---
# <a name="usernamesecuritytokenhandlerrequirement"></a><span data-ttu-id="2f65d-101">\<userNameSecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="2f65d-101">\<userNameSecurityTokenHandlerRequirement></span></span>
<span data-ttu-id="2f65d-102">Proporciona la configuración para <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> la clase o las clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="2f65d-102">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>  
  
<span data-ttu-id="2f65d-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2f65d-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2f65d-104">&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="2f65d-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="2f65d-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identityConfiguration**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="2f65d-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="2f65d-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> securityTokenHandlers**](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="2f65d-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="2f65d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Agregar >** ](add.md)</span><span class="sxs-lookup"><span data-stu-id="2f65d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)</span></span>\
<span data-ttu-id="2f65d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> userNameSecurityTokenHandlerRequirement**</span><span class="sxs-lookup"><span data-stu-id="2f65d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<userNameSecurityTokenHandlerRequirement>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f65d-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2f65d-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2f65d-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="2f65d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="2f65d-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="2f65d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2f65d-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="2f65d-112">Attributes</span></span>  
  
|<span data-ttu-id="2f65d-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="2f65d-113">Attribute</span></span>|<span data-ttu-id="2f65d-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="2f65d-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2f65d-115">membershipProviderName</span><span class="sxs-lookup"><span data-stu-id="2f65d-115">membershipProviderName</span></span>|<span data-ttu-id="2f65d-116">Especifica el <xref:System.Web.Security.MembershipProvider> que debe usar el controlador de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="2f65d-116">Specifies the <xref:System.Web.Security.MembershipProvider> that should be used by the security token handler.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2f65d-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="2f65d-117">Child Elements</span></span>  
 <span data-ttu-id="2f65d-118">None</span><span class="sxs-lookup"><span data-stu-id="2f65d-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2f65d-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="2f65d-119">Parent Elements</span></span>  
  
|<span data-ttu-id="2f65d-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="2f65d-120">Element</span></span>|<span data-ttu-id="2f65d-121">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="2f65d-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2f65d-122">\<add></span><span class="sxs-lookup"><span data-stu-id="2f65d-122">\<add></span></span>](add.md)|<span data-ttu-id="2f65d-123">Agrega el controlador de tokens de seguridad especificado a la colección de controladores de tokens.</span><span class="sxs-lookup"><span data-stu-id="2f65d-123">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2f65d-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2f65d-124">Remarks</span></span>  
 <span data-ttu-id="2f65d-125">El `<userNameSecurityTokenHandlerRequirement>` elemento establece la <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> propiedad cuando se <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> Inicializa un objeto a partir de la configuración.</span><span class="sxs-lookup"><span data-stu-id="2f65d-125">The `<userNameSecurityTokenHandlerRequirement>` element sets the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> property when a <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2f65d-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2f65d-126">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
    <userNameSecurityTokenHandlerRequirement membershipProviderName="AspNetSqlProvider/>  
</add>  
```
