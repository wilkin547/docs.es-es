---
description: 'Más información acerca de: ICorProfilerCallback8::D ynamicMethodJITCompilationStarted (método)'
title: ICorProfilerCallback8::D método ynamicMethodJITCompilationStarted
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationStarted
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 186b41564e0aabb069b06356b8eccbe90296ec4b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781706"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationstarted-method"></a><span data-ttu-id="6a004-103">ICorProfilerCallback8::D método ynamicMethodJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="6a004-103">ICorProfilerCallback8::DynamicMethodJITCompilationStarted Method</span></span>

<span data-ttu-id="6a004-104">[Se admite en el .NET Framework 4,7 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="6a004-104">[Supported in the .NET Framework 4.7 and later versions]</span></span>  
  
<span data-ttu-id="6a004-105">Notifica al generador de perfiles cada vez que se inicia la compilación JIT de un método dinámico.</span><span class="sxs-lookup"><span data-stu-id="6a004-105">Notifies the profiler whenever JIT compilation of a dynamic method has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a004-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6a004-106">Syntax</span></span>  
  
```cpp  
HRESULT DynamicMethodJITCompilationStarted(  
     [in]  FunctionID  functionId,
     [in]  BOOL        fIsSafeToBlock,
     [in]  LPCBYTE     pILHeader,
     [in]  LONG        cbILHeader
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6a004-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6a004-107">Parameters</span></span>  

<span data-ttu-id="6a004-108">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="6a004-108">[in] `functionId`</span></span>  
<span data-ttu-id="6a004-109">Identificador de la función en memoria para la que se inicia la compilación JIT.</span><span class="sxs-lookup"><span data-stu-id="6a004-109">The identifier of the in-memory function for which JIT compilation is started.</span></span>

<span data-ttu-id="6a004-110">[in] `fIsSafeToBlock` 
 `true` para indicar que el bloqueo puede hacer que el tiempo de ejecución espere a que el subproceso que realiza la llamada devuelva de esta devolución de llamada; `false`para indicar que el bloqueo no afectará al funcionamiento del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="6a004-110">[in] `fIsSafeToBlock`
`true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  

<span data-ttu-id="6a004-111">[in] `pILHeader` Puntero al primer byte del encabezado IL del método.</span><span class="sxs-lookup"><span data-stu-id="6a004-111">[in] `pILHeader` A pointer to the first byte of the method's IL header.</span></span>

<span data-ttu-id="6a004-112">[in] `cbILHeader` Número de bytes del encabezado IL.</span><span class="sxs-lookup"><span data-stu-id="6a004-112">[in] `cbILHeader` The number of bytes in the IL header.</span></span>

## <a name="remarks"></a><span data-ttu-id="6a004-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6a004-113">Remarks</span></span>  

<span data-ttu-id="6a004-114">Esta devolución de llamada se desencadena cada vez que se compila un método dinámico.</span><span class="sxs-lookup"><span data-stu-id="6a004-114">This callback is triggered whenever a dynamic method is JIT-compiled.</span></span> <span data-ttu-id="6a004-115">Esto incluye varios códigos auxiliares de IL y métodos LCG.</span><span class="sxs-lookup"><span data-stu-id="6a004-115">This includes various IL stubs and LCG methods.</span></span> <span data-ttu-id="6a004-116">Su objetivo es proporcionar a los escritores de Profiler información suficiente para identificar el método compilado para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="6a004-116">Its goal is to provide profiler writers with enough information to identify the compiled method to users.</span></span>

> [!NOTE]
> <span data-ttu-id="6a004-117">`functionId` los valores no se pueden usar para resolver sus tokens de metadatos, porque los métodos dinámicos no tienen metadatos.</span><span class="sxs-lookup"><span data-stu-id="6a004-117">`functionId` values cannot be used to resolve to their metadata tokens, because dynamic methods have no metadata.</span></span>

<span data-ttu-id="6a004-118">El `pILHeader` puntero solo es válido durante la devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="6a004-118">The `pILHeader` pointer is only valid during the callback.</span></span>

## <a name="requirements"></a><span data-ttu-id="6a004-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6a004-119">Requirements</span></span>  

 <span data-ttu-id="6a004-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6a004-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a004-121">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6a004-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6a004-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6a004-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6a004-123">**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6a004-123">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a004-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="6a004-124">See also</span></span>

- [<span data-ttu-id="6a004-125">Método DynamicMethodJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="6a004-125">DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [<span data-ttu-id="6a004-126">Interfaz ICorProfilerCallback8</span><span class="sxs-lookup"><span data-stu-id="6a004-126">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)
