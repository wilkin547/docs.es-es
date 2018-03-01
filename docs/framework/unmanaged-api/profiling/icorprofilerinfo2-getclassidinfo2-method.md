---
title: "ICorProfilerInfo2::GetClassIDInfo2 (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerInfo2.GetClassIDInfo2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetClassIDInfo2
helpviewer_keywords:
- GetClassIDInfo2 method [.NET Framework profiling]
- ICorProfilerInfo2::GetClassIDInfo2 method [.NET Framework profiling]
ms.assetid: 0141d582-d066-4d49-8d1f-ae82129a1960
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e0348462cdbff14486b31e1878f06b7565b47182
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo2getclassidinfo2-method"></a><span data-ttu-id="ec62a-102">ICorProfilerInfo2::GetClassIDInfo2 (Método)</span><span class="sxs-lookup"><span data-stu-id="ec62a-102">ICorProfilerInfo2::GetClassIDInfo2 Method</span></span>
<span data-ttu-id="ec62a-103">Obtiene el módulo primario y los metadatos (token) para la definición de genérica abierta de la clase especificada, el `ClassID` de su clase primaria y el `ClassID` para cada argumento de tipo, si está presente, de la clase.</span><span class="sxs-lookup"><span data-stu-id="ec62a-103">Gets the parent module and metadata token for the open generic definition of the specified class, the `ClassID` of its parent class, and the `ClassID` for each type argument, if present, of the class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec62a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ec62a-104">Syntax</span></span>  
  
