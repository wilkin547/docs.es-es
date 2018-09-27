---
title: '&lt;Tipo de notificación&gt;'
ms.date: 03/30/2017
ms.assetid: d17b5831-9a2c-45c4-b0d1-68f48e72e861
author: BrucePerlerMS
ms.openlocfilehash: 805377565b6e835fd9ffba915a003bc56529a3b6
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2018
ms.locfileid: "47234969"
---
# <a name="ltclaimtypegt"></a><span data-ttu-id="f7b48-102">&lt;Tipo de notificación&gt;</span><span class="sxs-lookup"><span data-stu-id="f7b48-102">&lt;claimType&gt;</span></span>
<span data-ttu-id="f7b48-103">Especifica una única notificación opcional u obligatoria para los tokens de seguridad entrantes.</span><span class="sxs-lookup"><span data-stu-id="f7b48-103">Specifies a single optional or required claim for incoming security tokens.</span></span>  
  
 <span data-ttu-id="f7b48-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="f7b48-104">\<system.identityModel></span></span>  
<span data-ttu-id="f7b48-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="f7b48-105">\<identityConfiguration></span></span>  
<span data-ttu-id="f7b48-106">\<claimTypeRequired ></span><span class="sxs-lookup"><span data-stu-id="f7b48-106">\<claimTypeRequired></span></span>  
<span data-ttu-id="f7b48-107">\<claimType ></span><span class="sxs-lookup"><span data-stu-id="f7b48-107">\<claimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7b48-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f7b48-108">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimTypeRequired>  
      <claimType type=URI optional=xs:boolean >  
      </claimType>  
    </claimTypeRequired>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f7b48-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f7b48-109">Attributes and Elements</span></span>  
 <span data-ttu-id="f7b48-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f7b48-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f7b48-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="f7b48-111">Attributes</span></span>  
  
|<span data-ttu-id="f7b48-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="f7b48-112">Attribute</span></span>|<span data-ttu-id="f7b48-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="f7b48-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f7b48-114">type</span><span class="sxs-lookup"><span data-stu-id="f7b48-114">type</span></span>|<span data-ttu-id="f7b48-115">Tipo de notificación.</span><span class="sxs-lookup"><span data-stu-id="f7b48-115">The claim type.</span></span> <span data-ttu-id="f7b48-116">Normalmente, un URI.</span><span class="sxs-lookup"><span data-stu-id="f7b48-116">Typically a URI.</span></span> <span data-ttu-id="f7b48-117">Requerido.</span><span class="sxs-lookup"><span data-stu-id="f7b48-117">Required.</span></span>|  
|<span data-ttu-id="f7b48-118">opcionales</span><span class="sxs-lookup"><span data-stu-id="f7b48-118">optional</span></span>|<span data-ttu-id="f7b48-119">Un valor booleano que especifica si el tipo de notificación es opcional.</span><span class="sxs-lookup"><span data-stu-id="f7b48-119">A boolean value that specifies whether the claim type is optional.</span></span> <span data-ttu-id="f7b48-120">Opcional.</span><span class="sxs-lookup"><span data-stu-id="f7b48-120">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f7b48-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f7b48-121">Child Elements</span></span>  
 <span data-ttu-id="f7b48-122">Ninguna</span><span class="sxs-lookup"><span data-stu-id="f7b48-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f7b48-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f7b48-123">Parent Elements</span></span>  
  
|<span data-ttu-id="f7b48-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="f7b48-124">Element</span></span>|<span data-ttu-id="f7b48-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="f7b48-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f7b48-126">\<claimTypeRequired ></span><span class="sxs-lookup"><span data-stu-id="f7b48-126">\<claimTypeRequired></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtyperequired.md)|<span data-ttu-id="f7b48-127">Especifica el conjunto de notificaciones necesarias para los tokens de seguridad entrantes.</span><span class="sxs-lookup"><span data-stu-id="f7b48-127">Specifies the set of required claims for incoming security tokens.</span></span>|
