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
ms.openlocfilehash: a0992ca8ac4bfffef681c74de455a0eeb627a042
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726852"
---
# <a name="ebindpolicylevels-enumeration"></a><span data-ttu-id="413e8-102">EBindPolicyLevels (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="413e8-102">EBindPolicyLevels Enumeration</span></span>

<span data-ttu-id="413e8-103">Proporciona marcas para especificar el nivel en el que se va a aplicar o modificar la Directiva de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="413e8-103">Provides flags to specify the level at which to apply or modify assembly policy.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="413e8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="413e8-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="413e8-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="413e8-105">Members</span></span>  
  
|<span data-ttu-id="413e8-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="413e8-106">Member</span></span>|<span data-ttu-id="413e8-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="413e8-107">Description</span></span>|  
|------------|-----------------|  
|`ePolicyLevelAdmin`|<span data-ttu-id="413e8-108">Especifica que debe aplicarse la Directiva en el nivel de administrador.</span><span class="sxs-lookup"><span data-stu-id="413e8-108">Specifies that policy should be applied at the administrator level.</span></span>|  
|`ePolicyLevelApp`|<span data-ttu-id="413e8-109">Especifica que la Directiva debe aplicarse en el nivel de aplicación.</span><span class="sxs-lookup"><span data-stu-id="413e8-109">Specifies that policy should be applied at the application level.</span></span>|  
|`ePolicyLevelHost`|<span data-ttu-id="413e8-110">Especifica que debe aplicarse la Directiva en el nivel de host.</span><span class="sxs-lookup"><span data-stu-id="413e8-110">Specifies that policy should be applied at the host level.</span></span>|  
|`ePolicyLevelNone`|<span data-ttu-id="413e8-111">No especifica ninguna marca de nivel de directiva.</span><span class="sxs-lookup"><span data-stu-id="413e8-111">Specifies no policy-level flags.</span></span>|  
|`ePolicyLevelPublisher`|<span data-ttu-id="413e8-112">Especifica que debe aplicarse la Directiva en el nivel de publicador.</span><span class="sxs-lookup"><span data-stu-id="413e8-112">Specifies that policy should be applied at the publisher level.</span></span>|  
|`ePolicyLevelRetargetable`|<span data-ttu-id="413e8-113">Especifica que la Directiva debe ser aplicable en los niveles variables.</span><span class="sxs-lookup"><span data-stu-id="413e8-113">Specifies that policy should be applicable at variable levels.</span></span>|  
|`ePolicyPortability`|<span data-ttu-id="413e8-114">Especifica que la Directiva debe admitir la portabilidad entre las implementaciones de un ensamblado de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="413e8-114">Specifies that policy should support portability between implementations of a .NET Framework assembly.</span></span> <span data-ttu-id="413e8-115">Vea el [\<supportPortability>](../../configure-apps/file-schema/runtime/supportportability-element.md) elemento de archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="413e8-115">See the [\<supportPortability>](../../configure-apps/file-schema/runtime/supportportability-element.md) configuration file element.</span></span>|  
|`ePolicyUnifiedToCLR`|<span data-ttu-id="413e8-116">Especifica que la Directiva se debe unificar con la del Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="413e8-116">Specifies that policy should be unified to that of the common language runtime (CLR).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="413e8-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="413e8-117">Remarks</span></span>  

 <span data-ttu-id="413e8-118">Esta enumeración se pasa a los métodos de la interfaz [ICLRHostBindingPolicyManager](iclrhostbindingpolicymanager-interface.md) para especificar cambios en la Directiva de aplicación.</span><span class="sxs-lookup"><span data-stu-id="413e8-118">This enumeration is passed to methods of the [ICLRHostBindingPolicyManager](iclrhostbindingpolicymanager-interface.md) interface to specify changes in application policy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="413e8-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="413e8-119">Requirements</span></span>  

 <span data-ttu-id="413e8-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="413e8-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="413e8-121">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="413e8-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="413e8-122">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="413e8-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="413e8-123">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="413e8-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="413e8-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="413e8-124">See also</span></span>

- [<span data-ttu-id="413e8-125">ICLRAssemblyIdentityManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="413e8-125">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="413e8-126">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="413e8-126">Hosting Enumerations</span></span>](hosting-enumerations.md)
