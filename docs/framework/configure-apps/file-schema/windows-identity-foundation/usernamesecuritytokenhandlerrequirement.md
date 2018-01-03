---
title: '&lt;userNameSecurityTokenHandlerRequirement&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6ec3bac1-b014-49ae-843c-c54518cb709a
caps.latest.revision: "4"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 31e0c2cf10b8bc93ade0d417763075c4419ac19f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltusernamesecuritytokenhandlerrequirementgt"></a><span data-ttu-id="71052-102">&lt;userNameSecurityTokenHandlerRequirement&gt;</span><span class="sxs-lookup"><span data-stu-id="71052-102">&lt;userNameSecurityTokenHandlerRequirement&gt;</span></span>
<span data-ttu-id="71052-103">Proporciona la configuración para el <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> clase o clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="71052-103">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="71052-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="71052-104">\<system.identityModel></span></span>  
<span data-ttu-id="71052-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="71052-105">\<identityConfiguration></span></span>  
<span data-ttu-id="71052-106">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="71052-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="71052-107">\<add></span><span class="sxs-lookup"><span data-stu-id="71052-107">\<add></span></span>  
<span data-ttu-id="71052-108">\<userNameSecurityTokenHandlerRequirement ></span><span class="sxs-lookup"><span data-stu-id="71052-108">\<userNameSecurityTokenHandlerRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71052-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="71052-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="71052-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="71052-110">Attributes and Elements</span></span>  
 <span data-ttu-id="71052-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="71052-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="71052-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="71052-112">Attributes</span></span>  
  
|<span data-ttu-id="71052-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="71052-113">Attribute</span></span>|<span data-ttu-id="71052-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="71052-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="71052-115">membershipProviderName</span><span class="sxs-lookup"><span data-stu-id="71052-115">membershipProviderName</span></span>|<span data-ttu-id="71052-116">Especifica la <xref:System.Web.Security.MembershipProvider> que debe usar el controlador de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="71052-116">Specifies the <xref:System.Web.Security.MembershipProvider> that should be used by the security token handler.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="71052-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="71052-117">Child Elements</span></span>  
 <span data-ttu-id="71052-118">Ninguna</span><span class="sxs-lookup"><span data-stu-id="71052-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="71052-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="71052-119">Parent Elements</span></span>  
  
|<span data-ttu-id="71052-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="71052-120">Element</span></span>|<span data-ttu-id="71052-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="71052-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="71052-122">\<add></span><span class="sxs-lookup"><span data-stu-id="71052-122">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="71052-123">Agrega el controlador de token de seguridad especificado a la colección de controlador de token.</span><span class="sxs-lookup"><span data-stu-id="71052-123">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="71052-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="71052-124">Remarks</span></span>  
 <span data-ttu-id="71052-125">El `<userNameSecurityTokenHandlerRequirement>` conjuntos de elementos del <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> propiedad cuando un <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> se inicializa el objeto de configuración.</span><span class="sxs-lookup"><span data-stu-id="71052-125">The `<userNameSecurityTokenHandlerRequirement>` element sets the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> property when a <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="71052-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="71052-126">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
    <userNameSecurityTokenHandlerRequirement membershipProviderName="AspNetSqlProvider/>  
</add>  
```
