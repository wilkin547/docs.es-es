---
description: 'Más información acerca de: FunctionEnter3 (función)'
title: FunctionEnter3 (Función)
ms.date: 03/30/2017
api_name:
- FunctionEnter3
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionEnter3
helpviewer_keywords:
- FunctionEnter3 function [.NET Framework profiling]
ms.assetid: ef782c53-dae7-4990-b4ad-fddb1e690d4e
topic_type:
- apiref
ms.openlocfilehash: 664b0ca5b40937eaa129e6843e55024802befbb7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99648680"
---
# <a name="functionenter3-function"></a><span data-ttu-id="1eff3-103">FunctionEnter3 (Función)</span><span class="sxs-lookup"><span data-stu-id="1eff3-103">FunctionEnter3 Function</span></span>

<span data-ttu-id="1eff3-104">Notifica al generador de perfiles que el control se pasa a una función.</span><span class="sxs-lookup"><span data-stu-id="1eff3-104">Notifies the profiler that control is being passed to a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1eff3-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1eff3-105">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionEnter3(FunctionOrRemappedID functionOrRemappedID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1eff3-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1eff3-106">Parameters</span></span>

- `functionOrRemappedID`

  <span data-ttu-id="1eff3-107">\[in] el identificador de la función a la que se pasa el control.</span><span class="sxs-lookup"><span data-stu-id="1eff3-107">\[in] The identifier of the function to which control is passed.</span></span>

## <a name="remarks"></a><span data-ttu-id="1eff3-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1eff3-108">Remarks</span></span>  

 <span data-ttu-id="1eff3-109">La `FunctionEnter3` función de devolución de llamada notifica al generador de perfiles cuando se llama a las funciones, pero no admite la inspección de argumentos.</span><span class="sxs-lookup"><span data-stu-id="1eff3-109">The `FunctionEnter3` callback function notifies the profiler as functions are being called, but does not support argument inspection.</span></span> <span data-ttu-id="1eff3-110">Use el [método ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3 (](icorprofilerinfo3-setenterleavefunctionhooks3-method.md) para registrar su implementación de esta función.</span><span class="sxs-lookup"><span data-stu-id="1eff3-110">Use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 method](icorprofilerinfo3-setenterleavefunctionhooks3-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="1eff3-111">La `FunctionEnter3` función es una devolución de llamada; debe implementarla.</span><span class="sxs-lookup"><span data-stu-id="1eff3-111">The `FunctionEnter3` function is a callback; you must implement it.</span></span> <span data-ttu-id="1eff3-112">La implementación debe usar el `__declspec(naked)` atributo de clase de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="1eff3-112">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="1eff3-113">El motor de ejecución no guarda ningún registro antes de llamar a esta función.</span><span class="sxs-lookup"><span data-stu-id="1eff3-113">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="1eff3-114">En la entrada, debe guardar todos los registros que use, incluidos los de la unidad de punto flotante (FPU).</span><span class="sxs-lookup"><span data-stu-id="1eff3-114">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="1eff3-115">Al salir, debe restaurar la pila desactivando todos los parámetros insertados por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="1eff3-115">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1eff3-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1eff3-116">Requirements</span></span>  

 <span data-ttu-id="1eff3-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1eff3-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1eff3-118">**Encabezado:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="1eff3-118">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="1eff3-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1eff3-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1eff3-120">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1eff3-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1eff3-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="1eff3-121">See also</span></span>

- [<span data-ttu-id="1eff3-122">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="1eff3-122">FunctionLeave3</span></span>](functionleave3-function.md)
- [<span data-ttu-id="1eff3-123">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="1eff3-123">FunctionTailcall3</span></span>](functiontailcall3-function.md)
- [<span data-ttu-id="1eff3-124">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="1eff3-124">FunctionEnter3WithInfo</span></span>](functionenter3withinfo-function.md)
- [<span data-ttu-id="1eff3-125">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="1eff3-125">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="1eff3-126">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="1eff3-126">FunctionTailcall3WithInfo</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="1eff3-127">Setenterleavefunctionhooks3 (</span><span class="sxs-lookup"><span data-stu-id="1eff3-127">SetEnterLeaveFunctionHooks3</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="1eff3-128">Setenterleavefunctionhooks3withinfo (</span><span class="sxs-lookup"><span data-stu-id="1eff3-128">SetEnterLeaveFunctionHooks3WithInfo</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="1eff3-129">Setfunctionidmapper (</span><span class="sxs-lookup"><span data-stu-id="1eff3-129">SetFunctionIDMapper</span></span>](icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="1eff3-130">Setfunctionidmapper2 (</span><span class="sxs-lookup"><span data-stu-id="1eff3-130">SetFunctionIDMapper2</span></span>](icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="1eff3-131">Funciones estáticas globales para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="1eff3-131">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
