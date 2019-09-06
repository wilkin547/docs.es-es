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
ms.openlocfilehash: 7b0d8033a5ea3b98623b9be384788ef7fc15bf04
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69665631"
---
# <a name="icorprofilerinfo8getfunctionfromip3-method"></a><span data-ttu-id="cc1fb-102">ICorProfilerInfo8:: GetFunctionFromIP3 (método)</span><span class="sxs-lookup"><span data-stu-id="cc1fb-102">ICorProfilerInfo8::GetFunctionFromIP3 Method</span></span>

<span data-ttu-id="cc1fb-103">Asigna un puntero de instrucción de código administrado a un FunctionID.</span><span class="sxs-lookup"><span data-stu-id="cc1fb-103">Maps a managed code instruction pointer to a FunctionID.</span></span> <span data-ttu-id="cc1fb-104">Este método funciona para los métodos dinámicos y no dinámicos.</span><span class="sxs-lookup"><span data-stu-id="cc1fb-104">This method works for both dynamic and non-dynamic methods.</span></span>

## <a name="syntax"></a><span data-ttu-id="cc1fb-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cc1fb-105">Syntax</span></span>

```cpp
HRESULT GetFunctionFromIP3([in] LPCBYTE ip,
                           [out] FunctionID *functionId,
                           [out] ReJITID * pReJitId);
```

#### <a name="parameters"></a><span data-ttu-id="cc1fb-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cc1fb-106">Parameters</span></span>

`ip` \
<span data-ttu-id="cc1fb-107">de Puntero de instrucción en código administrado.</span><span class="sxs-lookup"><span data-stu-id="cc1fb-107">[in] The instruction pointer in managed code.</span></span>

`pFunctionId` \
<span data-ttu-id="cc1fb-108">enuncia IDENTIFICADOR de la función.</span><span class="sxs-lookup"><span data-stu-id="cc1fb-108">[out] The function ID.</span></span>

`pReJitId` \
<span data-ttu-id="cc1fb-109">enuncia La identidad de la versión recompilada con JIT de la función.</span><span class="sxs-lookup"><span data-stu-id="cc1fb-109">[out] The identity of the JIT-recompiled version of the function.</span></span>

## <a name="remarks"></a><span data-ttu-id="cc1fb-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cc1fb-110">Remarks</span></span>

<span data-ttu-id="cc1fb-111">Este método funciona para los métodos dinámicos y no dinámicos.</span><span class="sxs-lookup"><span data-stu-id="cc1fb-111">This method works for both dynamic and non-dynamic methods.</span></span> <span data-ttu-id="cc1fb-112">Es un supraconjunto de [getfunctionfromip2 (](icorprofilerinfo4-getfunctionfromip2-method.md), que solo funciona con funciones con metadatos.</span><span class="sxs-lookup"><span data-stu-id="cc1fb-112">It is a superset of [GetFunctionFromIP2](icorprofilerinfo4-getfunctionfromip2-method.md), which only works for functions with metadata.</span></span>

## <a name="requirements"></a><span data-ttu-id="cc1fb-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cc1fb-113">Requirements</span></span>

<span data-ttu-id="cc1fb-114">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc1fb-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="cc1fb-115">**Encabezado**: Corprof. idl, Corprof. h</span><span class="sxs-lookup"><span data-stu-id="cc1fb-115">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="cc1fb-116">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cc1fb-116">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="cc1fb-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)</span><span class="sxs-lookup"><span data-stu-id="cc1fb-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)</span></span>

## <a name="see-also"></a><span data-ttu-id="cc1fb-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="cc1fb-118">See also</span></span>

- [<span data-ttu-id="cc1fb-119">Interfaz ICorProfilerInfo8</span><span class="sxs-lookup"><span data-stu-id="cc1fb-119">ICorProfilerInfo8 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-interface.md)
