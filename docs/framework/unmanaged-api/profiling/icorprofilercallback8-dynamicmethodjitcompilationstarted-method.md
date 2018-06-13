---
title: ICorProfilerCallback8::DynamicMethodJITCompilationStarted (método)
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationStarted
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ad74eeb4deeae73be40b3a0bc0f6a18ec2299780
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33454755"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationstarted-method"></a><span data-ttu-id="29c41-102">ICorProfilerCallback8::DynamicMethodJITCompilationStarted (método)</span><span class="sxs-lookup"><span data-stu-id="29c41-102">ICorProfilerCallback8::DynamicMethodJITCompilationStarted Method</span></span>
<span data-ttu-id="29c41-103">[Compatible con .NET Framework 4.7 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="29c41-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  
  
<span data-ttu-id="29c41-104">Notifica al generador de perfiles cada vez que se ha iniciado la compilación JIT de un método dinámico.</span><span class="sxs-lookup"><span data-stu-id="29c41-104">Notifies the profiler whenever JIT compilation of a dynamic method has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29c41-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="29c41-105">Syntax</span></span>  
  
```  
HRESULT DynamicMethodJITCompilationStarted(  
     [in]  FunctionID  functionId,   
     [in]  BOOL        fIsSafeToBlock,   
     [in]  LPCBYTE     pILHeader,   
     [in]  LONG        cbILHeader   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="29c41-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="29c41-106">Parameters</span></span>  
<span data-ttu-id="29c41-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="29c41-107">[in] `functionId`</span></span>  
<span data-ttu-id="29c41-108">El identificador de la función en memoria para qué JIT se inicia la compilación.</span><span class="sxs-lookup"><span data-stu-id="29c41-108">The identifier of the in-memory function for which JIT compilation is started.</span></span>   

<span data-ttu-id="29c41-109">[in] `fIsSafeToBlock` </span><span class="sxs-lookup"><span data-stu-id="29c41-109">[in] `fIsSafeToBlock` </span></span>  
<span data-ttu-id="29c41-110">`true` para indicar que el bloqueo puede causar el tiempo de ejecución esperar el subproceso de llamada devolver desde esta devolución de llamada; `false` para indicar que el bloqueo no afectará al funcionamiento del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="29c41-110">`true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  

<span data-ttu-id="29c41-111">[in] `pILHeader`  </span><span class="sxs-lookup"><span data-stu-id="29c41-111">[in] `pILHeader`  </span></span>  
<span data-ttu-id="29c41-112">Un puntero al primer byte del encabezado de IL del método.</span><span class="sxs-lookup"><span data-stu-id="29c41-112">A pointer to the first byte of the method's IL header.</span></span>   

<span data-ttu-id="29c41-113">[in] `cbILHeader`  </span><span class="sxs-lookup"><span data-stu-id="29c41-113">[in] `cbILHeader`  </span></span>  
<span data-ttu-id="29c41-114">El número de bytes en el encabezado de IL.</span><span class="sxs-lookup"><span data-stu-id="29c41-114">The number of bytes in the IL header.</span></span> 

## <a name="remarks"></a><span data-ttu-id="29c41-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="29c41-115">Remarks</span></span>  

<span data-ttu-id="29c41-116">Esta devolución de llamada se desencadena cuando un método dinámico está compilado JIT.</span><span class="sxs-lookup"><span data-stu-id="29c41-116">This callback is triggered whenever a dynamic method is JIT-compiled.</span></span> <span data-ttu-id="29c41-117">Esto incluye diversos métodos LCG y códigos auxiliares de IL.</span><span class="sxs-lookup"><span data-stu-id="29c41-117">This includes various IL stubs and LCG methods.</span></span> <span data-ttu-id="29c41-118">Su objetivo es proporcionar suficiente información para identificar el método compilado a los usuarios a escritores profiler.</span><span class="sxs-lookup"><span data-stu-id="29c41-118">Its goal is to provide profiler writers with enough information to identify the compiled method to users.</span></span>

> [!NOTE]
> <span data-ttu-id="29c41-119">`functionId` valores no se puede usar para resolver a sus tokens de metadatos, porque los métodos dinámicos no tienen metadatos.</span><span class="sxs-lookup"><span data-stu-id="29c41-119">`functionId` values cannot be used to resolve to their metadata tokens, because dynamic methods have no metadata.</span></span>

<span data-ttu-id="29c41-120">El `pILHeader` puntero solo es válido durante la devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="29c41-120">The `pILHeader` pointer is only valid during the callback.</span></span>

## <a name="requirements"></a><span data-ttu-id="29c41-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="29c41-121">Requirements</span></span>  
 <span data-ttu-id="29c41-122">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="29c41-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29c41-123">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="29c41-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="29c41-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="29c41-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="29c41-125">**Versiones de .NET framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="29c41-125">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29c41-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="29c41-126">See Also</span></span>  
 [<span data-ttu-id="29c41-127">DynamicMethodJITCompilationFinished (método)</span><span class="sxs-lookup"><span data-stu-id="29c41-127">DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)  
 [<span data-ttu-id="29c41-128">Interfaz ICorProfilerCallback8</span><span class="sxs-lookup"><span data-stu-id="29c41-128">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)
