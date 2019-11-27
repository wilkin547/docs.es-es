---
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
ms.openlocfilehash: 41021a524142afe34727584265aee578e31a64b3
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74433215"
---
# <a name="icorprofilerinfo2getfunctionfromtokenandtypeargs-method"></a><span data-ttu-id="fce18-102">ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs (Método)</span><span class="sxs-lookup"><span data-stu-id="fce18-102">ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs Method</span></span>
<span data-ttu-id="fce18-103">Obtiene el `FunctionID` de una función mediante el token de metadatos especificado, la clase contenedora y los valores de `ClassID` de cualquier argumento de tipo.</span><span class="sxs-lookup"><span data-stu-id="fce18-103">Gets the `FunctionID` of a function by using the specified metadata token, containing class, and `ClassID` values of any type arguments.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fce18-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fce18-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdMethodDef funcDef,  
    [in] ClassID classId,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] FunctionID* pFunctionID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fce18-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fce18-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="fce18-106">de IDENTIFICADOR del módulo en el que reside la función.</span><span class="sxs-lookup"><span data-stu-id="fce18-106">[in] The ID of the module in which the function resides.</span></span>  
  
 `funcDef`  
 <span data-ttu-id="fce18-107">de Un token de metadatos de `mdMethodDef` que hace referencia a la función.</span><span class="sxs-lookup"><span data-stu-id="fce18-107">[in] An `mdMethodDef` metadata token that references the function.</span></span>  
  
 `classId`  
 <span data-ttu-id="fce18-108">de IDENTIFICADOR de la clase contenedora de la función.</span><span class="sxs-lookup"><span data-stu-id="fce18-108">[in] The ID of the function's containing class.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="fce18-109">de El número de parámetros de tipo para la función especificada.</span><span class="sxs-lookup"><span data-stu-id="fce18-109">[in] The number of type parameters for the given function.</span></span> <span data-ttu-id="fce18-110">Este valor debe ser cero para las funciones no genéricas.</span><span class="sxs-lookup"><span data-stu-id="fce18-110">This value must be zero for non-generic functions.</span></span>  
  
 `typeArgs`  
 <span data-ttu-id="fce18-111">de Matriz de valores de `ClassID`, cada uno de los cuales es un argumento de la función.</span><span class="sxs-lookup"><span data-stu-id="fce18-111">[in] An array of `ClassID` values, each of which is an argument of the function.</span></span> <span data-ttu-id="fce18-112">El valor de `typeArgs` puede ser NULL si `cTypeArgs` está establecido en cero.</span><span class="sxs-lookup"><span data-stu-id="fce18-112">The value of `typeArgs` can be NULL if `cTypeArgs` is set to zero.</span></span>  
  
 `pFunctionID`  
 <span data-ttu-id="fce18-113">enuncia Puntero al `FunctionID` de la función especificada.</span><span class="sxs-lookup"><span data-stu-id="fce18-113">[out] A pointer to the `FunctionID` of the specified function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fce18-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fce18-114">Remarks</span></span>  
 <span data-ttu-id="fce18-115">Llamar al método `GetFunctionFromTokenAndTypeArgs` con un `mdMethodRef` metadatos en lugar de un token de metadatos de `mdMethodDef` puede tener resultados imprevisibles.</span><span class="sxs-lookup"><span data-stu-id="fce18-115">Calling the `GetFunctionFromTokenAndTypeArgs` method with an `mdMethodRef` metadata instead of an `mdMethodDef` metadata token can have unpredictable results.</span></span> <span data-ttu-id="fce18-116">Los llamadores deben resolver el `mdMethodRef` en un `mdMethodDef` al pasarlo.</span><span class="sxs-lookup"><span data-stu-id="fce18-116">Callers should resolve the `mdMethodRef` to an `mdMethodDef` when passing it.</span></span>  
  
 <span data-ttu-id="fce18-117">Si la función no está cargada todavía, la llamada a `GetFunctionFromTokenAndTypeArgs` provocará que se produzca la carga, lo que es una operación peligrosa en muchos contextos.</span><span class="sxs-lookup"><span data-stu-id="fce18-117">If the function is not already loaded, calling `GetFunctionFromTokenAndTypeArgs` will cause loading to occur, which is a dangerous operation in many contexts.</span></span> <span data-ttu-id="fce18-118">Por ejemplo, llamar a este método durante la carga de módulos o tipos podría provocar un bucle infinito, ya que el tiempo de ejecución intenta cargar elementos de forma circular.</span><span class="sxs-lookup"><span data-stu-id="fce18-118">For example, calling this method during loading of modules or types could lead to an infinite loop as the runtime attempts to circularly load things.</span></span>  
  
 <span data-ttu-id="fce18-119">En general, no se recomienda el uso de `GetFunctionFromTokenAndTypeArgs`.</span><span class="sxs-lookup"><span data-stu-id="fce18-119">In general, use of `GetFunctionFromTokenAndTypeArgs` is discouraged.</span></span> <span data-ttu-id="fce18-120">Si los perfiles están interesados en eventos para una función determinada, deben almacenar los `ModuleID` y `mdMethodDef` de esa función y usar [ICorProfilerInfo2:: getfunctioninfo2 (](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) para comprobar si un `FunctionID` determinado es el de la función deseada.</span><span class="sxs-lookup"><span data-stu-id="fce18-120">If profilers are interested in events for a particular function, they should store the `ModuleID` and `mdMethodDef` of that function, and use [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) to check whether a given `FunctionID` is that of the desired function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fce18-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fce18-121">Requirements</span></span>  
 <span data-ttu-id="fce18-122">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fce18-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fce18-123">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fce18-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fce18-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fce18-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fce18-125">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fce18-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fce18-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="fce18-126">See also</span></span>

- [<span data-ttu-id="fce18-127">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fce18-127">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="fce18-128">ICorProfilerInfo2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fce18-128">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
