---
title: "ICorProfilerInfo2::GetFunctionInfo2 (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetFunctionInfo2
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetFunctionInfo2
helpviewer_keywords:
- GetFunctionInfo2 method [.NET Framework profiling]
- ICorProfilerInfo2::GetFunctionInfo2 method [.NET Framework profiling]
ms.assetid: 0aa60f24-8bbd-4c83-83c5-86ad191b1d82
topic_type: apiref
caps.latest.revision: "18"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e7a48f109c22ae768e636a7f6b57e4e10ac76012
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo2getfunctioninfo2-method"></a><span data-ttu-id="ca845-102">ICorProfilerInfo2::GetFunctionInfo2 (Método)</span><span class="sxs-lookup"><span data-stu-id="ca845-102">ICorProfilerInfo2::GetFunctionInfo2 Method</span></span>
<span data-ttu-id="ca845-103">Obtiene la clase primaria, el token de metadatos y el `ClassID` de cada argumento de tipo, si está presente, de una función.</span><span class="sxs-lookup"><span data-stu-id="ca845-103">Gets the parent class, the metadata token, and the `ClassID` of each type argument, if present, of a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca845-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ca845-104">Syntax</span></span>  
  
```  
HRESULT GetFunctionInfo2(  
    [in]  FunctionID funcId,  
    [in]  COR_PRF_FRAME_INFO frameInfo,  
    [out] ClassID *pClassId,  
    [out] ModuleID *pModuleId,  
    [out] mdToken *pToken,  
    [in]  ULONG32 cTypeArgs,  
    [out] ULONG32 *pcTypeArgs,  
    [out] ClassID typeArgs[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ca845-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ca845-105">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="ca845-106">[in] Identificador de la función para la que se va a obtener la clase primaria y otra información.</span><span class="sxs-lookup"><span data-stu-id="ca845-106">[in] The ID of the function for which to get the parent class and other information.</span></span>  
  
 `frameInfo`  
 <span data-ttu-id="ca845-107">[in] Valor `COR_PRF_FRAME_INFO` que apunta a información acerca de un marco de pila.</span><span class="sxs-lookup"><span data-stu-id="ca845-107">[in] A `COR_PRF_FRAME_INFO` value that points to information about a stack frame.</span></span>  
  
 `pClassId`  
 <span data-ttu-id="ca845-108">[out] Puntero a la clase primaria de la función.</span><span class="sxs-lookup"><span data-stu-id="ca845-108">[out] A pointer to the parent class of the function.</span></span>  
  
 `pModuleId`  
 <span data-ttu-id="ca845-109">[out] Puntero al módulo en el que se define la clase primaria de la función.</span><span class="sxs-lookup"><span data-stu-id="ca845-109">[out] A pointer to the module in which the function's parent class is defined.</span></span>  
  
 `pToken`  
 <span data-ttu-id="ca845-110">[out] Puntero al token de metadatos para la función.</span><span class="sxs-lookup"><span data-stu-id="ca845-110">[out] A pointer to the metadata token for the function.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="ca845-111">[in] Tamaño de la matriz `typeArgs`.</span><span class="sxs-lookup"><span data-stu-id="ca845-111">[in] The size of the `typeArgs` array.</span></span>  
  
 `pcTypeArgs`  
 <span data-ttu-id="ca845-112">[out] Puntero al número total de valores `ClassID`.</span><span class="sxs-lookup"><span data-stu-id="ca845-112">[out] A pointer to the total number of `ClassID` values.</span></span>  
  
 `typeArgs`  
 <span data-ttu-id="ca845-113">[out] Matriz de valores `ClassID`, cada uno de los cuales es el identificador de un argumento de tipo de la función.</span><span class="sxs-lookup"><span data-stu-id="ca845-113">[out] An array of `ClassID` values, each of which is the ID of a type argument of the function.</span></span> <span data-ttu-id="ca845-114">Cuando el método vuelve, `typeArgs` contendrá algunos o todos los valores `ClassID`.</span><span class="sxs-lookup"><span data-stu-id="ca845-114">When the method returns, `typeArgs` will contain some or all of the `ClassID` values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ca845-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ca845-115">Remarks</span></span>  
 <span data-ttu-id="ca845-116">El código del generador de perfiles puede llamar a [ICorProfilerInfo:: GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) para obtener un [metadatos](../../../../docs/framework/unmanaged-api/metadata/index.md) interfaz para un módulo determinado.</span><span class="sxs-lookup"><span data-stu-id="ca845-116">The profiler code can call [ICorProfilerInfo::GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) to obtain a [metadata](../../../../docs/framework/unmanaged-api/metadata/index.md) interface for a given module.</span></span> <span data-ttu-id="ca845-117">Después, el token de metadatos que se devuelve a la ubicación a la que `pToken` hace referencia puede usarse para acceder a los metadatos de la función.</span><span class="sxs-lookup"><span data-stu-id="ca845-117">The metadata token that is returned to the location referenced by `pToken` can then be used to access the metadata for the function.</span></span>  
  
 <span data-ttu-id="ca845-118">El identificador de clase y los argumentos de tipo que se devuelven mediante los parámetros `pClassId` y `typeArgs` dependen del valor que se pasa en el parámetro `frameInfo`, como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="ca845-118">The class ID and type arguments that are returned through the `pClassId` and `typeArgs` parameters depend on the value that is passed in the `frameInfo` parameter, as shown in the following table.</span></span>  
  
|<span data-ttu-id="ca845-119">Valor del parámetro `frameInfo`</span><span class="sxs-lookup"><span data-stu-id="ca845-119">Value of the `frameInfo` parameter</span></span>|<span data-ttu-id="ca845-120">Resultado</span><span class="sxs-lookup"><span data-stu-id="ca845-120">Result</span></span>|  
|----------------------------------------|------------|  
|<span data-ttu-id="ca845-121">Un valor `COR_PRF_FRAME_INFO` que se obtiene de una devolución de llamada `FunctionEnter2`</span><span class="sxs-lookup"><span data-stu-id="ca845-121">A `COR_PRF_FRAME_INFO` value that was obtained from a `FunctionEnter2` callback</span></span>|<span data-ttu-id="ca845-122">El `ClassID` que se devuelve en la ubicación a la que `pClassId` hace referencia y todos los argumentos de tipo que se devuelven en la matriz `typeArgs` serán exactos.</span><span class="sxs-lookup"><span data-stu-id="ca845-122">The `ClassID`, returned in the location referenced by `pClassId`, and all type arguments, returned in the `typeArgs` array, will be exact.</span></span>|  
|<span data-ttu-id="ca845-123">Un valor `COR_PRF_FRAME_INFO` que se obtiene de un origen que no es una devolución de llamada `FunctionEnter2`</span><span class="sxs-lookup"><span data-stu-id="ca845-123">A `COR_PRF_FRAME_INFO` that was obtained from a source other than a `FunctionEnter2` callback</span></span>|<span data-ttu-id="ca845-124">El `ClassID` y los argumentos de tipo no se puede determinar exactamente.</span><span class="sxs-lookup"><span data-stu-id="ca845-124">The exact `ClassID` and type arguments cannot be determined.</span></span> <span data-ttu-id="ca845-125">Es decir, `ClassID` podría ser NULL y algunos argumentos de tipo podrían volver como <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="ca845-125">That is, the `ClassID` might be null and some type arguments might come back as <xref:System.Object>.</span></span>|  
|<span data-ttu-id="ca845-126">Cero</span><span class="sxs-lookup"><span data-stu-id="ca845-126">Zero</span></span>|<span data-ttu-id="ca845-127">El `ClassID` y los argumentos de tipo no se puede determinar exactamente.</span><span class="sxs-lookup"><span data-stu-id="ca845-127">The exact `ClassID` and type arguments cannot be determined.</span></span> <span data-ttu-id="ca845-128">Es decir, `ClassID` podría ser NULL y algunos argumentos de tipo podrían volver como <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="ca845-128">That is, the `ClassID` might be null and some type arguments might come back as <xref:System.Object>.</span></span>|  
  
 <span data-ttu-id="ca845-129">Después de que `GetFunctionInfo2` vuelva, debe comprobar que el búfer `typeArgs` era lo suficientemente grande como para contener todos los valores `ClassID`.</span><span class="sxs-lookup"><span data-stu-id="ca845-129">After `GetFunctionInfo2` returns, you must verify that the `typeArgs` buffer was large enough to contain all the `ClassID` values.</span></span> <span data-ttu-id="ca845-130">Para ello, compare el valor al que `pcTypeArgs` apunta con el valor del parámetro `cTypeArgs`.</span><span class="sxs-lookup"><span data-stu-id="ca845-130">To do this, compare the value that `pcTypeArgs` points to with the value of the `cTypeArgs` parameter.</span></span> <span data-ttu-id="ca845-131">Si `pcTypeArgs` apunta a un valor mayor que `cTypeArgs` dividido por el tamaño de un valor `ClassID`, asigne un búfer `pcTypeArgs` mayor, actualice `cTypeArgs` con el nuevo tamaño y vuelva a llamar a `GetFunctionInfo2`.</span><span class="sxs-lookup"><span data-stu-id="ca845-131">If `pcTypeArgs` points to a value that is larger than `cTypeArgs` divided by the size of a `ClassID` value, allocate a larger `pcTypeArgs` buffer, update `cTypeArgs` with the new, larger size, and call `GetFunctionInfo2` again.</span></span>  
  
 <span data-ttu-id="ca845-132">También puede llamar primero a `GetFunctionInfo2` con un búfer `pcTypeArgs` de longitud de cero para obtener el tamaño de búfer correcto.</span><span class="sxs-lookup"><span data-stu-id="ca845-132">Alternatively, you can first call `GetFunctionInfo2` with a zero-length `pcTypeArgs` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="ca845-133">Después, establezca el tamaño del búfer en el valor devuelto en `pcTypeArgs`, dividido por el tamaño de un valor `ClassID` y vuelva a llamar a `GetFunctionInfo2`.</span><span class="sxs-lookup"><span data-stu-id="ca845-133">You can then set the buffer size to the value returned in `pcTypeArgs` divided by the size of a `ClassID` value, and call `GetFunctionInfo2` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca845-134">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ca845-134">Requirements</span></span>  
 <span data-ttu-id="ca845-135">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca845-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca845-136">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ca845-136">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ca845-137">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ca845-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ca845-138">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca845-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca845-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="ca845-139">See Also</span></span>  
 [<span data-ttu-id="ca845-140">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ca845-140">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="ca845-141">ICorProfilerInfo2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ca845-141">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)  
 [<span data-ttu-id="ca845-142">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="ca845-142">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="ca845-143">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="ca845-143">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
