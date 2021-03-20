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
ms.openlocfilehash: b38bd7a4f440edba0a7156176f223ba38c9807cf
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2021
ms.locfileid: "104759122"
---
# <a name="icorprofilerinfo8getdynamicfunctioninfo-method"></a><span data-ttu-id="52d27-103">ICorProfilerInfo8:: GetDynamicFunctionInfo (método)</span><span class="sxs-lookup"><span data-stu-id="52d27-103">ICorProfilerInfo8::GetDynamicFunctionInfo Method</span></span>

<span data-ttu-id="52d27-104">Recupera información acerca de los métodos dinámicos.</span><span class="sxs-lookup"><span data-stu-id="52d27-104">Retrieves information about dynamic methods.</span></span>

## <a name="syntax"></a><span data-ttu-id="52d27-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="52d27-105">Syntax</span></span>

```cpp
HRESULT GetDynamicFunctionInfo( [in]  FunctionID              functionId,
                                [out] ModuleID                *moduleId,
                                [out] PCCOR_SIGNATURE         *ppvSig,
                                [out] ULONG                   *pbSig,
                                [in]  ULONG                   cchName,
                                [out] ULONG                   *pcchName,
                                [out] WCHAR                   wszName[]);
```

## <a name="parameters"></a><span data-ttu-id="52d27-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="52d27-106">Parameters</span></span>

<span data-ttu-id="52d27-107">`functionId` de IDENTIFICADOR de la función para la que se va a recuperar información.</span><span class="sxs-lookup"><span data-stu-id="52d27-107">`functionId` [in] The ID of the function for which to retrieve information.</span></span>

<span data-ttu-id="52d27-108">`moduleId` de Puntero al módulo en el que se define la clase primaria de la función.</span><span class="sxs-lookup"><span data-stu-id="52d27-108">`moduleId` [in] A pointer to the module in which the function's parent class is defined.</span></span>

<span data-ttu-id="52d27-109">`ppvSig` enuncia Puntero a la firma de la función.</span><span class="sxs-lookup"><span data-stu-id="52d27-109">`ppvSig` [out] A pointer to the signature for the function.</span></span>

<span data-ttu-id="52d27-110">`pbSig` enuncia Puntero al recuento de bytes para la firma de la función.</span><span class="sxs-lookup"><span data-stu-id="52d27-110">`pbSig` [out] A pointer to the count of bytes for the function signature.</span></span>

<span data-ttu-id="52d27-111">`cchName` de Tamaño máximo de la `wszName` matriz.</span><span class="sxs-lookup"><span data-stu-id="52d27-111">`cchName` [in] The maximum size of the `wszName` array.</span></span>

<span data-ttu-id="52d27-112">`pcchName` enuncia Número de caracteres de la `wszName` matriz.</span><span class="sxs-lookup"><span data-stu-id="52d27-112">`pcchName` [out] The number of characters in the `wszName` array.</span></span>

<span data-ttu-id="52d27-113">`wszName` enuncia Matriz de `WCHAR` que es el nombre de la función, si existe.</span><span class="sxs-lookup"><span data-stu-id="52d27-113">`wszName` [out] An array of `WCHAR` which is the name of the function, if one exists.</span></span>

## <a name="remarks"></a><span data-ttu-id="52d27-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="52d27-114">Remarks</span></span>

<span data-ttu-id="52d27-115">Ciertos métodos como código auxiliar de IL o LCG no tienen metadatos asociados que se pueden recuperar mediante las API [IMetaDataImport](../metadata/imetadataimport-interface.md) y [IMetaDataImport2](../metadata/imetadataimport2-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="52d27-115">Certain methods like IL Stubs or LCG do not have associated metadata that can be retrieved using the [IMetaDataImport](../metadata/imetadataimport-interface.md) and [IMetaDataImport2](../metadata/imetadataimport2-interface.md) APIs.</span></span> <span data-ttu-id="52d27-116">Estos métodos pueden ser detectados por los profileres a través de punteros de instrucción o escuchando [ICorProfilerCallback8::D ynamicmethodjitcompilationstarted](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md).</span><span class="sxs-lookup"><span data-stu-id="52d27-116">Such methods can be encountered by profilers through instruction pointers or by listening to [ICorProfilerCallback8::DynamicMethodJITCompilationStarted](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md).</span></span>

<span data-ttu-id="52d27-117">Esta API se puede usar para recuperar información acerca de los métodos dinámicos, incluido un nombre descriptivo, si está disponible.</span><span class="sxs-lookup"><span data-stu-id="52d27-117">This API can be used to retrieve information about dynamic methods, including a friendly name, if available.</span></span>

## <a name="requirements"></a><span data-ttu-id="52d27-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="52d27-118">Requirements</span></span>

<span data-ttu-id="52d27-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52d27-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="52d27-120">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="52d27-120">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="52d27-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="52d27-121">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="52d27-122">**.NET Framework versiones:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="52d27-122">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="52d27-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="52d27-123">See also</span></span>

- [<span data-ttu-id="52d27-124">Interface ICorProfilerInfo8</span><span class="sxs-lookup"><span data-stu-id="52d27-124">ICorProfilerInfo8 Interface</span></span>](icorprofilerinfo8-interface.md)
