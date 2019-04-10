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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 14751b41809eeda5e6bd990fae368879d0f30492
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59227839"
---
# <a name="igchostgetstats-method"></a><span data-ttu-id="c50b2-102">IGCHost::GetStats (Método)</span><span class="sxs-lookup"><span data-stu-id="c50b2-102">IGCHost::GetStats Method</span></span>
<span data-ttu-id="c50b2-103">Obtiene las estadísticas para el estado actual del sistema de recopilación de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="c50b2-103">Gets the statistics for the current state of the garbage collection system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c50b2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c50b2-104">Syntax</span></span>  
  
```  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c50b2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c50b2-105">Parameters</span></span>  
 `pStats`  
 <span data-ttu-id="c50b2-106">[in, out] Un puntero a un [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) estructura que contiene las estadísticas para el estado actual del sistema de recopilación de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="c50b2-106">[in, out] A pointer to a [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) structure that contains the statistics for the current state of the garbage collection system.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c50b2-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c50b2-107">Remarks</span></span>  
 <span data-ttu-id="c50b2-108">Las estadísticas se pueden usar un sistema de asignación inteligente para el sistema de recopilación de elementos no utilizados que funcione.</span><span class="sxs-lookup"><span data-stu-id="c50b2-108">The statistics can be used by a smart allocation system to help the garbage collection system operate.</span></span> <span data-ttu-id="c50b2-109">Por ejemplo, puede determinar el sistema de asignación después de revisar las estadísticas, lo que necesita para agregar más memoria o forzar una recolección.</span><span class="sxs-lookup"><span data-stu-id="c50b2-109">For example, the allocation system may determine, after reviewing the statistics, that it needs to add more memory or force a collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c50b2-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c50b2-110">Requirements</span></span>  
 <span data-ttu-id="c50b2-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c50b2-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c50b2-112">**Encabezado**: GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="c50b2-112">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="c50b2-113">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c50b2-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="c50b2-114">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="c50b2-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c50b2-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="c50b2-115">See also</span></span>

- [<span data-ttu-id="c50b2-116">IGCHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c50b2-116">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
