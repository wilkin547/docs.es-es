---
description: 'Más información sobre: ICorProfilerInfo8:: GetDynamicFunctionInfo (método)'
title: ICorProfilerInfo8::GetDynamicFunctionInfo
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo8.GetDynamicFunctionInfo
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 48c8dbe20ccafb3fb23e9e289f728d5e3370613a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99646587"
---
# <a name="icorprofilerinfo8getdynamicfunctioninfo-method"></a><span data-ttu-id="a93f9-103">ICorProfilerInfo8:: GetDynamicFunctionInfo (método)</span><span class="sxs-lookup"><span data-stu-id="a93f9-103">ICorProfilerInfo8::GetDynamicFunctionInfo Method</span></span>

<span data-ttu-id="a93f9-104">Recupera información acerca de los métodos dinámicos.</span><span class="sxs-lookup"><span data-stu-id="a93f9-104">Retrieves information about dynamic methods.</span></span>

## <a name="syntax"></a><span data-ttu-id="a93f9-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a93f9-105">Syntax</span></span>

```cpp
HRESULT GetDynamicFunctionInfo( [in]  FunctionID              functionId,
                                [out] ModuleID                *moduleId,
                                [out] PCCOR_SIGNATURE         *ppvSig,
                                [out] ULONG                   *pbSig,
                                [in]  ULONG                   cchName,
                                [out] ULONG                   *pcchName,
                                [out] WCHAR                   wszName[]);
```

## <a name="parameters"></a><span data-ttu-id="a93f9-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a93f9-106">Parameters</span></span>

- `functionId`

  <span data-ttu-id="a93f9-107">\[in] identificador de la función para la que se va a recuperar información.</span><span class="sxs-lookup"><span data-stu-id="a93f9-107">\[in] The ID of the function for which to retrieve information.</span></span>

- `moduleId`

  <span data-ttu-id="a93f9-108">\[in] un puntero al módulo en el que se define la clase primaria de la función.</span><span class="sxs-lookup"><span data-stu-id="a93f9-108">\[in] A pointer to the module in which the function's parent class is defined.</span></span>

- `ppvSig`

  <span data-ttu-id="a93f9-109">\[out] un puntero a la firma de la función.</span><span class="sxs-lookup"><span data-stu-id="a93f9-109">\[out] A pointer to the signature for the function.</span></span>

- `pbSig`

  <span data-ttu-id="a93f9-110">\[out] un puntero al recuento de bytes para la firma de la función.</span><span class="sxs-lookup"><span data-stu-id="a93f9-110">\[out] A pointer to the count of bytes for the function signature.</span></span>

- `cchName`

  <span data-ttu-id="a93f9-111">\[en] tamaño máximo de la `wszName` matriz.</span><span class="sxs-lookup"><span data-stu-id="a93f9-111">\[in] The maximum size of the `wszName` array.</span></span>

- `pcchName`

  <span data-ttu-id="a93f9-112">\[out] número de caracteres de la `wszName` matriz.</span><span class="sxs-lookup"><span data-stu-id="a93f9-112">\[out] The number of characters in the `wszName` array.</span></span>

- `wszName`

  <span data-ttu-id="a93f9-113">\[out] una matriz de `WCHAR` que es el nombre de la función, si existe.</span><span class="sxs-lookup"><span data-stu-id="a93f9-113">\[out] An array of `WCHAR` which is the name of the function, if one exists.</span></span>

## <a name="remarks"></a><span data-ttu-id="a93f9-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a93f9-114">Remarks</span></span>

<span data-ttu-id="a93f9-115">Ciertos métodos como código auxiliar de IL o LCG no tienen metadatos asociados que se pueden recuperar mediante las API [IMetaDataImport](../metadata/imetadataimport-interface.md) y [IMetaDataImport2](../metadata/imetadataimport2-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="a93f9-115">Certain methods like IL Stubs or LCG do not have associated metadata that can be retrieved using the [IMetaDataImport](../metadata/imetadataimport-interface.md) and [IMetaDataImport2](../metadata/imetadataimport2-interface.md) APIs.</span></span> <span data-ttu-id="a93f9-116">Estos métodos pueden ser detectados por los profileres a través de punteros de instrucción o escuchando [ICorProfilerCallback8::D ynamicmethodjitcompilationstarted](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md).</span><span class="sxs-lookup"><span data-stu-id="a93f9-116">Such methods can be encountered by profilers through instruction pointers or by listening to [ICorProfilerCallback8::DynamicMethodJITCompilationStarted](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md).</span></span>

<span data-ttu-id="a93f9-117">Esta API se puede usar para recuperar información acerca de los métodos dinámicos, incluido un nombre descriptivo, si está disponible.</span><span class="sxs-lookup"><span data-stu-id="a93f9-117">This API can be used to retrieve information about dynamic methods, including a friendly name, if available.</span></span>

## <a name="requirements"></a><span data-ttu-id="a93f9-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a93f9-118">Requirements</span></span>

<span data-ttu-id="a93f9-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a93f9-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="a93f9-120">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a93f9-120">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="a93f9-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a93f9-121">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="a93f9-122">**.NET Framework versiones:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="a93f9-122">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="a93f9-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="a93f9-123">See also</span></span>

- [<span data-ttu-id="a93f9-124">Interface ICorProfilerInfo8</span><span class="sxs-lookup"><span data-stu-id="a93f9-124">ICorProfilerInfo8 Interface</span></span>](icorprofilerinfo8-interface.md)
