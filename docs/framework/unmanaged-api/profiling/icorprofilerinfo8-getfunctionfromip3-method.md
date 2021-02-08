---
description: 'Más información sobre: ICorProfilerInfo8:: GetFunctionFromIP3 (método)'
title: ICorProfilerInfo8::GetFunctionFromIP3
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo8.GetFunctionFromIP3
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 3ce0a0964e26254ab09e515826b6bceb657e07bc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99783838"
---
# <a name="icorprofilerinfo8getfunctionfromip3-method"></a><span data-ttu-id="966a3-103">ICorProfilerInfo8:: GetFunctionFromIP3 (método)</span><span class="sxs-lookup"><span data-stu-id="966a3-103">ICorProfilerInfo8::GetFunctionFromIP3 Method</span></span>

<span data-ttu-id="966a3-104">Asigna un puntero de instrucción de código administrado a un FunctionID.</span><span class="sxs-lookup"><span data-stu-id="966a3-104">Maps a managed code instruction pointer to a FunctionID.</span></span> <span data-ttu-id="966a3-105">Este método funciona para los métodos dinámicos y no dinámicos.</span><span class="sxs-lookup"><span data-stu-id="966a3-105">This method works for both dynamic and non-dynamic methods.</span></span>

## <a name="syntax"></a><span data-ttu-id="966a3-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="966a3-106">Syntax</span></span>

```cpp
HRESULT GetFunctionFromIP3([in] LPCBYTE ip,
                           [out] FunctionID *functionId,
                           [out] ReJITID * pReJitId);
```

## <a name="parameters"></a><span data-ttu-id="966a3-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="966a3-107">Parameters</span></span>

- `ip`

  <span data-ttu-id="966a3-108">\[in] el puntero de instrucción en código administrado.</span><span class="sxs-lookup"><span data-stu-id="966a3-108">\[in] The instruction pointer in managed code.</span></span>

- `pFunctionId`

  <span data-ttu-id="966a3-109">\[out] el identificador de la función.</span><span class="sxs-lookup"><span data-stu-id="966a3-109">\[out] The function ID.</span></span>

- `pReJitId`

  <span data-ttu-id="966a3-110">\[out] la identidad de la versión recompilada con JIT de la función.</span><span class="sxs-lookup"><span data-stu-id="966a3-110">\[out] The identity of the JIT-recompiled version of the function.</span></span>

## <a name="remarks"></a><span data-ttu-id="966a3-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="966a3-111">Remarks</span></span>

<span data-ttu-id="966a3-112">Este método funciona para los métodos dinámicos y no dinámicos.</span><span class="sxs-lookup"><span data-stu-id="966a3-112">This method works for both dynamic and non-dynamic methods.</span></span> <span data-ttu-id="966a3-113">Es un supraconjunto de [getfunctionfromip2 (](icorprofilerinfo4-getfunctionfromip2-method.md), que solo funciona con funciones con metadatos.</span><span class="sxs-lookup"><span data-stu-id="966a3-113">It is a superset of [GetFunctionFromIP2](icorprofilerinfo4-getfunctionfromip2-method.md), which only works for functions with metadata.</span></span>

## <a name="requirements"></a><span data-ttu-id="966a3-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="966a3-114">Requirements</span></span>

<span data-ttu-id="966a3-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="966a3-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="966a3-116">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="966a3-116">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="966a3-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="966a3-117">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="966a3-118">**.NET Framework versiones:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="966a3-118">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="966a3-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="966a3-119">See also</span></span>

- [<span data-ttu-id="966a3-120">Interface ICorProfilerInfo8</span><span class="sxs-lookup"><span data-stu-id="966a3-120">ICorProfilerInfo8 Interface</span></span>](icorprofilerinfo8-interface.md)
