---
description: 'Más información acerca de: ICorProfilerInfo2:: GetFunctionFromTokenAndTypeArgs ((método)'
title: ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetFunctionFromTokenAndTypeArgs
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs
helpviewer_keywords:
- ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs method [.NET Framework profiling]
- GetFunctionFromTokenAndTypeArgs method [.NET Framework profiling]
ms.assetid: ce8f6aa6-4ebf-4a86-b429-4bbc8af41a8f
topic_type:
- apiref
ms.openlocfilehash: 4b4bb8631a5f33c939666af68226b19d2e4d666d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799043"
---
# <a name="icorprofilerinfo2getfunctionfromtokenandtypeargs-method"></a><span data-ttu-id="aad66-103">ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs (Método)</span><span class="sxs-lookup"><span data-stu-id="aad66-103">ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs Method</span></span>

<span data-ttu-id="aad66-104">Obtiene el `FunctionID` de una función mediante el token de metadatos especificado, la clase contenedora y `ClassID` los valores de cualquier argumento de tipo.</span><span class="sxs-lookup"><span data-stu-id="aad66-104">Gets the `FunctionID` of a function by using the specified metadata token, containing class, and `ClassID` values of any type arguments.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aad66-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aad66-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdMethodDef funcDef,  
    [in] ClassID classId,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] FunctionID* pFunctionID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aad66-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="aad66-106">Parameters</span></span>  

 `moduleID`  
 <span data-ttu-id="aad66-107">de IDENTIFICADOR del módulo en el que reside la función.</span><span class="sxs-lookup"><span data-stu-id="aad66-107">[in] The ID of the module in which the function resides.</span></span>  
  
 `funcDef`  
 <span data-ttu-id="aad66-108">de `mdMethodDef` Token de metadatos que hace referencia a la función.</span><span class="sxs-lookup"><span data-stu-id="aad66-108">[in] An `mdMethodDef` metadata token that references the function.</span></span>  
  
 `classId`  
 <span data-ttu-id="aad66-109">de IDENTIFICADOR de la clase contenedora de la función.</span><span class="sxs-lookup"><span data-stu-id="aad66-109">[in] The ID of the function's containing class.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="aad66-110">de El número de parámetros de tipo para la función especificada.</span><span class="sxs-lookup"><span data-stu-id="aad66-110">[in] The number of type parameters for the given function.</span></span> <span data-ttu-id="aad66-111">Este valor debe ser cero para las funciones no genéricas.</span><span class="sxs-lookup"><span data-stu-id="aad66-111">This value must be zero for non-generic functions.</span></span>  
  
 `typeArgs`  
 <span data-ttu-id="aad66-112">de Una matriz de `ClassID` valores, cada uno de los cuales es un argumento de la función.</span><span class="sxs-lookup"><span data-stu-id="aad66-112">[in] An array of `ClassID` values, each of which is an argument of the function.</span></span> <span data-ttu-id="aad66-113">El valor de `typeArgs` puede ser null si `cTypeArgs` está establecido en cero.</span><span class="sxs-lookup"><span data-stu-id="aad66-113">The value of `typeArgs` can be NULL if `cTypeArgs` is set to zero.</span></span>  
  
 `pFunctionID`  
 <span data-ttu-id="aad66-114">enuncia Puntero al `FunctionID` de la función especificada.</span><span class="sxs-lookup"><span data-stu-id="aad66-114">[out] A pointer to the `FunctionID` of the specified function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aad66-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="aad66-115">Remarks</span></span>  

 <span data-ttu-id="aad66-116">La llamada al `GetFunctionFromTokenAndTypeArgs` método con `mdMethodRef` metadatos en lugar de un `mdMethodDef` token de metadatos puede tener resultados imprevisibles.</span><span class="sxs-lookup"><span data-stu-id="aad66-116">Calling the `GetFunctionFromTokenAndTypeArgs` method with an `mdMethodRef` metadata instead of an `mdMethodDef` metadata token can have unpredictable results.</span></span> <span data-ttu-id="aad66-117">Los llamadores deben resolver el `mdMethodRef` en un `mdMethodDef` al pasarlo.</span><span class="sxs-lookup"><span data-stu-id="aad66-117">Callers should resolve the `mdMethodRef` to an `mdMethodDef` when passing it.</span></span>  
  
 <span data-ttu-id="aad66-118">Si la función no está cargada todavía, la llamada `GetFunctionFromTokenAndTypeArgs` a provocará que se produzca la carga, lo que es una operación peligrosa en muchos contextos.</span><span class="sxs-lookup"><span data-stu-id="aad66-118">If the function is not already loaded, calling `GetFunctionFromTokenAndTypeArgs` will cause loading to occur, which is a dangerous operation in many contexts.</span></span> <span data-ttu-id="aad66-119">Por ejemplo, llamar a este método durante la carga de módulos o tipos podría provocar un bucle infinito, ya que el tiempo de ejecución intenta cargar elementos de forma circular.</span><span class="sxs-lookup"><span data-stu-id="aad66-119">For example, calling this method during loading of modules or types could lead to an infinite loop as the runtime attempts to circularly load things.</span></span>  
  
 <span data-ttu-id="aad66-120">En general, `GetFunctionFromTokenAndTypeArgs` no se recomienda el uso de.</span><span class="sxs-lookup"><span data-stu-id="aad66-120">In general, use of `GetFunctionFromTokenAndTypeArgs` is discouraged.</span></span> <span data-ttu-id="aad66-121">Si los perfiles están interesados en eventos para una función determinada, deben almacenar `ModuleID` y `mdMethodDef` de esa función, y usar [ICorProfilerInfo2:: getfunctioninfo2 (](icorprofilerinfo2-getfunctioninfo2-method.md) para comprobar si un determinado `FunctionID` es el de la función deseada.</span><span class="sxs-lookup"><span data-stu-id="aad66-121">If profilers are interested in events for a particular function, they should store the `ModuleID` and `mdMethodDef` of that function, and use [ICorProfilerInfo2::GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) to check whether a given `FunctionID` is that of the desired function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aad66-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="aad66-122">Requirements</span></span>  

 <span data-ttu-id="aad66-123">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aad66-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aad66-124">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="aad66-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="aad66-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aad66-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aad66-126">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aad66-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aad66-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="aad66-127">See also</span></span>

- [<span data-ttu-id="aad66-128">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="aad66-128">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="aad66-129">ICorProfilerInfo2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="aad66-129">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
