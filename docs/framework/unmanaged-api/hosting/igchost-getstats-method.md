---
title: "IGCHost::GetStats (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IGCHost.GetStats
api_location: mscoree.dll
api_type: COM
f1_keywords: GetStats
helpviewer_keywords:
- GetStats method, IGCHost interface [.NET Framework hosting]
- IGCHost::GetStats method [.NET Framework hosting]
ms.assetid: c4ae022c-46ac-4f19-9ddd-09b955f19412
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6c8db4f854b73d04e7260457c978a7a644677559
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="igchostgetstats-method"></a><span data-ttu-id="53e2e-102">IGCHost::GetStats (Método)</span><span class="sxs-lookup"><span data-stu-id="53e2e-102">IGCHost::GetStats Method</span></span>
<span data-ttu-id="53e2e-103">Obtiene las estadísticas para el estado actual del sistema de recopilación de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="53e2e-103">Gets the statistics for the current state of the garbage collection system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53e2e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="53e2e-104">Syntax</span></span>  
  
```  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="53e2e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="53e2e-105">Parameters</span></span>  
 `pStats`  
 <span data-ttu-id="53e2e-106">[entrada, salida] Un puntero a un [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) estructura que contiene las estadísticas para el estado actual del sistema de recopilación de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="53e2e-106">[in, out] A pointer to a [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) structure that contains the statistics for the current state of the garbage collection system.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="53e2e-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="53e2e-107">Remarks</span></span>  
 <span data-ttu-id="53e2e-108">Las estadísticas se pueden utilizar un sistema de asignación inteligente para el sistema de recopilación de elementos no utilizados que funcione.</span><span class="sxs-lookup"><span data-stu-id="53e2e-108">The statistics can be used by a smart allocation system to help the garbage collection system operate.</span></span> <span data-ttu-id="53e2e-109">Por ejemplo, puede determinar el sistema de asignación después de revisar las estadísticas, que necesita agregar más memoria o forzar una recolección.</span><span class="sxs-lookup"><span data-stu-id="53e2e-109">For example, the allocation system may determine, after reviewing the statistics, that it needs to add more memory or force a collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53e2e-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="53e2e-110">Requirements</span></span>  
 <span data-ttu-id="53e2e-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="53e2e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53e2e-112">**Encabezado:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="53e2e-112">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="53e2e-113">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="53e2e-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="53e2e-114">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53e2e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53e2e-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="53e2e-115">See Also</span></span>  
 [<span data-ttu-id="53e2e-116">IGCHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="53e2e-116">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
