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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a8ffdb04bdf3fd2f605e2dffc5065a0d786bbaf7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69967916"
---
# <a name="icorprofilerinfo4getiltonativemapping2-method"></a><span data-ttu-id="c081a-102">ICorProfilerInfo4::GetILToNativeMapping2 (Método)</span><span class="sxs-lookup"><span data-stu-id="c081a-102">ICorProfilerInfo4::GetILToNativeMapping2 Method</span></span>
<span data-ttu-id="c081a-103">Obtiene una asignación de desplazamientos del lenguaje intermedio de Microsoft (MSIL) a los desplazamientos nativos para el código incluido en la versión recompilada con JIT de la función especificada.</span><span class="sxs-lookup"><span data-stu-id="c081a-103">Gets a map from Microsoft intermediate language (MSIL) offsets to native offsets for the code contained in the JIT-recompiled version of the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c081a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c081a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetILToNativeMapping(  
    [in] FunctionID functionId,  
    [in] ReJITID reJitId,  
    [in] ULONG32 cMap,  
    [out] ULONG32 *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        COR_DEBUG_IL_TO_NATIVE_MAP map[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c081a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c081a-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="c081a-106">[in] Identificador de la función que contiene el código.</span><span class="sxs-lookup"><span data-stu-id="c081a-106">[in] The ID of the function that contains the code.</span></span>  
  
 `pReJitId`  
 <span data-ttu-id="c081a-107">[in] Identidad de la función recompilada con JIT.</span><span class="sxs-lookup"><span data-stu-id="c081a-107">[in] The identity of the JIT-recompiled function.</span></span> <span data-ttu-id="c081a-108">La identidad debe ser cero en el .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="c081a-108">The identity must be zero in the .NET Framework 4.5.</span></span>  
  
 `cMap`  
 <span data-ttu-id="c081a-109">[in] Tamaño máximo de la matriz `map`.</span><span class="sxs-lookup"><span data-stu-id="c081a-109">[in] The maximum size of the `map` array.</span></span>  
  
 `pcMap`  
 <span data-ttu-id="c081a-110">enuncia Número total de estructuras COR_DEBUG_IL_TO_NATIVE_MAP disponibles.</span><span class="sxs-lookup"><span data-stu-id="c081a-110">[out] The total number of available COR_DEBUG_IL_TO_NATIVE_MAP structures.</span></span>  
  
 `map`  
 <span data-ttu-id="c081a-111">[out] Matriz de estructuras `COR_DEBUG_IL_TO_NATIVE_MAP`, cada una de las cuales especifica los desplazamientos.</span><span class="sxs-lookup"><span data-stu-id="c081a-111">[out] An array of `COR_DEBUG_IL_TO_NATIVE_MAP` structures, each of which specifies the offsets.</span></span> <span data-ttu-id="c081a-112">Después de que el método `GetILToNativeMapping2` vuelva, `map` contendrá algunas o todas las estructuras `COR_DEBUG_IL_TO_NATIVE_MAP`.</span><span class="sxs-lookup"><span data-stu-id="c081a-112">After the `GetILToNativeMapping2` method returns, `map` will contain some or all of the `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c081a-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c081a-113">Remarks</span></span>  
 <span data-ttu-id="c081a-114">`GetILToNativeMapping2`es similar al método [ICorProfilerInfo:: GetILToNativeMapping](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md) , salvo que permitirá al generador de perfiles especificar el identificador de la función recompilada en versiones futuras.</span><span class="sxs-lookup"><span data-stu-id="c081a-114">`GetILToNativeMapping2` is similar to the [ICorProfilerInfo::GetILToNativeMapping](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md) method, except that it will allow the profiler to specify the ID of the recompiled function in future releases.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c081a-115">El método [ICorProfilerFunctionControl:: SetILInstrumentedCodeMap (](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setilinstrumentedcodemap-method.md) no está implementado en la .NET Framework 4,5, por lo que las funciones que se han vuelto a compilar JIT no pueden tener una asignación de Il a nativo que difiere de la función compilada originalmente.</span><span class="sxs-lookup"><span data-stu-id="c081a-115">The [ICorProfilerFunctionControl::SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setilinstrumentedcodemap-method.md) method is not implemented in the .NET Framework 4.5, so functions that have been JIT-recompiled cannot have an IL-to-native mapping that differs from the originally compiled function.</span></span> <span data-ttu-id="c081a-116">Como tal, `GetILToNativeMapping2` no se puede llamar con un identificador de recompilación JIT distinto de cero en el .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="c081a-116">As such, `GetILToNativeMapping2` cannot be called with a nonzero JIT-recompiled ID in the .NET Framework 4.5.</span></span>  
  
 <span data-ttu-id="c081a-117">El método `GetILToNativeMapping2` devuelve una matriz de estructuras `COR_DEBUG_IL_TO_NATIVE_MAP`.</span><span class="sxs-lookup"><span data-stu-id="c081a-117">The `GetILToNativeMapping2` method returns an array of `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span> <span data-ttu-id="c081a-118">Para transmitir que ciertos intervalos de instrucciones nativas se corresponden con regiones especiales de código (por ejemplo, el prólogo), una entrada de la matriz puede `ilOffset` tener su campo establecido en un valor de la enumeración [CorDebugIlToNativeMappingTypes (](../../../../docs/framework/unmanaged-api/debugging/cordebugiltonativemappingtypes-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="c081a-118">To convey that certain ranges of native instructions correspond to special regions of code (for example, the prolog), an entry in the array can have its `ilOffset` field set to a value of the [CorDebugIlToNativeMappingTypes](../../../../docs/framework/unmanaged-api/debugging/cordebugiltonativemappingtypes-enumeration.md) enumeration.</span></span>  
  
 <span data-ttu-id="c081a-119">Después de la devolución de `GetILToNativeMapping2`, debe comprobar que el búfer `map` era lo suficientemente grande como para contener todas las estructuras `COR_DEBUG_IL_TO_NATIVE_MAP`.</span><span class="sxs-lookup"><span data-stu-id="c081a-119">After `GetILToNativeMapping2` returns, you must verify that the `map` buffer was large enough to contain all the `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span> <span data-ttu-id="c081a-120">Para ello, compare el valor de `cMap` con el valor del parámetro `pcMap`.</span><span class="sxs-lookup"><span data-stu-id="c081a-120">To do this, compare the value of `cMap` with the value of the `pcMap` parameter.</span></span> <span data-ttu-id="c081a-121">Si el valor de `pcMap`, al multiplicarlo por el tamaño de una estructura `COR_DEBUG_IL_TO_NATIVE_MAP`, es mayor que `cMap`, asigne un búfer `map` mayor, actualice `cMap` con el nuevo tamaño de mayores dimensiones y vuelva a llamar a `GetILToNativeMapping2`.</span><span class="sxs-lookup"><span data-stu-id="c081a-121">If the `pcMap` value, when it is multiplied by the size of a `COR_DEBUG_IL_TO_NATIVE_MAP` structure, is larger than `cMap`, allocate a larger `map` buffer, update `cMap` with the new, larger size, and call `GetILToNativeMapping2` again.</span></span>  
  
 <span data-ttu-id="c081a-122">También tiene la opción de llamar primero a `GetILToNativeMapping2` con un búfer `map` de longitud de cero para obtener el tamaño de búfer correcto.</span><span class="sxs-lookup"><span data-stu-id="c081a-122">Alternatively, you can first call `GetILToNativeMapping2` with a zero-length `map` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="c081a-123">Después, puede establecer el tamaño del búfer en el valor devuelto en `pcMap` y volver a llamar a `GetILToNativeMapping2`.</span><span class="sxs-lookup"><span data-stu-id="c081a-123">You can then set the buffer size to the value returned in `pcMap` and call `GetILToNativeMapping2` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c081a-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c081a-124">Requirements</span></span>  
 <span data-ttu-id="c081a-125">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c081a-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c081a-126">**Encabezado**: Corprof. idl, Corprof. h</span><span class="sxs-lookup"><span data-stu-id="c081a-126">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c081a-127">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c081a-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c081a-128">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c081a-128">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c081a-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="c081a-129">See also</span></span>

- [<span data-ttu-id="c081a-130">GetILToNativeMapping (método)</span><span class="sxs-lookup"><span data-stu-id="c081a-130">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md)
- [<span data-ttu-id="c081a-131">ICorProfilerInfo4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c081a-131">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [<span data-ttu-id="c081a-132">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="c081a-132">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="c081a-133">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="c081a-133">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
