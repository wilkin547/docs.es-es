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
ms.openlocfilehash: 62035d623d56f7521e0a599a13bc20778e3f18d1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449907"
---
# <a name="icorprofilercallbackjitinlining-method"></a><span data-ttu-id="d7643-102">ICorProfilerCallback::JITInlining (Método)</span><span class="sxs-lookup"><span data-stu-id="d7643-102">ICorProfilerCallback::JITInlining Method</span></span>
<span data-ttu-id="d7643-103">Notifica al generador de perfiles que el compilador Just-in-Time (JIT) está a punto de insertar una función en línea con otra función.</span><span class="sxs-lookup"><span data-stu-id="d7643-103">Notifies the profiler that the just-in-time (JIT) compiler is about to insert a function in line with another function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7643-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d7643-104">Syntax</span></span>  
  
```cpp  
HRESULT JITInlining(  
    [in]  FunctionID callerId,  
    [in]  FunctionID calleeId,  
    [out] BOOL      *pfShouldInline);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d7643-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d7643-105">Parameters</span></span>  
 `callerId`  
 <span data-ttu-id="d7643-106">de IDENTIFICADOR de la función en la que se insertará la función de `calleeId`.</span><span class="sxs-lookup"><span data-stu-id="d7643-106">[in] The ID of the function into which the `calleeId` function will be inserted.</span></span>  
  
 `calleeId`  
 <span data-ttu-id="d7643-107">de IDENTIFICADOR de la función que se va a insertar.</span><span class="sxs-lookup"><span data-stu-id="d7643-107">[in] The ID of the function to be inserted.</span></span>  
  
 `pfShouldInline`  
 <span data-ttu-id="d7643-108">[out] `true` para permitir que se produzca la inserción; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="d7643-108">[out] `true` to allow the insertion to occur; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d7643-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d7643-109">Remarks</span></span>  
 <span data-ttu-id="d7643-110">El generador de perfiles puede establecer `pfShouldInline` en `false` para impedir que la función `calleeId` se inserte en la función de `callerId`.</span><span class="sxs-lookup"><span data-stu-id="d7643-110">The profiler can set `pfShouldInline` to `false` to prevent the `calleeId` function from being inserted into the `callerId` function.</span></span> <span data-ttu-id="d7643-111">Además, el generador de perfiles puede deshabilitar globalmente la inserción en línea mediante el valor COR_PRF_DISABLE_INLINING de la enumeración [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="d7643-111">Also, the profiler can globally disable inline insertion by using the COR_PRF_DISABLE_INLINING value of the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
 <span data-ttu-id="d7643-112">Las funciones insertadas en línea no generan eventos para entrar o cerrar.</span><span class="sxs-lookup"><span data-stu-id="d7643-112">Functions inserted inline do not raise events for entering or leaving.</span></span> <span data-ttu-id="d7643-113">Por lo tanto, el generador de perfiles debe establecer `pfShouldInline` en `false` para generar un gráfico preciso.</span><span class="sxs-lookup"><span data-stu-id="d7643-113">Therefore, the profiler must set `pfShouldInline` to `false` in order to produce an accurate callgraph.</span></span> <span data-ttu-id="d7643-114">Establecer `pfShouldInline` en `false` afectará al rendimiento, ya que la inserción en línea normalmente aumenta la velocidad y reduce el número de eventos de compilación JIT independientes para el método insertado.</span><span class="sxs-lookup"><span data-stu-id="d7643-114">Setting `pfShouldInline` to `false` will affect performance, because inline insertion typically increases speed and reduces the number of separate JIT compilation events for the inserted method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7643-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d7643-115">Requirements</span></span>  
 <span data-ttu-id="d7643-116">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7643-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7643-117">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d7643-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d7643-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d7643-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d7643-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7643-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7643-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="d7643-120">See also</span></span>

- [<span data-ttu-id="d7643-121">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d7643-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
