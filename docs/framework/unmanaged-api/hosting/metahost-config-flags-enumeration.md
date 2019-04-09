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
ms.openlocfilehash: 6e322f5c7119d13c8a872bd87d00c1e55324b581
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59135783"
---
# <a name="metahostconfigflags-enumeration"></a><span data-ttu-id="3ee75-102">METAHOST_CONFIG_FLAGS (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="3ee75-102">METAHOST_CONFIG_FLAGS Enumeration</span></span>
<span data-ttu-id="3ee75-103">Describe las posibles marcas devueltas en el `pdwConfigFlags` parámetro de la [ICLRMetaHostPolicy:: GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) método, que indica la presencia y la configuración de la `useLegacyV2RuntimeActivationPolicy` atributo en el [ \<Inicio > elemento](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="3ee75-103">Describes the possible flags returned in the `pdwConfigFlags` parameter of the [ICLRMetaHostPolicy::GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) method, indicating the presence and setting of the `useLegacyV2RuntimeActivationPolicy` attribute in the [\<startup> element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) of the configuration file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ee75-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3ee75-104">Syntax</span></span>  
  
```  
typedef enum {  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_UNSET  = 0x00,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_TRUE   = 0x01,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_FALSE  = 0x02,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK   = 0x03  
} METAHOST_CONFIG_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="3ee75-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="3ee75-105">Members</span></span>  
  
|<span data-ttu-id="3ee75-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="3ee75-106">Member</span></span>|<span data-ttu-id="3ee75-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="3ee75-107">Description</span></span>|  
|------------|-----------------|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_UNSET`|<span data-ttu-id="3ee75-108">El `useLegacyV2RuntimeActivationPolicy` atributo no estaba presente en el [ \<Inicio > elemento](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md).</span><span class="sxs-lookup"><span data-stu-id="3ee75-108">The `useLegacyV2RuntimeActivationPolicy` attribute was not present in the [\<startup> Element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md).</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_TRUE`|<span data-ttu-id="3ee75-109">El `useLegacyV2RuntimeActivationPolicy` atributo estaba presente y establecido para `true`.</span><span class="sxs-lookup"><span data-stu-id="3ee75-109">The `useLegacyV2RuntimeActivationPolicy` attribute was present and set to `true`.</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_FALSE`|<span data-ttu-id="3ee75-110">El `useLegacyV2RuntimeActivationPolicy` atributo estaba presente y establecido para `false`.</span><span class="sxs-lookup"><span data-stu-id="3ee75-110">The `useLegacyV2RuntimeActivationPolicy` attribute was present and set to `false`.</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK`|<span data-ttu-id="3ee75-111">Esta máscara se aplican en el valor devuelto en `pdwConfigFlags` para obtener los valores correspondientes a `useLegacyV2RuntimeActivationPolicy`.</span><span class="sxs-lookup"><span data-stu-id="3ee75-111">Apply this mask to the value returned in `pdwConfigFlags` to get the values relevant to `useLegacyV2RuntimeActivationPolicy`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3ee75-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3ee75-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ee75-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3ee75-113">Requirements</span></span>  
 <span data-ttu-id="3ee75-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3ee75-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ee75-115">**Encabezado**: Metahost.h</span><span class="sxs-lookup"><span data-stu-id="3ee75-115">**Header:** Metahost.h</span></span>  
  
 <span data-ttu-id="3ee75-116">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3ee75-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="3ee75-117">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="3ee75-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3ee75-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="3ee75-118">See also</span></span>

- [<span data-ttu-id="3ee75-119">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="3ee75-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
- [<span data-ttu-id="3ee75-120">Método GetRequestedRuntime</span><span class="sxs-lookup"><span data-stu-id="3ee75-120">GetRequestedRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)
- [<span data-ttu-id="3ee75-121">\<Inicio > elemento</span><span class="sxs-lookup"><span data-stu-id="3ee75-121">\<startup> Element</span></span>](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)
