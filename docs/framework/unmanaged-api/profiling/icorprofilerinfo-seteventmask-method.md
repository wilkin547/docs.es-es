---
title: "ICorProfilerInfo::SetEventMask (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.SetEventMask
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::SetEventMask
helpviewer_keywords:
- ICorProfilerInfo::SetEventMask method [.NET Framework profiling]
- SetEventMask method [.NET Framework profiling]
ms.assetid: 44bc0f56-32fa-491e-a62d-52fc96d48125
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bb42be7f8e5722ec9924284c257e814a186564d0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfoseteventmask-method"></a><span data-ttu-id="7af20-102">ICorProfilerInfo::SetEventMask (Método)</span><span class="sxs-lookup"><span data-stu-id="7af20-102">ICorProfilerInfo::SetEventMask Method</span></span>
<span data-ttu-id="7af20-103">Establece un valor que especifica los tipos de eventos para los que el generador de perfiles quiere recibir notificaciones desde Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="7af20-103">Sets a value that specifies the types of events for which the profiler wants to receive notification from the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7af20-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7af20-104">Syntax</span></span>  
  
```  
HRESULT SetEventMask(  
    [in] DWORD dwEvents);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7af20-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7af20-105">Parameters</span></span>  
 `dwEvents`  
 <span data-ttu-id="7af20-106">[in] Valor de 4 bytes que especifica las categorías de eventos.</span><span class="sxs-lookup"><span data-stu-id="7af20-106">[in] A 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="7af20-107">Cada bit controla una funcionalidad, comportamiento o tipo de evento diferente.</span><span class="sxs-lookup"><span data-stu-id="7af20-107">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="7af20-108">Los bits se describen en la [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeración.</span><span class="sxs-lookup"><span data-stu-id="7af20-108">The bits are described in the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7af20-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7af20-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7af20-110">Debe llamar a la [SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) método en lugar de este método.</span><span class="sxs-lookup"><span data-stu-id="7af20-110">You should call the [SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) method instead of this method.</span></span> <span data-ttu-id="7af20-111">Aunque la `SetEventMask` método sigue siendo compatible, [SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) proporciona funcionalidad adicional.</span><span class="sxs-lookup"><span data-stu-id="7af20-111">Although the `SetEventMask` method continues to be supported, [SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) provides additional functionality.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7af20-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7af20-112">Requirements</span></span>  
 <span data-ttu-id="7af20-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7af20-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7af20-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7af20-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7af20-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7af20-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7af20-116">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7af20-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7af20-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="7af20-117">See Also</span></span>  
 [<span data-ttu-id="7af20-118">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7af20-118">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="7af20-119">SetEventMask2 (método)</span><span class="sxs-lookup"><span data-stu-id="7af20-119">SetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)
