---
description: 'Más información sobre: enumeración Ehostbindingpolicymodifyflags ('
title: EHostBindingPolicyModifyFlags (Enumeración)
ms.date: 03/30/2017
api_name:
- EHostBindingPolicyModifyFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EHostBindingPolicyModifyFlags
helpviewer_keywords:
- EHostBindingPolicyModifyFlags enumeration [.NET Framework hosting]
ms.assetid: 0339af16-ee1d-48ec-837d-a79d9a9c89f8
topic_type:
- apiref
ms.openlocfilehash: be8a15cad49097d1ea2e206e01da2d5d5dcb165a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785489"
---
# <a name="ehostbindingpolicymodifyflags-enumeration"></a><span data-ttu-id="b7ec8-103">EHostBindingPolicyModifyFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="b7ec8-103">EHostBindingPolicyModifyFlags Enumeration</span></span>

<span data-ttu-id="b7ec8-104">Permite al host especificar el tipo de redirección que debe realizar el Common Language Runtime (CLR) al aplicar las modificaciones de directiva de un ensamblado de origen a un ensamblado de destino.</span><span class="sxs-lookup"><span data-stu-id="b7ec8-104">Allows the host to specify the type of redirection the common language runtime (CLR) should perform when applying policy modifications from a source assembly to a target assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7ec8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b7ec8-105">Syntax</span></span>  
  
```cpp  
typedef enum _hostBindingPolicyModifyFlags {  
    HOST_BINDING_POLICY_MODIFY_DEFAULT  = 0,  
    HOST_BINDING_POLICY_MODIFY_CHAIN    = 1,  
    HOST_BINDING_POLICY_MODIFY_REMOVE   = 2,  
    HOST_BINDING_POLICY_MODIFY_MAX      = 3  
} EHostBindingPolicyModifyFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="b7ec8-106">Members</span><span class="sxs-lookup"><span data-stu-id="b7ec8-106">Members</span></span>  
  
|<span data-ttu-id="b7ec8-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="b7ec8-107">Member</span></span>|<span data-ttu-id="b7ec8-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="b7ec8-108">Description</span></span>|  
|------------|-----------------|  
|`HOST_BINDING_POLICY_MODIFY_CHAIN`|<span data-ttu-id="b7ec8-109">Especifica que CLR encadenará los valores de la Directiva del ensamblado de origen en los del ensamblado de destino.</span><span class="sxs-lookup"><span data-stu-id="b7ec8-109">Specifies that the CLR will chain policy values of the source assembly onto those of the target assembly.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_DEFAULT`|<span data-ttu-id="b7ec8-110">Especifica que CLR llevará a cabo la acción predeterminada.</span><span class="sxs-lookup"><span data-stu-id="b7ec8-110">Specifies that the CLR will perform the default action.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_MAX`|<span data-ttu-id="b7ec8-111">Especifica que CLR establecerá los valores de directiva del ensamblado de destino en los valores máximos.</span><span class="sxs-lookup"><span data-stu-id="b7ec8-111">Specifies that the CLR will set the policy values of the target assembly to the maximum values.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_REMOVE`|<span data-ttu-id="b7ec8-112">Especifica que CLR reemplazará los valores de directiva del ensamblado de destino por los del ensamblado de origen.</span><span class="sxs-lookup"><span data-stu-id="b7ec8-112">Specifies that the CLR will replace policy values of the target assembly with those of the source assembly.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b7ec8-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b7ec8-113">Remarks</span></span>  

 <span data-ttu-id="b7ec8-114">El método [ICLRHostBindingPolicyManager:: ModifyApplicationPolicy (](iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md) toma un parámetro de tipo `EHostBindingPolicyModifyFlags` .</span><span class="sxs-lookup"><span data-stu-id="b7ec8-114">The [ICLRHostBindingPolicyManager::ModifyApplicationPolicy](iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md) method takes a parameter of type `EHostBindingPolicyModifyFlags`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7ec8-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b7ec8-115">Requirements</span></span>  

 <span data-ttu-id="b7ec8-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7ec8-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7ec8-117">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="b7ec8-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b7ec8-118">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b7ec8-118">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b7ec8-119">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7ec8-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7ec8-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="b7ec8-120">See also</span></span>

- [<span data-ttu-id="b7ec8-121">ICLRHostBindingPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b7ec8-121">ICLRHostBindingPolicyManager Interface</span></span>](iclrhostbindingpolicymanager-interface.md)
- [<span data-ttu-id="b7ec8-122">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="b7ec8-122">Hosting Enumerations</span></span>](hosting-enumerations.md)
