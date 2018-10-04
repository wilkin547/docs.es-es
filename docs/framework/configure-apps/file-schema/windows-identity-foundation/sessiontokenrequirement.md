---
title: '&lt;sessionTokenRequirement&gt;'
ms.date: 03/30/2017
ms.assetid: 496a1735-cbb7-49d5-a6aa-dd5550462073
author: BrucePerlerMS
ms.openlocfilehash: 4d5d2348f04ace7596a3a513c5106ea612dc17b7
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "48792934"
---
# <a name="ltsessiontokenrequirementgt"></a><span data-ttu-id="827c9-102">&lt;sessionTokenRequirement&gt;</span><span class="sxs-lookup"><span data-stu-id="827c9-102">&lt;sessionTokenRequirement&gt;</span></span>
<span data-ttu-id="827c9-103">Proporciona la configuración de la <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> clase o clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="827c9-103">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="827c9-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="827c9-104">\<system.identityModel></span></span>  
<span data-ttu-id="827c9-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="827c9-105">\<identityConfiguration></span></span>  
<span data-ttu-id="827c9-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="827c9-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="827c9-107">\<add></span><span class="sxs-lookup"><span data-stu-id="827c9-107">\<add></span></span>  
<span data-ttu-id="827c9-108">\<sessionTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="827c9-108">\<sessionTokenRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="827c9-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="827c9-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="827c9-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="827c9-110">Attributes and Elements</span></span>  
 <span data-ttu-id="827c9-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="827c9-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="827c9-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="827c9-112">Attributes</span></span>  
  
|<span data-ttu-id="827c9-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="827c9-113">Attribute</span></span>|<span data-ttu-id="827c9-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="827c9-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="827c9-115">duración</span><span class="sxs-lookup"><span data-stu-id="827c9-115">lifetime</span></span>|<span data-ttu-id="827c9-116">Especifica la duración de los tokens de sesión.</span><span class="sxs-lookup"><span data-stu-id="827c9-116">Specifies the lifetime of session tokens.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="827c9-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="827c9-117">Child Elements</span></span>  
 <span data-ttu-id="827c9-118">Ninguna</span><span class="sxs-lookup"><span data-stu-id="827c9-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="827c9-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="827c9-119">Parent Elements</span></span>  
  
|<span data-ttu-id="827c9-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="827c9-120">Element</span></span>|<span data-ttu-id="827c9-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="827c9-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="827c9-122">\<add></span><span class="sxs-lookup"><span data-stu-id="827c9-122">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="827c9-123">Agrega el controlador de token de seguridad especificado a la colección de controladores de token.</span><span class="sxs-lookup"><span data-stu-id="827c9-123">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="827c9-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="827c9-124">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">           
    <sessionTokenRequirement lifetime="10:00" />  
</add>  
```
