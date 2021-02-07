---
description: 'Más información sobre: ICorProfilerCallback:: Jitinlining ((método)'
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
ms.openlocfilehash: 2bd6c48180b9484ef90b6afb505c8171aff57aa4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99705647"
---
# <a name="icorprofilercallbackjitinlining-method"></a><span data-ttu-id="21986-103">ICorProfilerCallback::JITInlining (Método)</span><span class="sxs-lookup"><span data-stu-id="21986-103">ICorProfilerCallback::JITInlining Method</span></span>

<span data-ttu-id="21986-104">Notifica al generador de perfiles que el compilador Just-in-Time (JIT) está a punto de insertar una función en línea con otra función.</span><span class="sxs-lookup"><span data-stu-id="21986-104">Notifies the profiler that the just-in-time (JIT) compiler is about to insert a function in line with another function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21986-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="21986-105">Syntax</span></span>  
  
```cpp  
HRESULT JITInlining(  
    [in]  FunctionID callerId,  
    [in]  FunctionID calleeId,  
    [out] BOOL      *pfShouldInline);  
```  
  
## <a name="parameters"></a><span data-ttu-id="21986-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="21986-106">Parameters</span></span>  

 `callerId`  
 <span data-ttu-id="21986-107">de IDENTIFICADOR de la función en la que se `calleeId` insertará la función.</span><span class="sxs-lookup"><span data-stu-id="21986-107">[in] The ID of the function into which the `calleeId` function will be inserted.</span></span>  
  
 `calleeId`  
 <span data-ttu-id="21986-108">de IDENTIFICADOR de la función que se va a insertar.</span><span class="sxs-lookup"><span data-stu-id="21986-108">[in] The ID of the function to be inserted.</span></span>  
  
 `pfShouldInline`  
 <span data-ttu-id="21986-109">[out] `true` para permitir que se produzca la inserción; en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="21986-109">[out] `true` to allow the insertion to occur; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="21986-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="21986-110">Remarks</span></span>  

 <span data-ttu-id="21986-111">El generador de perfiles puede establecer `pfShouldInline` en `false` para evitar que la `calleeId` función se inserte en la `callerId` función.</span><span class="sxs-lookup"><span data-stu-id="21986-111">The profiler can set `pfShouldInline` to `false` to prevent the `calleeId` function from being inserted into the `callerId` function.</span></span> <span data-ttu-id="21986-112">Además, el generador de perfiles puede deshabilitar globalmente la inserción en línea mediante el valor COR_PRF_DISABLE_INLINING de la enumeración [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="21986-112">Also, the profiler can globally disable inline insertion by using the COR_PRF_DISABLE_INLINING value of the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
 <span data-ttu-id="21986-113">Las funciones insertadas en línea no generan eventos para entrar o cerrar.</span><span class="sxs-lookup"><span data-stu-id="21986-113">Functions inserted inline do not raise events for entering or leaving.</span></span> <span data-ttu-id="21986-114">Por lo tanto, el generador de perfiles debe establecer en `pfShouldInline` para `false` generar un gráfico preciso.</span><span class="sxs-lookup"><span data-stu-id="21986-114">Therefore, the profiler must set `pfShouldInline` to `false` in order to produce an accurate callgraph.</span></span> <span data-ttu-id="21986-115">Si `pfShouldInline` se establece en `false` , afectará al rendimiento, ya que la inserción en línea normalmente aumenta la velocidad y reduce el número de eventos de compilación JIT independientes para el método insertado.</span><span class="sxs-lookup"><span data-stu-id="21986-115">Setting `pfShouldInline` to `false` will affect performance, because inline insertion typically increases speed and reduces the number of separate JIT compilation events for the inserted method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21986-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="21986-116">Requirements</span></span>  

 <span data-ttu-id="21986-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="21986-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21986-118">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="21986-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="21986-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="21986-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="21986-120">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21986-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21986-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="21986-121">See also</span></span>

- [<span data-ttu-id="21986-122">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="21986-122">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
