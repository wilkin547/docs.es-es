---
title: '&lt;claimTypeRequired&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c469d71f-6c77-4a24-97aa-53efa126ceef
caps.latest.revision: "5"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 491277e39b29d7c3e0a0d69ec8745b2c6718a91e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltclaimtyperequiredgt"></a><span data-ttu-id="9486e-102">&lt;claimTypeRequired&gt;</span><span class="sxs-lookup"><span data-stu-id="9486e-102">&lt;claimTypeRequired&gt;</span></span>
<span data-ttu-id="9486e-103">Especifica el conjunto de notificaciones necesarias para los tokens de seguridad entrantes.</span><span class="sxs-lookup"><span data-stu-id="9486e-103">Specifies the set of required claims for incoming security tokens.</span></span>  
  
 <span data-ttu-id="9486e-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="9486e-104">\<system.identityModel></span></span>  
<span data-ttu-id="9486e-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="9486e-105">\<identityConfiguration></span></span>  
<span data-ttu-id="9486e-106">\<claimTypeRequired ></span><span class="sxs-lookup"><span data-stu-id="9486e-106">\<claimTypeRequired></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9486e-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9486e-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimTypeRequired>  
    </claimTypeRequired>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9486e-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9486e-108">Attributes and Elements</span></span>  
 <span data-ttu-id="9486e-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9486e-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9486e-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="9486e-110">Attributes</span></span>  
 <span data-ttu-id="9486e-111">Ninguna</span><span class="sxs-lookup"><span data-stu-id="9486e-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9486e-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9486e-112">Child Elements</span></span>  
  
|<span data-ttu-id="9486e-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="9486e-113">Element</span></span>|<span data-ttu-id="9486e-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="9486e-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9486e-115">\<claimType ></span><span class="sxs-lookup"><span data-stu-id="9486e-115">\<claimType></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtype.md)|<span data-ttu-id="9486e-116">Especifica una única notificación obligatorio u opcional para los tokens de seguridad entrantes.</span><span class="sxs-lookup"><span data-stu-id="9486e-116">Specifies a single optional or required claim for incoming security tokens.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9486e-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9486e-117">Parent Elements</span></span>  
  
|<span data-ttu-id="9486e-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="9486e-118">Element</span></span>|<span data-ttu-id="9486e-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="9486e-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9486e-120">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="9486e-120">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="9486e-121">Especifica los valores de identidad de nivel de servicio.</span><span class="sxs-lookup"><span data-stu-id="9486e-121">Specifies service-level identity settings.</span></span>|
