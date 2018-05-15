---
title: '&lt;sessionTokenRequirement&gt;'
ms.date: 03/30/2017
ms.assetid: 496a1735-cbb7-49d5-a6aa-dd5550462073
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 6c40948633eaf892db06e9bba756158dfc3c4a2e
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltsessiontokenrequirementgt"></a><span data-ttu-id="3446b-102">&lt;sessionTokenRequirement&gt;</span><span class="sxs-lookup"><span data-stu-id="3446b-102">&lt;sessionTokenRequirement&gt;</span></span>
<span data-ttu-id="3446b-103">Proporciona la configuración para el <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> clase o clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="3446b-103">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="3446b-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="3446b-104">\<system.identityModel></span></span>  
<span data-ttu-id="3446b-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="3446b-105">\<identityConfiguration></span></span>  
<span data-ttu-id="3446b-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="3446b-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="3446b-107">\<add></span><span class="sxs-lookup"><span data-stu-id="3446b-107">\<add></span></span>  
<span data-ttu-id="3446b-108">\<sessionTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="3446b-108">\<sessionTokenRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3446b-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3446b-109">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">  
        <sessionTokenRequirement lifetime=TimeSpan >  
        </sessionTokenRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3446b-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3446b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3446b-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3446b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3446b-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="3446b-112">Attributes</span></span>  
  
|<span data-ttu-id="3446b-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="3446b-113">Attribute</span></span>|<span data-ttu-id="3446b-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="3446b-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3446b-115">duración</span><span class="sxs-lookup"><span data-stu-id="3446b-115">lifetime</span></span>|<span data-ttu-id="3446b-116">Especifica la duración de token de sesión.</span><span class="sxs-lookup"><span data-stu-id="3446b-116">Specifies the lifetime of session tokens.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3446b-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3446b-117">Child Elements</span></span>  
 <span data-ttu-id="3446b-118">Ninguna</span><span class="sxs-lookup"><span data-stu-id="3446b-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3446b-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3446b-119">Parent Elements</span></span>  
  
|<span data-ttu-id="3446b-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="3446b-120">Element</span></span>|<span data-ttu-id="3446b-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="3446b-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3446b-122">\<add></span><span class="sxs-lookup"><span data-stu-id="3446b-122">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="3446b-123">Agrega el controlador de token de seguridad especificado a la colección de controlador de token.</span><span class="sxs-lookup"><span data-stu-id="3446b-123">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="3446b-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3446b-124">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">           
    <sessionTokenRequirement lifetime="10:00" />  
</add>  
```
