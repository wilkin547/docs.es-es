---
description: 'Más información acerca de: ICorProfilerInfo2:: Getclassidinfo2 ((método)'
title: ICorProfilerInfo2::GetClassIDInfo2 (Método)
ms.date: 03/30/2017
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
ms.openlocfilehash: 44ef38b5f50da0f0aea045bd755614e00dae8c22
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760529"
---
# <a name="icorprofilerinfo2getclassidinfo2-method"></a><span data-ttu-id="0c5a0-103">ICorProfilerInfo2::GetClassIDInfo2 (Método)</span><span class="sxs-lookup"><span data-stu-id="0c5a0-103">ICorProfilerInfo2::GetClassIDInfo2 Method</span></span>

<span data-ttu-id="0c5a0-104">Obtiene el módulo primario y el token de metadatos para la definición genérica abierta de la clase especificada, el `ClassID` de su clase primaria y el `ClassID` para cada argumento de tipo, si está presente, de la clase.</span><span class="sxs-lookup"><span data-stu-id="0c5a0-104">Gets the parent module and metadata token for the open generic definition of the specified class, the `ClassID` of its parent class, and the `ClassID` for each type argument, if present, of the class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c5a0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0c5a0-105">Syntax</span></span>  
  
```cpp  
HRESULT GetClassIDInfo2(  
    [in]  ClassID classId,  
    [out] ModuleID *pModuleId,  
    [out] mdTypeDef *pTypeDefToken,  
    [out] ClassID *pParentClassId,  
    [in]  ULONG32 cNumTypeArgs,  
    [out] ULONG32 *pcNumTypeArgs,  
    [out] ClassID typeArgs[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c5a0-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0c5a0-106">Parameters</span></span>  

 `classId`  
 <span data-ttu-id="0c5a0-107">[in] Identificador de la clase para la que se recuperará información.</span><span class="sxs-lookup"><span data-stu-id="0c5a0-107">[in] The ID of the class for which information will be retrieved.</span></span>  
  
 `pModuleId`  
 <span data-ttu-id="0c5a0-108">enuncia Puntero al identificador del módulo primario para la definición genérica abierta de la clase especificada.</span><span class="sxs-lookup"><span data-stu-id="0c5a0-108">[out] Pointer to the ID of the parent module for the open generic definition of the specified class.</span></span>  
  
 `pTypeDefToken`  
 <span data-ttu-id="0c5a0-109">enuncia Puntero al símbolo (token) de metadatos para la definición genérica abierta de la clase especificada.</span><span class="sxs-lookup"><span data-stu-id="0c5a0-109">[out] Pointer to the metadata token for the open generic definition of the specified class.</span></span>  
  
 `pParentClassId`  
 <span data-ttu-id="0c5a0-110">[out] Puntero al identificador de la clase primaria.</span><span class="sxs-lookup"><span data-stu-id="0c5a0-110">[out] Pointer to the ID of the parent class.</span></span>  
  
 `cNumTypeArgs`  
 <span data-ttu-id="0c5a0-111">[in] Tamaño de la matriz `typeArgs`.</span><span class="sxs-lookup"><span data-stu-id="0c5a0-111">[in] The size of the `typeArgs` array.</span></span>  
  
 `pcNumTypeArgs`  
 <span data-ttu-id="0c5a0-112">[out] Puntero al número total de elementos disponibles.</span><span class="sxs-lookup"><span data-stu-id="0c5a0-112">[out] Pointer to the total number of available elements.</span></span>  
  
 `typeArgs`  
 <span data-ttu-id="0c5a0-113">[out] Matriz de valores `ClassID`, cada uno de los cuales representa el identificador de un argumento de tipo de la clase.</span><span class="sxs-lookup"><span data-stu-id="0c5a0-113">[out] An array of `ClassID` values, each of which represents the ID of a type argument of the class.</span></span> <span data-ttu-id="0c5a0-114">Cuando el método vuelve, `typeArgs` contendrá algunos o todos los valores `ClassID` disponibles.</span><span class="sxs-lookup"><span data-stu-id="0c5a0-114">When the method returns, `typeArgs` will contain some or all the available `ClassID` values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0c5a0-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0c5a0-115">Remarks</span></span>  

 <span data-ttu-id="0c5a0-116">El `GetClassIDInfo2` método es similar al método [ICorProfilerInfo:: GetClassIDInfo (](icorprofilerinfo-getclassidinfo-method.md) , pero `GetClassIDInfo2` obtiene información adicional sobre un tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="0c5a0-116">The `GetClassIDInfo2` method is similar to the [ICorProfilerInfo::GetClassIDInfo](icorprofilerinfo-getclassidinfo-method.md) method, but `GetClassIDInfo2` obtains additional information about a generic type.</span></span>  
  
 <span data-ttu-id="0c5a0-117">El código del generador de perfiles puede llamar a [ICorProfilerInfo:: GetModuleMetaData (](icorprofilerinfo-getmodulemetadata-method.md) para obtener una interfaz de [metadatos](../metadata/index.md) para un módulo determinado.</span><span class="sxs-lookup"><span data-stu-id="0c5a0-117">The profiler code can call [ICorProfilerInfo::GetModuleMetaData](icorprofilerinfo-getmodulemetadata-method.md) to obtain a [metadata](../metadata/index.md) interface for a given module.</span></span> <span data-ttu-id="0c5a0-118">Después, el token de metadatos que se devuelve a la ubicación a la que `pTypeDefToken` hace referencia puede usarse para acceder a los metadatos de la clase.</span><span class="sxs-lookup"><span data-stu-id="0c5a0-118">The metadata token that is returned to the location referenced by `pTypeDefToken` can then be used to access the metadata for the class.</span></span>  
  
 <span data-ttu-id="0c5a0-119">Después de que `GetClassIDInfo2` vuelva, debe comprobar que el búfer `typeArgs` era lo suficientemente grande como para contener todos los valores `ClassID`.</span><span class="sxs-lookup"><span data-stu-id="0c5a0-119">After `GetClassIDInfo2` returns, you must verify that the `typeArgs` buffer was large enough to contain all the `ClassID` values.</span></span> <span data-ttu-id="0c5a0-120">Para ello, compare el valor al que `pcNumTypeArgs` apunta con el valor del parámetro `cNumTypeArgs`.</span><span class="sxs-lookup"><span data-stu-id="0c5a0-120">To do this, compare the value that `pcNumTypeArgs` points to with the value of the `cNumTypeArgs` parameter.</span></span> <span data-ttu-id="0c5a0-121">Si `pcNumTypeArgs` apunta un valor mayor que `cNumTypeArgs`, asigne un búfer `typeArgs` mayor, actualice `cNumTypeArgs` con el nuevo tamaño de mayores dimensiones y vuelva a llamar a `GetClassIDInfo2`.</span><span class="sxs-lookup"><span data-stu-id="0c5a0-121">If `pcNumTypeArgs` points to a value that is larger than `cNumTypeArgs`, allocate a larger `typeArgs` buffer, update `cNumTypeArgs` with the new, larger size, and call `GetClassIDInfo2` again.</span></span>  
  
 <span data-ttu-id="0c5a0-122">También tiene la opción de llamar primero a `GetClassIDInfo2` con un búfer `typeArgs` de longitud de cero para obtener el tamaño de búfer correcto.</span><span class="sxs-lookup"><span data-stu-id="0c5a0-122">Alternatively, you can first call `GetClassIDInfo2` with a zero-length `typeArgs` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="0c5a0-123">Después, puede establecer el tamaño del búfer `typeArgs` en el valor devuelto en `pcNumTypeArgs` y volver a llamar a `GetClassIDInfo2`.</span><span class="sxs-lookup"><span data-stu-id="0c5a0-123">You can then set the `typeArgs` buffer size to the value returned in `pcNumTypeArgs` and call `GetClassIDInfo2` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c5a0-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0c5a0-124">Requirements</span></span>  

 <span data-ttu-id="0c5a0-125">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c5a0-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c5a0-126">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0c5a0-126">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0c5a0-127">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0c5a0-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0c5a0-128">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c5a0-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c5a0-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="0c5a0-129">See also</span></span>

- [<span data-ttu-id="0c5a0-130">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0c5a0-130">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="0c5a0-131">ICorProfilerInfo2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0c5a0-131">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
- [<span data-ttu-id="0c5a0-132">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="0c5a0-132">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="0c5a0-133">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="0c5a0-133">Profiling</span></span>](index.md)
