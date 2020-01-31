---
title: ICorProfilerInfo8::IsFunctionDynamic
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo8.IsFunctionDynamic
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 50b4de2de3e74a5835ee5706999892735269d4c2
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76861741"
---
# <a name="icorprofilerinfo8isfunctiondynamic-method"></a><span data-ttu-id="41d2d-102">ICorProfilerInfo8:: IsFunctionDynamic (método)</span><span class="sxs-lookup"><span data-stu-id="41d2d-102">ICorProfilerInfo8::IsFunctionDynamic Method</span></span>

<span data-ttu-id="41d2d-103">Determina si una función no tiene metadatos asociados.</span><span class="sxs-lookup"><span data-stu-id="41d2d-103">Determines if a function does not have associated metadata.</span></span>

## <a name="syntax"></a><span data-ttu-id="41d2d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="41d2d-104">Syntax</span></span>

```cpp
HRESULT IsFunctionDynamic( [in]  FunctionID  functionId,
                           [out] BOOL        *isDynamic);
```

## <a name="parameters"></a><span data-ttu-id="41d2d-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="41d2d-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="41d2d-106">\[en] el `FunctionID` que identifica la función en cuestión.</span><span class="sxs-lookup"><span data-stu-id="41d2d-106">\[in]  The `FunctionID` that identifies the function in question.</span></span>

- `isDynamic`

  <span data-ttu-id="41d2d-107">\[out] un puntero a una `BOOL` que contendrá un valor que indica si la función no tiene metadatos.</span><span class="sxs-lookup"><span data-stu-id="41d2d-107">\[out] A pointer to a `BOOL` that will contain a value indicating if the function has no metadata.</span></span>

## <a name="remarks"></a><span data-ttu-id="41d2d-108">Notas</span><span class="sxs-lookup"><span data-stu-id="41d2d-108">Remarks</span></span>

<span data-ttu-id="41d2d-109">Una función se considera dinámica si no tiene metadatos.</span><span class="sxs-lookup"><span data-stu-id="41d2d-109">A function is considered dynamic if it has no metadata.</span></span> <span data-ttu-id="41d2d-110">Ciertos métodos como el código auxiliar de IL o los métodos LCG no tienen metadatos asociados que se pueden recuperar mediante las API de IMetaDataImport.</span><span class="sxs-lookup"><span data-stu-id="41d2d-110">Certain methods like IL Stubs or LCG Methods do not have associated metadata that can be retrieved using the IMetaDataImport APIs.</span></span> <span data-ttu-id="41d2d-111">Estos métodos pueden ser detectados por los profileres a través de punteros de instrucción o escuchando a [ICorProfilerCallback::D ynamicmethodjitcompilationstarted](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md).</span><span class="sxs-lookup"><span data-stu-id="41d2d-111">These methods can be encountered by profilers through instruction pointers or by listening to [ICorProfilerCallback::DynamicMethodJITCompilationStarted](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="41d2d-112">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="41d2d-112">Requirements</span></span>

<span data-ttu-id="41d2d-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41d2d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="41d2d-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="41d2d-114">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="41d2d-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="41d2d-115">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="41d2d-116">**.NET Framework versiones:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="41d2d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="41d2d-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="41d2d-117">See also</span></span>

- [<span data-ttu-id="41d2d-118">Interfaz ICorProfilerInfo8</span><span class="sxs-lookup"><span data-stu-id="41d2d-118">ICorProfilerInfo8 Interface</span></span>](icorprofilerinfo8-interface.md)
