---
description: 'Más información sobre: IGCHost:: Getstats ((método)'
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
ms.openlocfilehash: 564224d01e23c8ac1fe81025ee87dabc41ed5166
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99709700"
---
# <a name="igchostgetstats-method"></a><span data-ttu-id="666e1-103">IGCHost::GetStats (Método)</span><span class="sxs-lookup"><span data-stu-id="666e1-103">IGCHost::GetStats Method</span></span>

<span data-ttu-id="666e1-104">Obtiene las estadísticas para el estado actual del sistema de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="666e1-104">Gets the statistics for the current state of the garbage collection system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="666e1-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="666e1-105">Syntax</span></span>  
  
```cpp  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="666e1-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="666e1-106">Parameters</span></span>  

 `pStats`  
 <span data-ttu-id="666e1-107">[in, out] Puntero a una estructura de [COR_GC_STATS](cor-gc-stats-structure.md) que contiene las estadísticas para el estado actual del sistema de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="666e1-107">[in, out] A pointer to a [COR_GC_STATS](cor-gc-stats-structure.md) structure that contains the statistics for the current state of the garbage collection system.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="666e1-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="666e1-108">Remarks</span></span>  

 <span data-ttu-id="666e1-109">Las estadísticas se pueden usar en un sistema de asignación inteligente para ayudar al funcionamiento del sistema de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="666e1-109">The statistics can be used by a smart allocation system to help the garbage collection system operate.</span></span> <span data-ttu-id="666e1-110">Por ejemplo, el sistema de asignación puede determinar, después de revisar las estadísticas, que necesita agregar más memoria o forzar una colección.</span><span class="sxs-lookup"><span data-stu-id="666e1-110">For example, the allocation system may determine, after reviewing the statistics, that it needs to add more memory or force a collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="666e1-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="666e1-111">Requirements</span></span>  

 <span data-ttu-id="666e1-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="666e1-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="666e1-113">**Encabezado:** GCHost. idl, GCHost. h</span><span class="sxs-lookup"><span data-stu-id="666e1-113">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="666e1-114">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="666e1-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="666e1-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="666e1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="666e1-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="666e1-116">See also</span></span>

- [<span data-ttu-id="666e1-117">IGCHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="666e1-117">IGCHost Interface</span></span>](igchost-interface.md)
