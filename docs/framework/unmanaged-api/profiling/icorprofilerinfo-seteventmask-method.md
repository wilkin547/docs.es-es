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
ms.openlocfilehash: ed39411fa88c38da58e8a881c47d19b3b8c9ff8d
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76869284"
---
# <a name="icorprofilerinfoseteventmask-method"></a><span data-ttu-id="ba552-102">ICorProfilerInfo::SetEventMask (Método)</span><span class="sxs-lookup"><span data-stu-id="ba552-102">ICorProfilerInfo::SetEventMask Method</span></span>
<span data-ttu-id="ba552-103">Establece un valor que especifica los tipos de eventos para los que el generador de perfiles quiere recibir notificaciones desde Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="ba552-103">Sets a value that specifies the types of events for which the profiler wants to receive notification from the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba552-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ba552-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEventMask(  
    [in] DWORD dwEvents);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ba552-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="ba552-105">Parameters</span></span>  
 `dwEvents`  
 <span data-ttu-id="ba552-106">[in] Valor de 4 bytes que especifica las categorías de eventos.</span><span class="sxs-lookup"><span data-stu-id="ba552-106">[in] A 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="ba552-107">Cada bit controla una funcionalidad, comportamiento o tipo de evento diferente.</span><span class="sxs-lookup"><span data-stu-id="ba552-107">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="ba552-108">Los bits se describen en la enumeración [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="ba552-108">The bits are described in the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ba552-109">Notas</span><span class="sxs-lookup"><span data-stu-id="ba552-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ba552-110">Debe llamar al método [SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) en lugar de a este método.</span><span class="sxs-lookup"><span data-stu-id="ba552-110">You should call the [SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) method instead of this method.</span></span> <span data-ttu-id="ba552-111">Aunque el método de `SetEventMask` se sigue admitiendo, [SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) proporciona funcionalidad adicional.</span><span class="sxs-lookup"><span data-stu-id="ba552-111">Although the `SetEventMask` method continues to be supported, [SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) provides additional functionality.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba552-112">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="ba552-112">Requirements</span></span>  
 <span data-ttu-id="ba552-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ba552-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba552-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ba552-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ba552-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ba552-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ba552-116">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba552-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba552-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="ba552-117">See also</span></span>

- [<span data-ttu-id="ba552-118">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ba552-118">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="ba552-119">SetEventMask2 (método)</span><span class="sxs-lookup"><span data-stu-id="ba552-119">SetEventMask2 Method</span></span>](icorprofilerinfo5-seteventmask2-method.md)
