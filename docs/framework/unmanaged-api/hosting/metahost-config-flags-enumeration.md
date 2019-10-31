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
ms.openlocfilehash: 07cab119810c4da25d16a4ad7c13f2d2bda16455
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140314"
---
# <a name="metahost_config_flags-enumeration"></a><span data-ttu-id="0bff3-102">METAHOST_CONFIG_FLAGS (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="0bff3-102">METAHOST_CONFIG_FLAGS Enumeration</span></span>
<span data-ttu-id="0bff3-103">Describe las posibles marcas devueltas en el parámetro `pdwConfigFlags` del método [ICLRMetaHostPolicy:: GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) , que indica la presencia y el establecimiento del atributo `useLegacyV2RuntimeActivationPolicy` en el [elemento\<startup >](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) de la archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="0bff3-103">Describes the possible flags returned in the `pdwConfigFlags` parameter of the [ICLRMetaHostPolicy::GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) method, indicating the presence and setting of the `useLegacyV2RuntimeActivationPolicy` attribute in the [\<startup> element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) of the configuration file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0bff3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0bff3-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_UNSET  = 0x00,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_TRUE   = 0x01,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_FALSE  = 0x02,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK   = 0x03  
} METAHOST_CONFIG_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="0bff3-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="0bff3-105">Members</span></span>  
  
|<span data-ttu-id="0bff3-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="0bff3-106">Member</span></span>|<span data-ttu-id="0bff3-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="0bff3-107">Description</span></span>|  
|------------|-----------------|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_UNSET`|<span data-ttu-id="0bff3-108">El atributo `useLegacyV2RuntimeActivationPolicy` no estaba presente en el [elemento > de inicio de\<](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md).</span><span class="sxs-lookup"><span data-stu-id="0bff3-108">The `useLegacyV2RuntimeActivationPolicy` attribute was not present in the [\<startup> Element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md).</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_TRUE`|<span data-ttu-id="0bff3-109">El atributo `useLegacyV2RuntimeActivationPolicy` estaba presente y se estableció en `true`.</span><span class="sxs-lookup"><span data-stu-id="0bff3-109">The `useLegacyV2RuntimeActivationPolicy` attribute was present and set to `true`.</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_FALSE`|<span data-ttu-id="0bff3-110">El atributo `useLegacyV2RuntimeActivationPolicy` estaba presente y se estableció en `false`.</span><span class="sxs-lookup"><span data-stu-id="0bff3-110">The `useLegacyV2RuntimeActivationPolicy` attribute was present and set to `false`.</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK`|<span data-ttu-id="0bff3-111">Aplique esta máscara al valor devuelto en `pdwConfigFlags` para obtener los valores relevantes para `useLegacyV2RuntimeActivationPolicy`.</span><span class="sxs-lookup"><span data-stu-id="0bff3-111">Apply this mask to the value returned in `pdwConfigFlags` to get the values relevant to `useLegacyV2RuntimeActivationPolicy`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0bff3-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0bff3-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0bff3-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0bff3-113">Requirements</span></span>  
 <span data-ttu-id="0bff3-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0bff3-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0bff3-115">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="0bff3-115">**Header:** Metahost.h</span></span>  
  
 <span data-ttu-id="0bff3-116">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="0bff3-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0bff3-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0bff3-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bff3-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="0bff3-118">See also</span></span>

- [<span data-ttu-id="0bff3-119">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="0bff3-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
- [<span data-ttu-id="0bff3-120">GetRequestedRuntime (método)</span><span class="sxs-lookup"><span data-stu-id="0bff3-120">GetRequestedRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)
- [<span data-ttu-id="0bff3-121">Elemento \<startup></span><span class="sxs-lookup"><span data-stu-id="0bff3-121">\<startup> Element</span></span>](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)
