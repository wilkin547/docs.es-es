---
title: <sessionTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 496a1735-cbb7-49d5-a6aa-dd5550462073
author: BrucePerlerMS
ms.openlocfilehash: 0c575e02862884e8f7ecf062138c36fe731f8e19
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55271907"
---
# <a name="sessiontokenrequirement"></a><span data-ttu-id="09b25-101">\<sessionTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="09b25-101">\<sessionTokenRequirement></span></span>
<span data-ttu-id="09b25-102">Proporciona la configuración de la <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> clase o clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="09b25-102">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="09b25-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="09b25-103">\<system.identityModel></span></span>  
<span data-ttu-id="09b25-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="09b25-104">\<identityConfiguration></span></span>  
<span data-ttu-id="09b25-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="09b25-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="09b25-106">\<add></span><span class="sxs-lookup"><span data-stu-id="09b25-106">\<add></span></span>  
<span data-ttu-id="09b25-107">\<sessionTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="09b25-107">\<sessionTokenRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09b25-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="09b25-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="09b25-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="09b25-109">Attributes and Elements</span></span>  
 <span data-ttu-id="09b25-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="09b25-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="09b25-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="09b25-111">Attributes</span></span>  
  
|<span data-ttu-id="09b25-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="09b25-112">Attribute</span></span>|<span data-ttu-id="09b25-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="09b25-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="09b25-114">duración</span><span class="sxs-lookup"><span data-stu-id="09b25-114">lifetime</span></span>|<span data-ttu-id="09b25-115">Especifica la duración de los tokens de sesión.</span><span class="sxs-lookup"><span data-stu-id="09b25-115">Specifies the lifetime of session tokens.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="09b25-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="09b25-116">Child Elements</span></span>  
 <span data-ttu-id="09b25-117">Ninguna</span><span class="sxs-lookup"><span data-stu-id="09b25-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="09b25-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="09b25-118">Parent Elements</span></span>  
  
|<span data-ttu-id="09b25-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="09b25-119">Element</span></span>|<span data-ttu-id="09b25-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="09b25-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="09b25-121">\<add></span><span class="sxs-lookup"><span data-stu-id="09b25-121">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="09b25-122">Agrega el controlador de token de seguridad especificado a la colección de controladores de token.</span><span class="sxs-lookup"><span data-stu-id="09b25-122">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="09b25-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="09b25-123">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">           
    <sessionTokenRequirement lifetime="10:00" />  
</add>  
```
