---
title: ICorProfilerInfo::SetEventMask (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetEventMask
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetEventMask
helpviewer_keywords:
- ICorProfilerInfo::SetEventMask method [.NET Framework profiling]
- SetEventMask method [.NET Framework profiling]
ms.assetid: 44bc0f56-32fa-491e-a62d-52fc96d48125
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 34aba20704ff8dc0d699ebee9440745d19c697b8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54566013"
---
# <a name="icorprofilerinfoseteventmask-method"></a><span data-ttu-id="2501a-102">ICorProfilerInfo::SetEventMask (Método)</span><span class="sxs-lookup"><span data-stu-id="2501a-102">ICorProfilerInfo::SetEventMask Method</span></span>
<span data-ttu-id="2501a-103">Establece un valor que especifica los tipos de eventos para los que el generador de perfiles quiere recibir notificaciones desde Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="2501a-103">Sets a value that specifies the types of events for which the profiler wants to receive notification from the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2501a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2501a-104">Syntax</span></span>  
  
```  
HRESULT SetEventMask(  
    [in] DWORD dwEvents);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2501a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2501a-105">Parameters</span></span>  
 `dwEvents`  
 <span data-ttu-id="2501a-106">[in] Valor de 4 bytes que especifica las categorías de eventos.</span><span class="sxs-lookup"><span data-stu-id="2501a-106">[in] A 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="2501a-107">Cada bit controla una funcionalidad, comportamiento o tipo de evento diferente.</span><span class="sxs-lookup"><span data-stu-id="2501a-107">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="2501a-108">Los bits se describen en la [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeración.</span><span class="sxs-lookup"><span data-stu-id="2501a-108">The bits are described in the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2501a-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2501a-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2501a-110">Debe llamar a la [SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) método en lugar de este método.</span><span class="sxs-lookup"><span data-stu-id="2501a-110">You should call the [SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) method instead of this method.</span></span> <span data-ttu-id="2501a-111">Aunque el `SetEventMask` método sigue siendo compatible, [SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) proporciona funcionalidad adicional.</span><span class="sxs-lookup"><span data-stu-id="2501a-111">Although the `SetEventMask` method continues to be supported, [SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) provides additional functionality.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2501a-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2501a-112">Requirements</span></span>  
 <span data-ttu-id="2501a-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2501a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2501a-114">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2501a-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2501a-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2501a-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2501a-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2501a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2501a-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="2501a-117">See also</span></span>
- [<span data-ttu-id="2501a-118">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2501a-118">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="2501a-119">SetEventMask2 (método)</span><span class="sxs-lookup"><span data-stu-id="2501a-119">SetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)
