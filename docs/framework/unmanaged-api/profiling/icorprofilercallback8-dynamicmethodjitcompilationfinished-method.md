---
description: 'Más información acerca de: ICorProfilerCallback8::D ynamicMethodJITCompilationFinished (método)'
title: ICorProfilerCallback8::D método ynamicMethodJITCompilationFinished
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationFinished
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: d076307b9e57c27753297cad8eebc1b9aa9433f6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781719"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationfinished-method"></a><span data-ttu-id="442ac-103">ICorProfilerCallback8::D método ynamicMethodJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="442ac-103">ICorProfilerCallback8::DynamicMethodJITCompilationFinished Method</span></span>

<span data-ttu-id="442ac-104">[Se admite en el .NET Framework 4,7 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="442ac-104">[Supported in the .NET Framework 4.7 and later versions]</span></span>  
  
<span data-ttu-id="442ac-105">Notifica al generador de perfiles cada vez que se ha completado la compilación JIT de un método dinámico.</span><span class="sxs-lookup"><span data-stu-id="442ac-105">Notifies the profiler whenever JIT compilation of a dynamic method has completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="442ac-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="442ac-106">Syntax</span></span>  
  
```cpp  
HRESULT DynamicMethodJITCompilationFinished(  
     [in]  FunctionID  functionId,
     [in]  BOOL        hrStatus,
     [in]  BOOL        fIsSafeToBlock
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="442ac-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="442ac-107">Parameters</span></span>  

<span data-ttu-id="442ac-108">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="442ac-108">[in] `functionId`</span></span>  
<span data-ttu-id="442ac-109">Identificador de la función en memoria para la que se inicia la compilación JIT.</span><span class="sxs-lookup"><span data-stu-id="442ac-109">The identifier of the in-memory function for which JIT compilation is started.</span></span>

<span data-ttu-id="442ac-110">[in] `hrStatus` Valor que indica si la compilación JIT se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="442ac-110">[in] `hrStatus` A value that indicates whether the JIT compilation was successful.</span></span>

<span data-ttu-id="442ac-111">[in] `fIsSafeToBlock` 
 `true` para indicar que el bloqueo puede hacer que el tiempo de ejecución espere a que el subproceso que realiza la llamada devuelva de esta devolución de llamada; `false`para indicar que el bloqueo no afectará al funcionamiento del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="442ac-111">[in] `fIsSafeToBlock`
`true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  

## <a name="remarks"></a><span data-ttu-id="442ac-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="442ac-112">Remarks</span></span>  

<span data-ttu-id="442ac-113">Esta devolución de llamada se desencadena cuando finaliza la compilación JIT de un método dinámico.</span><span class="sxs-lookup"><span data-stu-id="442ac-113">This callback is triggered whenever JIT compilation of a dynamic method has finished.</span></span> <span data-ttu-id="442ac-114">Esto incluye varios códigos auxiliares de IL y métodos LCG.</span><span class="sxs-lookup"><span data-stu-id="442ac-114">This includes various IL stubs and LCG methods.</span></span> <span data-ttu-id="442ac-115">Su objetivo es proporcionar a los escritores de Profiler información suficiente para identificar el método compilado para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="442ac-115">Its goal is to provide profiler writers with enough information to identify the compiled method to users.</span></span>

> [!NOTE]
> <span data-ttu-id="442ac-116">`functionId` los valores no se pueden usar para resolver sus tokens de metadatos, porque los métodos dinámicos no tienen metadatos.</span><span class="sxs-lookup"><span data-stu-id="442ac-116">`functionId` values cannot be used to resolve to their metadata tokens, because dynamic methods have no metadata.</span></span>

## <a name="requirements"></a><span data-ttu-id="442ac-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="442ac-117">Requirements</span></span>  

 <span data-ttu-id="442ac-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="442ac-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="442ac-119">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="442ac-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="442ac-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="442ac-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="442ac-121">**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="442ac-121">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="442ac-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="442ac-122">See also</span></span>

- [<span data-ttu-id="442ac-123">Método DynamicMethodJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="442ac-123">DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="442ac-124">Interfaz ICorProfilerCallback8</span><span class="sxs-lookup"><span data-stu-id="442ac-124">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)
