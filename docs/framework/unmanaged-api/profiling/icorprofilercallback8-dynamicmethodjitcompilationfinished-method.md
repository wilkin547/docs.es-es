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
ms.openlocfilehash: 6354667e754da42692cc0de2dc5330c56f951aa1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725448"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationfinished-method"></a><span data-ttu-id="138ff-102">ICorProfilerCallback8::D método ynamicMethodJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="138ff-102">ICorProfilerCallback8::DynamicMethodJITCompilationFinished Method</span></span>

<span data-ttu-id="138ff-103">[Se admite en el .NET Framework 4,7 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="138ff-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  
  
<span data-ttu-id="138ff-104">Notifica al generador de perfiles cada vez que se ha completado la compilación JIT de un método dinámico.</span><span class="sxs-lookup"><span data-stu-id="138ff-104">Notifies the profiler whenever JIT compilation of a dynamic method has completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="138ff-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="138ff-105">Syntax</span></span>  
  
```cpp  
HRESULT DynamicMethodJITCompilationFinished(  
     [in]  FunctionID  functionId,
     [in]  BOOL        hrStatus,
     [in]  BOOL        fIsSafeToBlock
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="138ff-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="138ff-106">Parameters</span></span>  

<span data-ttu-id="138ff-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="138ff-107">[in] `functionId`</span></span>  
<span data-ttu-id="138ff-108">Identificador de la función en memoria para la que se inicia la compilación JIT.</span><span class="sxs-lookup"><span data-stu-id="138ff-108">The identifier of the in-memory function for which JIT compilation is started.</span></span>

<span data-ttu-id="138ff-109">[in] `hrStatus` Valor que indica si la compilación JIT se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="138ff-109">[in] `hrStatus` A value that indicates whether the JIT compilation was successful.</span></span>

<span data-ttu-id="138ff-110">[in] `fIsSafeToBlock` 
 `true` para indicar que el bloqueo puede hacer que el tiempo de ejecución espere a que el subproceso que realiza la llamada devuelva de esta devolución de llamada; `false`para indicar que el bloqueo no afectará al funcionamiento del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="138ff-110">[in] `fIsSafeToBlock`
`true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  

## <a name="remarks"></a><span data-ttu-id="138ff-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="138ff-111">Remarks</span></span>  

<span data-ttu-id="138ff-112">Esta devolución de llamada se desencadena cuando finaliza la compilación JIT de un método dinámico.</span><span class="sxs-lookup"><span data-stu-id="138ff-112">This callback is triggered whenever JIT compilation of a dynamic method has finished.</span></span> <span data-ttu-id="138ff-113">Esto incluye varios códigos auxiliares de IL y métodos LCG.</span><span class="sxs-lookup"><span data-stu-id="138ff-113">This includes various IL stubs and LCG methods.</span></span> <span data-ttu-id="138ff-114">Su objetivo es proporcionar a los escritores de Profiler información suficiente para identificar el método compilado para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="138ff-114">Its goal is to provide profiler writers with enough information to identify the compiled method to users.</span></span>

> [!NOTE]
> <span data-ttu-id="138ff-115">`functionId` los valores no se pueden usar para resolver sus tokens de metadatos, porque los métodos dinámicos no tienen metadatos.</span><span class="sxs-lookup"><span data-stu-id="138ff-115">`functionId` values cannot be used to resolve to their metadata tokens, because dynamic methods have no metadata.</span></span>

## <a name="requirements"></a><span data-ttu-id="138ff-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="138ff-116">Requirements</span></span>  

 <span data-ttu-id="138ff-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="138ff-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="138ff-118">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="138ff-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="138ff-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="138ff-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="138ff-120">**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="138ff-120">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="138ff-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="138ff-121">See also</span></span>

- [<span data-ttu-id="138ff-122">Método DynamicMethodJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="138ff-122">DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="138ff-123">Interfaz ICorProfilerCallback8</span><span class="sxs-lookup"><span data-stu-id="138ff-123">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)
