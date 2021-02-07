---
description: 'Más información acerca de: interfaz ICorProfilerInfo5'
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
ms.openlocfilehash: c89faf3db08adeee3ffcfbb755a5da5ae44b3c7d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99737277"
---
# <a name="icorprofilerinfo5-interface"></a><span data-ttu-id="8a546-103">ICorProfilerInfo5 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8a546-103">ICorProfilerInfo5 Interface</span></span>

<span data-ttu-id="8a546-104">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="8a546-104">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="8a546-105">Subclase de [ICorProfilerInfo4](icorprofilerinfo4-interface.md) que proporciona métodos para que los profileres de código puedan usar para comunicarse con el Common Language Runtime (CLR) para controlar la supervisión de eventos.</span><span class="sxs-lookup"><span data-stu-id="8a546-105">A subclass of [ICorProfilerInfo4](icorprofilerinfo4-interface.md) that provides methods for use by code profilers to communicate with the common language runtime (CLR) to control event monitoring.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8a546-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="8a546-106">Methods</span></span>  
  
|<span data-ttu-id="8a546-107">Método</span><span class="sxs-lookup"><span data-stu-id="8a546-107">Method</span></span>|<span data-ttu-id="8a546-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="8a546-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8a546-109">GetEventMask2 (método)</span><span class="sxs-lookup"><span data-stu-id="8a546-109">GetEventMask2 Method</span></span>](icorprofilerinfo5-geteventmask2-method.md)|<span data-ttu-id="8a546-110">Obtiene las categorías de eventos actuales para las que el generador de perfiles quiere recibir notificaciones de CLR.</span><span class="sxs-lookup"><span data-stu-id="8a546-110">Gets the current event categories for which the profiler wants to receive notifications from the CLR.</span></span>|  
|[<span data-ttu-id="8a546-111">SetEventMask2 (método)</span><span class="sxs-lookup"><span data-stu-id="8a546-111">SetEventMask2 Method</span></span>](icorprofilerinfo5-seteventmask2-method.md)|<span data-ttu-id="8a546-112">Establece un valor que especifica los tipos de eventos para los que el generador de perfiles quiere recibir notificaciones de eventos desde CLR.</span><span class="sxs-lookup"><span data-stu-id="8a546-112">Sets a value that specifies the types of events for which the profiler wants to receive event notifications from the CLR.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8a546-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8a546-113">Remarks</span></span>  

 <span data-ttu-id="8a546-114">Los métodos disponibles en esta interfaz están diseñados para reemplazar los métodos [ICorProfilerInfo:: GetEventMask (](icorprofilerinfo-geteventmask-method.md) y [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) .</span><span class="sxs-lookup"><span data-stu-id="8a546-114">The methods available on this interface are intended to replace the [ICorProfilerInfo::GetEventMask](icorprofilerinfo-geteventmask-method.md) and [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a546-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8a546-115">Requirements</span></span>  

 <span data-ttu-id="8a546-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a546-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a546-117">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8a546-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8a546-118">**.NET Framework versiones:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a546-118">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a546-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="8a546-119">See also</span></span>

- [<span data-ttu-id="8a546-120">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="8a546-120">Profiling Interfaces</span></span>](profiling-interfaces.md)
