---
description: 'Más información sobre: ICorProfilerCallback:: JITCompilationFinished ((método)'
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
ms.openlocfilehash: 32a47860ae2e973d32ef12b2bd9002bb1de45ee9
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2021
ms.locfileid: "104760332"
---
# <a name="icorprofilercallbackjitcompilationfinished-method"></a><span data-ttu-id="88077-103">ICorProfilerCallback::JITCompilationFinished (Método)</span><span class="sxs-lookup"><span data-stu-id="88077-103">ICorProfilerCallback::JITCompilationFinished Method</span></span>

<span data-ttu-id="88077-104">Notifica al generador de perfiles que el compilador Just-in-Time (JIT) ha terminado de compilar una función.</span><span class="sxs-lookup"><span data-stu-id="88077-104">Notifies the profiler that the just-in-time (JIT) compiler has finished compiling a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88077-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="88077-105">Syntax</span></span>  
  
```cpp  
HRESULT JITCompilationFinished(  
    [in] FunctionID functionId,  
    [in] HRESULT    hrStatus,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a><span data-ttu-id="88077-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="88077-106">Parameters</span></span>

<span data-ttu-id="88077-107">`functionId` de IDENTIFICADOR de la función que se compiló.</span><span class="sxs-lookup"><span data-stu-id="88077-107">`functionId` [in] The ID of the function that was compiled.</span></span>

<span data-ttu-id="88077-108">`hrStatus` de Valor que indica si la compilación se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="88077-108">`hrStatus` [in] A value indicating whether compilation was successful.</span></span>

<span data-ttu-id="88077-109">`fIsSafeToBlock` de Un valor que indica al generador de perfiles si el bloqueo afectará al funcionamiento del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="88077-109">`fIsSafeToBlock` [in] A value indicating to the profiler whether blocking will affect the operation of the runtime.</span></span> <span data-ttu-id="88077-110">El valor es `true` si el bloqueo puede hacer que el tiempo de ejecución espere a que el subproceso que realiza la llamada devuelva de esta devolución de llamada; de lo contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="88077-110">The value is `true` if blocking may cause the runtime to wait for the calling thread to return from this callback; otherwise, `false`.</span></span>

<span data-ttu-id="88077-111">Aunque un valor de `true` no dañará el tiempo de ejecución, puede sesgar los resultados de la generación de perfiles.</span><span class="sxs-lookup"><span data-stu-id="88077-111">Although a value of `true` will not harm the runtime, it can skew the profiling results.</span></span>

## <a name="requirements"></a><span data-ttu-id="88077-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="88077-112">Requirements</span></span>  

 <span data-ttu-id="88077-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="88077-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88077-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="88077-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="88077-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="88077-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="88077-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="88077-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88077-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="88077-117">See also</span></span>

- [<span data-ttu-id="88077-118">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="88077-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="88077-119">Método JITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="88077-119">JITCompilationStarted Method</span></span>](icorprofilercallback-jitcompilationstarted-method.md)
