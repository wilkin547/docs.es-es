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
ms.openlocfilehash: f6a4ee32d1f0bd6f66b2cd2249dd90522062cdab
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120950"
---
# <a name="icorprofilerinfogeteventmask-method"></a><span data-ttu-id="36547-102">ICorProfilerInfo::GetEventMask (Método)</span><span class="sxs-lookup"><span data-stu-id="36547-102">ICorProfilerInfo::GetEventMask Method</span></span>
<span data-ttu-id="36547-103">Obtiene las categorías de eventos actuales para las que el generador de perfiles quiere recibir notificaciones de eventos para Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="36547-103">Gets the current event categories for which the profiler wants to receive event notifications from the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36547-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="36547-104">Syntax</span></span>  
  
```cpp  
HRESULT GetEventMask(  
    [out] DWORD *pdwEvents);  
```  
  
## <a name="parameters"></a><span data-ttu-id="36547-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="36547-105">Parameters</span></span>  
 `pdwEvents`  
 <span data-ttu-id="36547-106">[out] Puntero a un valor de 4 bytes que especifica las categorías de eventos.</span><span class="sxs-lookup"><span data-stu-id="36547-106">[out] A pointer to a 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="36547-107">Cada bit controla una funcionalidad, comportamiento o tipo de evento diferente.</span><span class="sxs-lookup"><span data-stu-id="36547-107">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="36547-108">Los bits se describen en la enumeración [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="36547-108">The bits are described in the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="36547-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="36547-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="36547-110">Debe llamar al método [GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) en lugar de a este método.</span><span class="sxs-lookup"><span data-stu-id="36547-110">You should call the [GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) method instead of this method.</span></span> <span data-ttu-id="36547-111">Aunque el método de `SetEventMask` se sigue admitiendo, [GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) proporciona funcionalidad adicional.</span><span class="sxs-lookup"><span data-stu-id="36547-111">Although the `SetEventMask` method continues to be supported, [GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) provides additional functionality.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36547-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="36547-112">Requirements</span></span>  
 <span data-ttu-id="36547-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="36547-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36547-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="36547-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="36547-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="36547-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="36547-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36547-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36547-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="36547-117">See also</span></span>

- [<span data-ttu-id="36547-118">GetEventMask2 (método)</span><span class="sxs-lookup"><span data-stu-id="36547-118">GetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md)
- [<span data-ttu-id="36547-119">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="36547-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
