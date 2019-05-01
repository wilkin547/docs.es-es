---
title: Método ICorProfilerCallback8::DynamicMethodJITCompilationStarted
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
ms.openlocfilehash: c4b8bffeb71497a7dd8e2ed25b833f9216d8017e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049744"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationstarted-method"></a><span data-ttu-id="53c40-102">Método ICorProfilerCallback8::DynamicMethodJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="53c40-102">ICorProfilerCallback8::DynamicMethodJITCompilationStarted Method</span></span>
<span data-ttu-id="53c40-103">[Se admite en .NET Framework 4.7 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="53c40-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  
  
<span data-ttu-id="53c40-104">Notifica al generador de perfiles cada vez que se ha iniciado la compilación JIT de un método dinámico.</span><span class="sxs-lookup"><span data-stu-id="53c40-104">Notifies the profiler whenever JIT compilation of a dynamic method has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53c40-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="53c40-105">Syntax</span></span>  
  
```  
HRESULT DynamicMethodJITCompilationStarted(  
     [in]  FunctionID  functionId,   
     [in]  BOOL        fIsSafeToBlock,   
     [in]  LPCBYTE     pILHeader,   
     [in]  LONG        cbILHeader   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="53c40-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="53c40-106">Parameters</span></span>  
<span data-ttu-id="53c40-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="53c40-107">[in] `functionId`</span></span>  
<span data-ttu-id="53c40-108">El identificador de la función en memoria para que JIT se inicia la compilación.</span><span class="sxs-lookup"><span data-stu-id="53c40-108">The identifier of the in-memory function for which JIT compilation is started.</span></span>   

<span data-ttu-id="53c40-109">[in] `fIsSafeToBlock` </span><span class="sxs-lookup"><span data-stu-id="53c40-109">[in] `fIsSafeToBlock` </span></span>  
<span data-ttu-id="53c40-110">`true` para indicar que el bloqueo puede causar el tiempo de ejecución esperar el subproceso de llamada devolver desde esta devolución de llamada; `false` para indicar que la de bloqueo no afectará al funcionamiento del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="53c40-110">`true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  

<span data-ttu-id="53c40-111">[in] `pILHeader`  </span><span class="sxs-lookup"><span data-stu-id="53c40-111">[in] `pILHeader`  </span></span>  
<span data-ttu-id="53c40-112">Un puntero al primer byte del encabezado de IL del método.</span><span class="sxs-lookup"><span data-stu-id="53c40-112">A pointer to the first byte of the method's IL header.</span></span>   

<span data-ttu-id="53c40-113">[in] `cbILHeader`  </span><span class="sxs-lookup"><span data-stu-id="53c40-113">[in] `cbILHeader`  </span></span>  
<span data-ttu-id="53c40-114">El número de bytes en el encabezado de IL.</span><span class="sxs-lookup"><span data-stu-id="53c40-114">The number of bytes in the IL header.</span></span> 

## <a name="remarks"></a><span data-ttu-id="53c40-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="53c40-115">Remarks</span></span>  

<span data-ttu-id="53c40-116">Esta devolución de llamada se desencadena cada vez que un método dinámico está compilado JIT.</span><span class="sxs-lookup"><span data-stu-id="53c40-116">This callback is triggered whenever a dynamic method is JIT-compiled.</span></span> <span data-ttu-id="53c40-117">Esto incluye diversos métodos LCG y código auxiliar de IL.</span><span class="sxs-lookup"><span data-stu-id="53c40-117">This includes various IL stubs and LCG methods.</span></span> <span data-ttu-id="53c40-118">Su objetivo es proporcionar los escritores del generador de perfiles con la suficiente información para identificar el método compilado a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="53c40-118">Its goal is to provide profiler writers with enough information to identify the compiled method to users.</span></span>

> [!NOTE]
> <span data-ttu-id="53c40-119">`functionId` los valores no se puede usar para resolver a sus tokens de metadatos, porque los métodos dinámicos no tienen ningún metadato.</span><span class="sxs-lookup"><span data-stu-id="53c40-119">`functionId` values cannot be used to resolve to their metadata tokens, because dynamic methods have no metadata.</span></span>

<span data-ttu-id="53c40-120">El `pILHeader` puntero solo es válido durante la devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="53c40-120">The `pILHeader` pointer is only valid during the callback.</span></span>

## <a name="requirements"></a><span data-ttu-id="53c40-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="53c40-121">Requirements</span></span>  
 <span data-ttu-id="53c40-122">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="53c40-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53c40-123">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="53c40-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="53c40-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="53c40-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="53c40-125">**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="53c40-125">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53c40-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="53c40-126">See also</span></span>

- [<span data-ttu-id="53c40-127">DynamicMethodJITCompilationFinished (método)</span><span class="sxs-lookup"><span data-stu-id="53c40-127">DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [<span data-ttu-id="53c40-128">ICorProfilerCallback8 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="53c40-128">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)
