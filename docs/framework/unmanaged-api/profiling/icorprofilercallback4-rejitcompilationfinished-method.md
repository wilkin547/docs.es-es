---
description: 'Más información sobre: ICorProfilerCallback4:: Rejitcompilationfinished ((método)'
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
ms.openlocfilehash: 2d7270b5a8cf31fd81505c148429da5f7025319a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99788727"
---
# <a name="icorprofilercallback4rejitcompilationfinished-method"></a><span data-ttu-id="3adee-103">ICorProfilerCallback4::ReJITCompilationFinished (Método)</span><span class="sxs-lookup"><span data-stu-id="3adee-103">ICorProfilerCallback4::ReJITCompilationFinished Method</span></span>

<span data-ttu-id="3adee-104">Notifica al generador de perfiles que el compilador Just-in-Time (JIT) ha terminado de volver a compilar una función.</span><span class="sxs-lookup"><span data-stu-id="3adee-104">Notifies the profiler that the just-in-time (JIT) compiler has finished recompiling a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3adee-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3adee-105">Syntax</span></span>  
  
```cpp  
HRESULT ReJITCompilationFinished(  
    [in] FunctionID functionId,    [in] ReJITID rejitId,  
    [in] HRESULT    hrStatus,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3adee-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3adee-106">Parameters</span></span>  

 `functionId`  
 <span data-ttu-id="3adee-107">de IDENTIFICADOR de la función que se volvió a compilar.</span><span class="sxs-lookup"><span data-stu-id="3adee-107">[in] The ID of the function that was recompiled.</span></span>  
  
 `rejitId`  
 <span data-ttu-id="3adee-108">[in] Identidad de la función recompilada con JIT.</span><span class="sxs-lookup"><span data-stu-id="3adee-108">[in] The identity of the JIT-recompiled function.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="3adee-109">de Valor que indica si la recompilación JIT se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="3adee-109">[in] A value that indicates whether the JIT recompilation was successful.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="3adee-110">[in] `true` para indicar que el bloqueo puede hacer que el tiempo de ejecución espere a que el subproceso que realiza la llamada devuelva de esta devolución de llamada; `false` para indicar que el bloqueo no afectará al funcionamiento del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="3adee-110">[in] `true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  
  
 <span data-ttu-id="3adee-111">Un valor de no `true` perjudica al tiempo de ejecución, pero puede afectar a los resultados de la generación de perfiles.</span><span class="sxs-lookup"><span data-stu-id="3adee-111">A value of `true` does not harm the runtime, but can affect the profiling results.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3adee-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3adee-112">Requirements</span></span>  

 <span data-ttu-id="3adee-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3adee-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3adee-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3adee-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3adee-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3adee-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3adee-116">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3adee-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3adee-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="3adee-117">See also</span></span>

- [<span data-ttu-id="3adee-118">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3adee-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="3adee-119">ICorProfilerCallback4 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3adee-119">ICorProfilerCallback4 Interface</span></span>](icorprofilercallback4-interface.md)
- [<span data-ttu-id="3adee-120">Método JITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="3adee-120">JITCompilationStarted Method</span></span>](icorprofilercallback-jitcompilationstarted-method.md)
- [<span data-ttu-id="3adee-121">Método ReJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="3adee-121">ReJITCompilationStarted Method</span></span>](icorprofilercallback4-rejitcompilationstarted-method.md)
