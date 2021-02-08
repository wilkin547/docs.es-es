---
description: 'Más información acerca de: ICorProfilerObjectEnum:: Next (método)'
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
ms.openlocfilehash: 7f61fa1d4e28043bf5eda95f67dde0d8e87d8c0d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781420"
---
# <a name="icorprofilerobjectenumnext-method"></a><span data-ttu-id="852a0-103">ICorProfilerObjectEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="852a0-103">ICorProfilerObjectEnum::Next Method</span></span>

<span data-ttu-id="852a0-104">Obtiene el número especificado de objetos contiguos de una colección secuencial de objetos, empezando en la posición actual del enumerador en la secuencia.</span><span class="sxs-lookup"><span data-stu-id="852a0-104">Gets the specified number of contiguous objects from a sequential collection of objects, starting at the enumerator's current position in the sequence.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="852a0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="852a0-105">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG                    celt,  
    [out, size_is(celt), length_is(*pceltFetched)]
        ObjectID                  objects[],  
    [out] ULONG                   *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="852a0-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="852a0-106">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="852a0-107">[in] Número de objetos que se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="852a0-107">[in] The number of objects to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="852a0-108">enuncia Matriz de `ObjectID` valores, cada uno de los cuales representa un objeto recuperado.</span><span class="sxs-lookup"><span data-stu-id="852a0-108">[out] An array of `ObjectID` values, each of which represents a retrieved object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="852a0-109">[out] Puntero al número de elementos realmente devueltos en la matriz `objects`.</span><span class="sxs-lookup"><span data-stu-id="852a0-109">[out] A pointer to the number of elements actually returned in the `objects` array.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="852a0-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="852a0-110">Requirements</span></span>  

 <span data-ttu-id="852a0-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="852a0-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="852a0-112">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="852a0-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="852a0-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="852a0-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="852a0-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="852a0-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="852a0-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="852a0-115">See also</span></span>

- [<span data-ttu-id="852a0-116">ICorProfilerObjectEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="852a0-116">ICorProfilerObjectEnum Interface</span></span>](icorprofilerobjectenum-interface.md)
