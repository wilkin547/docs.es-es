---
title: "IGCHost2::SetGCStartupLimitsEx (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IGCHost2.SetGCStartupLimitsEx
api_location: mscoree.dll
api_type: COM
f1_keywords: IGCHost2::SetGCStartupLimitsEx
helpviewer_keywords:
- IGCHost2::SetGCStartupLimitsEx method [.NET Framework hosting]
- SetGCStartupLimitsEx method, IGCHost2 interface [.NET Framework hosting]
ms.assetid: bba941c2-1c57-46d3-bbf5-5fb92700c490
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ae924447e38dfec8d365fe6cdc85e5dccb028714
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="igchost2setgcstartuplimitsex-method"></a><span data-ttu-id="e5710-102">IGCHost2::SetGCStartupLimitsEx (Método)</span><span class="sxs-lookup"><span data-stu-id="e5710-102">IGCHost2::SetGCStartupLimitsEx Method</span></span>
<span data-ttu-id="e5710-103">Establece el tamaño del segmento y el tamaño máximo para la generación 0.</span><span class="sxs-lookup"><span data-stu-id="e5710-103">Sets the segment size and the maximum size for generation 0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5710-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e5710-104">Syntax</span></span>  
  
```  
HRESULT SetGCStartupLimitsEx (  
    [in] SIZE_T SegmentSize,  
    [in] SIZE_T MaxGen0Size  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e5710-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e5710-105">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="e5710-106">[in] El tamaño del segmento utilizado por el sistema de recopilación de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="e5710-106">[in] The size of the segment used by the garbage collection system.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="e5710-107">[in] El tamaño máximo para la generación 0.</span><span class="sxs-lookup"><span data-stu-id="e5710-107">[in] The maximum size for generation 0.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e5710-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e5710-108">Remarks</span></span>  
 <span data-ttu-id="e5710-109">Los valores que `SetGCStartupLimitsEx` se pueden especificar conjuntos sólo antes de que se inicie el host.</span><span class="sxs-lookup"><span data-stu-id="e5710-109">The values that `SetGCStartupLimitsEx` sets can be specified only before the host is started.</span></span> <span data-ttu-id="e5710-110">Estos valores no se puede cambiar más adelante.</span><span class="sxs-lookup"><span data-stu-id="e5710-110">These values cannot be changed later.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5710-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e5710-111">Requirements</span></span>  
 <span data-ttu-id="e5710-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5710-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5710-113">**Encabezado:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="e5710-113">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="e5710-114">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e5710-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e5710-115">**Versiones de .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5710-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5710-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="e5710-116">See Also</span></span>  
 [<span data-ttu-id="e5710-117">IGCHost2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e5710-117">IGCHost2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost2-interface.md)
