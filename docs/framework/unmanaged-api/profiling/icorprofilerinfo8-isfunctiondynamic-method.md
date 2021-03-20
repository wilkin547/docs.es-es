---
description: 'Más información sobre: ICorProfilerInfo8:: IsFunctionDynamic (método)'
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
ms.openlocfilehash: 139edeed3e078668974382f1719c8e03f83e2a09
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2021
ms.locfileid: "104759083"
---
# <a name="icorprofilerinfo8isfunctiondynamic-method"></a><span data-ttu-id="4b350-103">ICorProfilerInfo8:: IsFunctionDynamic (método)</span><span class="sxs-lookup"><span data-stu-id="4b350-103">ICorProfilerInfo8::IsFunctionDynamic Method</span></span>

<span data-ttu-id="4b350-104">Determina si una función no tiene metadatos asociados.</span><span class="sxs-lookup"><span data-stu-id="4b350-104">Determines if a function does not have associated metadata.</span></span>

## <a name="syntax"></a><span data-ttu-id="4b350-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4b350-105">Syntax</span></span>

```cpp
HRESULT IsFunctionDynamic( [in]  FunctionID  functionId,
                           [out] BOOL        *isDynamic);
```

## <a name="parameters"></a><span data-ttu-id="4b350-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4b350-106">Parameters</span></span>

<span data-ttu-id="4b350-107">`functionId` de  `FunctionID` Que identifica la función en cuestión.</span><span class="sxs-lookup"><span data-stu-id="4b350-107">`functionId` [in]  The `FunctionID` that identifies the function in question.</span></span>

<span data-ttu-id="4b350-108">`isDynamic` enuncia Un puntero a un `BOOL` que contendrá un valor que indica si la función no tiene metadatos.</span><span class="sxs-lookup"><span data-stu-id="4b350-108">`isDynamic` [out] A pointer to a `BOOL` that will contain a value indicating if the function has no metadata.</span></span>

## <a name="remarks"></a><span data-ttu-id="4b350-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4b350-109">Remarks</span></span>

<span data-ttu-id="4b350-110">Una función se considera dinámica si no tiene metadatos.</span><span class="sxs-lookup"><span data-stu-id="4b350-110">A function is considered dynamic if it has no metadata.</span></span> <span data-ttu-id="4b350-111">Ciertos métodos como el código auxiliar de IL o los métodos LCG no tienen metadatos asociados que se pueden recuperar mediante las API de IMetaDataImport.</span><span class="sxs-lookup"><span data-stu-id="4b350-111">Certain methods like IL Stubs or LCG Methods do not have associated metadata that can be retrieved using the IMetaDataImport APIs.</span></span> <span data-ttu-id="4b350-112">Estos métodos pueden ser detectados por los profileres a través de punteros de instrucción o escuchando a [ICorProfilerCallback::D ynamicmethodjitcompilationstarted](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md).</span><span class="sxs-lookup"><span data-stu-id="4b350-112">These methods can be encountered by profilers through instruction pointers or by listening to [ICorProfilerCallback::DynamicMethodJITCompilationStarted](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="4b350-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4b350-113">Requirements</span></span>

<span data-ttu-id="4b350-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b350-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="4b350-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4b350-115">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="4b350-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4b350-116">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="4b350-117">**.NET Framework versiones:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="4b350-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="4b350-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4b350-118">See also</span></span>

- [<span data-ttu-id="4b350-119">Interface ICorProfilerInfo8</span><span class="sxs-lookup"><span data-stu-id="4b350-119">ICorProfilerInfo8 Interface</span></span>](icorprofilerinfo8-interface.md)
