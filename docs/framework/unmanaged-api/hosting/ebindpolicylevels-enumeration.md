---
title: EBindPolicyLevels (Enumeración)
ms.date: 03/30/2017
api_name:
- EBindPolicyLevels
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EBindPolicyLevels
helpviewer_keywords:
- EBindPolicyLevels enumeration [.NET Framework hosting]
ms.assetid: a9e00b4f-b6d0-4257-bd88-4fe9af97b8fa
topic_type:
- apiref
ms.openlocfilehash: 81aef6beb9ee6d622519738d24fdd0a4d42a75b1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136551"
---
# <a name="ebindpolicylevels-enumeration"></a><span data-ttu-id="f11b0-102">EBindPolicyLevels (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="f11b0-102">EBindPolicyLevels Enumeration</span></span>
<span data-ttu-id="f11b0-103">Proporciona marcas para especificar el nivel en el que se va a aplicar o modificar la Directiva de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f11b0-103">Provides flags to specify the level at which to apply or modify assembly policy.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f11b0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f11b0-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="f11b0-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="f11b0-105">Members</span></span>  
  
|<span data-ttu-id="f11b0-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="f11b0-106">Member</span></span>|<span data-ttu-id="f11b0-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="f11b0-107">Description</span></span>|  
|------------|-----------------|  
|`ePolicyLevelAdmin`|<span data-ttu-id="f11b0-108">Especifica que debe aplicarse la Directiva en el nivel de administrador.</span><span class="sxs-lookup"><span data-stu-id="f11b0-108">Specifies that policy should be applied at the administrator level.</span></span>|  
|`ePolicyLevelApp`|<span data-ttu-id="f11b0-109">Especifica que la Directiva debe aplicarse en el nivel de aplicación.</span><span class="sxs-lookup"><span data-stu-id="f11b0-109">Specifies that policy should be applied at the application level.</span></span>|  
|`ePolicyLevelHost`|<span data-ttu-id="f11b0-110">Especifica que debe aplicarse la Directiva en el nivel de host.</span><span class="sxs-lookup"><span data-stu-id="f11b0-110">Specifies that policy should be applied at the host level.</span></span>|  
|`ePolicyLevelNone`|<span data-ttu-id="f11b0-111">No especifica ninguna marca de nivel de directiva.</span><span class="sxs-lookup"><span data-stu-id="f11b0-111">Specifies no policy-level flags.</span></span>|  
|`ePolicyLevelPublisher`|<span data-ttu-id="f11b0-112">Especifica que debe aplicarse la Directiva en el nivel de publicador.</span><span class="sxs-lookup"><span data-stu-id="f11b0-112">Specifies that policy should be applied at the publisher level.</span></span>|  
|`ePolicyLevelRetargetable`|<span data-ttu-id="f11b0-113">Especifica que la Directiva debe ser aplicable en los niveles variables.</span><span class="sxs-lookup"><span data-stu-id="f11b0-113">Specifies that policy should be applicable at variable levels.</span></span>|  
|`ePolicyPortability`|<span data-ttu-id="f11b0-114">Especifica que la Directiva debe admitir la portabilidad entre las implementaciones de un ensamblado de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f11b0-114">Specifies that policy should support portability between implementations of a .NET Framework assembly.</span></span> <span data-ttu-id="f11b0-115">Vea el elemento [\<supportPortability >](../../../../docs/framework/configure-apps/file-schema/runtime/supportportability-element.md) archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="f11b0-115">See the [\<supportPortability>](../../../../docs/framework/configure-apps/file-schema/runtime/supportportability-element.md) configuration file element.</span></span>|  
|`ePolicyUnifiedToCLR`|<span data-ttu-id="f11b0-116">Especifica que la Directiva se debe unificar con la del Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="f11b0-116">Specifies that policy should be unified to that of the common language runtime (CLR).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f11b0-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f11b0-117">Remarks</span></span>  
 <span data-ttu-id="f11b0-118">Esta enumeración se pasa a los métodos de la interfaz [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) para especificar cambios en la Directiva de aplicación.</span><span class="sxs-lookup"><span data-stu-id="f11b0-118">This enumeration is passed to methods of the [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) interface to specify changes in application policy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f11b0-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f11b0-119">Requirements</span></span>  
 <span data-ttu-id="f11b0-120">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f11b0-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f11b0-121">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f11b0-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f11b0-122">**Biblioteca:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f11b0-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f11b0-123">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f11b0-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f11b0-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="f11b0-124">See also</span></span>

- [<span data-ttu-id="f11b0-125">ICLRAssemblyIdentityManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f11b0-125">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="f11b0-126">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="f11b0-126">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
