---
title: <sessionTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 496a1735-cbb7-49d5-a6aa-dd5550462073
author: BrucePerlerMS
ms.openlocfilehash: 254d34149892abeaf31b9227f7567eb0a66ec0b6
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943676"
---
# <a name="sessiontokenrequirement"></a><span data-ttu-id="56e52-101">\<sessionTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="56e52-101">\<sessionTokenRequirement></span></span>
<span data-ttu-id="56e52-102">Proporciona la configuración para <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> la clase o las clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="56e52-102">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="56e52-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="56e52-103">\<system.identityModel></span></span>  
<span data-ttu-id="56e52-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="56e52-104">\<identityConfiguration></span></span>  
<span data-ttu-id="56e52-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="56e52-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="56e52-106">\<add></span><span class="sxs-lookup"><span data-stu-id="56e52-106">\<add></span></span>  
<span data-ttu-id="56e52-107">\<sessionTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="56e52-107">\<sessionTokenRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56e52-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="56e52-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="56e52-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="56e52-109">Attributes and Elements</span></span>  
 <span data-ttu-id="56e52-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="56e52-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="56e52-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="56e52-111">Attributes</span></span>  
  
|<span data-ttu-id="56e52-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="56e52-112">Attribute</span></span>|<span data-ttu-id="56e52-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="56e52-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="56e52-114">duración</span><span class="sxs-lookup"><span data-stu-id="56e52-114">lifetime</span></span>|<span data-ttu-id="56e52-115">Especifica la duración de los tokens de sesión.</span><span class="sxs-lookup"><span data-stu-id="56e52-115">Specifies the lifetime of session tokens.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="56e52-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="56e52-116">Child Elements</span></span>  
 <span data-ttu-id="56e52-117">None</span><span class="sxs-lookup"><span data-stu-id="56e52-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="56e52-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="56e52-118">Parent Elements</span></span>  
  
|<span data-ttu-id="56e52-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="56e52-119">Element</span></span>|<span data-ttu-id="56e52-120">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="56e52-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="56e52-121">\<add></span><span class="sxs-lookup"><span data-stu-id="56e52-121">\<add></span></span>](add.md)|<span data-ttu-id="56e52-122">Agrega el controlador de tokens de seguridad especificado a la colección de controladores de tokens.</span><span class="sxs-lookup"><span data-stu-id="56e52-122">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="56e52-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="56e52-123">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">           
    <sessionTokenRequirement lifetime="10:00" />  
</add>  
```
