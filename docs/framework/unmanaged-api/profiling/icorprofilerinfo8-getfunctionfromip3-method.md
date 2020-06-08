---
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
ms.openlocfilehash: 6822757608429ca5f4ef9520ab7574d440b67b26
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495261"
---
# <a name="icorprofilerinfo8getfunctionfromip3-method"></a><span data-ttu-id="40478-102">ICorProfilerInfo8:: GetFunctionFromIP3 (método)</span><span class="sxs-lookup"><span data-stu-id="40478-102">ICorProfilerInfo8::GetFunctionFromIP3 Method</span></span>

<span data-ttu-id="40478-103">Asigna un puntero de instrucción de código administrado a un FunctionID.</span><span class="sxs-lookup"><span data-stu-id="40478-103">Maps a managed code instruction pointer to a FunctionID.</span></span> <span data-ttu-id="40478-104">Este método funciona para los métodos dinámicos y no dinámicos.</span><span class="sxs-lookup"><span data-stu-id="40478-104">This method works for both dynamic and non-dynamic methods.</span></span>

## <a name="syntax"></a><span data-ttu-id="40478-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="40478-105">Syntax</span></span>

```cpp
HRESULT GetFunctionFromIP3([in] LPCBYTE ip,
                           [out] FunctionID *functionId,
                           [out] ReJITID * pReJitId);
```

## <a name="parameters"></a><span data-ttu-id="40478-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="40478-106">Parameters</span></span>

- `ip`

  <span data-ttu-id="40478-107">\[in] el puntero de instrucción en código administrado.</span><span class="sxs-lookup"><span data-stu-id="40478-107">\[in] The instruction pointer in managed code.</span></span>

- `pFunctionId`

  <span data-ttu-id="40478-108">\[out] el identificador de la función.</span><span class="sxs-lookup"><span data-stu-id="40478-108">\[out] The function ID.</span></span>

- `pReJitId`

  <span data-ttu-id="40478-109">\[out] la identidad de la versión recompilada con JIT de la función.</span><span class="sxs-lookup"><span data-stu-id="40478-109">\[out] The identity of the JIT-recompiled version of the function.</span></span>

## <a name="remarks"></a><span data-ttu-id="40478-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="40478-110">Remarks</span></span>

<span data-ttu-id="40478-111">Este método funciona para los métodos dinámicos y no dinámicos.</span><span class="sxs-lookup"><span data-stu-id="40478-111">This method works for both dynamic and non-dynamic methods.</span></span> <span data-ttu-id="40478-112">Es un supraconjunto de [getfunctionfromip2 (](icorprofilerinfo4-getfunctionfromip2-method.md), que solo funciona con funciones con metadatos.</span><span class="sxs-lookup"><span data-stu-id="40478-112">It is a superset of [GetFunctionFromIP2](icorprofilerinfo4-getfunctionfromip2-method.md), which only works for functions with metadata.</span></span>

## <a name="requirements"></a><span data-ttu-id="40478-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="40478-113">Requirements</span></span>

<span data-ttu-id="40478-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="40478-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="40478-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="40478-115">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="40478-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="40478-116">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="40478-117">**.NET Framework versiones:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="40478-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="40478-118">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="40478-118">See also</span></span>

- [<span data-ttu-id="40478-119">Interface ICorProfilerInfo8</span><span class="sxs-lookup"><span data-stu-id="40478-119">ICorProfilerInfo8 Interface</span></span>](icorprofilerinfo8-interface.md)
