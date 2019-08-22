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
ms.openlocfilehash: 046db493db77572904a8454a5b002dcae15b9e1d
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69661159"
---
# <a name="icorprofilerinfo8isfunctiondynamic-method"></a><span data-ttu-id="d16a9-102">ICorProfilerInfo8:: IsFunctionDynamic (método)</span><span class="sxs-lookup"><span data-stu-id="d16a9-102">ICorProfilerInfo8::IsFunctionDynamic Method</span></span>

<span data-ttu-id="d16a9-103">Determina si una función no tiene metadatos asociados.</span><span class="sxs-lookup"><span data-stu-id="d16a9-103">Determines if a function does not have associated metadata.</span></span>

## <a name="syntax"></a><span data-ttu-id="d16a9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d16a9-104">Syntax</span></span>

```cpp
HRESULT IsFunctionDynamic( [in]  FunctionID  functionId,
                           [out] BOOL        *isDynamic);
```

#### <a name="parameters"></a><span data-ttu-id="d16a9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d16a9-105">Parameters</span></span>

`functionId` \
<span data-ttu-id="d16a9-106">de  `FunctionID` Que identifica la función en cuestión.</span><span class="sxs-lookup"><span data-stu-id="d16a9-106">[in]  The `FunctionID` that identifies the function in question.</span></span>

`isDynamic` \
<span data-ttu-id="d16a9-107">enuncia Un puntero a un `BOOL` que contendrá un valor que indica si la función no tiene metadatos.</span><span class="sxs-lookup"><span data-stu-id="d16a9-107">[out] A pointer to a `BOOL` that will contain a value indicating if the function has no metadata.</span></span>

## <a name="remarks"></a><span data-ttu-id="d16a9-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d16a9-108">Remarks</span></span>

<span data-ttu-id="d16a9-109">Una función se considera dinámica si no tiene metadatos.</span><span class="sxs-lookup"><span data-stu-id="d16a9-109">A function is considered dynamic if it has no metadata.</span></span> <span data-ttu-id="d16a9-110">Ciertos métodos como el código auxiliar de IL o los métodos LCG no tienen metadatos asociados que se pueden recuperar mediante las API de IMetaDataImport.</span><span class="sxs-lookup"><span data-stu-id="d16a9-110">Certain methods like IL Stubs or LCG Methods do not have associated metadata that can be retrieved using the IMetaDataImport APIs.</span></span> <span data-ttu-id="d16a9-111">Estos métodos pueden ser detectados por los profileres a través de punteros de instrucción o escuchando a [ICorProfilerCallback::D ynamicmethodjitcompilationstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md).</span><span class="sxs-lookup"><span data-stu-id="d16a9-111">These methods can be encountered by profilers through instruction pointers or by listening to [ICorProfilerCallback::DynamicMethodJITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="d16a9-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d16a9-112">Requirements</span></span>

<span data-ttu-id="d16a9-113">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d16a9-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="d16a9-114">**Encabezado**: Corprof. idl, Corprof. h</span><span class="sxs-lookup"><span data-stu-id="d16a9-114">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="d16a9-115">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d16a9-115">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="d16a9-116">**.NET Framework versiones:** [! INCLUIR[net_current_v472plus](../../../../includes/net-current-v472plus.md)</span><span class="sxs-lookup"><span data-stu-id="d16a9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)</span></span>

## <a name="see-also"></a><span data-ttu-id="d16a9-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="d16a9-117">See also</span></span>

- [<span data-ttu-id="d16a9-118">Interfaz ICorProfilerInfo8</span><span class="sxs-lookup"><span data-stu-id="d16a9-118">ICorProfilerInfo8 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-interface.md)
