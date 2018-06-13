---
title: '&lt;ClaimType&gt;'
ms.date: 03/30/2017
ms.assetid: d17b5831-9a2c-45c4-b0d1-68f48e72e861
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 94f8586a9ca63b8c1f1128cdda4a74ccfe0f5416
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32767432"
---
# <a name="ltclaimtypegt"></a><span data-ttu-id="8e875-102">&lt;ClaimType&gt;</span><span class="sxs-lookup"><span data-stu-id="8e875-102">&lt;claimType&gt;</span></span>
<span data-ttu-id="8e875-103">Especifica una única notificación obligatorio u opcional para los tokens de seguridad entrantes.</span><span class="sxs-lookup"><span data-stu-id="8e875-103">Specifies a single optional or required claim for incoming security tokens.</span></span>  
  
 <span data-ttu-id="8e875-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="8e875-104">\<system.identityModel></span></span>  
<span data-ttu-id="8e875-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="8e875-105">\<identityConfiguration></span></span>  
<span data-ttu-id="8e875-106">\<claimTypeRequired ></span><span class="sxs-lookup"><span data-stu-id="8e875-106">\<claimTypeRequired></span></span>  
<span data-ttu-id="8e875-107">\<claimType ></span><span class="sxs-lookup"><span data-stu-id="8e875-107">\<claimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e875-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8e875-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8e875-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="8e875-109">Attributes and Elements</span></span>  
 <span data-ttu-id="8e875-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="8e875-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8e875-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="8e875-111">Attributes</span></span>  
  
|<span data-ttu-id="8e875-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="8e875-112">Attribute</span></span>|<span data-ttu-id="8e875-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="8e875-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8e875-114">type</span><span class="sxs-lookup"><span data-stu-id="8e875-114">type</span></span>|<span data-ttu-id="8e875-115">Tipo de notificación.</span><span class="sxs-lookup"><span data-stu-id="8e875-115">The claim type.</span></span> <span data-ttu-id="8e875-116">Normalmente un URI.</span><span class="sxs-lookup"><span data-stu-id="8e875-116">Typically a URI.</span></span> <span data-ttu-id="8e875-117">Requerido.</span><span class="sxs-lookup"><span data-stu-id="8e875-117">Required.</span></span>|  
|<span data-ttu-id="8e875-118">opcionales</span><span class="sxs-lookup"><span data-stu-id="8e875-118">optional</span></span>|<span data-ttu-id="8e875-119">Un valor booleano que especifica si el tipo de notificación es opcional.</span><span class="sxs-lookup"><span data-stu-id="8e875-119">A boolean value that specifies whether the claim type is optional.</span></span> <span data-ttu-id="8e875-120">Opcional.</span><span class="sxs-lookup"><span data-stu-id="8e875-120">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8e875-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="8e875-121">Child Elements</span></span>  
 <span data-ttu-id="8e875-122">Ninguna</span><span class="sxs-lookup"><span data-stu-id="8e875-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8e875-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8e875-123">Parent Elements</span></span>  
  
|<span data-ttu-id="8e875-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="8e875-124">Element</span></span>|<span data-ttu-id="8e875-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="8e875-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8e875-126">\<claimTypeRequired ></span><span class="sxs-lookup"><span data-stu-id="8e875-126">\<claimTypeRequired></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtyperequired.md)|<span data-ttu-id="8e875-127">Especifica el conjunto de notificaciones necesarias para los tokens de seguridad entrantes.</span><span class="sxs-lookup"><span data-stu-id="8e875-127">Specifies the set of required claims for incoming security tokens.</span></span>|
