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
ms.openlocfilehash: 17a6220598010c0bee9c3f0485860aa0b2dc5f3a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727112"
---
# <a name="icorprofilerinfo2getfunctionfromtokenandtypeargs-method"></a><span data-ttu-id="74fde-102">ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs (Método)</span><span class="sxs-lookup"><span data-stu-id="74fde-102">ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs Method</span></span>

<span data-ttu-id="74fde-103">Obtiene el `FunctionID` de una función mediante el token de metadatos especificado, la clase contenedora y `ClassID` los valores de cualquier argumento de tipo.</span><span class="sxs-lookup"><span data-stu-id="74fde-103">Gets the `FunctionID` of a function by using the specified metadata token, containing class, and `ClassID` values of any type arguments.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74fde-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="74fde-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdMethodDef funcDef,  
    [in] ClassID classId,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] FunctionID* pFunctionID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="74fde-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="74fde-105">Parameters</span></span>  

 `moduleID`  
 <span data-ttu-id="74fde-106">de IDENTIFICADOR del módulo en el que reside la función.</span><span class="sxs-lookup"><span data-stu-id="74fde-106">[in] The ID of the module in which the function resides.</span></span>  
  
 `funcDef`  
 <span data-ttu-id="74fde-107">de `mdMethodDef` Token de metadatos que hace referencia a la función.</span><span class="sxs-lookup"><span data-stu-id="74fde-107">[in] An `mdMethodDef` metadata token that references the function.</span></span>  
  
 `classId`  
 <span data-ttu-id="74fde-108">de IDENTIFICADOR de la clase contenedora de la función.</span><span class="sxs-lookup"><span data-stu-id="74fde-108">[in] The ID of the function's containing class.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="74fde-109">de El número de parámetros de tipo para la función especificada.</span><span class="sxs-lookup"><span data-stu-id="74fde-109">[in] The number of type parameters for the given function.</span></span> <span data-ttu-id="74fde-110">Este valor debe ser cero para las funciones no genéricas.</span><span class="sxs-lookup"><span data-stu-id="74fde-110">This value must be zero for non-generic functions.</span></span>  
  
 `typeArgs`  
 <span data-ttu-id="74fde-111">de Una matriz de `ClassID` valores, cada uno de los cuales es un argumento de la función.</span><span class="sxs-lookup"><span data-stu-id="74fde-111">[in] An array of `ClassID` values, each of which is an argument of the function.</span></span> <span data-ttu-id="74fde-112">El valor de `typeArgs` puede ser null si `cTypeArgs` está establecido en cero.</span><span class="sxs-lookup"><span data-stu-id="74fde-112">The value of `typeArgs` can be NULL if `cTypeArgs` is set to zero.</span></span>  
  
 `pFunctionID`  
 <span data-ttu-id="74fde-113">enuncia Puntero al `FunctionID` de la función especificada.</span><span class="sxs-lookup"><span data-stu-id="74fde-113">[out] A pointer to the `FunctionID` of the specified function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="74fde-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="74fde-114">Remarks</span></span>  

 <span data-ttu-id="74fde-115">La llamada al `GetFunctionFromTokenAndTypeArgs` método con `mdMethodRef` metadatos en lugar de un `mdMethodDef` token de metadatos puede tener resultados imprevisibles.</span><span class="sxs-lookup"><span data-stu-id="74fde-115">Calling the `GetFunctionFromTokenAndTypeArgs` method with an `mdMethodRef` metadata instead of an `mdMethodDef` metadata token can have unpredictable results.</span></span> <span data-ttu-id="74fde-116">Los llamadores deben resolver el `mdMethodRef` en un `mdMethodDef` al pasarlo.</span><span class="sxs-lookup"><span data-stu-id="74fde-116">Callers should resolve the `mdMethodRef` to an `mdMethodDef` when passing it.</span></span>  
  
 <span data-ttu-id="74fde-117">Si la función no está cargada todavía, la llamada `GetFunctionFromTokenAndTypeArgs` a provocará que se produzca la carga, lo que es una operación peligrosa en muchos contextos.</span><span class="sxs-lookup"><span data-stu-id="74fde-117">If the function is not already loaded, calling `GetFunctionFromTokenAndTypeArgs` will cause loading to occur, which is a dangerous operation in many contexts.</span></span> <span data-ttu-id="74fde-118">Por ejemplo, llamar a este método durante la carga de módulos o tipos podría provocar un bucle infinito, ya que el tiempo de ejecución intenta cargar elementos de forma circular.</span><span class="sxs-lookup"><span data-stu-id="74fde-118">For example, calling this method during loading of modules or types could lead to an infinite loop as the runtime attempts to circularly load things.</span></span>  
  
 <span data-ttu-id="74fde-119">En general, `GetFunctionFromTokenAndTypeArgs` no se recomienda el uso de.</span><span class="sxs-lookup"><span data-stu-id="74fde-119">In general, use of `GetFunctionFromTokenAndTypeArgs` is discouraged.</span></span> <span data-ttu-id="74fde-120">Si los perfiles están interesados en eventos para una función determinada, deben almacenar `ModuleID` y `mdMethodDef` de esa función, y usar [ICorProfilerInfo2:: getfunctioninfo2 (](icorprofilerinfo2-getfunctioninfo2-method.md) para comprobar si un determinado `FunctionID` es el de la función deseada.</span><span class="sxs-lookup"><span data-stu-id="74fde-120">If profilers are interested in events for a particular function, they should store the `ModuleID` and `mdMethodDef` of that function, and use [ICorProfilerInfo2::GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) to check whether a given `FunctionID` is that of the desired function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74fde-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="74fde-121">Requirements</span></span>  

 <span data-ttu-id="74fde-122">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74fde-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74fde-123">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="74fde-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="74fde-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="74fde-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="74fde-125">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74fde-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74fde-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="74fde-126">See also</span></span>

- [<span data-ttu-id="74fde-127">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="74fde-127">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="74fde-128">ICorProfilerInfo2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="74fde-128">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
