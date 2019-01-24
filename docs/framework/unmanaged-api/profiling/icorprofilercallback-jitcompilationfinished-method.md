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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4d2e75d357b1f56df676163744015a1a3f77c17b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54530763"
---
# <a name="icorprofilercallbackjitcompilationfinished-method"></a><span data-ttu-id="2870c-102">ICorProfilerCallback::JITCompilationFinished (Método)</span><span class="sxs-lookup"><span data-stu-id="2870c-102">ICorProfilerCallback::JITCompilationFinished Method</span></span>
<span data-ttu-id="2870c-103">Notifica al generador de perfiles que el compilador de just-in-time (JIT) ha terminado de compilar una función.</span><span class="sxs-lookup"><span data-stu-id="2870c-103">Notifies the profiler that the just-in-time (JIT) compiler has finished compiling a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2870c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2870c-104">Syntax</span></span>  
  
```  
HRESULT JITCompilationFinished(  
    [in] FunctionID functionId,  
    [in] HRESULT    hrStatus,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2870c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2870c-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="2870c-106">[in] El identificador de la función que se compiló.</span><span class="sxs-lookup"><span data-stu-id="2870c-106">[in] The ID of the function that was compiled.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="2870c-107">[in] Un valor que indica si la compilación fue correcta.</span><span class="sxs-lookup"><span data-stu-id="2870c-107">[in] A value indicating whether compilation was successful.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="2870c-108">[in] Un valor que indica al generador de perfiles si el bloqueo afectará al funcionamiento del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="2870c-108">[in] A value indicating to the profiler whether blocking will affect the operation of the runtime.</span></span> <span data-ttu-id="2870c-109">El valor es `true` Si bloqueo puede provocar el tiempo de ejecución esperar el subproceso de llamada devolver desde esta devolución de llamada; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="2870c-109">The value is `true` if blocking may cause the runtime to wait for the calling thread to return from this callback; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="2870c-110">Aunque un valor de `true` no dañarán el tiempo de ejecución, pueden sesgar los resultados de la generación de perfiles.</span><span class="sxs-lookup"><span data-stu-id="2870c-110">Although a value of `true` will not harm the runtime, it can skew the profiling results.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2870c-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2870c-111">Requirements</span></span>  
 <span data-ttu-id="2870c-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2870c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2870c-113">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2870c-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2870c-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2870c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2870c-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2870c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2870c-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="2870c-116">See also</span></span>
- [<span data-ttu-id="2870c-117">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2870c-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="2870c-118">JITCompilationStarted (método)</span><span class="sxs-lookup"><span data-stu-id="2870c-118">JITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)
