---
title: ICorProfilerInfo4::InitializeCurrentThread (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4::InitializeCurrentThread
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::InitializeCurrentThread
helpviewer_keywords:
- ICorProfilerInfo4::InitializeCurrentThread method [.NET Framework profiling]
- InitializeCurrentThread method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 18a3335c-8c75-476c-b6de-72c0bfedae5d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b9bb5a2629e435d76691d48feef6689191b66373
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957897"
---
# <a name="icorprofilerinfo4initializecurrentthread-method"></a><span data-ttu-id="d9a1d-102">ICorProfilerInfo4::InitializeCurrentThread (Método)</span><span class="sxs-lookup"><span data-stu-id="d9a1d-102">ICorProfilerInfo4::InitializeCurrentThread Method</span></span>
<span data-ttu-id="d9a1d-103">Inicializa el subproceso actual antes de las llamadas posteriores a la API del generador de perfiles en el mismo subproceso, de modo que se pueda evitar el interbloqueo.</span><span class="sxs-lookup"><span data-stu-id="d9a1d-103">Initializes the current thread in advance of subsequent profiler API calls on the same thread, so that deadlock can be avoided.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9a1d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d9a1d-104">Syntax</span></span>  
  
```cpp  
HRESULT InitializeCurrentThread ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="d9a1d-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d9a1d-105">Remarks</span></span>  
 <span data-ttu-id="d9a1d-106">Se recomienda llamar `InitializeCurrentThread` a en cualquier subproceso que llame a una API del generador de perfiles mientras haya subprocesos suspendidos.</span><span class="sxs-lookup"><span data-stu-id="d9a1d-106">We recommend that you call `InitializeCurrentThread` on any thread that will call a profiler API while there are suspended threads.</span></span> <span data-ttu-id="d9a1d-107">Este método lo suelen usar los profileres de muestreo que crean su propio subproceso para llamar al método [ICorProfilerInfo2::D ostacksnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) para realizar los recorridos de la pila mientras se suspende el subproceso de destino.</span><span class="sxs-lookup"><span data-stu-id="d9a1d-107">This method is typically used by sampling profilers that create their own thread to call the [ICorProfilerInfo2::DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) method to perform stack walks while the target thread is suspended.</span></span> <span data-ttu-id="d9a1d-108">Mediante una `InitializeCurrentThread` llamada a una vez cuando el generador de perfiles crea primero el subproceso de muestreo, los perfiles pueden garantizar que la inicialización diferida por subproceso que CLR `DoStackSnapshot` realizará de otro modo durante la primera llamada a puede tener lugar de forma segura cuando no haya otros subprocesos Suspend.</span><span class="sxs-lookup"><span data-stu-id="d9a1d-108">By calling `InitializeCurrentThread` once when the profiler first creates the sampling thread, profilers can ensure that lazy per-thread initialization that the CLR would otherwise perform during the first call to `DoStackSnapshot` can now occur safely when no other threads are suspended.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d9a1d-109">`InitializeCurrentThread`realiza la inicialización de antemano para finalizar las tareas que toman bloqueos y pueden interbloquearse.</span><span class="sxs-lookup"><span data-stu-id="d9a1d-109">`InitializeCurrentThread` does the initialization in advance to finish tasks that take locks, and may deadlock.</span></span> <span data-ttu-id="d9a1d-110">Llame `InitializeCurrentThread` solo cuando no haya subprocesos suspendidos.</span><span class="sxs-lookup"><span data-stu-id="d9a1d-110">Call `InitializeCurrentThread` only when there are no suspended threads.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9a1d-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d9a1d-111">Requirements</span></span>  
 <span data-ttu-id="d9a1d-112">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d9a1d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9a1d-113">**Encabezado**: Corprof. idl, Corprof. h</span><span class="sxs-lookup"><span data-stu-id="d9a1d-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d9a1d-114">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d9a1d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d9a1d-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9a1d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9a1d-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="d9a1d-116">See also</span></span>

- [<span data-ttu-id="d9a1d-117">ICorProfilerInfo4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d9a1d-117">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [<span data-ttu-id="d9a1d-118">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="d9a1d-118">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="d9a1d-119">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="d9a1d-119">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
