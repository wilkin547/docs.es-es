---
title: ICorProfilerCallback8::D método ynamicMethodJITCompilationFinished
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationFinished
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 0e04459614ca697908fb9b71ecc3931ac305a838
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136585"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationfinished-method"></a><span data-ttu-id="3b0fe-102">ICorProfilerCallback8::D método ynamicMethodJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="3b0fe-102">ICorProfilerCallback8::DynamicMethodJITCompilationFinished Method</span></span>
<span data-ttu-id="3b0fe-103">[Se admite en el .NET Framework 4,7 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="3b0fe-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  
  
<span data-ttu-id="3b0fe-104">Notifica al generador de perfiles cada vez que se ha completado la compilación JIT de un método dinámico.</span><span class="sxs-lookup"><span data-stu-id="3b0fe-104">Notifies the profiler whenever JIT compilation of a dynamic method has completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b0fe-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3b0fe-105">Syntax</span></span>  
  
```cpp  
HRESULT DynamicMethodJITCompilationFinished(  
     [in]  FunctionID  functionId,   
     [in]  BOOL        hrStatus,   
     [in]  BOOL        fIsSafeToBlock   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3b0fe-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3b0fe-106">Parameters</span></span>  
<span data-ttu-id="3b0fe-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="3b0fe-107">[in] `functionId`</span></span>  
<span data-ttu-id="3b0fe-108">Identificador de la función en memoria para la que se inicia la compilación JIT.</span><span class="sxs-lookup"><span data-stu-id="3b0fe-108">The identifier of the in-memory function for which JIT compilation is started.</span></span>   

<span data-ttu-id="3b0fe-109">[in] `hrStatus` </span><span class="sxs-lookup"><span data-stu-id="3b0fe-109">[in] `hrStatus` </span></span>  
<span data-ttu-id="3b0fe-110">Valor que indica si la compilación JIT se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="3b0fe-110">A value that indicates whether the JIT compilation was successful.</span></span>

<span data-ttu-id="3b0fe-111">[in] `fIsSafeToBlock` </span><span class="sxs-lookup"><span data-stu-id="3b0fe-111">[in] `fIsSafeToBlock` </span></span>  
<span data-ttu-id="3b0fe-112">`true` para indicar que el bloqueo puede hacer que el tiempo de ejecución espere a que el subproceso que realiza la llamada devuelva de esta devolución de llamada; `false` para indicar que el bloqueo no afectará al funcionamiento del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="3b0fe-112">`true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  

## <a name="remarks"></a><span data-ttu-id="3b0fe-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3b0fe-113">Remarks</span></span>  

<span data-ttu-id="3b0fe-114">Esta devolución de llamada se desencadena cuando finaliza la compilación JIT de un método dinámico.</span><span class="sxs-lookup"><span data-stu-id="3b0fe-114">This callback is triggered whenever JIT compilation of a dynamic method has finished.</span></span> <span data-ttu-id="3b0fe-115">Esto incluye varios códigos auxiliares de IL y métodos LCG.</span><span class="sxs-lookup"><span data-stu-id="3b0fe-115">This includes various IL stubs and LCG methods.</span></span> <span data-ttu-id="3b0fe-116">Su objetivo es proporcionar a los escritores de Profiler información suficiente para identificar el método compilado para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="3b0fe-116">Its goal is to provide profiler writers with enough information to identify the compiled method to users.</span></span>

> [!NOTE]
> <span data-ttu-id="3b0fe-117">`functionId` valores no se pueden usar para resolver sus tokens de metadatos, porque los métodos dinámicos no tienen metadatos.</span><span class="sxs-lookup"><span data-stu-id="3b0fe-117">`functionId` values cannot be used to resolve to their metadata tokens, because dynamic methods have no metadata.</span></span>

## <a name="requirements"></a><span data-ttu-id="3b0fe-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3b0fe-118">Requirements</span></span>  
 <span data-ttu-id="3b0fe-119">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3b0fe-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b0fe-120">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3b0fe-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3b0fe-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3b0fe-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3b0fe-122">**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="3b0fe-122">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b0fe-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="3b0fe-123">See also</span></span>

- [<span data-ttu-id="3b0fe-124">DynamicMethodJITCompilationStarted (método)</span><span class="sxs-lookup"><span data-stu-id="3b0fe-124">DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="3b0fe-125">ICorProfilerCallback8 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3b0fe-125">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)
