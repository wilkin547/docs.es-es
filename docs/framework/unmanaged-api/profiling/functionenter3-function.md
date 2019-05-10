---
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d05475f06a206dcb88d198c713767618453d742e
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64586908"
---
# <a name="functionenter3-function"></a><span data-ttu-id="fb7f5-102">FunctionEnter3 (Función)</span><span class="sxs-lookup"><span data-stu-id="fb7f5-102">FunctionEnter3 Function</span></span>
<span data-ttu-id="fb7f5-103">Notifica al generador de perfiles que se pasa a una función de control.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-103">Notifies the profiler that control is being passed to a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb7f5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fb7f5-104">Syntax</span></span>  
  
```  
void __stdcall FunctionEnter3(FunctionOrRemappedID functionOrRemappedID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fb7f5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fb7f5-105">Parameters</span></span>  
 `functionOrRemappedID`  
 <span data-ttu-id="fb7f5-106">[in] El identificador de la función a la que se pasa el control.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-106">[in] The identifier of the function to which control is passed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fb7f5-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fb7f5-107">Remarks</span></span>  
 <span data-ttu-id="fb7f5-108">El `FunctionEnter3` función de devolución de llamada notifica el generador de perfiles cuando las funciones se llama a, pero hace no inspección de argumento de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-108">The `FunctionEnter3` callback function notifies the profiler as functions are being called, but does not support argument inspection.</span></span> <span data-ttu-id="fb7f5-109">Use la [ICorProfilerInfo3:: Setenterleavefunctionhooks3 (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) para registrar su implementación de esta función.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-109">Use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="fb7f5-110">El `FunctionEnter3` función es una devolución de llamada; debe implementar.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-110">The `FunctionEnter3` function is a callback; you must implement it.</span></span> <span data-ttu-id="fb7f5-111">La implementación debe usar el `__declspec(naked)` atributo de clase de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-111">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="fb7f5-112">El motor de ejecución no guarda ningún registro antes de llamar a esta función.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-112">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="fb7f5-113">En la entrada, debe guardar todos los registros que utilice, incluidos los de la unidad de punto flotante (FPU).</span><span class="sxs-lookup"><span data-stu-id="fb7f5-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="fb7f5-114">En la salida, debe restaurar la pila debe extraer todos los parámetros que se insertaron su llamador.</span><span class="sxs-lookup"><span data-stu-id="fb7f5-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb7f5-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fb7f5-115">Requirements</span></span>  
 <span data-ttu-id="fb7f5-116">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fb7f5-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb7f5-117">**Encabezado**: CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="fb7f5-117">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="fb7f5-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fb7f5-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fb7f5-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb7f5-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb7f5-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="fb7f5-120">See also</span></span>

- [<span data-ttu-id="fb7f5-121">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="fb7f5-121">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)
- [<span data-ttu-id="fb7f5-122">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="fb7f5-122">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="fb7f5-123">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="fb7f5-123">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)
- [<span data-ttu-id="fb7f5-124">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="fb7f5-124">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [<span data-ttu-id="fb7f5-125">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="fb7f5-125">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [<span data-ttu-id="fb7f5-126">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="fb7f5-126">SetEnterLeaveFunctionHooks3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="fb7f5-127">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="fb7f5-127">SetEnterLeaveFunctionHooks3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="fb7f5-128">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="fb7f5-128">SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="fb7f5-129">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="fb7f5-129">SetFunctionIDMapper2</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="fb7f5-130">Funciones estáticas globales para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="fb7f5-130">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
