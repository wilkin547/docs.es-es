---
title: ICorProfilerCallback4::ReJITCompilationFinished (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.ReJITCompilationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::ReJITCompilationFinished
helpviewer_keywords:
- ICorProfilerCallback4::ReJITCompilationFinished method [.NET Framework profiling]
- ReJITCompilationFinished method, ICorProfilerCallback4 interface [.NET Framework profiling]
ms.assetid: 3b5cff02-2005-44eb-a2bc-50214c4b0e1d
topic_type:
- apiref
ms.openlocfilehash: a6c2209433a652523fd8e3a7cc2db1272600e1bd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730271"
---
# <a name="icorprofilercallback4rejitcompilationfinished-method"></a><span data-ttu-id="ff3e7-102">ICorProfilerCallback4::ReJITCompilationFinished (Método)</span><span class="sxs-lookup"><span data-stu-id="ff3e7-102">ICorProfilerCallback4::ReJITCompilationFinished Method</span></span>

<span data-ttu-id="ff3e7-103">Notifica al generador de perfiles que el compilador Just-in-Time (JIT) ha terminado de volver a compilar una función.</span><span class="sxs-lookup"><span data-stu-id="ff3e7-103">Notifies the profiler that the just-in-time (JIT) compiler has finished recompiling a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff3e7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ff3e7-104">Syntax</span></span>  
  
```cpp  
HRESULT ReJITCompilationFinished(  
    [in] FunctionID functionId,    [in] ReJITID rejitId,  
    [in] HRESULT    hrStatus,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ff3e7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ff3e7-105">Parameters</span></span>  

 `functionId`  
 <span data-ttu-id="ff3e7-106">de IDENTIFICADOR de la función que se volvió a compilar.</span><span class="sxs-lookup"><span data-stu-id="ff3e7-106">[in] The ID of the function that was recompiled.</span></span>  
  
 `rejitId`  
 <span data-ttu-id="ff3e7-107">[in] Identidad de la función recompilada con JIT.</span><span class="sxs-lookup"><span data-stu-id="ff3e7-107">[in] The identity of the JIT-recompiled function.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="ff3e7-108">de Valor que indica si la recompilación JIT se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="ff3e7-108">[in] A value that indicates whether the JIT recompilation was successful.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="ff3e7-109">[in] `true` para indicar que el bloqueo puede hacer que el tiempo de ejecución espere a que el subproceso que realiza la llamada devuelva de esta devolución de llamada; `false` para indicar que el bloqueo no afectará al funcionamiento del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ff3e7-109">[in] `true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  
  
 <span data-ttu-id="ff3e7-110">Un valor de no `true` perjudica al tiempo de ejecución, pero puede afectar a los resultados de la generación de perfiles.</span><span class="sxs-lookup"><span data-stu-id="ff3e7-110">A value of `true` does not harm the runtime, but can affect the profiling results.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff3e7-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ff3e7-111">Requirements</span></span>  

 <span data-ttu-id="ff3e7-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff3e7-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff3e7-113">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ff3e7-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ff3e7-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ff3e7-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ff3e7-115">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff3e7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff3e7-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ff3e7-116">See also</span></span>

- [<span data-ttu-id="ff3e7-117">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ff3e7-117">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="ff3e7-118">ICorProfilerCallback4 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ff3e7-118">ICorProfilerCallback4 Interface</span></span>](icorprofilercallback4-interface.md)
- [<span data-ttu-id="ff3e7-119">Método JITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="ff3e7-119">JITCompilationStarted Method</span></span>](icorprofilercallback-jitcompilationstarted-method.md)
- [<span data-ttu-id="ff3e7-120">Método ReJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="ff3e7-120">ReJITCompilationStarted Method</span></span>](icorprofilercallback4-rejitcompilationstarted-method.md)
