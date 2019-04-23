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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b8f2b08662e719a3308a62ab5b60f5dc490f2a6a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59142212"
---
# <a name="ebindpolicylevels-enumeration"></a><span data-ttu-id="63a36-102">EBindPolicyLevels (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="63a36-102">EBindPolicyLevels Enumeration</span></span>
<span data-ttu-id="63a36-103">Proporciona marcas para especificar el nivel en el que se va a aplicar o modificar la directiva de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="63a36-103">Provides flags to specify the level at which to apply or modify assembly policy.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63a36-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="63a36-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="63a36-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="63a36-105">Members</span></span>  
  
|<span data-ttu-id="63a36-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="63a36-106">Member</span></span>|<span data-ttu-id="63a36-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="63a36-107">Description</span></span>|  
|------------|-----------------|  
|`ePolicyLevelAdmin`|<span data-ttu-id="63a36-108">Especifica que debe aplicarse la directiva en el nivel de administrador.</span><span class="sxs-lookup"><span data-stu-id="63a36-108">Specifies that policy should be applied at the administrator level.</span></span>|  
|`ePolicyLevelApp`|<span data-ttu-id="63a36-109">Especifica que debe aplicarse la directiva en el nivel de aplicación.</span><span class="sxs-lookup"><span data-stu-id="63a36-109">Specifies that policy should be applied at the application level.</span></span>|  
|`ePolicyLevelHost`|<span data-ttu-id="63a36-110">Especifica que debe aplicarse la directiva a nivel de host.</span><span class="sxs-lookup"><span data-stu-id="63a36-110">Specifies that policy should be applied at the host level.</span></span>|  
|`ePolicyLevelNone`|<span data-ttu-id="63a36-111">No especifica ningún indicador de nivel de directiva.</span><span class="sxs-lookup"><span data-stu-id="63a36-111">Specifies no policy-level flags.</span></span>|  
|`ePolicyLevelPublisher`|<span data-ttu-id="63a36-112">Especifica que debe aplicarse la directiva en el nivel de publicador.</span><span class="sxs-lookup"><span data-stu-id="63a36-112">Specifies that policy should be applied at the publisher level.</span></span>|  
|`ePolicyLevelRetargetable`|<span data-ttu-id="63a36-113">Especifica que Directiva debe aplicarse en niveles variables.</span><span class="sxs-lookup"><span data-stu-id="63a36-113">Specifies that policy should be applicable at variable levels.</span></span>|  
|`ePolicyPortability`|<span data-ttu-id="63a36-114">Especifica que Directiva debe admitir la portabilidad entre las implementaciones de un ensamblado de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="63a36-114">Specifies that policy should support portability between implementations of a .NET Framework assembly.</span></span> <span data-ttu-id="63a36-115">Consulte la [ \<supportPortability >](../../../../docs/framework/configure-apps/file-schema/runtime/supportportability-element.md) elemento del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="63a36-115">See the [\<supportPortability>](../../../../docs/framework/configure-apps/file-schema/runtime/supportportability-element.md) configuration file element.</span></span>|  
|`ePolicyUnifiedToCLR`|<span data-ttu-id="63a36-116">Especifica que la directiva debe unificarse para que el de common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="63a36-116">Specifies that policy should be unified to that of the common language runtime (CLR).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="63a36-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="63a36-117">Remarks</span></span>  
 <span data-ttu-id="63a36-118">Esta enumeración se pasa a los métodos de la [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) interfaz para especificar los cambios en la directiva de aplicación.</span><span class="sxs-lookup"><span data-stu-id="63a36-118">This enumeration is passed to methods of the [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) interface to specify changes in application policy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63a36-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="63a36-119">Requirements</span></span>  
 <span data-ttu-id="63a36-120">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63a36-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63a36-121">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="63a36-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="63a36-122">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="63a36-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="63a36-123">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63a36-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63a36-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="63a36-124">See also</span></span>

- [<span data-ttu-id="63a36-125">ICLRAssemblyIdentityManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="63a36-125">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="63a36-126">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="63a36-126">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
