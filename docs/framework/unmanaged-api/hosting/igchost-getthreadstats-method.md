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
ms.openlocfilehash: 36eeb7ed4f80979ef2edb930e65963a1db0c894f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134901"
---
# <a name="igchostgetthreadstats-method"></a><span data-ttu-id="58303-102">IGCHost::GetThreadStats (Método)</span><span class="sxs-lookup"><span data-stu-id="58303-102">IGCHost::GetThreadStats Method</span></span>
<span data-ttu-id="58303-103">Obtiene las estadísticas por subproceso para la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="58303-103">Gets the per-thread statistics for garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58303-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="58303-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadStats (  
    [in] DWORD *pFiberCookie,  
    [in, out] COR_GC_THREAD_STATS *pStats  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="58303-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="58303-105">Parameters</span></span>  
 `pFiberCookie`  
 <span data-ttu-id="58303-106">de Puntero a una cookie de fibra que especifica el subproceso para el que se van a recuperar las estadísticas.</span><span class="sxs-lookup"><span data-stu-id="58303-106">[in] A pointer to a fiber cookie that specifies the thread for which to retrieve the statistics.</span></span>  
  
 `pStats`  
 <span data-ttu-id="58303-107">[in, out] Puntero a una estructura [COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) que contiene las estadísticas de recolección de elementos no utilizados para el subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="58303-107">[in, out] A pointer to a [COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) structure that contains the garbage collection statistics for the specified thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58303-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="58303-108">Requirements</span></span>  
 <span data-ttu-id="58303-109">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58303-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58303-110">**Encabezado:** GCHost. idl, GCHost. h</span><span class="sxs-lookup"><span data-stu-id="58303-110">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="58303-111">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="58303-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="58303-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58303-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58303-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="58303-113">See also</span></span>

- [<span data-ttu-id="58303-114">IGCHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="58303-114">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
