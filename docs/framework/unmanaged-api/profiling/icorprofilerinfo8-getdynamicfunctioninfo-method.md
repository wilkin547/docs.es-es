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
ms.openlocfilehash: 45a40d49cea2dd5f881fbd47cc2fb4bd96e8f9ff
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70243984"
---
# <a name="icorprofilerinfo8getdynamicfunctioninfo-method"></a><span data-ttu-id="b91a9-102">ICorProfilerInfo8:: GetDynamicFunctionInfo (método)</span><span class="sxs-lookup"><span data-stu-id="b91a9-102">ICorProfilerInfo8::GetDynamicFunctionInfo Method</span></span>

<span data-ttu-id="b91a9-103">Recupera información acerca de los métodos dinámicos.</span><span class="sxs-lookup"><span data-stu-id="b91a9-103">Retrieves information about dynamic methods.</span></span>

## <a name="syntax"></a><span data-ttu-id="b91a9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b91a9-104">Syntax</span></span>

```cpp
HRESULT GetDynamicFunctionInfo( [in]  FunctionID              functionId,
                                [out] ModuleID                *moduleId,
                                [out] PCCOR_SIGNATURE         *ppvSig,
                                [out] ULONG                   *pbSig,
                                [in]  ULONG                   cchName,
                                [out] ULONG                   *pcchName,
                                [out] WCHAR                   wszName[]);
```

#### <a name="parameters"></a><span data-ttu-id="b91a9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b91a9-105">Parameters</span></span>

`functionId` \
<span data-ttu-id="b91a9-106">de IDENTIFICADOR de la función para la que se va a recuperar información.</span><span class="sxs-lookup"><span data-stu-id="b91a9-106">[in] The ID of the function for which to retrieve information.</span></span>

`moduleId` \
<span data-ttu-id="b91a9-107">de Puntero al módulo en el que se define la clase primaria de la función.</span><span class="sxs-lookup"><span data-stu-id="b91a9-107">[in] A pointer to the module in which the function's parent class is defined.</span></span>

`ppvSig` \
<span data-ttu-id="b91a9-108">enuncia Puntero a la firma de la función.</span><span class="sxs-lookup"><span data-stu-id="b91a9-108">[out] A pointer to the signature for the function.</span></span>

`pbSig` \
<span data-ttu-id="b91a9-109">enuncia Puntero al recuento de bytes para la firma de la función.</span><span class="sxs-lookup"><span data-stu-id="b91a9-109">[out] A pointer to the count of bytes for the function signature.</span></span>

`cchName` \
<span data-ttu-id="b91a9-110">[in] Tamaño máximo de la matriz `wszName`.</span><span class="sxs-lookup"><span data-stu-id="b91a9-110">[in] The maximum size of the `wszName` array.</span></span>

`pcchName` \
<span data-ttu-id="b91a9-111">enuncia Número de caracteres de la `wszName` matriz.</span><span class="sxs-lookup"><span data-stu-id="b91a9-111">[out] The number of characters in the `wszName` array.</span></span>

`wszName` \
<span data-ttu-id="b91a9-112">enuncia Matriz de `WCHAR` que es el nombre de la función, si existe.</span><span class="sxs-lookup"><span data-stu-id="b91a9-112">[out] An array of `WCHAR` which is the name of the function, if one exists.</span></span>

## <a name="remarks"></a><span data-ttu-id="b91a9-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b91a9-113">Remarks</span></span>

<span data-ttu-id="b91a9-114">Ciertos métodos como código auxiliar de IL o LCG no tienen metadatos asociados que se pueden recuperar mediante las API [IMetaDataImport](../metadata/imetadataimport-interface.md) y [IMetaDataImport2](../metadata/imetadataimport2-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="b91a9-114">Certain methods like IL Stubs or LCG do not have associated metadata that can be retrieved using the [IMetaDataImport](../metadata/imetadataimport-interface.md) and [IMetaDataImport2](../metadata/imetadataimport2-interface.md) APIs.</span></span> <span data-ttu-id="b91a9-115">Estos métodos pueden ser detectados por los profileres a través de punteros de instrucción o escuchando [ICorProfilerCallback8::D ynamicmethodjitcompilationstarted](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md).</span><span class="sxs-lookup"><span data-stu-id="b91a9-115">Such methods can be encountered by profilers through instruction pointers or by listening to [ICorProfilerCallback8::DynamicMethodJITCompilationStarted](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md).</span></span>

<span data-ttu-id="b91a9-116">Esta API se puede usar para recuperar información acerca de los métodos dinámicos, incluido un nombre descriptivo, si está disponible.</span><span class="sxs-lookup"><span data-stu-id="b91a9-116">This API can be used to retrieve information about dynamic methods, including a friendly name, if available.</span></span>

## <a name="requirements"></a><span data-ttu-id="b91a9-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b91a9-117">Requirements</span></span>

<span data-ttu-id="b91a9-118">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b91a9-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="b91a9-119">**Encabezado**: Corprof. idl, Corprof. h</span><span class="sxs-lookup"><span data-stu-id="b91a9-119">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="b91a9-120">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b91a9-120">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="b91a9-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b91a9-121">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="b91a9-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="b91a9-122">See also</span></span>

- [<span data-ttu-id="b91a9-123">Interfaz ICorProfilerInfo8</span><span class="sxs-lookup"><span data-stu-id="b91a9-123">ICorProfilerInfo8 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-interface.md)
