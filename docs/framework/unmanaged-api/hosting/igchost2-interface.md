---
title: IGCHost2 (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a616e724d6fb26734fcda48d6a9b39605e0284a5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="igchost2-interface"></a><span data-ttu-id="5a463-102">IGCHost2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5a463-102">IGCHost2 Interface</span></span>
<span data-ttu-id="5a463-103">Proporciona métodos para obtener información sobre el sistema de recopilación de elementos no utilizados y para controlar algunos aspectos de la recolección de elementos.</span><span class="sxs-lookup"><span data-stu-id="5a463-103">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5a463-104">Para el nuevo desarrollo, se recomienda que realice la [ICLRGCManager2](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md) interfaz en su lugar.</span><span class="sxs-lookup"><span data-stu-id="5a463-104">For new development, we recommend that you use the [ICLRGCManager2](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md) interface instead.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5a463-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="5a463-105">Methods</span></span>  
  
|<span data-ttu-id="5a463-106">Método</span><span class="sxs-lookup"><span data-stu-id="5a463-106">Method</span></span>|<span data-ttu-id="5a463-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="5a463-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5a463-108">SetGCStartupLimitsEx (método)</span><span class="sxs-lookup"><span data-stu-id="5a463-108">SetGCStartupLimitsEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md)|<span data-ttu-id="5a463-109">Establece el tamaño del segmento y el tamaño máximo para la generación 0.</span><span class="sxs-lookup"><span data-stu-id="5a463-109">Sets the segment size and the maximum size for generation 0.</span></span> <span data-ttu-id="5a463-110">Permite la generación 0 y tamaño de segmento mayor que `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="5a463-110">Enables generation 0 and segment sizes larger than `DWORD`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5a463-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5a463-111">Requirements</span></span>  
 <span data-ttu-id="5a463-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a463-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a463-113">**Encabezado:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="5a463-113">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="5a463-114">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5a463-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5a463-115">**Versiones de .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a463-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a463-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="5a463-116">See Also</span></span>  
 [<span data-ttu-id="5a463-117">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="5a463-117">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="5a463-118">Interfaces de hospedaje de CLR</span><span class="sxs-lookup"><span data-stu-id="5a463-118">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 [<span data-ttu-id="5a463-119">CorRuntimeHost (coclase)</span><span class="sxs-lookup"><span data-stu-id="5a463-119">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
