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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2fa8cc15f77ff59e3d3c570341d9bba70cf1e953
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33431719"
---
# <a name="ehostbindingpolicymodifyflags-enumeration"></a><span data-ttu-id="fa457-102">EHostBindingPolicyModifyFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="fa457-102">EHostBindingPolicyModifyFlags Enumeration</span></span>
<span data-ttu-id="fa457-103">Permite al host especificar el tipo de redireccionamiento que debe realizar common language runtime (CLR) al aplicar las modificaciones de directiva de un ensamblado de origen a un ensamblado de destino.</span><span class="sxs-lookup"><span data-stu-id="fa457-103">Allows the host to specify the type of redirection the common language runtime (CLR) should perform when applying policy modifications from a source assembly to a target assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa457-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fa457-104">Syntax</span></span>  
  
```  
typedef enum _hostBindingPolicyModifyFlags {  
    HOST_BINDING_POLICY_MODIFY_DEFAULT  = 0,  
    HOST_BINDING_POLICY_MODIFY_CHAIN    = 1,  
    HOST_BINDING_POLICY_MODIFY_REMOVE   = 2,  
    HOST_BINDING_POLICY_MODIFY_MAX      = 3  
} EHostBindingPolicyModifyFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="fa457-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="fa457-105">Members</span></span>  
  
|<span data-ttu-id="fa457-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="fa457-106">Member</span></span>|<span data-ttu-id="fa457-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="fa457-107">Description</span></span>|  
|------------|-----------------|  
|`HOST_BINDING_POLICY_MODIFY_CHAIN`|<span data-ttu-id="fa457-108">Especifica que CLR encadenará los valores de directiva del ensamblado de origen a los del ensamblado de destino.</span><span class="sxs-lookup"><span data-stu-id="fa457-108">Specifies that the CLR will chain policy values of the source assembly onto those of the target assembly.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_DEFAULT`|<span data-ttu-id="fa457-109">Especifica que el CLR llevará a cabo la acción predeterminada.</span><span class="sxs-lookup"><span data-stu-id="fa457-109">Specifies that the CLR will perform the default action.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_MAX`|<span data-ttu-id="fa457-110">Especifica que el CLR establecerá los valores de directiva del ensamblado de destino para los valores máximos.</span><span class="sxs-lookup"><span data-stu-id="fa457-110">Specifies that the CLR will set the policy values of the target assembly to the maximum values.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_REMOVE`|<span data-ttu-id="fa457-111">Especifica que CLR reemplazará los valores de directiva del ensamblado de destino con los del ensamblado de origen.</span><span class="sxs-lookup"><span data-stu-id="fa457-111">Specifies that the CLR will replace policy values of the target assembly with those of the source assembly.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fa457-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fa457-112">Remarks</span></span>  
 <span data-ttu-id="fa457-113">El [ICLRHostBindingPolicyManager:: ModifyApplicationPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md) método toma un parámetro de tipo `EHostBindingPolicyModifyFlags`.</span><span class="sxs-lookup"><span data-stu-id="fa457-113">The [ICLRHostBindingPolicyManager::ModifyApplicationPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md) method takes a parameter of type `EHostBindingPolicyModifyFlags`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa457-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fa457-114">Requirements</span></span>  
 <span data-ttu-id="fa457-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa457-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa457-116">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fa457-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fa457-117">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fa457-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fa457-118">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa457-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa457-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="fa457-119">See Also</span></span>  
 [<span data-ttu-id="fa457-120">ICLRHostBindingPolicyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fa457-120">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)  
 [<span data-ttu-id="fa457-121">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="fa457-121">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
