---
title: <sessionTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 496a1735-cbb7-49d5-a6aa-dd5550462073
author: BrucePerlerMS
ms.openlocfilehash: 0c575e02862884e8f7ecf062138c36fe731f8e19
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61793775"
---
# <a name="sessiontokenrequirement"></a><span data-ttu-id="4ec62-101">\<sessionTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="4ec62-101">\<sessionTokenRequirement></span></span>
<span data-ttu-id="4ec62-102">Proporciona la configuración de la <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> clase o clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="4ec62-102">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="4ec62-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="4ec62-103">\<system.identityModel></span></span>  
<span data-ttu-id="4ec62-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="4ec62-104">\<identityConfiguration></span></span>  
<span data-ttu-id="4ec62-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="4ec62-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="4ec62-106">\<add></span><span class="sxs-lookup"><span data-stu-id="4ec62-106">\<add></span></span>  
<span data-ttu-id="4ec62-107">\<sessionTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="4ec62-107">\<sessionTokenRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ec62-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4ec62-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4ec62-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4ec62-109">Attributes and Elements</span></span>  
 <span data-ttu-id="4ec62-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="4ec62-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4ec62-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="4ec62-111">Attributes</span></span>  
  
|<span data-ttu-id="4ec62-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="4ec62-112">Attribute</span></span>|<span data-ttu-id="4ec62-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="4ec62-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4ec62-114">duración</span><span class="sxs-lookup"><span data-stu-id="4ec62-114">lifetime</span></span>|<span data-ttu-id="4ec62-115">Especifica la duración de los tokens de sesión.</span><span class="sxs-lookup"><span data-stu-id="4ec62-115">Specifies the lifetime of session tokens.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4ec62-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4ec62-116">Child Elements</span></span>  
 <span data-ttu-id="4ec62-117">Ninguna</span><span class="sxs-lookup"><span data-stu-id="4ec62-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4ec62-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4ec62-118">Parent Elements</span></span>  
  
|<span data-ttu-id="4ec62-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="4ec62-119">Element</span></span>|<span data-ttu-id="4ec62-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="4ec62-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4ec62-121">\<add></span><span class="sxs-lookup"><span data-stu-id="4ec62-121">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="4ec62-122">Agrega el controlador de token de seguridad especificado a la colección de controladores de token.</span><span class="sxs-lookup"><span data-stu-id="4ec62-122">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="4ec62-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4ec62-123">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">           
    <sessionTokenRequirement lifetime="10:00" />  
</add>  
```
