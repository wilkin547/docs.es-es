---
title: ICorProfilerInfo5 (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo5
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 7bd48c34-37ed-4230-9eec-39a17280f05d
topic_type:
- apiref
ms.openlocfilehash: 82f6262c2c576b49be4e7fcaa14043950df4c67a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495632"
---
# <a name="icorprofilerinfo5-interface"></a><span data-ttu-id="c26d4-102">ICorProfilerInfo5 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c26d4-102">ICorProfilerInfo5 Interface</span></span>
<span data-ttu-id="c26d4-103">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="c26d4-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="c26d4-104">Subclase de [ICorProfilerInfo4](icorprofilerinfo4-interface.md) que proporciona métodos para que los profileres de código puedan usar para comunicarse con el Common Language Runtime (CLR) para controlar la supervisión de eventos.</span><span class="sxs-lookup"><span data-stu-id="c26d4-104">A subclass of [ICorProfilerInfo4](icorprofilerinfo4-interface.md) that provides methods for use by code profilers to communicate with the common language runtime (CLR) to control event monitoring.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c26d4-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="c26d4-105">Methods</span></span>  
  
|<span data-ttu-id="c26d4-106">Método</span><span class="sxs-lookup"><span data-stu-id="c26d4-106">Method</span></span>|<span data-ttu-id="c26d4-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="c26d4-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c26d4-108">GetEventMask2 (método)</span><span class="sxs-lookup"><span data-stu-id="c26d4-108">GetEventMask2 Method</span></span>](icorprofilerinfo5-geteventmask2-method.md)|<span data-ttu-id="c26d4-109">Obtiene las categorías de eventos actuales para las que el generador de perfiles quiere recibir notificaciones de CLR.</span><span class="sxs-lookup"><span data-stu-id="c26d4-109">Gets the current event categories for which the profiler wants to receive notifications from the CLR.</span></span>|  
|[<span data-ttu-id="c26d4-110">SetEventMask2 (método)</span><span class="sxs-lookup"><span data-stu-id="c26d4-110">SetEventMask2 Method</span></span>](icorprofilerinfo5-seteventmask2-method.md)|<span data-ttu-id="c26d4-111">Establece un valor que especifica los tipos de eventos para los que el generador de perfiles quiere recibir notificaciones de eventos desde CLR.</span><span class="sxs-lookup"><span data-stu-id="c26d4-111">Sets a value that specifies the types of events for which the profiler wants to receive event notifications from the CLR.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c26d4-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c26d4-112">Remarks</span></span>  
 <span data-ttu-id="c26d4-113">Los métodos disponibles en esta interfaz están diseñados para reemplazar los métodos [ICorProfilerInfo:: GetEventMask (](icorprofilerinfo-geteventmask-method.md) y [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) .</span><span class="sxs-lookup"><span data-stu-id="c26d4-113">The methods available on this interface are intended to replace the [ICorProfilerInfo::GetEventMask](icorprofilerinfo-geteventmask-method.md) and [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c26d4-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c26d4-114">Requirements</span></span>  
 <span data-ttu-id="c26d4-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c26d4-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c26d4-116">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c26d4-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c26d4-117">**.NET Framework versiones:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c26d4-117">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c26d4-118">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="c26d4-118">See also</span></span>

- [<span data-ttu-id="c26d4-119">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="c26d4-119">Profiling Interfaces</span></span>](profiling-interfaces.md)
