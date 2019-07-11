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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 13a7ad5b59dd318f823645d28f9c3ccbec8a8cb0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781085"
---
# <a name="metahostconfigflags-enumeration"></a><span data-ttu-id="5bc47-102">METAHOST_CONFIG_FLAGS (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="5bc47-102">METAHOST_CONFIG_FLAGS Enumeration</span></span>
<span data-ttu-id="5bc47-103">Describe las posibles marcas devueltas en el `pdwConfigFlags` parámetro de la [ICLRMetaHostPolicy:: GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) método, que indica la presencia y la configuración de la `useLegacyV2RuntimeActivationPolicy` atributo en el [ \<Inicio > elemento](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="5bc47-103">Describes the possible flags returned in the `pdwConfigFlags` parameter of the [ICLRMetaHostPolicy::GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) method, indicating the presence and setting of the `useLegacyV2RuntimeActivationPolicy` attribute in the [\<startup> element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) of the configuration file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bc47-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5bc47-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_UNSET  = 0x00,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_TRUE   = 0x01,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_FALSE  = 0x02,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK   = 0x03  
} METAHOST_CONFIG_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="5bc47-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="5bc47-105">Members</span></span>  
  
|<span data-ttu-id="5bc47-106">Member</span><span class="sxs-lookup"><span data-stu-id="5bc47-106">Member</span></span>|<span data-ttu-id="5bc47-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="5bc47-107">Description</span></span>|  
|------------|-----------------|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_UNSET`|<span data-ttu-id="5bc47-108">El `useLegacyV2RuntimeActivationPolicy` atributo no estaba presente en el [ \<Inicio > elemento](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md).</span><span class="sxs-lookup"><span data-stu-id="5bc47-108">The `useLegacyV2RuntimeActivationPolicy` attribute was not present in the [\<startup> Element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md).</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_TRUE`|<span data-ttu-id="5bc47-109">El `useLegacyV2RuntimeActivationPolicy` atributo estaba presente y establecido para `true`.</span><span class="sxs-lookup"><span data-stu-id="5bc47-109">The `useLegacyV2RuntimeActivationPolicy` attribute was present and set to `true`.</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_FALSE`|<span data-ttu-id="5bc47-110">El `useLegacyV2RuntimeActivationPolicy` atributo estaba presente y establecido para `false`.</span><span class="sxs-lookup"><span data-stu-id="5bc47-110">The `useLegacyV2RuntimeActivationPolicy` attribute was present and set to `false`.</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK`|<span data-ttu-id="5bc47-111">Esta máscara se aplican en el valor devuelto en `pdwConfigFlags` para obtener los valores correspondientes a `useLegacyV2RuntimeActivationPolicy`.</span><span class="sxs-lookup"><span data-stu-id="5bc47-111">Apply this mask to the value returned in `pdwConfigFlags` to get the values relevant to `useLegacyV2RuntimeActivationPolicy`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5bc47-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5bc47-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5bc47-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5bc47-113">Requirements</span></span>  
 <span data-ttu-id="5bc47-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5bc47-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5bc47-115">**Encabezado**: Metahost.h</span><span class="sxs-lookup"><span data-stu-id="5bc47-115">**Header:** Metahost.h</span></span>  
  
 <span data-ttu-id="5bc47-116">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5bc47-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5bc47-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5bc47-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bc47-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="5bc47-118">See also</span></span>

- [<span data-ttu-id="5bc47-119">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="5bc47-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
- [<span data-ttu-id="5bc47-120">GetRequestedRuntime (método)</span><span class="sxs-lookup"><span data-stu-id="5bc47-120">GetRequestedRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)
- [<span data-ttu-id="5bc47-121">Elemento \<startup></span><span class="sxs-lookup"><span data-stu-id="5bc47-121">\<startup> Element</span></span>](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)
