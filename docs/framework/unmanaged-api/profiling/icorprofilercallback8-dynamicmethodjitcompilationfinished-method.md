---
title: ICorProfilerCallback8::DynamicMethodJITCompilationFinished Método
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationFinished
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: c2e9489654a0fe5fa65ec638ed0f991a6c01415a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175114"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationfinished-method"></a><span data-ttu-id="04f6a-102">ICorProfilerCallback8::DynamicMethodJITCompilationFinished Método</span><span class="sxs-lookup"><span data-stu-id="04f6a-102">ICorProfilerCallback8::DynamicMethodJITCompilationFinished Method</span></span>
<span data-ttu-id="04f6a-103">[Soportado en .NET Framework 4.7 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="04f6a-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  
  
<span data-ttu-id="04f6a-104">Notifica al generador de perfiles cada vez que se ha completado la compilación JIT de un método dinámico.</span><span class="sxs-lookup"><span data-stu-id="04f6a-104">Notifies the profiler whenever JIT compilation of a dynamic method has completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04f6a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="04f6a-105">Syntax</span></span>  
  
```cpp  
HRESULT DynamicMethodJITCompilationFinished(  
     [in]  FunctionID  functionId,
     [in]  BOOL        hrStatus,
     [in]  BOOL        fIsSafeToBlock
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="04f6a-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="04f6a-106">Parameters</span></span>  
<span data-ttu-id="04f6a-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="04f6a-107">[in] `functionId`</span></span>  
<span data-ttu-id="04f6a-108">Identificador de la función en memoria para la que se inicia la compilación JIT.</span><span class="sxs-lookup"><span data-stu-id="04f6a-108">The identifier of the in-memory function for which JIT compilation is started.</span></span>

<span data-ttu-id="04f6a-109">[en] `hrStatus` Valor que indica si la compilación JIT se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="04f6a-109">[in] `hrStatus` A value that indicates whether the JIT compilation was successful.</span></span>

<span data-ttu-id="04f6a-110">[en] `fIsSafeToBlock` para indicar que el bloqueo puede hacer que el tiempo de ejecución espere a que el subproceso que realiza la llamada vuelva de esta devolución de 
 `true` llamada; `false` para indicar que el bloqueo no afectará al funcionamiento del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="04f6a-110">[in] `fIsSafeToBlock`
`true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  

## <a name="remarks"></a><span data-ttu-id="04f6a-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="04f6a-111">Remarks</span></span>  

<span data-ttu-id="04f6a-112">Esta devolución de llamada se desencadena cada vez que la compilación JIT de un método dinámico ha finalizado.</span><span class="sxs-lookup"><span data-stu-id="04f6a-112">This callback is triggered whenever JIT compilation of a dynamic method has finished.</span></span> <span data-ttu-id="04f6a-113">Esto incluye varios talones de IL y métodos LCG.</span><span class="sxs-lookup"><span data-stu-id="04f6a-113">This includes various IL stubs and LCG methods.</span></span> <span data-ttu-id="04f6a-114">Su objetivo es proporcionar a los escritores de generadores de perfiles suficiente información para identificar el método compilado a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="04f6a-114">Its goal is to provide profiler writers with enough information to identify the compiled method to users.</span></span>

> [!NOTE]
> <span data-ttu-id="04f6a-115">`functionId`los valores no se pueden usar para resolver en sus tokens de metadatos, porque los métodos dinámicos no tienen metadatos.</span><span class="sxs-lookup"><span data-stu-id="04f6a-115">`functionId` values cannot be used to resolve to their metadata tokens, because dynamic methods have no metadata.</span></span>

## <a name="requirements"></a><span data-ttu-id="04f6a-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="04f6a-116">Requirements</span></span>  
 <span data-ttu-id="04f6a-117">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04f6a-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04f6a-118">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="04f6a-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="04f6a-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="04f6a-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="04f6a-120">**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="04f6a-120">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04f6a-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="04f6a-121">See also</span></span>

- [<span data-ttu-id="04f6a-122">DynamicMethodJITCompilationStarted (método)</span><span class="sxs-lookup"><span data-stu-id="04f6a-122">DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="04f6a-123">ICorProfilerCallback8 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="04f6a-123">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)
