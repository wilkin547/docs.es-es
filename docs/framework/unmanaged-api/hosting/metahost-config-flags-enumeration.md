---
title: METAHOST_CONFIG_FLAGS (Enumeración)
ms.date: 03/30/2017
api_name:
- METAHOST_CONFIG_FLAGS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- METAHOST_CONFIG_FLAGS
helpviewer_keywords:
- METAHOST_CONFIG_FLAGS enumeration [.NET Framework hosting]
ms.assetid: 6f1e389f-ed99-4d6a-a0ba-72d7d869a01d
topic_type:
- apiref
ms.openlocfilehash: 01e55659bf2a348ec763f51112cbdcd706f27c84
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730011"
---
# <a name="metahost_config_flags-enumeration"></a><span data-ttu-id="e2247-102">METAHOST_CONFIG_FLAGS (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="e2247-102">METAHOST_CONFIG_FLAGS Enumeration</span></span>

<span data-ttu-id="e2247-103">Describe las posibles marcas devueltas en el `pdwConfigFlags` parámetro del método [ICLRMetaHostPolicy:: GetRequestedRuntime](iclrmetahostpolicy-getrequestedruntime-method.md) , que indica la presencia y el establecimiento del `useLegacyV2RuntimeActivationPolicy` atributo en el [ \<startup> elemento](../../configure-apps/file-schema/startup/startup-element.md) del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="e2247-103">Describes the possible flags returned in the `pdwConfigFlags` parameter of the [ICLRMetaHostPolicy::GetRequestedRuntime](iclrmetahostpolicy-getrequestedruntime-method.md) method, indicating the presence and setting of the `useLegacyV2RuntimeActivationPolicy` attribute in the [\<startup> element](../../configure-apps/file-schema/startup/startup-element.md) of the configuration file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2247-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e2247-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_UNSET  = 0x00,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_TRUE   = 0x01,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_FALSE  = 0x02,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK   = 0x03  
} METAHOST_CONFIG_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="e2247-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="e2247-105">Members</span></span>  
  
|<span data-ttu-id="e2247-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="e2247-106">Member</span></span>|<span data-ttu-id="e2247-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="e2247-107">Description</span></span>|  
|------------|-----------------|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_UNSET`|<span data-ttu-id="e2247-108">El `useLegacyV2RuntimeActivationPolicy` atributo no estaba presente en el [ \<startup> elemento](../../configure-apps/file-schema/startup/startup-element.md).</span><span class="sxs-lookup"><span data-stu-id="e2247-108">The `useLegacyV2RuntimeActivationPolicy` attribute was not present in the [\<startup> Element](../../configure-apps/file-schema/startup/startup-element.md).</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_TRUE`|<span data-ttu-id="e2247-109">El `useLegacyV2RuntimeActivationPolicy` atributo estaba presente y se estableció en `true` .</span><span class="sxs-lookup"><span data-stu-id="e2247-109">The `useLegacyV2RuntimeActivationPolicy` attribute was present and set to `true`.</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_FALSE`|<span data-ttu-id="e2247-110">El `useLegacyV2RuntimeActivationPolicy` atributo estaba presente y se estableció en `false` .</span><span class="sxs-lookup"><span data-stu-id="e2247-110">The `useLegacyV2RuntimeActivationPolicy` attribute was present and set to `false`.</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK`|<span data-ttu-id="e2247-111">Aplique esta máscara al valor devuelto en `pdwConfigFlags` para obtener los valores relevantes para `useLegacyV2RuntimeActivationPolicy` .</span><span class="sxs-lookup"><span data-stu-id="e2247-111">Apply this mask to the value returned in `pdwConfigFlags` to get the values relevant to `useLegacyV2RuntimeActivationPolicy`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e2247-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e2247-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2247-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e2247-113">Requirements</span></span>  

 <span data-ttu-id="e2247-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2247-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2247-115">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="e2247-115">**Header:** Metahost.h</span></span>  
  
 <span data-ttu-id="e2247-116">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e2247-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e2247-117">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2247-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2247-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e2247-118">See also</span></span>

- [<span data-ttu-id="e2247-119">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="e2247-119">Hosting Enumerations</span></span>](hosting-enumerations.md)
- [<span data-ttu-id="e2247-120">Método GetRequestedRuntime</span><span class="sxs-lookup"><span data-stu-id="e2247-120">GetRequestedRuntime Method</span></span>](iclrmetahostpolicy-getrequestedruntime-method.md)
- [<span data-ttu-id="e2247-121">Elemento \<startup></span><span class="sxs-lookup"><span data-stu-id="e2247-121">\<startup> Element</span></span>](../../configure-apps/file-schema/startup/startup-element.md)
