---
title: IGCHost2 (Interfaz)
ms.date: 03/30/2017
api_name:
- IGCHost2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IGCHost2
helpviewer_keywords:
- IGCHost2 interface [.NET Framework hosting]
ms.assetid: e5323fa4-18ac-424d-859d-a65a550d08d9
topic_type:
- apiref
ms.openlocfilehash: 43c16415c91521194e0d88be84dd176c3fdadad1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134836"
---
# <a name="igchost2-interface"></a><span data-ttu-id="5c333-102">IGCHost2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5c333-102">IGCHost2 Interface</span></span>
<span data-ttu-id="5c333-103">Proporciona métodos para obtener información sobre el sistema de recolección de elementos no utilizados y para controlar algunos aspectos de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="5c333-103">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5c333-104">En el caso del nuevo desarrollo, se recomienda utilizar la interfaz [iclrgcmanager2 (](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="5c333-104">For new development, we recommend that you use the [ICLRGCManager2](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md) interface instead.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5c333-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="5c333-105">Methods</span></span>  
  
|<span data-ttu-id="5c333-106">Método</span><span class="sxs-lookup"><span data-stu-id="5c333-106">Method</span></span>|<span data-ttu-id="5c333-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="5c333-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5c333-108">SetGCStartupLimitsEx (método)</span><span class="sxs-lookup"><span data-stu-id="5c333-108">SetGCStartupLimitsEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md)|<span data-ttu-id="5c333-109">Establece el tamaño del segmento y el tamaño máximo de la generación 0.</span><span class="sxs-lookup"><span data-stu-id="5c333-109">Sets the segment size and the maximum size for generation 0.</span></span> <span data-ttu-id="5c333-110">Habilita la generación 0 y los tamaños de segmento mayores que `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="5c333-110">Enables generation 0 and segment sizes larger than `DWORD`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5c333-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5c333-111">Requirements</span></span>  
 <span data-ttu-id="5c333-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c333-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c333-113">**Encabezado:** GCHost. idl, GCHost. h</span><span class="sxs-lookup"><span data-stu-id="5c333-113">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="5c333-114">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="5c333-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5c333-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c333-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c333-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="5c333-116">See also</span></span>

- [<span data-ttu-id="5c333-117">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="5c333-117">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="5c333-118">Interfaces de hospedaje de CLR</span><span class="sxs-lookup"><span data-stu-id="5c333-118">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [<span data-ttu-id="5c333-119">CorRuntimeHost (coclase)</span><span class="sxs-lookup"><span data-stu-id="5c333-119">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
