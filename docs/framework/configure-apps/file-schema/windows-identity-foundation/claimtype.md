---
title: <claimType>
ms.date: 03/30/2017
ms.assetid: d17b5831-9a2c-45c4-b0d1-68f48e72e861
author: BrucePerlerMS
ms.openlocfilehash: 6bc185572528d4229ee53f1421eaa5bf27b053e6
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55267240"
---
# <a name="claimtype"></a><span data-ttu-id="d79b2-101">\<claimType></span><span class="sxs-lookup"><span data-stu-id="d79b2-101">\<claimType></span></span>
<span data-ttu-id="d79b2-102">Especifica una única notificación opcional u obligatoria para los tokens de seguridad entrantes.</span><span class="sxs-lookup"><span data-stu-id="d79b2-102">Specifies a single optional or required claim for incoming security tokens.</span></span>  
  
 <span data-ttu-id="d79b2-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="d79b2-103">\<system.identityModel></span></span>  
<span data-ttu-id="d79b2-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="d79b2-104">\<identityConfiguration></span></span>  
<span data-ttu-id="d79b2-105">\<claimTypeRequired></span><span class="sxs-lookup"><span data-stu-id="d79b2-105">\<claimTypeRequired></span></span>  
<span data-ttu-id="d79b2-106">\<claimType></span><span class="sxs-lookup"><span data-stu-id="d79b2-106">\<claimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d79b2-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d79b2-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d79b2-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d79b2-108">Attributes and Elements</span></span>  
 <span data-ttu-id="d79b2-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d79b2-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d79b2-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="d79b2-110">Attributes</span></span>  
  
|<span data-ttu-id="d79b2-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="d79b2-111">Attribute</span></span>|<span data-ttu-id="d79b2-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="d79b2-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d79b2-113">type</span><span class="sxs-lookup"><span data-stu-id="d79b2-113">type</span></span>|<span data-ttu-id="d79b2-114">Tipo de notificación.</span><span class="sxs-lookup"><span data-stu-id="d79b2-114">The claim type.</span></span> <span data-ttu-id="d79b2-115">Normalmente, un URI.</span><span class="sxs-lookup"><span data-stu-id="d79b2-115">Typically a URI.</span></span> <span data-ttu-id="d79b2-116">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="d79b2-116">Required.</span></span>|  
|<span data-ttu-id="d79b2-117">opcionales</span><span class="sxs-lookup"><span data-stu-id="d79b2-117">optional</span></span>|<span data-ttu-id="d79b2-118">Un valor booleano que especifica si el tipo de notificación es opcional.</span><span class="sxs-lookup"><span data-stu-id="d79b2-118">A boolean value that specifies whether the claim type is optional.</span></span> <span data-ttu-id="d79b2-119">Opcional.</span><span class="sxs-lookup"><span data-stu-id="d79b2-119">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d79b2-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d79b2-120">Child Elements</span></span>  
 <span data-ttu-id="d79b2-121">Ninguna</span><span class="sxs-lookup"><span data-stu-id="d79b2-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d79b2-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d79b2-122">Parent Elements</span></span>  
  
|<span data-ttu-id="d79b2-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="d79b2-123">Element</span></span>|<span data-ttu-id="d79b2-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="d79b2-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d79b2-125">\<claimTypeRequired></span><span class="sxs-lookup"><span data-stu-id="d79b2-125">\<claimTypeRequired></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtyperequired.md)|<span data-ttu-id="d79b2-126">Especifica el conjunto de notificaciones necesarias para los tokens de seguridad entrantes.</span><span class="sxs-lookup"><span data-stu-id="d79b2-126">Specifies the set of required claims for incoming security tokens.</span></span>|
