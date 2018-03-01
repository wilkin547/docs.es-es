---
title: "ICorDebugFunction3::GetActiveReJitRequestILCode (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- cpp
api_name:
- ICorDebugFunction3.GetActiveReJitRequestILCode
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 88584574-ade5-45b2-9778-489ed5c4dd7f
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ae041a9a5973194398bbfed41771396b305f52fd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugfunction3getactiverejitrequestilcode-method"></a><span data-ttu-id="7dae1-102">ICorDebugFunction3::GetActiveReJitRequestILCode (Método)</span><span class="sxs-lookup"><span data-stu-id="7dae1-102">ICorDebugFunction3::GetActiveReJitRequestILCode Method</span></span>
<span data-ttu-id="7dae1-103">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="7dae1-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="7dae1-104">Obtiene un puntero de interfaz a una [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) que contiene el IL de una solicitud ReJIT activa.</span><span class="sxs-lookup"><span data-stu-id="7dae1-104">Gets an interface pointer to an [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) that contains the IL from an active ReJIT request.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7dae1-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7dae1-105">Syntax</span></span>  
  
```cpp
HRESULT GetActiveReJitRequestILCode(  
   ICorDebugILCode **ppReJitedILCode  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7dae1-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7dae1-106">Parameters</span></span>  
 `ppReJitedILCode`  
 <span data-ttu-id="7dae1-107">Puntero al IL desde una solicitud ReJIT activa.</span><span class="sxs-lookup"><span data-stu-id="7dae1-107">A pointer to the IL from an active ReJIT request.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7dae1-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7dae1-108">Remarks</span></span>  
 <span data-ttu-id="7dae1-109">Si el método que representa este objeto `ICorDebugFunction3` tiene una solicitud ReJIT activa, `ppReJitedILCode` devuelve un puntero a su IL.</span><span class="sxs-lookup"><span data-stu-id="7dae1-109">If the method represented by this `ICorDebugFunction3` object has an active ReJIT request, `ppReJitedILCode` returns a pointer to its IL.</span></span> <span data-ttu-id="7dae1-110">Si no hay ninguna solicitud activa, que es un caso común, a continuación, `ppReJitedILCode` es **null**.</span><span class="sxs-lookup"><span data-stu-id="7dae1-110">If there is no active request, which is a common case, then `ppReJitedILCode` is **null**.</span></span>  
  
 <span data-ttu-id="7dae1-111">Una solicitud ReJIT se convierte en activa justo después de ejecución vuelva de la [icorprofilercallback4:: Getrejitparameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) llamada al método.</span><span class="sxs-lookup"><span data-stu-id="7dae1-111">A ReJIT request becomes active just after execution returns from the [ICorProfilerCallback4::GetReJITParameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) method call.</span></span> <span data-ttu-id="7dae1-112">Puede que JIT aún no la haya compilado y que los subprocesos se estén ejecutando en la versión original del código.</span><span class="sxs-lookup"><span data-stu-id="7dae1-112">It may not yet be JIT-compiled, and threads may still be executing in the original version of the code.</span></span> <span data-ttu-id="7dae1-113">Una solicitud ReJIT pasa a estar inactiva durante la llamada del generador de perfiles a la [icorprofilerinfo4:: Requestrevert](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrevert-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="7dae1-113">A ReJIT request becomes inactive during the profiler's call to the [ICorProfilerInfo4::RequestRevert](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrevert-method.md) method.</span></span> <span data-ttu-id="7dae1-114">Incluso después de revertir el IL, un subproceso puede seguir ejecutándose en el código JIT nuevamente compilado (ReJIT).</span><span class="sxs-lookup"><span data-stu-id="7dae1-114">Even after the IL is reverted, a thread can still be executing in the JIT-recompiled (ReJIT) code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7dae1-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7dae1-115">Requirements</span></span>  
 <span data-ttu-id="7dae1-116">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7dae1-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7dae1-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7dae1-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7dae1-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7dae1-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7dae1-119">**Versiones de .NET framework:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7dae1-119">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7dae1-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="7dae1-120">See Also</span></span>  
 [<span data-ttu-id="7dae1-121">ICorDebugFunction3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7dae1-121">ICorDebugFunction3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction3-interface.md)  
 [<span data-ttu-id="7dae1-122">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="7dae1-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="7dae1-123">ReJIT: Una guía de procedimientos</span><span class="sxs-lookup"><span data-stu-id="7dae1-123">ReJIT: A How-To Guide</span></span>](http://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
