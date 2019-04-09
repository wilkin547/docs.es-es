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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5b249605833e8fbd219495ab92bebc2eff6177eb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59094260"
---
# <a name="icorprofilerinfo5-interface"></a><span data-ttu-id="fe31b-102">ICorProfilerInfo5 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fe31b-102">ICorProfilerInfo5 Interface</span></span>
<span data-ttu-id="fe31b-103">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="fe31b-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="fe31b-104">Una subclase de [ICorProfilerInfo4](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md) que proporciona métodos para su uso por los generadores de perfiles de código para comunicarse con common language runtime (CLR) para controlar la supervisión de eventos.</span><span class="sxs-lookup"><span data-stu-id="fe31b-104">A subclass of [ICorProfilerInfo4](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md) that provides methods for use by code profilers to communicate with the common language runtime (CLR) to control event monitoring.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fe31b-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="fe31b-105">Methods</span></span>  
  
|<span data-ttu-id="fe31b-106">Método</span><span class="sxs-lookup"><span data-stu-id="fe31b-106">Method</span></span>|<span data-ttu-id="fe31b-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="fe31b-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fe31b-108">Método GetEventMask2</span><span class="sxs-lookup"><span data-stu-id="fe31b-108">GetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md)|<span data-ttu-id="fe31b-109">Obtiene las categorías de eventos actuales para las que el generador de perfiles quiere recibir notificaciones de CLR.</span><span class="sxs-lookup"><span data-stu-id="fe31b-109">Gets the current event categories for which the profiler wants to receive notifications from the CLR.</span></span>|  
|[<span data-ttu-id="fe31b-110">Método SetEventMask2</span><span class="sxs-lookup"><span data-stu-id="fe31b-110">SetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)|<span data-ttu-id="fe31b-111">Establece un valor que especifica los tipos de eventos para los que el generador de perfiles quiere recibir notificaciones de eventos desde CLR.</span><span class="sxs-lookup"><span data-stu-id="fe31b-111">Sets a value that specifies the types of events for which the profiler wants to receive event notifications from the CLR.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fe31b-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fe31b-112">Remarks</span></span>  
 <span data-ttu-id="fe31b-113">Los métodos disponibles en esta interfaz están pensados para reemplazar el [ICorProfilerInfo:: GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md) y [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) métodos.</span><span class="sxs-lookup"><span data-stu-id="fe31b-113">The methods available on this interface are intended to replace the [ICorProfilerInfo::GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md) and [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe31b-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fe31b-114">Requirements</span></span>  
 <span data-ttu-id="fe31b-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fe31b-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe31b-116">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fe31b-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 **<span data-ttu-id="fe31b-117">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="fe31b-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fe31b-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="fe31b-118">See also</span></span>

- [<span data-ttu-id="fe31b-119">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="fe31b-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
