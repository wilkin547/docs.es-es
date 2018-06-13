---
title: ICorProfilerCallback8::DynamicMethodJITCompilationFinished (método)
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationFinished
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 49b5ead8b5428d855b7dab81dced1de6325fd07b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455002"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationfinished-method"></a><span data-ttu-id="4991c-102">ICorProfilerCallback8::DynamicMethodJITCompilationFinished (método)</span><span class="sxs-lookup"><span data-stu-id="4991c-102">ICorProfilerCallback8::DynamicMethodJITCompilationFinished Method</span></span>
<span data-ttu-id="4991c-103">[Compatible con .NET Framework 4.7 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="4991c-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  
  
<span data-ttu-id="4991c-104">Notifica al generador de perfiles cada vez que se ha completado la compilación JIT de un método dinámico.</span><span class="sxs-lookup"><span data-stu-id="4991c-104">Notifies the profiler whenever JIT compilation of a dynamic method has completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4991c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4991c-105">Syntax</span></span>  
  
```  
HRESULT DynamicMethodJITCompilationFinished(  
     [in]  FunctionID  functionId,   
     [in]  BOOL        hrStatus,   
     [in]  BOOL        fIsSafeToBlock   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4991c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4991c-106">Parameters</span></span>  
<span data-ttu-id="4991c-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="4991c-107">[in] `functionId`</span></span>  
<span data-ttu-id="4991c-108">El identificador de la función en memoria para qué JIT se inicia la compilación.</span><span class="sxs-lookup"><span data-stu-id="4991c-108">The identifier of the in-memory function for which JIT compilation is started.</span></span>   

<span data-ttu-id="4991c-109">[in] `hrStatus` </span><span class="sxs-lookup"><span data-stu-id="4991c-109">[in] `hrStatus` </span></span>  
<span data-ttu-id="4991c-110">Un valor que indica si la compilación JIT se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="4991c-110">A value that indicates whether the JIT compilation was successful.</span></span>

<span data-ttu-id="4991c-111">[in] `fIsSafeToBlock` </span><span class="sxs-lookup"><span data-stu-id="4991c-111">[in] `fIsSafeToBlock` </span></span>  
<span data-ttu-id="4991c-112">`true` para indicar que el bloqueo puede causar el tiempo de ejecución esperar el subproceso de llamada devolver desde esta devolución de llamada; `false` para indicar que el bloqueo no afectará al funcionamiento del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4991c-112">`true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  

## <a name="remarks"></a><span data-ttu-id="4991c-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4991c-113">Remarks</span></span>  

<span data-ttu-id="4991c-114">Esta devolución de llamada se desencadena cada vez que ha terminado la compilación JIT de un método dinámico.</span><span class="sxs-lookup"><span data-stu-id="4991c-114">This callback is triggered whenever JIT compilation of a dynamic method has finished.</span></span> <span data-ttu-id="4991c-115">Esto incluye diversos métodos LCG y códigos auxiliares de IL.</span><span class="sxs-lookup"><span data-stu-id="4991c-115">This includes various IL stubs and LCG methods.</span></span> <span data-ttu-id="4991c-116">Su objetivo es proporcionar suficiente información para identificar el método compilado a los usuarios a escritores profiler.</span><span class="sxs-lookup"><span data-stu-id="4991c-116">Its goal is to provide profiler writers with enough information to identify the compiled method to users.</span></span>

> [!NOTE]
> <span data-ttu-id="4991c-117">`functionId` valores no se puede usar para resolver a sus tokens de metadatos, porque los métodos dinámicos no tienen metadatos.</span><span class="sxs-lookup"><span data-stu-id="4991c-117">`functionId` values cannot be used to resolve to their metadata tokens, because dynamic methods have no metadata.</span></span>

## <a name="requirements"></a><span data-ttu-id="4991c-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4991c-118">Requirements</span></span>  
 <span data-ttu-id="4991c-119">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4991c-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4991c-120">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4991c-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4991c-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4991c-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4991c-122">**Versiones de .NET framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="4991c-122">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4991c-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="4991c-123">See Also</span></span>  
 [<span data-ttu-id="4991c-124">DynamicMethodJITCompilationStarted (método)</span><span class="sxs-lookup"><span data-stu-id="4991c-124">DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)  
 [<span data-ttu-id="4991c-125">Interfaz ICorProfilerCallback8</span><span class="sxs-lookup"><span data-stu-id="4991c-125">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)
