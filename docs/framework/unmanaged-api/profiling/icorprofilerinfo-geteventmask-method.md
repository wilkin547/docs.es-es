---
title: "ICorProfilerInfo::GetEventMask (Método)"
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
- ICorProfilerInfo.GetEventMask
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetEventMask
helpviewer_keywords:
- GetEventMask method [.NET Framework profiling]
- ICorProfilerInfo::GetEventMask method [.NET Framework profiling]
ms.assetid: ec34cc13-45a3-4695-abc3-b3347d4e6fc2
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1f8bfc0dc5686aa560bfa8282256b5e476976136
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfogeteventmask-method"></a><span data-ttu-id="24ef6-102">ICorProfilerInfo::GetEventMask (Método)</span><span class="sxs-lookup"><span data-stu-id="24ef6-102">ICorProfilerInfo::GetEventMask Method</span></span>
<span data-ttu-id="24ef6-103">Obtiene las categorías de eventos actuales para las que el generador de perfiles quiere recibir notificaciones de eventos para Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="24ef6-103">Gets the current event categories for which the profiler wants to receive event notifications from the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24ef6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="24ef6-104">Syntax</span></span>  
  
```  
HRESULT GetEventMask(  
    [out] DWORD *pdwEvents);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="24ef6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="24ef6-105">Parameters</span></span>  
 `pdwEvents`  
 <span data-ttu-id="24ef6-106">[out] Puntero a un valor de 4 bytes que especifica las categorías de eventos.</span><span class="sxs-lookup"><span data-stu-id="24ef6-106">[out] A pointer to a 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="24ef6-107">Cada bit controla una funcionalidad, comportamiento o tipo de evento diferente.</span><span class="sxs-lookup"><span data-stu-id="24ef6-107">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="24ef6-108">Los bits se describen en la [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeración.</span><span class="sxs-lookup"><span data-stu-id="24ef6-108">The bits are described in the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="24ef6-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="24ef6-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="24ef6-110">Debe llamar a la [GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) método en lugar de este método.</span><span class="sxs-lookup"><span data-stu-id="24ef6-110">You should call the [GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) method instead of this method.</span></span> <span data-ttu-id="24ef6-111">Aunque la `SetEventMask` método sigue siendo compatible, [GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) proporciona funcionalidad adicional.</span><span class="sxs-lookup"><span data-stu-id="24ef6-111">Although the `SetEventMask` method continues to be supported, [GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) provides additional functionality.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24ef6-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="24ef6-112">Requirements</span></span>  
 <span data-ttu-id="24ef6-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="24ef6-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24ef6-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="24ef6-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="24ef6-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="24ef6-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="24ef6-116">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24ef6-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24ef6-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="24ef6-117">See Also</span></span>  
 [<span data-ttu-id="24ef6-118">GetEventMask2 (método)</span><span class="sxs-lookup"><span data-stu-id="24ef6-118">GetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md)  
 [<span data-ttu-id="24ef6-119">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="24ef6-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
