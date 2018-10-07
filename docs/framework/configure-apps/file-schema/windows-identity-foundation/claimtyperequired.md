---
title: '&lt;claimTypeRequired&gt;'
ms.date: 03/30/2017
ms.assetid: c469d71f-6c77-4a24-97aa-53efa126ceef
author: BrucePerlerMS
ms.openlocfilehash: df4494de6b76943849db2bedef8f43ad894b6bd1
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2018
ms.locfileid: "48837768"
---
# <a name="ltclaimtyperequiredgt"></a><span data-ttu-id="9539d-102">&lt;claimTypeRequired&gt;</span><span class="sxs-lookup"><span data-stu-id="9539d-102">&lt;claimTypeRequired&gt;</span></span>
<span data-ttu-id="9539d-103">Especifica el conjunto de notificaciones necesarias para los tokens de seguridad entrantes.</span><span class="sxs-lookup"><span data-stu-id="9539d-103">Specifies the set of required claims for incoming security tokens.</span></span>  
  
 <span data-ttu-id="9539d-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="9539d-104">\<system.identityModel></span></span>  
<span data-ttu-id="9539d-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="9539d-105">\<identityConfiguration></span></span>  
<span data-ttu-id="9539d-106">\<claimTypeRequired ></span><span class="sxs-lookup"><span data-stu-id="9539d-106">\<claimTypeRequired></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9539d-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9539d-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimTypeRequired>  
    </claimTypeRequired>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9539d-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9539d-108">Attributes and Elements</span></span>  
 <span data-ttu-id="9539d-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9539d-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9539d-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="9539d-110">Attributes</span></span>  
 <span data-ttu-id="9539d-111">Ninguna</span><span class="sxs-lookup"><span data-stu-id="9539d-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9539d-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9539d-112">Child Elements</span></span>  
  
|<span data-ttu-id="9539d-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="9539d-113">Element</span></span>|<span data-ttu-id="9539d-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="9539d-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9539d-115">\<claimType ></span><span class="sxs-lookup"><span data-stu-id="9539d-115">\<claimType></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtype.md)|<span data-ttu-id="9539d-116">Especifica una única notificación opcional u obligatoria para los tokens de seguridad entrantes.</span><span class="sxs-lookup"><span data-stu-id="9539d-116">Specifies a single optional or required claim for incoming security tokens.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9539d-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9539d-117">Parent Elements</span></span>  
  
|<span data-ttu-id="9539d-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="9539d-118">Element</span></span>|<span data-ttu-id="9539d-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="9539d-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9539d-120">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="9539d-120">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="9539d-121">Especifica los valores de identidad de nivel de servicio.</span><span class="sxs-lookup"><span data-stu-id="9539d-121">Specifies service-level identity settings.</span></span>|
