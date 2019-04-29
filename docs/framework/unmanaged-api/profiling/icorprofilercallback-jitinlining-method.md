---
title: ICorProfilerCallback::JITInlining (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITInlining
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITInlining
helpviewer_keywords:
- JITInlining method [.NET Framework profiling]
- ICorProfilerCallback::JITInlining method [.NET Framework profiling]
ms.assetid: c2f45801-dd38-4b78-b6b7-64397dc73f83
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 60183291fda551e328ee1def03c02240314a71e4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61598238"
---
# <a name="icorprofilercallbackjitinlining-method"></a><span data-ttu-id="117ed-102">ICorProfilerCallback::JITInlining (Método)</span><span class="sxs-lookup"><span data-stu-id="117ed-102">ICorProfilerCallback::JITInlining Method</span></span>
<span data-ttu-id="117ed-103">Notifica que el generador de perfiles que el compilador just-in-time (JIT) está a punto de insertar una función en consonancia con otra función.</span><span class="sxs-lookup"><span data-stu-id="117ed-103">Notifies the profiler that the just-in-time (JIT) compiler is about to insert a function in line with another function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="117ed-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="117ed-104">Syntax</span></span>  
  
```  
HRESULT JITInlining(  
    [in]  FunctionID callerId,  
    [in]  FunctionID calleeId,  
    [out] BOOL      *pfShouldInline);  
```  
  
## <a name="parameters"></a><span data-ttu-id="117ed-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="117ed-105">Parameters</span></span>  
 `callerId`  
 <span data-ttu-id="117ed-106">[in] El identificador de la función en la que el `calleeId` función que se va a insertar.</span><span class="sxs-lookup"><span data-stu-id="117ed-106">[in] The ID of the function into which the `calleeId` function will be inserted.</span></span>  
  
 `calleeId`  
 <span data-ttu-id="117ed-107">[in] Id. de la función que se va a insertar.</span><span class="sxs-lookup"><span data-stu-id="117ed-107">[in] The ID of the function to be inserted.</span></span>  
  
 `pfShouldInline`  
 <span data-ttu-id="117ed-108">[out] `true` para permitir la inserción; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="117ed-108">[out] `true` to allow the insertion to occur; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="117ed-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="117ed-109">Remarks</span></span>  
 <span data-ttu-id="117ed-110">Puede establecer el generador de perfiles `pfShouldInline` a `false` para evitar la `calleeId` función desde la que se inserta en la `callerId` función.</span><span class="sxs-lookup"><span data-stu-id="117ed-110">The profiler can set `pfShouldInline` to `false` to prevent the `calleeId` function from being inserted into the `callerId` function.</span></span> <span data-ttu-id="117ed-111">Además, el generador de perfiles puede deshabilitar globalmente inserción en línea mediante el uso del valor COR_PRF_DISABLE_INLINING de la [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeración.</span><span class="sxs-lookup"><span data-stu-id="117ed-111">Also, the profiler can globally disable inline insertion by using the COR_PRF_DISABLE_INLINING value of the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
 <span data-ttu-id="117ed-112">En línea de funciones insertadas no provocan eventos de entrada o salida.</span><span class="sxs-lookup"><span data-stu-id="117ed-112">Functions inserted inline do not raise events for entering or leaving.</span></span> <span data-ttu-id="117ed-113">Por lo tanto, debe establecer el generador de perfiles `pfShouldInline` a `false` con el fin de generar un gráfico de llamadas preciso.</span><span class="sxs-lookup"><span data-stu-id="117ed-113">Therefore, the profiler must set `pfShouldInline` to `false` in order to produce an accurate callgraph.</span></span> <span data-ttu-id="117ed-114">Establecer `pfShouldInline` a `false` afectará al rendimiento, porque la inserción en línea normalmente aumenta la velocidad y reduce el número de eventos de compilación JIT independientes para el método insertado.</span><span class="sxs-lookup"><span data-stu-id="117ed-114">Setting `pfShouldInline` to `false` will affect performance, because inline insertion typically increases speed and reduces the number of separate JIT compilation events for the inserted method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="117ed-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="117ed-115">Requirements</span></span>  
 <span data-ttu-id="117ed-116">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="117ed-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="117ed-117">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="117ed-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="117ed-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="117ed-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="117ed-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="117ed-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="117ed-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="117ed-120">See also</span></span>

- [<span data-ttu-id="117ed-121">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="117ed-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
