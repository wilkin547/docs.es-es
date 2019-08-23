---
title: <userNameSecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: 6ec3bac1-b014-49ae-843c-c54518cb709a
author: BrucePerlerMS
ms.openlocfilehash: fed8964e03b80e365fdc5eafd45b4fc372a6e352
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944251"
---
# <a name="usernamesecuritytokenhandlerrequirement"></a><span data-ttu-id="253b5-101">\<userNameSecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="253b5-101">\<userNameSecurityTokenHandlerRequirement></span></span>
<span data-ttu-id="253b5-102">Proporciona la configuración para <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> la clase o las clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="253b5-102">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="253b5-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="253b5-103">\<system.identityModel></span></span>  
<span data-ttu-id="253b5-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="253b5-104">\<identityConfiguration></span></span>  
<span data-ttu-id="253b5-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="253b5-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="253b5-106">\<add></span><span class="sxs-lookup"><span data-stu-id="253b5-106">\<add></span></span>  
<span data-ttu-id="253b5-107">\<userNameSecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="253b5-107">\<userNameSecurityTokenHandlerRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="253b5-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="253b5-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="253b5-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="253b5-109">Attributes and Elements</span></span>  
 <span data-ttu-id="253b5-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="253b5-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="253b5-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="253b5-111">Attributes</span></span>  
  
|<span data-ttu-id="253b5-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="253b5-112">Attribute</span></span>|<span data-ttu-id="253b5-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="253b5-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="253b5-114">membershipProviderName</span><span class="sxs-lookup"><span data-stu-id="253b5-114">membershipProviderName</span></span>|<span data-ttu-id="253b5-115">Especifica el <xref:System.Web.Security.MembershipProvider> que debe usar el controlador de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="253b5-115">Specifies the <xref:System.Web.Security.MembershipProvider> that should be used by the security token handler.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="253b5-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="253b5-116">Child Elements</span></span>  
 <span data-ttu-id="253b5-117">None</span><span class="sxs-lookup"><span data-stu-id="253b5-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="253b5-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="253b5-118">Parent Elements</span></span>  
  
|<span data-ttu-id="253b5-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="253b5-119">Element</span></span>|<span data-ttu-id="253b5-120">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="253b5-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="253b5-121">\<add></span><span class="sxs-lookup"><span data-stu-id="253b5-121">\<add></span></span>](add.md)|<span data-ttu-id="253b5-122">Agrega el controlador de tokens de seguridad especificado a la colección de controladores de tokens.</span><span class="sxs-lookup"><span data-stu-id="253b5-122">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="253b5-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="253b5-123">Remarks</span></span>  
 <span data-ttu-id="253b5-124">El `<userNameSecurityTokenHandlerRequirement>` elemento establece la <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> propiedad cuando se <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> Inicializa un objeto a partir de la configuración.</span><span class="sxs-lookup"><span data-stu-id="253b5-124">The `<userNameSecurityTokenHandlerRequirement>` element sets the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> property when a <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="253b5-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="253b5-125">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
    <userNameSecurityTokenHandlerRequirement membershipProviderName="AspNetSqlProvider/>  
</add>  
```
