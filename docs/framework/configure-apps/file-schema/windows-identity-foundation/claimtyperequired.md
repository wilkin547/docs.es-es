---
title: '&lt;claimTypeRequired&gt;'
ms.date: 03/30/2017
ms.assetid: c469d71f-6c77-4a24-97aa-53efa126ceef
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 6fb600aac46b3ee5cb54fa904d35ac7b7ed90719
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltclaimtyperequiredgt"></a><span data-ttu-id="d8746-102">&lt;claimTypeRequired&gt;</span><span class="sxs-lookup"><span data-stu-id="d8746-102">&lt;claimTypeRequired&gt;</span></span>
<span data-ttu-id="d8746-103">Especifica el conjunto de notificaciones necesarias para los tokens de seguridad entrantes.</span><span class="sxs-lookup"><span data-stu-id="d8746-103">Specifies the set of required claims for incoming security tokens.</span></span>  
  
 <span data-ttu-id="d8746-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="d8746-104">\<system.identityModel></span></span>  
<span data-ttu-id="d8746-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="d8746-105">\<identityConfiguration></span></span>  
<span data-ttu-id="d8746-106">\<claimTypeRequired ></span><span class="sxs-lookup"><span data-stu-id="d8746-106">\<claimTypeRequired></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8746-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d8746-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimTypeRequired>  
    </claimTypeRequired>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d8746-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d8746-108">Attributes and Elements</span></span>  
 <span data-ttu-id="d8746-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d8746-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d8746-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="d8746-110">Attributes</span></span>  
 <span data-ttu-id="d8746-111">Ninguna</span><span class="sxs-lookup"><span data-stu-id="d8746-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d8746-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d8746-112">Child Elements</span></span>  
  
|<span data-ttu-id="d8746-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="d8746-113">Element</span></span>|<span data-ttu-id="d8746-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="d8746-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d8746-115">\<claimType ></span><span class="sxs-lookup"><span data-stu-id="d8746-115">\<claimType></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtype.md)|<span data-ttu-id="d8746-116">Especifica una única notificación obligatorio u opcional para los tokens de seguridad entrantes.</span><span class="sxs-lookup"><span data-stu-id="d8746-116">Specifies a single optional or required claim for incoming security tokens.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d8746-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d8746-117">Parent Elements</span></span>  
  
|<span data-ttu-id="d8746-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="d8746-118">Element</span></span>|<span data-ttu-id="d8746-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="d8746-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d8746-120">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="d8746-120">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="d8746-121">Especifica los valores de identidad de nivel de servicio.</span><span class="sxs-lookup"><span data-stu-id="d8746-121">Specifies service-level identity settings.</span></span>|
