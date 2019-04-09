---
title: Método ICorProfilerCallback8::DynamicMethodJITCompilationFinished
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
ms.openlocfilehash: 9dbe8d4f7050b93ffb34280be6d63367ef294ae8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59206595"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationfinished-method"></a><span data-ttu-id="5fba3-102">Método ICorProfilerCallback8::DynamicMethodJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="5fba3-102">ICorProfilerCallback8::DynamicMethodJITCompilationFinished Method</span></span>
<span data-ttu-id="5fba3-103">[Se admite en .NET Framework 4.7 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="5fba3-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  
  
<span data-ttu-id="5fba3-104">Notifica al generador de perfiles cada vez que se ha completado la compilación JIT de un método dinámico.</span><span class="sxs-lookup"><span data-stu-id="5fba3-104">Notifies the profiler whenever JIT compilation of a dynamic method has completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5fba3-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5fba3-105">Syntax</span></span>  
  
```  
HRESULT DynamicMethodJITCompilationFinished(  
     [in]  FunctionID  functionId,   
     [in]  BOOL        hrStatus,   
     [in]  BOOL        fIsSafeToBlock   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5fba3-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5fba3-106">Parameters</span></span>  
<span data-ttu-id="5fba3-107">[in]</span><span class="sxs-lookup"><span data-stu-id="5fba3-107">[in]</span></span> `functionId`  
<span data-ttu-id="5fba3-108">El identificador de la función en memoria para que JIT se inicia la compilación.</span><span class="sxs-lookup"><span data-stu-id="5fba3-108">The identifier of the in-memory function for which JIT compilation is started.</span></span>   

<span data-ttu-id="5fba3-109">[in]</span><span class="sxs-lookup"><span data-stu-id="5fba3-109">[in]</span></span> `hrStatus`   
<span data-ttu-id="5fba3-110">Un valor que indica si la compilación JIT fue correcta.</span><span class="sxs-lookup"><span data-stu-id="5fba3-110">A value that indicates whether the JIT compilation was successful.</span></span>

<span data-ttu-id="5fba3-111">[in]</span><span class="sxs-lookup"><span data-stu-id="5fba3-111">[in]</span></span> `fIsSafeToBlock`   
`true` <span data-ttu-id="5fba3-112">para indicar que el bloqueo puede causar el tiempo de ejecución esperar el subproceso de llamada devolver desde esta devolución de llamada; `false` para indicar que la de bloqueo no afectará al funcionamiento del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="5fba3-112">to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  

## <a name="remarks"></a><span data-ttu-id="5fba3-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5fba3-113">Remarks</span></span>  

<span data-ttu-id="5fba3-114">Esta devolución de llamada se desencadena cada vez que ha finalizado la compilación JIT de un método dinámico.</span><span class="sxs-lookup"><span data-stu-id="5fba3-114">This callback is triggered whenever JIT compilation of a dynamic method has finished.</span></span> <span data-ttu-id="5fba3-115">Esto incluye diversos métodos LCG y código auxiliar de IL.</span><span class="sxs-lookup"><span data-stu-id="5fba3-115">This includes various IL stubs and LCG methods.</span></span> <span data-ttu-id="5fba3-116">Su objetivo es proporcionar los escritores del generador de perfiles con la suficiente información para identificar el método compilado a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="5fba3-116">Its goal is to provide profiler writers with enough information to identify the compiled method to users.</span></span>

> [!NOTE]
> `functionId` <span data-ttu-id="5fba3-117">los valores no se puede usar para resolver a sus tokens de metadatos, porque los métodos dinámicos no tienen ningún metadato.</span><span class="sxs-lookup"><span data-stu-id="5fba3-117">values cannot be used to resolve to their metadata tokens, because dynamic methods have no metadata.</span></span>

## <a name="requirements"></a><span data-ttu-id="5fba3-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5fba3-118">Requirements</span></span>  
 <span data-ttu-id="5fba3-119">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5fba3-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5fba3-120">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5fba3-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5fba3-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5fba3-121">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="5fba3-122">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="5fba3-122">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5fba3-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="5fba3-123">See also</span></span>

- [<span data-ttu-id="5fba3-124">Método DynamicMethodJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="5fba3-124">DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="5fba3-125">Interfaz ICorProfilerCallback8</span><span class="sxs-lookup"><span data-stu-id="5fba3-125">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)
