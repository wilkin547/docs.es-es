---
title: ICorDebugILCode2::GetInstrumentedILMap (Método)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILCode2.GetInstrumentedILMap
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 7a4e3085-8f95-40ef-a4be-7d6146f47ce2
topic_type:
- apiref
ms.openlocfilehash: 097502f4321531922d6c4385e2eccbf32f66f026
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688359"
---
# <a name="icordebugilcode2getinstrumentedilmap-method"></a><span data-ttu-id="cfabb-102">ICorDebugILCode2::GetInstrumentedILMap (Método)</span><span class="sxs-lookup"><span data-stu-id="cfabb-102">ICorDebugILCode2::GetInstrumentedILMap Method</span></span>

<span data-ttu-id="cfabb-103">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="cfabb-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="cfabb-104">Devuelve la correspondencia entre los desplazamientos del lenguaje intermedio instrumentado del generador de perfiles y los desplazamientos del IL del método original para esta instancia.</span><span class="sxs-lookup"><span data-stu-id="cfabb-104">Returns a map from profiler-instrumented intermediate language (IL) offsets to original method IL offsets for this instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfabb-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cfabb-105">Syntax</span></span>  
  
```cpp
HRESULT GetInstrumentedILMap(  
   [in] ULONG32 cMap,  
   [out] ULONG32 *pcMap,  
   [out, size_is(cMap), length_is(*pcMap)] COR_IL_MAP map[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cfabb-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cfabb-106">Parameters</span></span>  

 <span data-ttu-id="cfabb-107">cMap</span><span class="sxs-lookup"><span data-stu-id="cfabb-107">cMap</span></span>  
 <span data-ttu-id="cfabb-108">[in] Capacidad de almacenamiento de la matriz `map`.</span><span class="sxs-lookup"><span data-stu-id="cfabb-108">[in] The storage capacity of the `map` array.</span></span> <span data-ttu-id="cfabb-109">Vea la sección Comentarios para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="cfabb-109">See the Remarks section for more information.</span></span>  
  
 <span data-ttu-id="cfabb-110">pcMap</span><span class="sxs-lookup"><span data-stu-id="cfabb-110">pcMap</span></span>  
 <span data-ttu-id="cfabb-111">[out] Número de valores COR_IL_MAP que se escriben en la matriz de asignaciones.</span><span class="sxs-lookup"><span data-stu-id="cfabb-111">[out] The number of COR_IL_MAP values written to the map array.</span></span>  
  
 <span data-ttu-id="cfabb-112">mapa</span><span class="sxs-lookup"><span data-stu-id="cfabb-112">map</span></span>  
 <span data-ttu-id="cfabb-113">[out] Matriz de valores COR_IL_MAP que proporcionan información sobre las asignaciones del IL instrumentado del generador de perfiles al IL del método original.</span><span class="sxs-lookup"><span data-stu-id="cfabb-113">[out] An array of COR_IL_MAP values that provide information on mappings from profiler-instrumented IL to the IL of the original method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cfabb-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cfabb-114">Remarks</span></span>  

 <span data-ttu-id="cfabb-115">Si el generador de perfiles establece la asignación llamando al método [ICorProfilerInfo:: SetILInstrumentedCodeMap (](../profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md) , el depurador puede llamar a este método para recuperar la asignación y usar la asignación internamente al calcular los desplazamientos de Il para los seguimientos de la pila y la duración de las variables.</span><span class="sxs-lookup"><span data-stu-id="cfabb-115">If the profiler sets the mapping by calling the [ICorProfilerInfo::SetILInstrumentedCodeMap](../profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md) method, the debugger can call this method to retrieve the mapping and to use the mapping internally when calculating IL offsets for stack traces and variable lifetimes.</span></span>  
  
 <span data-ttu-id="cfabb-116">Si `cMap` es 0 y `pcMap` no es **null**, `pcMap` se establece en el número de valores de COR_IL_MAP disponibles.</span><span class="sxs-lookup"><span data-stu-id="cfabb-116">If `cMap` is 0 and `pcMap` is non-**null**, `pcMap` is set to the number of available COR_IL_MAP values.</span></span> <span data-ttu-id="cfabb-117">Si `cMap` no es cero, representa la capacidad de almacenamiento de la matriz `map`.</span><span class="sxs-lookup"><span data-stu-id="cfabb-117">If `cMap` is non-zero, it represents the storage capacity of the `map` array.</span></span> <span data-ttu-id="cfabb-118">Cuando el método vuelve, `map` contiene un máximo de `cMap` elementos y `pcMap` se establece en el número de valores COR_IL_MAP escritos realmente en la `map` matriz.</span><span class="sxs-lookup"><span data-stu-id="cfabb-118">When the method returns, `map` contains a maximum of `cMap` items, and `pcMap` is set to the number of COR_IL_MAP values actually written to the `map` array.</span></span>  
  
 <span data-ttu-id="cfabb-119">Si el IL no se ha instrumentado o un generador de perfiles no ha proporcionado la asignación, este método devuelve `S_OK` y establece `pcMap` en 0.</span><span class="sxs-lookup"><span data-stu-id="cfabb-119">If the IL hasn't been instrumented or the mapping wasn't provided by a profiler, this method returns `S_OK` and sets `pcMap` to 0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cfabb-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cfabb-120">Requirements</span></span>  

 <span data-ttu-id="cfabb-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cfabb-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cfabb-122">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cfabb-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cfabb-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cfabb-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cfabb-124">**.NET Framework versiones:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cfabb-124">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfabb-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cfabb-125">See also</span></span>

- [<span data-ttu-id="cfabb-126">ICorProfilerInfo::SetILInstrumentedCodeMap</span><span class="sxs-lookup"><span data-stu-id="cfabb-126">ICorProfilerInfo::SetILInstrumentedCodeMap</span></span>](../profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md)
- [<span data-ttu-id="cfabb-127">ICorDebugILCode2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="cfabb-127">ICorDebugILCode2 Interface</span></span>](icordebugilcode2-interface.md)
- [<span data-ttu-id="cfabb-128">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="cfabb-128">Debugging Interfaces</span></span>](debugging-interfaces.md)
