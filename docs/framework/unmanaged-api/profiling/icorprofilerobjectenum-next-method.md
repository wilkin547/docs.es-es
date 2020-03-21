---
title: ICorProfilerObjectEnum::Next (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerObjectEnum.Next
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerObjectEnum::Next
helpviewer_keywords:
- Next method, ICorProfilerObjectEnum interface [.NET Framework profiling]
- ICorProfilerObjectEnum::Next method [.NET Framework profiling]
ms.assetid: b420433c-5ebe-4986-bba1-97902e6db819
topic_type:
- apiref
ms.openlocfilehash: b6e26d1538cab30db66e887aee89b8fbae501bdb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177012"
---
# <a name="icorprofilerobjectenumnext-method"></a><span data-ttu-id="c1ab6-102">ICorProfilerObjectEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="c1ab6-102">ICorProfilerObjectEnum::Next Method</span></span>
<span data-ttu-id="c1ab6-103">Obtiene el número especificado de objetos contiguos de una colección secuencial de objetos, comenzando en la posición actual del enumerador en la secuencia.</span><span class="sxs-lookup"><span data-stu-id="c1ab6-103">Gets the specified number of contiguous objects from a sequential collection of objects, starting at the enumerator's current position in the sequence.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1ab6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c1ab6-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG                    celt,  
    [out, size_is(celt), length_is(*pceltFetched)]
        ObjectID                  objects[],  
    [out] ULONG                   *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c1ab6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c1ab6-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="c1ab6-106">[in] Número de objetos que se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="c1ab6-106">[in] The number of objects to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="c1ab6-107">[fuera] Matriz de `ObjectID` valores, cada uno de los cuales representa un objeto recuperado.</span><span class="sxs-lookup"><span data-stu-id="c1ab6-107">[out] An array of `ObjectID` values, each of which represents a retrieved object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="c1ab6-108">[out] Puntero al número de elementos realmente devueltos en la matriz `objects`.</span><span class="sxs-lookup"><span data-stu-id="c1ab6-108">[out] A pointer to the number of elements actually returned in the `objects` array.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1ab6-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c1ab6-109">Requirements</span></span>  
 <span data-ttu-id="c1ab6-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c1ab6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1ab6-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c1ab6-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c1ab6-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c1ab6-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c1ab6-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1ab6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1ab6-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c1ab6-114">See also</span></span>

- [<span data-ttu-id="c1ab6-115">ICorProfilerObjectEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c1ab6-115">ICorProfilerObjectEnum Interface</span></span>](icorprofilerobjectenum-interface.md)
