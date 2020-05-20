---
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
ms.openlocfilehash: 256c362ae0aea51fea16ce799db243b105dee81a
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616247"
---
# <a name="ehostbindingpolicymodifyflags-enumeration"></a><span data-ttu-id="d006a-102">EHostBindingPolicyModifyFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="d006a-102">EHostBindingPolicyModifyFlags Enumeration</span></span>
<span data-ttu-id="d006a-103">Permite al host especificar el tipo de redirección que debe realizar el Common Language Runtime (CLR) al aplicar las modificaciones de directiva de un ensamblado de origen a un ensamblado de destino.</span><span class="sxs-lookup"><span data-stu-id="d006a-103">Allows the host to specify the type of redirection the common language runtime (CLR) should perform when applying policy modifications from a source assembly to a target assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d006a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d006a-104">Syntax</span></span>  
  
```cpp  
typedef enum _hostBindingPolicyModifyFlags {  
    HOST_BINDING_POLICY_MODIFY_DEFAULT  = 0,  
    HOST_BINDING_POLICY_MODIFY_CHAIN    = 1,  
    HOST_BINDING_POLICY_MODIFY_REMOVE   = 2,  
    HOST_BINDING_POLICY_MODIFY_MAX      = 3  
} EHostBindingPolicyModifyFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="d006a-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="d006a-105">Members</span></span>  
  
|<span data-ttu-id="d006a-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="d006a-106">Member</span></span>|<span data-ttu-id="d006a-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="d006a-107">Description</span></span>|  
|------------|-----------------|  
|`HOST_BINDING_POLICY_MODIFY_CHAIN`|<span data-ttu-id="d006a-108">Especifica que CLR encadenará los valores de la Directiva del ensamblado de origen en los del ensamblado de destino.</span><span class="sxs-lookup"><span data-stu-id="d006a-108">Specifies that the CLR will chain policy values of the source assembly onto those of the target assembly.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_DEFAULT`|<span data-ttu-id="d006a-109">Especifica que CLR llevará a cabo la acción predeterminada.</span><span class="sxs-lookup"><span data-stu-id="d006a-109">Specifies that the CLR will perform the default action.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_MAX`|<span data-ttu-id="d006a-110">Especifica que CLR establecerá los valores de directiva del ensamblado de destino en los valores máximos.</span><span class="sxs-lookup"><span data-stu-id="d006a-110">Specifies that the CLR will set the policy values of the target assembly to the maximum values.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_REMOVE`|<span data-ttu-id="d006a-111">Especifica que CLR reemplazará los valores de directiva del ensamblado de destino por los del ensamblado de origen.</span><span class="sxs-lookup"><span data-stu-id="d006a-111">Specifies that the CLR will replace policy values of the target assembly with those of the source assembly.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d006a-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d006a-112">Remarks</span></span>  
 <span data-ttu-id="d006a-113">El método [ICLRHostBindingPolicyManager:: ModifyApplicationPolicy (](iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md) toma un parámetro de tipo `EHostBindingPolicyModifyFlags` .</span><span class="sxs-lookup"><span data-stu-id="d006a-113">The [ICLRHostBindingPolicyManager::ModifyApplicationPolicy](iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md) method takes a parameter of type `EHostBindingPolicyModifyFlags`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d006a-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d006a-114">Requirements</span></span>  
 <span data-ttu-id="d006a-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d006a-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d006a-116">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="d006a-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d006a-117">**Biblioteca:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d006a-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d006a-118">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d006a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d006a-119">Consulta también</span><span class="sxs-lookup"><span data-stu-id="d006a-119">See also</span></span>

- [<span data-ttu-id="d006a-120">ICLRHostBindingPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d006a-120">ICLRHostBindingPolicyManager Interface</span></span>](iclrhostbindingpolicymanager-interface.md)
- [<span data-ttu-id="d006a-121">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="d006a-121">Hosting Enumerations</span></span>](hosting-enumerations.md)
