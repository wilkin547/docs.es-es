---
title: ICorProfilerCallback::JITCompilationFinished (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITCompilationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITCompilationFinished
helpviewer_keywords:
- JITCompilationFinished method [.NET Framework profiling]
- ICorProfilerCallback::JITCompilationFinished method [.NET Framework profiling]
ms.assetid: 8dcd7537-d0c6-498c-8a56-2c060310ef65
topic_type:
- apiref
ms.openlocfilehash: 98e81d2d02a9495b678d49fb916f99068dd604f8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725539"
---
# <a name="icorprofilercallbackjitcompilationfinished-method"></a><span data-ttu-id="3b407-102">ICorProfilerCallback::JITCompilationFinished (Método)</span><span class="sxs-lookup"><span data-stu-id="3b407-102">ICorProfilerCallback::JITCompilationFinished Method</span></span>

<span data-ttu-id="3b407-103">Notifica al generador de perfiles que el compilador Just-in-Time (JIT) ha terminado de compilar una función.</span><span class="sxs-lookup"><span data-stu-id="3b407-103">Notifies the profiler that the just-in-time (JIT) compiler has finished compiling a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b407-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3b407-104">Syntax</span></span>  
  
```cpp  
HRESULT JITCompilationFinished(  
    [in] FunctionID functionId,  
    [in] HRESULT    hrStatus,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3b407-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3b407-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="3b407-106">\[in] identificador de la función que se compiló.</span><span class="sxs-lookup"><span data-stu-id="3b407-106">\[in] The ID of the function that was compiled.</span></span>

- `hrStatus`

  <span data-ttu-id="3b407-107">\[in] un valor que indica si la compilación se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="3b407-107">\[in] A value indicating whether compilation was successful.</span></span>

- `fIsSafeToBlock`

  <span data-ttu-id="3b407-108">\[in] un valor que indica al generador de perfiles si el bloqueo afectará al funcionamiento del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="3b407-108">\[in] A value indicating to the profiler whether blocking will affect the operation of the runtime.</span></span> <span data-ttu-id="3b407-109">El valor es `true` si el bloqueo puede hacer que el tiempo de ejecución espere a que el subproceso que realiza la llamada devuelva de esta devolución de llamada; de lo contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="3b407-109">The value is `true` if blocking may cause the runtime to wait for the calling thread to return from this callback; otherwise, `false`.</span></span>

  <span data-ttu-id="3b407-110">Aunque un valor de `true` no dañará el tiempo de ejecución, puede sesgar los resultados de la generación de perfiles.</span><span class="sxs-lookup"><span data-stu-id="3b407-110">Although a value of `true` will not harm the runtime, it can skew the profiling results.</span></span>

## <a name="requirements"></a><span data-ttu-id="3b407-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3b407-111">Requirements</span></span>  

 <span data-ttu-id="3b407-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3b407-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b407-113">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3b407-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3b407-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3b407-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3b407-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b407-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b407-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3b407-116">See also</span></span>

- [<span data-ttu-id="3b407-117">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3b407-117">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="3b407-118">Método JITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="3b407-118">JITCompilationStarted Method</span></span>](icorprofilercallback-jitcompilationstarted-method.md)
