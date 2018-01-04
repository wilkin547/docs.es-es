---
title: "EBindPolicyLevels (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: EBindPolicyLevels
api_location: mscoree.dll
api_type: COM
f1_keywords: EBindPolicyLevels
helpviewer_keywords: EBindPolicyLevels enumeration [.NET Framework hosting]
ms.assetid: a9e00b4f-b6d0-4257-bd88-4fe9af97b8fa
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 52e4d4522c7401aba198deed7853ccca71752d83
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ebindpolicylevels-enumeration"></a><span data-ttu-id="423fa-102">EBindPolicyLevels (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="423fa-102">EBindPolicyLevels Enumeration</span></span>
<span data-ttu-id="423fa-103">Proporciona las marcas que especifican el nivel en el que se va a aplicar o modificar la directiva de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="423fa-103">Provides flags to specify the level at which to apply or modify assembly policy.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="423fa-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="423fa-104">Syntax</span></span>  
  
```  
typedef enum {  
    ePolicyLevelNone         = 0x0,  
    ePolicyLevelRetargetable = 0x1,  
    ePolicyUnifiedToCLR      = 0x2,  
    ePolicyLevelApp          = 0x4,  
    ePolicyLevelPublisher    = 0x8,  
    ePolicyLevelHost         = 0x10,  
    ePolicyLevelAdmin        = 0x20  
    ePolicyPortability       = 0x40  
} EBindPolicyLevels;  
```  
  
## <a name="members"></a><span data-ttu-id="423fa-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="423fa-105">Members</span></span>  
  
|<span data-ttu-id="423fa-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="423fa-106">Member</span></span>|<span data-ttu-id="423fa-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="423fa-107">Description</span></span>|  
|------------|-----------------|  
|`ePolicyLevelAdmin`|<span data-ttu-id="423fa-108">Especifica que la directiva debe aplicarse en el nivel de administrador.</span><span class="sxs-lookup"><span data-stu-id="423fa-108">Specifies that policy should be applied at the administrator level.</span></span>|  
|`ePolicyLevelApp`|<span data-ttu-id="423fa-109">Especifica que la directiva debe aplicarse en el nivel de aplicación.</span><span class="sxs-lookup"><span data-stu-id="423fa-109">Specifies that policy should be applied at the application level.</span></span>|  
|`ePolicyLevelHost`|<span data-ttu-id="423fa-110">Especifica que la directiva debe aplicarse en el nivel de host.</span><span class="sxs-lookup"><span data-stu-id="423fa-110">Specifies that policy should be applied at the host level.</span></span>|  
|`ePolicyLevelNone`|<span data-ttu-id="423fa-111">No especifica ningún indicador de nivel de directiva.</span><span class="sxs-lookup"><span data-stu-id="423fa-111">Specifies no policy-level flags.</span></span>|  
|`ePolicyLevelPublisher`|<span data-ttu-id="423fa-112">Especifica que la directiva debe aplicarse en el nivel del Editor.</span><span class="sxs-lookup"><span data-stu-id="423fa-112">Specifies that policy should be applied at the publisher level.</span></span>|  
|`ePolicyLevelRetargetable`|<span data-ttu-id="423fa-113">Especifica que Directiva debe aplicarse en niveles variables.</span><span class="sxs-lookup"><span data-stu-id="423fa-113">Specifies that policy should be applicable at variable levels.</span></span>|  
|`ePolicyPortability`|<span data-ttu-id="423fa-114">Especifica que la directiva debe admitir portabilidad entre las implementaciones de un ensamblado de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="423fa-114">Specifies that policy should support portability between implementations of a .NET Framework assembly.</span></span> <span data-ttu-id="423fa-115">Consulte la [ \<supportPortability >](../../../../docs/framework/configure-apps/file-schema/runtime/supportportability-element.md) elemento de archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="423fa-115">See the [\<supportPortability>](../../../../docs/framework/configure-apps/file-schema/runtime/supportportability-element.md) configuration file element.</span></span>|  
|`ePolicyUnifiedToCLR`|<span data-ttu-id="423fa-116">Especifica que la directiva debe unificarse a la de common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="423fa-116">Specifies that policy should be unified to that of the common language runtime (CLR).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="423fa-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="423fa-117">Remarks</span></span>  
 <span data-ttu-id="423fa-118">Esta enumeración se pasa a métodos de la [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) interfaz para especificar los cambios en la directiva de aplicación.</span><span class="sxs-lookup"><span data-stu-id="423fa-118">This enumeration is passed to methods of the [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) interface to specify changes in application policy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="423fa-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="423fa-119">Requirements</span></span>  
 <span data-ttu-id="423fa-120">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="423fa-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="423fa-121">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="423fa-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="423fa-122">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="423fa-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="423fa-123">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="423fa-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="423fa-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="423fa-124">See Also</span></span>  
 [<span data-ttu-id="423fa-125">ICLRAssemblyIdentityManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="423fa-125">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="423fa-126">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="423fa-126">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
