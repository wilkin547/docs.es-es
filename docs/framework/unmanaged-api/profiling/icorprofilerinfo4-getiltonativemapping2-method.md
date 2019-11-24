---
title: ICorProfilerInfo4::GetILToNativeMapping2 (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetILToNativeMapping2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetILToNativeMapping2
helpviewer_keywords:
- ICorProfilerInfo4::GetILToNativeMapping2 method [.NET Framework profiling]
- GetILToNativeMapping2 method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 756c1c25-08a7-4060-9798-dbeaa2f3bee5
topic_type:
- apiref
ms.openlocfilehash: dfce86e95ba41a65e72524546072244a47f8360c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442928"
---
# <a name="icorprofilerinfo4getiltonativemapping2-method"></a><span data-ttu-id="9dd91-102">ICorProfilerInfo4::GetILToNativeMapping2 (Método)</span><span class="sxs-lookup"><span data-stu-id="9dd91-102">ICorProfilerInfo4::GetILToNativeMapping2 Method</span></span>
<span data-ttu-id="9dd91-103">Obtiene una asignación de desplazamientos del lenguaje intermedio de Microsoft (MSIL) a los desplazamientos nativos para el código incluido en la versión recompilada con JIT de la función especificada.</span><span class="sxs-lookup"><span data-stu-id="9dd91-103">Gets a map from Microsoft intermediate language (MSIL) offsets to native offsets for the code contained in the JIT-recompiled version of the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9dd91-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9dd91-104">Syntax</span></span>  
  
```cpp  
HRESULT GetILToNativeMapping(  
    [in] FunctionID functionId,  
    [in] ReJITID reJitId,  
    [in] ULONG32 cMap,  
    [out] ULONG32 *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        COR_DEBUG_IL_TO_NATIVE_MAP map[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9dd91-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9dd91-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="9dd91-106">[in] Identificador de la función que contiene el código.</span><span class="sxs-lookup"><span data-stu-id="9dd91-106">[in] The ID of the function that contains the code.</span></span>  
  
 `pReJitId`  
 <span data-ttu-id="9dd91-107">[in] Identidad de la función recompilada con JIT.</span><span class="sxs-lookup"><span data-stu-id="9dd91-107">[in] The identity of the JIT-recompiled function.</span></span> <span data-ttu-id="9dd91-108">The identity must be zero in the .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="9dd91-108">The identity must be zero in the .NET Framework 4.5.</span></span>  
  
 `cMap`  
 <span data-ttu-id="9dd91-109">[in] Tamaño máximo de la matriz `map`.</span><span class="sxs-lookup"><span data-stu-id="9dd91-109">[in] The maximum size of the `map` array.</span></span>  
  
 `pcMap`  
 <span data-ttu-id="9dd91-110">[out] The total number of available COR_DEBUG_IL_TO_NATIVE_MAP structures.</span><span class="sxs-lookup"><span data-stu-id="9dd91-110">[out] The total number of available COR_DEBUG_IL_TO_NATIVE_MAP structures.</span></span>  
  
 `map`  
 <span data-ttu-id="9dd91-111">[out] Matriz de estructuras `COR_DEBUG_IL_TO_NATIVE_MAP`, cada una de las cuales especifica los desplazamientos.</span><span class="sxs-lookup"><span data-stu-id="9dd91-111">[out] An array of `COR_DEBUG_IL_TO_NATIVE_MAP` structures, each of which specifies the offsets.</span></span> <span data-ttu-id="9dd91-112">Después de que el método `GetILToNativeMapping2` vuelva, `map` contendrá algunas o todas las estructuras `COR_DEBUG_IL_TO_NATIVE_MAP`.</span><span class="sxs-lookup"><span data-stu-id="9dd91-112">After the `GetILToNativeMapping2` method returns, `map` will contain some or all of the `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9dd91-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9dd91-113">Remarks</span></span>  
 <span data-ttu-id="9dd91-114">`GetILToNativeMapping2` is similar to the [ICorProfilerInfo::GetILToNativeMapping](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md) method, except that it will allow the profiler to specify the ID of the recompiled function in future releases.</span><span class="sxs-lookup"><span data-stu-id="9dd91-114">`GetILToNativeMapping2` is similar to the [ICorProfilerInfo::GetILToNativeMapping](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md) method, except that it will allow the profiler to specify the ID of the recompiled function in future releases.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9dd91-115">The [ICorProfilerFunctionControl::SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setilinstrumentedcodemap-method.md) method is not implemented in the .NET Framework 4.5, so functions that have been JIT-recompiled cannot have an IL-to-native mapping that differs from the originally compiled function.</span><span class="sxs-lookup"><span data-stu-id="9dd91-115">The [ICorProfilerFunctionControl::SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setilinstrumentedcodemap-method.md) method is not implemented in the .NET Framework 4.5, so functions that have been JIT-recompiled cannot have an IL-to-native mapping that differs from the originally compiled function.</span></span> <span data-ttu-id="9dd91-116">As such, `GetILToNativeMapping2` cannot be called with a nonzero JIT-recompiled ID in the .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="9dd91-116">As such, `GetILToNativeMapping2` cannot be called with a nonzero JIT-recompiled ID in the .NET Framework 4.5.</span></span>  
  
 <span data-ttu-id="9dd91-117">El método `GetILToNativeMapping2` devuelve una matriz de estructuras `COR_DEBUG_IL_TO_NATIVE_MAP`.</span><span class="sxs-lookup"><span data-stu-id="9dd91-117">The `GetILToNativeMapping2` method returns an array of `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span> <span data-ttu-id="9dd91-118">To convey that certain ranges of native instructions correspond to special regions of code (for example, the prolog), an entry in the array can have its `ilOffset` field set to a value of the [CorDebugIlToNativeMappingTypes](../../../../docs/framework/unmanaged-api/debugging/cordebugiltonativemappingtypes-enumeration.md) enumeration.</span><span class="sxs-lookup"><span data-stu-id="9dd91-118">To convey that certain ranges of native instructions correspond to special regions of code (for example, the prolog), an entry in the array can have its `ilOffset` field set to a value of the [CorDebugIlToNativeMappingTypes](../../../../docs/framework/unmanaged-api/debugging/cordebugiltonativemappingtypes-enumeration.md) enumeration.</span></span>  
  
 <span data-ttu-id="9dd91-119">Después de la devolución de `GetILToNativeMapping2`, debe comprobar que el búfer `map` era lo suficientemente grande como para contener todas las estructuras `COR_DEBUG_IL_TO_NATIVE_MAP`.</span><span class="sxs-lookup"><span data-stu-id="9dd91-119">After `GetILToNativeMapping2` returns, you must verify that the `map` buffer was large enough to contain all the `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span> <span data-ttu-id="9dd91-120">Para ello, compare el valor de `cMap` con el valor del parámetro `pcMap`.</span><span class="sxs-lookup"><span data-stu-id="9dd91-120">To do this, compare the value of `cMap` with the value of the `pcMap` parameter.</span></span> <span data-ttu-id="9dd91-121">Si el valor de `pcMap`, al multiplicarlo por el tamaño de una estructura `COR_DEBUG_IL_TO_NATIVE_MAP`, es mayor que `cMap`, asigne un búfer `map` mayor, actualice `cMap` con el nuevo tamaño de mayores dimensiones y vuelva a llamar a `GetILToNativeMapping2`.</span><span class="sxs-lookup"><span data-stu-id="9dd91-121">If the `pcMap` value, when it is multiplied by the size of a `COR_DEBUG_IL_TO_NATIVE_MAP` structure, is larger than `cMap`, allocate a larger `map` buffer, update `cMap` with the new, larger size, and call `GetILToNativeMapping2` again.</span></span>  
  
 <span data-ttu-id="9dd91-122">También tiene la opción de llamar primero a `GetILToNativeMapping2` con un búfer `map` de longitud de cero para obtener el tamaño de búfer correcto.</span><span class="sxs-lookup"><span data-stu-id="9dd91-122">Alternatively, you can first call `GetILToNativeMapping2` with a zero-length `map` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="9dd91-123">Después, puede establecer el tamaño del búfer en el valor devuelto en `pcMap` y volver a llamar a `GetILToNativeMapping2`.</span><span class="sxs-lookup"><span data-stu-id="9dd91-123">You can then set the buffer size to the value returned in `pcMap` and call `GetILToNativeMapping2` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9dd91-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9dd91-124">Requirements</span></span>  
 <span data-ttu-id="9dd91-125">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9dd91-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9dd91-126">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9dd91-126">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9dd91-127">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9dd91-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9dd91-128">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9dd91-128">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9dd91-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="9dd91-129">See also</span></span>

- [<span data-ttu-id="9dd91-130">GetILToNativeMapping (método)</span><span class="sxs-lookup"><span data-stu-id="9dd91-130">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md)
- [<span data-ttu-id="9dd91-131">ICorProfilerInfo4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9dd91-131">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [<span data-ttu-id="9dd91-132">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="9dd91-132">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="9dd91-133">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="9dd91-133">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
