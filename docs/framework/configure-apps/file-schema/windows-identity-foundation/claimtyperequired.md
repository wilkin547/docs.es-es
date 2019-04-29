---
title: <claimTypeRequired>
ms.date: 03/30/2017
ms.assetid: c469d71f-6c77-4a24-97aa-53efa126ceef
author: BrucePerlerMS
ms.openlocfilehash: eafaf253e27db632f17acfce4445a07d18b109aa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61778461"
---
# <a name="claimtyperequired"></a><span data-ttu-id="c8d2b-101">\<claimTypeRequired></span><span class="sxs-lookup"><span data-stu-id="c8d2b-101">\<claimTypeRequired></span></span>
<span data-ttu-id="c8d2b-102">Especifica el conjunto de notificaciones necesarias para los tokens de seguridad entrantes.</span><span class="sxs-lookup"><span data-stu-id="c8d2b-102">Specifies the set of required claims for incoming security tokens.</span></span>  
  
 <span data-ttu-id="c8d2b-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="c8d2b-103">\<system.identityModel></span></span>  
<span data-ttu-id="c8d2b-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="c8d2b-104">\<identityConfiguration></span></span>  
<span data-ttu-id="c8d2b-105">\<claimTypeRequired></span><span class="sxs-lookup"><span data-stu-id="c8d2b-105">\<claimTypeRequired></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8d2b-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c8d2b-106">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimTypeRequired>  
    </claimTypeRequired>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c8d2b-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c8d2b-107">Attributes and Elements</span></span>  
 <span data-ttu-id="c8d2b-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c8d2b-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c8d2b-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="c8d2b-109">Attributes</span></span>  
 <span data-ttu-id="c8d2b-110">Ninguna</span><span class="sxs-lookup"><span data-stu-id="c8d2b-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c8d2b-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c8d2b-111">Child Elements</span></span>  
  
|<span data-ttu-id="c8d2b-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="c8d2b-112">Element</span></span>|<span data-ttu-id="c8d2b-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="c8d2b-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c8d2b-114">\<claimType></span><span class="sxs-lookup"><span data-stu-id="c8d2b-114">\<claimType></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtype.md)|<span data-ttu-id="c8d2b-115">Especifica una única notificación opcional u obligatoria para los tokens de seguridad entrantes.</span><span class="sxs-lookup"><span data-stu-id="c8d2b-115">Specifies a single optional or required claim for incoming security tokens.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c8d2b-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c8d2b-116">Parent Elements</span></span>  
  
|<span data-ttu-id="c8d2b-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="c8d2b-117">Element</span></span>|<span data-ttu-id="c8d2b-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="c8d2b-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c8d2b-119">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="c8d2b-119">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="c8d2b-120">Especifica los valores de identidad de nivel de servicio.</span><span class="sxs-lookup"><span data-stu-id="c8d2b-120">Specifies service-level identity settings.</span></span>|
