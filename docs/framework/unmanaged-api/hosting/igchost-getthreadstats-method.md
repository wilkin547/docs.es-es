---
description: 'Más información sobre: IGCHost:: GetThreadStats ((método)'
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
ms.openlocfilehash: 2d923560e915a0c88035caad70ad91149d793cb8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99709664"
---
# <a name="igchostgetthreadstats-method"></a><span data-ttu-id="3e4fa-103">IGCHost::GetThreadStats (Método)</span><span class="sxs-lookup"><span data-stu-id="3e4fa-103">IGCHost::GetThreadStats Method</span></span>

<span data-ttu-id="3e4fa-104">Obtiene las estadísticas por subproceso para la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="3e4fa-104">Gets the per-thread statistics for garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e4fa-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3e4fa-105">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadStats (  
    [in] DWORD *pFiberCookie,  
    [in, out] COR_GC_THREAD_STATS *pStats  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3e4fa-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3e4fa-106">Parameters</span></span>  

 `pFiberCookie`  
 <span data-ttu-id="3e4fa-107">de Puntero a una cookie de fibra que especifica el subproceso para el que se van a recuperar las estadísticas.</span><span class="sxs-lookup"><span data-stu-id="3e4fa-107">[in] A pointer to a fiber cookie that specifies the thread for which to retrieve the statistics.</span></span>  
  
 `pStats`  
 <span data-ttu-id="3e4fa-108">[in, out] Puntero a una estructura de [COR_GC_THREAD_STATS](cor-gc-thread-stats-structure.md) que contiene las estadísticas de recolección de elementos no utilizados para el subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="3e4fa-108">[in, out] A pointer to a [COR_GC_THREAD_STATS](cor-gc-thread-stats-structure.md) structure that contains the garbage collection statistics for the specified thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e4fa-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3e4fa-109">Requirements</span></span>  

 <span data-ttu-id="3e4fa-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3e4fa-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e4fa-111">**Encabezado:** GCHost. idl, GCHost. h</span><span class="sxs-lookup"><span data-stu-id="3e4fa-111">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="3e4fa-112">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3e4fa-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3e4fa-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e4fa-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e4fa-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="3e4fa-114">See also</span></span>

- [<span data-ttu-id="3e4fa-115">IGCHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3e4fa-115">IGCHost Interface</span></span>](igchost-interface.md)
