---
title: '&lt;claimType&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d17b5831-9a2c-45c4-b0d1-68f48e72e861
caps.latest.revision: "4"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: c4ee8833578b082f25c427b13d77072d1954197f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="ltclaimtypegt"></a><span data-ttu-id="c040d-102">&lt;claimType&gt;</span><span class="sxs-lookup"><span data-stu-id="c040d-102">&lt;claimType&gt;</span></span>
<span data-ttu-id="c040d-103">Especifica una única notificación obligatorio u opcional para los tokens de seguridad entrantes.</span><span class="sxs-lookup"><span data-stu-id="c040d-103">Specifies a single optional or required claim for incoming security tokens.</span></span>  
  
 <span data-ttu-id="c040d-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="c040d-104">\<system.identityModel></span></span>  
<span data-ttu-id="c040d-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="c040d-105">\<identityConfiguration></span></span>  
<span data-ttu-id="c040d-106">\<claimTypeRequired ></span><span class="sxs-lookup"><span data-stu-id="c040d-106">\<claimTypeRequired></span></span>  
<span data-ttu-id="c040d-107">\<claimType ></span><span class="sxs-lookup"><span data-stu-id="c040d-107">\<claimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c040d-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c040d-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c040d-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c040d-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c040d-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c040d-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c040d-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="c040d-111">Attributes</span></span>  
  
|<span data-ttu-id="c040d-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="c040d-112">Attribute</span></span>|<span data-ttu-id="c040d-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="c040d-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c040d-114">type</span><span class="sxs-lookup"><span data-stu-id="c040d-114">type</span></span>|<span data-ttu-id="c040d-115">Tipo de notificación.</span><span class="sxs-lookup"><span data-stu-id="c040d-115">The claim type.</span></span> <span data-ttu-id="c040d-116">Normalmente un URI.</span><span class="sxs-lookup"><span data-stu-id="c040d-116">Typically a URI.</span></span> <span data-ttu-id="c040d-117">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="c040d-117">Required.</span></span>|  
|<span data-ttu-id="c040d-118">opcionales</span><span class="sxs-lookup"><span data-stu-id="c040d-118">optional</span></span>|<span data-ttu-id="c040d-119">Un valor booleano que especifica si el tipo de notificación es opcional.</span><span class="sxs-lookup"><span data-stu-id="c040d-119">A boolean value that specifies whether the claim type is optional.</span></span> <span data-ttu-id="c040d-120">Opcional.</span><span class="sxs-lookup"><span data-stu-id="c040d-120">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c040d-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c040d-121">Child Elements</span></span>  
 <span data-ttu-id="c040d-122">Ninguna</span><span class="sxs-lookup"><span data-stu-id="c040d-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c040d-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c040d-123">Parent Elements</span></span>  
  
|<span data-ttu-id="c040d-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="c040d-124">Element</span></span>|<span data-ttu-id="c040d-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="c040d-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c040d-126">\<claimTypeRequired ></span><span class="sxs-lookup"><span data-stu-id="c040d-126">\<claimTypeRequired></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtyperequired.md)|<span data-ttu-id="c040d-127">Especifica el conjunto de notificaciones necesarias para los tokens de seguridad entrantes.</span><span class="sxs-lookup"><span data-stu-id="c040d-127">Specifies the set of required claims for incoming security tokens.</span></span>|
