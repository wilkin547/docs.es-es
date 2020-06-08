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
ms.openlocfilehash: 7faa4a5f7b1ca1fbf165c40eb3a3cb32a42a21a4
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84498341"
---
# <a name="icorprofilerinfogeteventmask-method"></a><span data-ttu-id="02ebb-102">ICorProfilerInfo::GetEventMask (Método)</span><span class="sxs-lookup"><span data-stu-id="02ebb-102">ICorProfilerInfo::GetEventMask Method</span></span>
<span data-ttu-id="02ebb-103">Obtiene las categorías de eventos actuales para las que el generador de perfiles quiere recibir notificaciones de eventos para Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="02ebb-103">Gets the current event categories for which the profiler wants to receive event notifications from the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02ebb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="02ebb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetEventMask(  
    [out] DWORD *pdwEvents);  
```  
  
## <a name="parameters"></a><span data-ttu-id="02ebb-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="02ebb-105">Parameters</span></span>  
 `pdwEvents`  
 <span data-ttu-id="02ebb-106">[out] Puntero a un valor de 4 bytes que especifica las categorías de eventos.</span><span class="sxs-lookup"><span data-stu-id="02ebb-106">[out] A pointer to a 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="02ebb-107">Cada bit controla una funcionalidad, comportamiento o tipo de evento diferente.</span><span class="sxs-lookup"><span data-stu-id="02ebb-107">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="02ebb-108">Los bits se describen en la enumeración [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="02ebb-108">The bits are described in the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="02ebb-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="02ebb-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="02ebb-110">Debe llamar al método [GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) en lugar de a este método.</span><span class="sxs-lookup"><span data-stu-id="02ebb-110">You should call the [GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) method instead of this method.</span></span> <span data-ttu-id="02ebb-111">Aunque el `SetEventMask` método se sigue admitiendo, [GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) proporciona funcionalidad adicional.</span><span class="sxs-lookup"><span data-stu-id="02ebb-111">Although the `SetEventMask` method continues to be supported, [GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) provides additional functionality.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02ebb-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="02ebb-112">Requirements</span></span>  
 <span data-ttu-id="02ebb-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="02ebb-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02ebb-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="02ebb-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="02ebb-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="02ebb-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="02ebb-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02ebb-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02ebb-117">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="02ebb-117">See also</span></span>

- [<span data-ttu-id="02ebb-118">GetEventMask2 (método)</span><span class="sxs-lookup"><span data-stu-id="02ebb-118">GetEventMask2 Method</span></span>](icorprofilerinfo5-geteventmask2-method.md)
- [<span data-ttu-id="02ebb-119">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="02ebb-119">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
