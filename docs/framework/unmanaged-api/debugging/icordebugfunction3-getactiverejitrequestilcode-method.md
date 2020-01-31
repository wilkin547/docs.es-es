---
title: ICorDebugFunction3::GetActiveReJitRequestILCode (Método)
ms.date: 03/30/2017
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
ms.openlocfilehash: 70a55b833acb7fa946c694a63e1e8b51562938bc
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777727"
---
# <a name="icordebugfunction3getactiverejitrequestilcode-method"></a><span data-ttu-id="e03f9-102">ICorDebugFunction3::GetActiveReJitRequestILCode (Método)</span><span class="sxs-lookup"><span data-stu-id="e03f9-102">ICorDebugFunction3::GetActiveReJitRequestILCode Method</span></span>
<span data-ttu-id="e03f9-103">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="e03f9-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="e03f9-104">Obtiene un puntero de interfaz a un [ICorDebugILCode](icordebugilcode-interface.md) que contiene el Il de una solicitud ReJIT activa.</span><span class="sxs-lookup"><span data-stu-id="e03f9-104">Gets an interface pointer to an [ICorDebugILCode](icordebugilcode-interface.md) that contains the IL from an active ReJIT request.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e03f9-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e03f9-105">Syntax</span></span>  
  
```cpp
HRESULT GetActiveReJitRequestILCode(  
   ICorDebugILCode **ppReJitedILCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e03f9-106">Parameters</span><span class="sxs-lookup"><span data-stu-id="e03f9-106">Parameters</span></span>  
 `ppReJitedILCode`  
 <span data-ttu-id="e03f9-107">Puntero al IL desde una solicitud ReJIT activa.</span><span class="sxs-lookup"><span data-stu-id="e03f9-107">A pointer to the IL from an active ReJIT request.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e03f9-108">Notas</span><span class="sxs-lookup"><span data-stu-id="e03f9-108">Remarks</span></span>  
 <span data-ttu-id="e03f9-109">Si el método que representa este objeto `ICorDebugFunction3` tiene una solicitud ReJIT activa, `ppReJitedILCode` devuelve un puntero a su IL.</span><span class="sxs-lookup"><span data-stu-id="e03f9-109">If the method represented by this `ICorDebugFunction3` object has an active ReJIT request, `ppReJitedILCode` returns a pointer to its IL.</span></span> <span data-ttu-id="e03f9-110">Si no hay ninguna solicitud activa, que es un caso común, `ppReJitedILCode` es **null**.</span><span class="sxs-lookup"><span data-stu-id="e03f9-110">If there is no active request, which is a common case, then `ppReJitedILCode` is **null**.</span></span>  
  
 <span data-ttu-id="e03f9-111">Una solicitud ReJIT se activa justo después de que la ejecución vuelva de la llamada al método [ICorProfilerCallback4:: getrejitparameters (](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) .</span><span class="sxs-lookup"><span data-stu-id="e03f9-111">A ReJIT request becomes active just after execution returns from the [ICorProfilerCallback4::GetReJITParameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) method call.</span></span> <span data-ttu-id="e03f9-112">Puede que JIT aún no la haya compilado y que los subprocesos se estén ejecutando en la versión original del código.</span><span class="sxs-lookup"><span data-stu-id="e03f9-112">It may not yet be JIT-compiled, and threads may still be executing in the original version of the code.</span></span> <span data-ttu-id="e03f9-113">Una solicitud ReJIT pasa a estar inactiva durante la llamada del generador de perfiles al método [ICorProfilerInfo4:: requestrevert (](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrevert-method.md) .</span><span class="sxs-lookup"><span data-stu-id="e03f9-113">A ReJIT request becomes inactive during the profiler's call to the [ICorProfilerInfo4::RequestRevert](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrevert-method.md) method.</span></span> <span data-ttu-id="e03f9-114">Incluso después de revertir el IL, un subproceso puede seguir ejecutándose en el código JIT nuevamente compilado (ReJIT).</span><span class="sxs-lookup"><span data-stu-id="e03f9-114">Even after the IL is reverted, a thread can still be executing in the JIT-recompiled (ReJIT) code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e03f9-115">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="e03f9-115">Requirements</span></span>  
 <span data-ttu-id="e03f9-116">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e03f9-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e03f9-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e03f9-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e03f9-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e03f9-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e03f9-119">**.NET Framework versiones:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e03f9-119">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e03f9-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="e03f9-120">See also</span></span>

- [<span data-ttu-id="e03f9-121">ICorDebugFunction3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e03f9-121">ICorDebugFunction3 Interface</span></span>](icordebugfunction3-interface.md)
- [<span data-ttu-id="e03f9-122">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="e03f9-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="e03f9-123">ReJIT: Guía de procedimientos</span><span class="sxs-lookup"><span data-stu-id="e03f9-123">ReJIT: A How-To Guide</span></span>](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
