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
ms.openlocfilehash: a2faf22b48dd0b809d6c3668a37f2119733a9b18
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129450"
---
# <a name="ehostbindingpolicymodifyflags-enumeration"></a><span data-ttu-id="56101-102">EHostBindingPolicyModifyFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="56101-102">EHostBindingPolicyModifyFlags Enumeration</span></span>
<span data-ttu-id="56101-103">Permite al host especificar el tipo de redirección que debe realizar el Common Language Runtime (CLR) al aplicar las modificaciones de directiva de un ensamblado de origen a un ensamblado de destino.</span><span class="sxs-lookup"><span data-stu-id="56101-103">Allows the host to specify the type of redirection the common language runtime (CLR) should perform when applying policy modifications from a source assembly to a target assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56101-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="56101-104">Syntax</span></span>  
  
```cpp  
typedef enum _hostBindingPolicyModifyFlags {  
    HOST_BINDING_POLICY_MODIFY_DEFAULT  = 0,  
    HOST_BINDING_POLICY_MODIFY_CHAIN    = 1,  
    HOST_BINDING_POLICY_MODIFY_REMOVE   = 2,  
    HOST_BINDING_POLICY_MODIFY_MAX      = 3  
} EHostBindingPolicyModifyFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="56101-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="56101-105">Members</span></span>  
  
|<span data-ttu-id="56101-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="56101-106">Member</span></span>|<span data-ttu-id="56101-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="56101-107">Description</span></span>|  
|------------|-----------------|  
|`HOST_BINDING_POLICY_MODIFY_CHAIN`|<span data-ttu-id="56101-108">Especifica que CLR encadenará los valores de la Directiva del ensamblado de origen en los del ensamblado de destino.</span><span class="sxs-lookup"><span data-stu-id="56101-108">Specifies that the CLR will chain policy values of the source assembly onto those of the target assembly.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_DEFAULT`|<span data-ttu-id="56101-109">Especifica que CLR llevará a cabo la acción predeterminada.</span><span class="sxs-lookup"><span data-stu-id="56101-109">Specifies that the CLR will perform the default action.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_MAX`|<span data-ttu-id="56101-110">Especifica que CLR establecerá los valores de directiva del ensamblado de destino en los valores máximos.</span><span class="sxs-lookup"><span data-stu-id="56101-110">Specifies that the CLR will set the policy values of the target assembly to the maximum values.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_REMOVE`|<span data-ttu-id="56101-111">Especifica que CLR reemplazará los valores de directiva del ensamblado de destino por los del ensamblado de origen.</span><span class="sxs-lookup"><span data-stu-id="56101-111">Specifies that the CLR will replace policy values of the target assembly with those of the source assembly.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="56101-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="56101-112">Remarks</span></span>  
 <span data-ttu-id="56101-113">El método [ICLRHostBindingPolicyManager:: ModifyApplicationPolicy (](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md) toma un parámetro de tipo `EHostBindingPolicyModifyFlags`.</span><span class="sxs-lookup"><span data-stu-id="56101-113">The [ICLRHostBindingPolicyManager::ModifyApplicationPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md) method takes a parameter of type `EHostBindingPolicyModifyFlags`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="56101-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="56101-114">Requirements</span></span>  
 <span data-ttu-id="56101-115">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="56101-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56101-116">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="56101-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="56101-117">**Biblioteca:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="56101-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="56101-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="56101-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56101-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="56101-119">See also</span></span>

- [<span data-ttu-id="56101-120">ICLRHostBindingPolicyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="56101-120">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
- [<span data-ttu-id="56101-121">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="56101-121">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
