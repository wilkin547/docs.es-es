---
title: IGCHost::GetStats (Método)
ms.date: 03/30/2017
api_name:
- IGCHost.GetStats
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetStats
helpviewer_keywords:
- GetStats method, IGCHost interface [.NET Framework hosting]
- IGCHost::GetStats method [.NET Framework hosting]
ms.assetid: c4ae022c-46ac-4f19-9ddd-09b955f19412
topic_type:
- apiref
ms.openlocfilehash: c86786a34ff236fb57a1ea6bc4d00b9cd5c4a717
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134896"
---
# <a name="igchostgetstats-method"></a><span data-ttu-id="e7976-102">IGCHost::GetStats (Método)</span><span class="sxs-lookup"><span data-stu-id="e7976-102">IGCHost::GetStats Method</span></span>
<span data-ttu-id="e7976-103">Obtiene las estadísticas para el estado actual del sistema de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="e7976-103">Gets the statistics for the current state of the garbage collection system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7976-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e7976-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e7976-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e7976-105">Parameters</span></span>  
 `pStats`  
 <span data-ttu-id="e7976-106">[in, out] Puntero a una estructura [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) que contiene las estadísticas para el estado actual del sistema de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="e7976-106">[in, out] A pointer to a [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) structure that contains the statistics for the current state of the garbage collection system.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e7976-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e7976-107">Remarks</span></span>  
 <span data-ttu-id="e7976-108">Las estadísticas se pueden usar en un sistema de asignación inteligente para ayudar al funcionamiento del sistema de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="e7976-108">The statistics can be used by a smart allocation system to help the garbage collection system operate.</span></span> <span data-ttu-id="e7976-109">Por ejemplo, el sistema de asignación puede determinar, después de revisar las estadísticas, que necesita agregar más memoria o forzar una colección.</span><span class="sxs-lookup"><span data-stu-id="e7976-109">For example, the allocation system may determine, after reviewing the statistics, that it needs to add more memory or force a collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7976-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e7976-110">Requirements</span></span>  
 <span data-ttu-id="e7976-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7976-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7976-112">**Encabezado:** GCHost. idl, GCHost. h</span><span class="sxs-lookup"><span data-stu-id="e7976-112">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="e7976-113">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e7976-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e7976-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7976-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7976-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="e7976-115">See also</span></span>

- [<span data-ttu-id="e7976-116">IGCHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e7976-116">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
