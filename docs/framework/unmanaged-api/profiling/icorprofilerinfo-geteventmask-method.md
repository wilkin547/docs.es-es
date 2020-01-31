---
title: ICorProfilerInfo::GetEventMask (Método)
ms.date: 03/30/2017
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
ms.openlocfilehash: 63f19fe899abd75380249e171f248480949bc471
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863912"
---
# <a name="icorprofilerinfogeteventmask-method"></a><span data-ttu-id="b1134-102">ICorProfilerInfo::GetEventMask (Método)</span><span class="sxs-lookup"><span data-stu-id="b1134-102">ICorProfilerInfo::GetEventMask Method</span></span>
<span data-ttu-id="b1134-103">Obtiene las categorías de eventos actuales para las que el generador de perfiles quiere recibir notificaciones de eventos para Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="b1134-103">Gets the current event categories for which the profiler wants to receive event notifications from the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1134-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b1134-104">Syntax</span></span>  
  
```cpp  
HRESULT GetEventMask(  
    [out] DWORD *pdwEvents);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b1134-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="b1134-105">Parameters</span></span>  
 `pdwEvents`  
 <span data-ttu-id="b1134-106">[out] Puntero a un valor de 4 bytes que especifica las categorías de eventos.</span><span class="sxs-lookup"><span data-stu-id="b1134-106">[out] A pointer to a 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="b1134-107">Cada bit controla una funcionalidad, comportamiento o tipo de evento diferente.</span><span class="sxs-lookup"><span data-stu-id="b1134-107">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="b1134-108">Los bits se describen en la enumeración [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="b1134-108">The bits are described in the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b1134-109">Notas</span><span class="sxs-lookup"><span data-stu-id="b1134-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b1134-110">Debe llamar al método [GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) en lugar de a este método.</span><span class="sxs-lookup"><span data-stu-id="b1134-110">You should call the [GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) method instead of this method.</span></span> <span data-ttu-id="b1134-111">Aunque el método de `SetEventMask` se sigue admitiendo, [GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) proporciona funcionalidad adicional.</span><span class="sxs-lookup"><span data-stu-id="b1134-111">Although the `SetEventMask` method continues to be supported, [GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) provides additional functionality.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1134-112">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="b1134-112">Requirements</span></span>  
 <span data-ttu-id="b1134-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b1134-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1134-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b1134-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b1134-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b1134-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b1134-116">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1134-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1134-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="b1134-117">See also</span></span>

- [<span data-ttu-id="b1134-118">GetEventMask2 (método)</span><span class="sxs-lookup"><span data-stu-id="b1134-118">GetEventMask2 Method</span></span>](icorprofilerinfo5-geteventmask2-method.md)
- [<span data-ttu-id="b1134-119">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b1134-119">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
