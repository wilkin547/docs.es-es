---
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
ms.openlocfilehash: 9b5059d9e4bf9b79dc67664c7a7971041d1cf35b
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76861689"
---
# <a name="icorprofilerinfo8getdynamicfunctioninfo-method"></a><span data-ttu-id="5df90-102">ICorProfilerInfo8:: GetDynamicFunctionInfo (método)</span><span class="sxs-lookup"><span data-stu-id="5df90-102">ICorProfilerInfo8::GetDynamicFunctionInfo Method</span></span>

<span data-ttu-id="5df90-103">Recupera información acerca de los métodos dinámicos.</span><span class="sxs-lookup"><span data-stu-id="5df90-103">Retrieves information about dynamic methods.</span></span>

## <a name="syntax"></a><span data-ttu-id="5df90-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5df90-104">Syntax</span></span>

```cpp
HRESULT GetDynamicFunctionInfo( [in]  FunctionID              functionId,
                                [out] ModuleID                *moduleId,
                                [out] PCCOR_SIGNATURE         *ppvSig,
                                [out] ULONG                   *pbSig,
                                [in]  ULONG                   cchName,
                                [out] ULONG                   *pcchName,
                                [out] WCHAR                   wszName[]);
```

## <a name="parameters"></a><span data-ttu-id="5df90-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="5df90-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="5df90-106">\[en] identificador de la función para la que se va a recuperar información.</span><span class="sxs-lookup"><span data-stu-id="5df90-106">\[in] The ID of the function for which to retrieve information.</span></span>

- `moduleId`

  <span data-ttu-id="5df90-107">\[en] un puntero al módulo en el que se define la clase primaria de la función.</span><span class="sxs-lookup"><span data-stu-id="5df90-107">\[in] A pointer to the module in which the function's parent class is defined.</span></span>

- `ppvSig`

  <span data-ttu-id="5df90-108">\[out] un puntero a la firma de la función.</span><span class="sxs-lookup"><span data-stu-id="5df90-108">\[out] A pointer to the signature for the function.</span></span>

- `pbSig`

  <span data-ttu-id="5df90-109">\[out] un puntero al recuento de bytes para la firma de la función.</span><span class="sxs-lookup"><span data-stu-id="5df90-109">\[out] A pointer to the count of bytes for the function signature.</span></span>

- `cchName`

  <span data-ttu-id="5df90-110">\[en] el tamaño máximo de la matriz de `wszName`.</span><span class="sxs-lookup"><span data-stu-id="5df90-110">\[in] The maximum size of the `wszName` array.</span></span>

- `pcchName`

  <span data-ttu-id="5df90-111">\[out] número de caracteres de la matriz de `wszName`.</span><span class="sxs-lookup"><span data-stu-id="5df90-111">\[out] The number of characters in the `wszName` array.</span></span>

- `wszName`

  <span data-ttu-id="5df90-112">\[out] una matriz de `WCHAR` que es el nombre de la función, si existe.</span><span class="sxs-lookup"><span data-stu-id="5df90-112">\[out] An array of `WCHAR` which is the name of the function, if one exists.</span></span>

## <a name="remarks"></a><span data-ttu-id="5df90-113">Notas</span><span class="sxs-lookup"><span data-stu-id="5df90-113">Remarks</span></span>

<span data-ttu-id="5df90-114">Ciertos métodos como código auxiliar de IL o LCG no tienen metadatos asociados que se pueden recuperar mediante las API [IMetaDataImport](../metadata/imetadataimport-interface.md) y [IMetaDataImport2](../metadata/imetadataimport2-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="5df90-114">Certain methods like IL Stubs or LCG do not have associated metadata that can be retrieved using the [IMetaDataImport](../metadata/imetadataimport-interface.md) and [IMetaDataImport2](../metadata/imetadataimport2-interface.md) APIs.</span></span> <span data-ttu-id="5df90-115">Estos métodos pueden ser detectados por los profileres a través de punteros de instrucción o escuchando [ICorProfilerCallback8::D ynamicmethodjitcompilationstarted](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md).</span><span class="sxs-lookup"><span data-stu-id="5df90-115">Such methods can be encountered by profilers through instruction pointers or by listening to [ICorProfilerCallback8::DynamicMethodJITCompilationStarted](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md).</span></span>

<span data-ttu-id="5df90-116">Esta API se puede usar para recuperar información acerca de los métodos dinámicos, incluido un nombre descriptivo, si está disponible.</span><span class="sxs-lookup"><span data-stu-id="5df90-116">This API can be used to retrieve information about dynamic methods, including a friendly name, if available.</span></span>

## <a name="requirements"></a><span data-ttu-id="5df90-117">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="5df90-117">Requirements</span></span>

<span data-ttu-id="5df90-118">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5df90-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="5df90-119">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5df90-119">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="5df90-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5df90-120">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="5df90-121">**.NET Framework versiones:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="5df90-121">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="5df90-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="5df90-122">See also</span></span>

- [<span data-ttu-id="5df90-123">Interfaz ICorProfilerInfo8</span><span class="sxs-lookup"><span data-stu-id="5df90-123">ICorProfilerInfo8 Interface</span></span>](icorprofilerinfo8-interface.md)