```  
HRESULT GetClassIDInfo2(  
    [in]  ClassID classId,  
    [out] ModuleID *pModuleId,  
    [out] mdTypeDef *pTypeDefToken,  
    [out] ClassID *pParentClassId,  
    [in]  ULONG32 cNumTypeArgs,  
    [out] ULONG32 *pcNumTypeArgs,  
    [out] ClassID typeArgs[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ec62a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ec62a-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="ec62a-106">[in] Identificador de la clase para la que se recuperará información.</span><span class="sxs-lookup"><span data-stu-id="ec62a-106">[in] The ID of the class for which information will be retrieved.</span></span>  
  
 `pModuleId`  
 <span data-ttu-id="ec62a-107">[out] Puntero al identificador del módulo primario para la definición de genérico abierto de la clase especificada.</span><span class="sxs-lookup"><span data-stu-id="ec62a-107">[out] Pointer to the ID of the parent module for the open generic definition of the specified class.</span></span>  
  
 `pTypeDefToken`  
 <span data-ttu-id="ec62a-108">[out] Puntero al token de metadatos para la definición de genérico abierto de la clase especificada.</span><span class="sxs-lookup"><span data-stu-id="ec62a-108">[out] Pointer to the metadata token for the open generic definition of the specified class.</span></span>  
  
 `pParentClassId`  
 <span data-ttu-id="ec62a-109">[out] Puntero al identificador de la clase primaria.</span><span class="sxs-lookup"><span data-stu-id="ec62a-109">[out] Pointer to the ID of the parent class.</span></span>  
  
 `cNumTypeArgs`  
 <span data-ttu-id="ec62a-110">[in] Tamaño de la matriz `typeArgs`.</span><span class="sxs-lookup"><span data-stu-id="ec62a-110">[in] The size of the `typeArgs` array.</span></span>  
  
 `pcNumTypeArgs`  
 <span data-ttu-id="ec62a-111">[out] Puntero al número total de elementos disponibles.</span><span class="sxs-lookup"><span data-stu-id="ec62a-111">[out] Pointer to the total number of available elements.</span></span>  
  
 `typeArgs`  
 <span data-ttu-id="ec62a-112">[out] Matriz de valores `ClassID`, cada uno de los cuales representa el identificador de un argumento de tipo de la clase.</span><span class="sxs-lookup"><span data-stu-id="ec62a-112">[out] An array of `ClassID` values, each of which represents the ID of a type argument of the class.</span></span> <span data-ttu-id="ec62a-113">Cuando el método vuelve, `typeArgs` contendrá algunos o todos los valores `ClassID` disponibles.</span><span class="sxs-lookup"><span data-stu-id="ec62a-113">When the method returns, `typeArgs` will contain some or all the available `ClassID` values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ec62a-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ec62a-114">Remarks</span></span>  
 <span data-ttu-id="ec62a-115">El `GetClassIDInfo2` método es similar a la [ICorProfilerInfo:: GetClassIDInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getclassidinfo-method.md) método, pero `GetClassIDInfo2` obtiene información adicional sobre un tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="ec62a-115">The `GetClassIDInfo2` method is similar to the [ICorProfilerInfo::GetClassIDInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getclassidinfo-method.md) method, but `GetClassIDInfo2` obtains additional information about a generic type.</span></span>  
  
 <span data-ttu-id="ec62a-116">El código del generador de perfiles puede llamar a [ICorProfilerInfo:: GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) para obtener un [metadatos](../../../../docs/framework/unmanaged-api/metadata/index.md) interfaz para un módulo determinado.</span><span class="sxs-lookup"><span data-stu-id="ec62a-116">The profiler code can call [ICorProfilerInfo::GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) to obtain a [metadata](../../../../docs/framework/unmanaged-api/metadata/index.md) interface for a given module.</span></span> <span data-ttu-id="ec62a-117">Después, el token de metadatos que se devuelve a la ubicación a la que `pTypeDefToken` hace referencia puede usarse para acceder a los metadatos de la clase.</span><span class="sxs-lookup"><span data-stu-id="ec62a-117">The metadata token that is returned to the location referenced by `pTypeDefToken` can then be used to access the metadata for the class.</span></span>  
  
 <span data-ttu-id="ec62a-118">Después de que `GetClassIDInfo2` vuelva, debe comprobar que el búfer `typeArgs` era lo suficientemente grande como para contener todos los valores `ClassID`.</span><span class="sxs-lookup"><span data-stu-id="ec62a-118">After `GetClassIDInfo2` returns, you must verify that the `typeArgs` buffer was large enough to contain all the `ClassID` values.</span></span> <span data-ttu-id="ec62a-119">Para ello, compare el valor al que `pcNumTypeArgs` apunta con el valor del parámetro `cNumTypeArgs`.</span><span class="sxs-lookup"><span data-stu-id="ec62a-119">To do this, compare the value that `pcNumTypeArgs` points to with the value of the `cNumTypeArgs` parameter.</span></span> <span data-ttu-id="ec62a-120">Si `pcNumTypeArgs` apunta un valor mayor que `cNumTypeArgs`, asigne un búfer `typeArgs` mayor, actualice `cNumTypeArgs` con el nuevo tamaño de mayores dimensiones y vuelva a llamar a `GetClassIDInfo2`.</span><span class="sxs-lookup"><span data-stu-id="ec62a-120">If `pcNumTypeArgs` points to a value that is larger than `cNumTypeArgs`, allocate a larger `typeArgs` buffer, update `cNumTypeArgs` with the new, larger size, and call `GetClassIDInfo2` again.</span></span>  
  
 <span data-ttu-id="ec62a-121">También tiene la opción de llamar primero a `GetClassIDInfo2` con un búfer `typeArgs` de longitud de cero para obtener el tamaño de búfer correcto.</span><span class="sxs-lookup"><span data-stu-id="ec62a-121">Alternatively, you can first call `GetClassIDInfo2` with a zero-length `typeArgs` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="ec62a-122">Después, puede establecer el tamaño del búfer `typeArgs` en el valor devuelto en `pcNumTypeArgs` y volver a llamar a `GetClassIDInfo2`.</span><span class="sxs-lookup"><span data-stu-id="ec62a-122">You can then set the `typeArgs` buffer size to the value returned in `pcNumTypeArgs` and call `GetClassIDInfo2` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec62a-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ec62a-123">Requirements</span></span>  
 <span data-ttu-id="ec62a-124">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec62a-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec62a-125">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ec62a-125">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ec62a-126">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ec62a-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ec62a-127">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec62a-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec62a-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="ec62a-128">See Also</span></span>  
 [<span data-ttu-id="ec62a-129">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ec62a-129">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="ec62a-130">ICorProfilerInfo2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ec62a-130">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)  
 [<span data-ttu-id="ec62a-131">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="ec62a-131">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="ec62a-132">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="ec62a-132">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
