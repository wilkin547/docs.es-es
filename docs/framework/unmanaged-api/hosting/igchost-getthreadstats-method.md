---
title: IGCHost::GetThreadStats (Método)
ms.date: 03/30/2017
api_name:
- IGCHost.GetThreadStats
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetThreadStats
helpviewer_keywords:
- IGCHost::GetThreadStats method [.NET Framework hosting]
- GetThreadStats method [.NET Framework hosting]
ms.assetid: 826baa9b-9218-4736-a509-7ab193b125a0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 74827fac102ee6045965f4ba9d74dd3b1aa0af86
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33437575"
---
# <a name="igchostgetthreadstats-method"></a><span data-ttu-id="87f41-102">IGCHost::GetThreadStats (Método)</span><span class="sxs-lookup"><span data-stu-id="87f41-102">IGCHost::GetThreadStats Method</span></span>
<span data-ttu-id="87f41-103">Obtiene las estadísticas por subproceso para la recolección.</span><span class="sxs-lookup"><span data-stu-id="87f41-103">Gets the per-thread statistics for garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87f41-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="87f41-104">Syntax</span></span>  
  
```  
HRESULT GetThreadStats (  
    [in] DWORD *pFiberCookie,  
    [in, out] COR_GC_THREAD_STATS *pStats  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="87f41-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="87f41-105">Parameters</span></span>  
 `pFiberCookie`  
 <span data-ttu-id="87f41-106">[in] Un puntero a una cookie de fibra que especifica el subproceso para el que se va a recuperar las estadísticas.</span><span class="sxs-lookup"><span data-stu-id="87f41-106">[in] A pointer to a fiber cookie that specifies the thread for which to retrieve the statistics.</span></span>  
  
 `pStats`  
 <span data-ttu-id="87f41-107">[entrada, salida] Un puntero a un [COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) estructura que contiene las estadísticas de la colección de elementos no utilizados para el subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="87f41-107">[in, out] A pointer to a [COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) structure that contains the garbage collection statistics for the specified thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87f41-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="87f41-108">Requirements</span></span>  
 <span data-ttu-id="87f41-109">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="87f41-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87f41-110">**Encabezado:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="87f41-110">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="87f41-111">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="87f41-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="87f41-112">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87f41-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87f41-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="87f41-113">See Also</span></span>  
 [<span data-ttu-id="87f41-114">IGCHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="87f41-114">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
