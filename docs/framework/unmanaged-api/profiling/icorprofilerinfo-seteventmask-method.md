---
description: 'Más información acerca de: ICorProfilerInfo:: SetEventMask (método)'
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
ms.openlocfilehash: e389d25abfecfc9a5dec8834e412fe618324e311
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99687199"
---
# <a name="icorprofilerinfoseteventmask-method"></a><span data-ttu-id="fbf82-103">ICorProfilerInfo::SetEventMask (Método)</span><span class="sxs-lookup"><span data-stu-id="fbf82-103">ICorProfilerInfo::SetEventMask Method</span></span>

<span data-ttu-id="fbf82-104">Establece un valor que especifica los tipos de eventos para los que el generador de perfiles quiere recibir notificaciones desde Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="fbf82-104">Sets a value that specifies the types of events for which the profiler wants to receive notification from the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fbf82-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fbf82-105">Syntax</span></span>  
  
```cpp  
HRESULT SetEventMask(  
    [in] DWORD dwEvents);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fbf82-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fbf82-106">Parameters</span></span>  

 `dwEvents`  
 <span data-ttu-id="fbf82-107">[in] Valor de 4 bytes que especifica las categorías de eventos.</span><span class="sxs-lookup"><span data-stu-id="fbf82-107">[in] A 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="fbf82-108">Cada bit controla una funcionalidad, comportamiento o tipo de evento diferente.</span><span class="sxs-lookup"><span data-stu-id="fbf82-108">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="fbf82-109">Los bits se describen en la enumeración [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="fbf82-109">The bits are described in the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fbf82-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="fbf82-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fbf82-111">Debe llamar al método [SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) en lugar de a este método.</span><span class="sxs-lookup"><span data-stu-id="fbf82-111">You should call the [SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) method instead of this method.</span></span> <span data-ttu-id="fbf82-112">Aunque el `SetEventMask` método se sigue admitiendo, [SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) proporciona funcionalidad adicional.</span><span class="sxs-lookup"><span data-stu-id="fbf82-112">Although the `SetEventMask` method continues to be supported, [SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) provides additional functionality.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fbf82-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fbf82-113">Requirements</span></span>  

 <span data-ttu-id="fbf82-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fbf82-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fbf82-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fbf82-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fbf82-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fbf82-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fbf82-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fbf82-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbf82-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="fbf82-118">See also</span></span>

- [<span data-ttu-id="fbf82-119">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fbf82-119">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="fbf82-120">SetEventMask2 (método)</span><span class="sxs-lookup"><span data-stu-id="fbf82-120">SetEventMask2 Method</span></span>](icorprofilerinfo5-seteventmask2-method.md)
