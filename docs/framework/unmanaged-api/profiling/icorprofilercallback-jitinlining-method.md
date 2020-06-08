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
ms.openlocfilehash: 13ce44c9c7a04b870278bc8926dd9fe5daf10bc3
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500018"
---
# <a name="icorprofilercallbackjitinlining-method"></a><span data-ttu-id="0fc51-102">ICorProfilerCallback::JITInlining (Método)</span><span class="sxs-lookup"><span data-stu-id="0fc51-102">ICorProfilerCallback::JITInlining Method</span></span>
<span data-ttu-id="0fc51-103">Notifica al generador de perfiles que el compilador Just-in-Time (JIT) está a punto de insertar una función en línea con otra función.</span><span class="sxs-lookup"><span data-stu-id="0fc51-103">Notifies the profiler that the just-in-time (JIT) compiler is about to insert a function in line with another function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fc51-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0fc51-104">Syntax</span></span>  
  
```cpp  
HRESULT JITInlining(  
    [in]  FunctionID callerId,  
    [in]  FunctionID calleeId,  
    [out] BOOL      *pfShouldInline);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0fc51-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0fc51-105">Parameters</span></span>  
 `callerId`  
 <span data-ttu-id="0fc51-106">de IDENTIFICADOR de la función en la que se `calleeId` insertará la función.</span><span class="sxs-lookup"><span data-stu-id="0fc51-106">[in] The ID of the function into which the `calleeId` function will be inserted.</span></span>  
  
 `calleeId`  
 <span data-ttu-id="0fc51-107">de IDENTIFICADOR de la función que se va a insertar.</span><span class="sxs-lookup"><span data-stu-id="0fc51-107">[in] The ID of the function to be inserted.</span></span>  
  
 `pfShouldInline`  
 <span data-ttu-id="0fc51-108">[out] `true` para permitir que se produzca la inserción; en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="0fc51-108">[out] `true` to allow the insertion to occur; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0fc51-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0fc51-109">Remarks</span></span>  
 <span data-ttu-id="0fc51-110">El generador de perfiles puede establecer `pfShouldInline` en `false` para evitar que la `calleeId` función se inserte en la `callerId` función.</span><span class="sxs-lookup"><span data-stu-id="0fc51-110">The profiler can set `pfShouldInline` to `false` to prevent the `calleeId` function from being inserted into the `callerId` function.</span></span> <span data-ttu-id="0fc51-111">Además, el generador de perfiles puede deshabilitar globalmente la inserción en línea mediante el valor COR_PRF_DISABLE_INLINING de la enumeración [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="0fc51-111">Also, the profiler can globally disable inline insertion by using the COR_PRF_DISABLE_INLINING value of the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
 <span data-ttu-id="0fc51-112">Las funciones insertadas en línea no generan eventos para entrar o cerrar.</span><span class="sxs-lookup"><span data-stu-id="0fc51-112">Functions inserted inline do not raise events for entering or leaving.</span></span> <span data-ttu-id="0fc51-113">Por lo tanto, el generador de perfiles debe establecer en `pfShouldInline` para `false` generar un gráfico preciso.</span><span class="sxs-lookup"><span data-stu-id="0fc51-113">Therefore, the profiler must set `pfShouldInline` to `false` in order to produce an accurate callgraph.</span></span> <span data-ttu-id="0fc51-114">Si `pfShouldInline` se establece en `false` , afectará al rendimiento, ya que la inserción en línea normalmente aumenta la velocidad y reduce el número de eventos de compilación JIT independientes para el método insertado.</span><span class="sxs-lookup"><span data-stu-id="0fc51-114">Setting `pfShouldInline` to `false` will affect performance, because inline insertion typically increases speed and reduces the number of separate JIT compilation events for the inserted method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0fc51-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0fc51-115">Requirements</span></span>  
 <span data-ttu-id="0fc51-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0fc51-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0fc51-117">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0fc51-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0fc51-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0fc51-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0fc51-119">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0fc51-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fc51-120">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="0fc51-120">See also</span></span>

- [<span data-ttu-id="0fc51-121">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0fc51-121">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
