---
title: ICorProfilerCallback8::D método ynamicMethodJITCompilationStarted
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationStarted
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 1eaf29e1c93f352facde4af2ee57910783d82e5d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136461"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationstarted-method"></a><span data-ttu-id="2e7ec-102">ICorProfilerCallback8::D método ynamicMethodJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="2e7ec-102">ICorProfilerCallback8::DynamicMethodJITCompilationStarted Method</span></span>
<span data-ttu-id="2e7ec-103">[Se admite en el .NET Framework 4,7 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="2e7ec-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  
  
<span data-ttu-id="2e7ec-104">Notifica al generador de perfiles cada vez que se inicia la compilación JIT de un método dinámico.</span><span class="sxs-lookup"><span data-stu-id="2e7ec-104">Notifies the profiler whenever JIT compilation of a dynamic method has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e7ec-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2e7ec-105">Syntax</span></span>  
  
```cpp  
HRESULT DynamicMethodJITCompilationStarted(  
     [in]  FunctionID  functionId,   
     [in]  BOOL        fIsSafeToBlock,   
     [in]  LPCBYTE     pILHeader,   
     [in]  LONG        cbILHeader   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2e7ec-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2e7ec-106">Parameters</span></span>  
<span data-ttu-id="2e7ec-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="2e7ec-107">[in] `functionId`</span></span>  
<span data-ttu-id="2e7ec-108">Identificador de la función en memoria para la que se inicia la compilación JIT.</span><span class="sxs-lookup"><span data-stu-id="2e7ec-108">The identifier of the in-memory function for which JIT compilation is started.</span></span>   

<span data-ttu-id="2e7ec-109">[in] `fIsSafeToBlock` </span><span class="sxs-lookup"><span data-stu-id="2e7ec-109">[in] `fIsSafeToBlock` </span></span>  
<span data-ttu-id="2e7ec-110">`true` para indicar que el bloqueo puede hacer que el tiempo de ejecución espere a que el subproceso que realiza la llamada devuelva de esta devolución de llamada; `false` para indicar que el bloqueo no afectará al funcionamiento del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="2e7ec-110">`true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  

<span data-ttu-id="2e7ec-111">[in] `pILHeader`  </span><span class="sxs-lookup"><span data-stu-id="2e7ec-111">[in] `pILHeader`  </span></span>  
<span data-ttu-id="2e7ec-112">Puntero al primer byte del encabezado IL del método.</span><span class="sxs-lookup"><span data-stu-id="2e7ec-112">A pointer to the first byte of the method's IL header.</span></span>   

<span data-ttu-id="2e7ec-113">[in] `cbILHeader`  </span><span class="sxs-lookup"><span data-stu-id="2e7ec-113">[in] `cbILHeader`  </span></span>  
<span data-ttu-id="2e7ec-114">Número de bytes del encabezado IL.</span><span class="sxs-lookup"><span data-stu-id="2e7ec-114">The number of bytes in the IL header.</span></span> 

## <a name="remarks"></a><span data-ttu-id="2e7ec-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2e7ec-115">Remarks</span></span>  

<span data-ttu-id="2e7ec-116">Esta devolución de llamada se desencadena cada vez que se compila un método dinámico.</span><span class="sxs-lookup"><span data-stu-id="2e7ec-116">This callback is triggered whenever a dynamic method is JIT-compiled.</span></span> <span data-ttu-id="2e7ec-117">Esto incluye varios códigos auxiliares de IL y métodos LCG.</span><span class="sxs-lookup"><span data-stu-id="2e7ec-117">This includes various IL stubs and LCG methods.</span></span> <span data-ttu-id="2e7ec-118">Su objetivo es proporcionar a los escritores de Profiler información suficiente para identificar el método compilado para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="2e7ec-118">Its goal is to provide profiler writers with enough information to identify the compiled method to users.</span></span>

> [!NOTE]
> <span data-ttu-id="2e7ec-119">`functionId` valores no se pueden usar para resolver sus tokens de metadatos, porque los métodos dinámicos no tienen metadatos.</span><span class="sxs-lookup"><span data-stu-id="2e7ec-119">`functionId` values cannot be used to resolve to their metadata tokens, because dynamic methods have no metadata.</span></span>

<span data-ttu-id="2e7ec-120">El puntero `pILHeader` solo es válido durante la devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="2e7ec-120">The `pILHeader` pointer is only valid during the callback.</span></span>

## <a name="requirements"></a><span data-ttu-id="2e7ec-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2e7ec-121">Requirements</span></span>  
 <span data-ttu-id="2e7ec-122">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2e7ec-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e7ec-123">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2e7ec-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2e7ec-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2e7ec-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2e7ec-125">**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="2e7ec-125">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e7ec-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="2e7ec-126">See also</span></span>

- [<span data-ttu-id="2e7ec-127">DynamicMethodJITCompilationFinished (método)</span><span class="sxs-lookup"><span data-stu-id="2e7ec-127">DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [<span data-ttu-id="2e7ec-128">ICorProfilerCallback8 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2e7ec-128">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)
