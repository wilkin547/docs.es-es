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
ms.openlocfilehash: 9e7f682752cfefae63b574655a4fc5e8964146a0
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213184"
---
# <a name="icordebugfunction3getactiverejitrequestilcode-method"></a><span data-ttu-id="751ce-102">ICorDebugFunction3::GetActiveReJitRequestILCode (Método)</span><span class="sxs-lookup"><span data-stu-id="751ce-102">ICorDebugFunction3::GetActiveReJitRequestILCode Method</span></span>
<span data-ttu-id="751ce-103">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="751ce-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="751ce-104">Obtiene un puntero de interfaz a un [ICorDebugILCode](icordebugilcode-interface.md) que contiene el Il de una solicitud ReJIT activa.</span><span class="sxs-lookup"><span data-stu-id="751ce-104">Gets an interface pointer to an [ICorDebugILCode](icordebugilcode-interface.md) that contains the IL from an active ReJIT request.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="751ce-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="751ce-105">Syntax</span></span>  
  
```cpp
HRESULT GetActiveReJitRequestILCode(  
   ICorDebugILCode **ppReJitedILCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="751ce-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="751ce-106">Parameters</span></span>  
 `ppReJitedILCode`  
 <span data-ttu-id="751ce-107">Puntero al IL desde una solicitud ReJIT activa.</span><span class="sxs-lookup"><span data-stu-id="751ce-107">A pointer to the IL from an active ReJIT request.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="751ce-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="751ce-108">Remarks</span></span>  
 <span data-ttu-id="751ce-109">Si el método que representa este objeto `ICorDebugFunction3` tiene una solicitud ReJIT activa, `ppReJitedILCode` devuelve un puntero a su IL.</span><span class="sxs-lookup"><span data-stu-id="751ce-109">If the method represented by this `ICorDebugFunction3` object has an active ReJIT request, `ppReJitedILCode` returns a pointer to its IL.</span></span> <span data-ttu-id="751ce-110">Si no hay ninguna solicitud activa, que es un caso común, `ppReJitedILCode` es **null**.</span><span class="sxs-lookup"><span data-stu-id="751ce-110">If there is no active request, which is a common case, then `ppReJitedILCode` is **null**.</span></span>  
  
 <span data-ttu-id="751ce-111">Una solicitud ReJIT se activa justo después de que la ejecución vuelva de la llamada al método [ICorProfilerCallback4:: getrejitparameters (](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) .</span><span class="sxs-lookup"><span data-stu-id="751ce-111">A ReJIT request becomes active just after execution returns from the [ICorProfilerCallback4::GetReJITParameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) method call.</span></span> <span data-ttu-id="751ce-112">Puede que JIT aún no la haya compilado y que los subprocesos se estén ejecutando en la versión original del código.</span><span class="sxs-lookup"><span data-stu-id="751ce-112">It may not yet be JIT-compiled, and threads may still be executing in the original version of the code.</span></span> <span data-ttu-id="751ce-113">Una solicitud ReJIT pasa a estar inactiva durante la llamada del generador de perfiles al método [ICorProfilerInfo4:: requestrevert (](../profiling/icorprofilerinfo4-requestrevert-method.md) .</span><span class="sxs-lookup"><span data-stu-id="751ce-113">A ReJIT request becomes inactive during the profiler's call to the [ICorProfilerInfo4::RequestRevert](../profiling/icorprofilerinfo4-requestrevert-method.md) method.</span></span> <span data-ttu-id="751ce-114">Incluso después de revertir el IL, un subproceso puede seguir ejecutándose en el código JIT nuevamente compilado (ReJIT).</span><span class="sxs-lookup"><span data-stu-id="751ce-114">Even after the IL is reverted, a thread can still be executing in the JIT-recompiled (ReJIT) code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="751ce-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="751ce-115">Requirements</span></span>  
 <span data-ttu-id="751ce-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="751ce-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="751ce-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="751ce-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="751ce-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="751ce-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="751ce-119">**.NET Framework versiones:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="751ce-119">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="751ce-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="751ce-120">See also</span></span>

- [<span data-ttu-id="751ce-121">ICorDebugFunction3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="751ce-121">ICorDebugFunction3 Interface</span></span>](icordebugfunction3-interface.md)
- [<span data-ttu-id="751ce-122">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="751ce-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="751ce-123">ReJIT: Guía de procedimientos</span><span class="sxs-lookup"><span data-stu-id="751ce-123">ReJIT: A How-To Guide</span></span>](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
