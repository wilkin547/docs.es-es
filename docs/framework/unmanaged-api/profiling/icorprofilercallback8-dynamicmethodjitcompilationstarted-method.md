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
ms.openlocfilehash: 46a25fc6e9119481f728275e0569429cc6c46dc9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725435"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationstarted-method"></a><span data-ttu-id="7d331-102">ICorProfilerCallback8::D método ynamicMethodJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="7d331-102">ICorProfilerCallback8::DynamicMethodJITCompilationStarted Method</span></span>

<span data-ttu-id="7d331-103">[Se admite en el .NET Framework 4,7 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="7d331-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  
  
<span data-ttu-id="7d331-104">Notifica al generador de perfiles cada vez que se inicia la compilación JIT de un método dinámico.</span><span class="sxs-lookup"><span data-stu-id="7d331-104">Notifies the profiler whenever JIT compilation of a dynamic method has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d331-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7d331-105">Syntax</span></span>  
  
```cpp  
HRESULT DynamicMethodJITCompilationStarted(  
     [in]  FunctionID  functionId,
     [in]  BOOL        fIsSafeToBlock,
     [in]  LPCBYTE     pILHeader,
     [in]  LONG        cbILHeader
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d331-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7d331-106">Parameters</span></span>  

<span data-ttu-id="7d331-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="7d331-107">[in] `functionId`</span></span>  
<span data-ttu-id="7d331-108">Identificador de la función en memoria para la que se inicia la compilación JIT.</span><span class="sxs-lookup"><span data-stu-id="7d331-108">The identifier of the in-memory function for which JIT compilation is started.</span></span>

<span data-ttu-id="7d331-109">[in] `fIsSafeToBlock` 
 `true` para indicar que el bloqueo puede hacer que el tiempo de ejecución espere a que el subproceso que realiza la llamada devuelva de esta devolución de llamada; `false`para indicar que el bloqueo no afectará al funcionamiento del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="7d331-109">[in] `fIsSafeToBlock`
`true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  

<span data-ttu-id="7d331-110">[in] `pILHeader` Puntero al primer byte del encabezado IL del método.</span><span class="sxs-lookup"><span data-stu-id="7d331-110">[in] `pILHeader` A pointer to the first byte of the method's IL header.</span></span>

<span data-ttu-id="7d331-111">[in] `cbILHeader` Número de bytes del encabezado IL.</span><span class="sxs-lookup"><span data-stu-id="7d331-111">[in] `cbILHeader` The number of bytes in the IL header.</span></span>

## <a name="remarks"></a><span data-ttu-id="7d331-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7d331-112">Remarks</span></span>  

<span data-ttu-id="7d331-113">Esta devolución de llamada se desencadena cada vez que se compila un método dinámico.</span><span class="sxs-lookup"><span data-stu-id="7d331-113">This callback is triggered whenever a dynamic method is JIT-compiled.</span></span> <span data-ttu-id="7d331-114">Esto incluye varios códigos auxiliares de IL y métodos LCG.</span><span class="sxs-lookup"><span data-stu-id="7d331-114">This includes various IL stubs and LCG methods.</span></span> <span data-ttu-id="7d331-115">Su objetivo es proporcionar a los escritores de Profiler información suficiente para identificar el método compilado para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="7d331-115">Its goal is to provide profiler writers with enough information to identify the compiled method to users.</span></span>

> [!NOTE]
> <span data-ttu-id="7d331-116">`functionId` los valores no se pueden usar para resolver sus tokens de metadatos, porque los métodos dinámicos no tienen metadatos.</span><span class="sxs-lookup"><span data-stu-id="7d331-116">`functionId` values cannot be used to resolve to their metadata tokens, because dynamic methods have no metadata.</span></span>

<span data-ttu-id="7d331-117">El `pILHeader` puntero solo es válido durante la devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="7d331-117">The `pILHeader` pointer is only valid during the callback.</span></span>

## <a name="requirements"></a><span data-ttu-id="7d331-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7d331-118">Requirements</span></span>  

 <span data-ttu-id="7d331-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d331-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d331-120">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7d331-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7d331-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7d331-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7d331-122">**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="7d331-122">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d331-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7d331-123">See also</span></span>

- [<span data-ttu-id="7d331-124">Método DynamicMethodJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="7d331-124">DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [<span data-ttu-id="7d331-125">Interfaz ICorProfilerCallback8</span><span class="sxs-lookup"><span data-stu-id="7d331-125">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)
