---
title: '&lt;userNameSecurityTokenHandlerRequirement&gt;'
ms.date: 03/30/2017
ms.assetid: 6ec3bac1-b014-49ae-843c-c54518cb709a
author: BrucePerlerMS
ms.openlocfilehash: dfcaad8b150321fda2a86e601bf57204cbdc1a0e
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2018
ms.locfileid: "47216021"
---
# <a name="ltusernamesecuritytokenhandlerrequirementgt"></a><span data-ttu-id="a33ce-102">&lt;userNameSecurityTokenHandlerRequirement&gt;</span><span class="sxs-lookup"><span data-stu-id="a33ce-102">&lt;userNameSecurityTokenHandlerRequirement&gt;</span></span>
<span data-ttu-id="a33ce-103">Proporciona la configuración de la <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> clase o clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="a33ce-103">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="a33ce-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="a33ce-104">\<system.identityModel></span></span>  
<span data-ttu-id="a33ce-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="a33ce-105">\<identityConfiguration></span></span>  
<span data-ttu-id="a33ce-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="a33ce-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="a33ce-107">\<add></span><span class="sxs-lookup"><span data-stu-id="a33ce-107">\<add></span></span>  
<span data-ttu-id="a33ce-108">\<userNameSecurityTokenHandlerRequirement ></span><span class="sxs-lookup"><span data-stu-id="a33ce-108">\<userNameSecurityTokenHandlerRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a33ce-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a33ce-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a33ce-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a33ce-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a33ce-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a33ce-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a33ce-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="a33ce-112">Attributes</span></span>  
  
|<span data-ttu-id="a33ce-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="a33ce-113">Attribute</span></span>|<span data-ttu-id="a33ce-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="a33ce-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a33ce-115">membershipProviderName</span><span class="sxs-lookup"><span data-stu-id="a33ce-115">membershipProviderName</span></span>|<span data-ttu-id="a33ce-116">Especifica el <xref:System.Web.Security.MembershipProvider> que debe usar el controlador de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="a33ce-116">Specifies the <xref:System.Web.Security.MembershipProvider> that should be used by the security token handler.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a33ce-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a33ce-117">Child Elements</span></span>  
 <span data-ttu-id="a33ce-118">Ninguna</span><span class="sxs-lookup"><span data-stu-id="a33ce-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a33ce-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a33ce-119">Parent Elements</span></span>  
  
|<span data-ttu-id="a33ce-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="a33ce-120">Element</span></span>|<span data-ttu-id="a33ce-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="a33ce-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a33ce-122">\<add></span><span class="sxs-lookup"><span data-stu-id="a33ce-122">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="a33ce-123">Agrega el controlador de token de seguridad especificado a la colección de controladores de token.</span><span class="sxs-lookup"><span data-stu-id="a33ce-123">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a33ce-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a33ce-124">Remarks</span></span>  
 <span data-ttu-id="a33ce-125">El `<userNameSecurityTokenHandlerRequirement>` conjuntos de elementos del <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> propiedad cuando un <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> se inicializa el objeto de configuración.</span><span class="sxs-lookup"><span data-stu-id="a33ce-125">The `<userNameSecurityTokenHandlerRequirement>` element sets the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> property when a <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a33ce-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a33ce-126">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
    <userNameSecurityTokenHandlerRequirement membershipProviderName="AspNetSqlProvider/>  
</add>  
```
