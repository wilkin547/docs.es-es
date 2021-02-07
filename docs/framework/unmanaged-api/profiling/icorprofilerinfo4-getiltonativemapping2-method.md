---
description: 'Más información sobre: ICorProfilerInfo4:: Getiltonativemapping2 ((método)'
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
ms.openlocfilehash: f548dbef3444c6e63e51cd5f3db79e567b2630b5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99686796"
---
# <a name="icorprofilerinfo4getiltonativemapping2-method"></a><span data-ttu-id="1bb6e-103">ICorProfilerInfo4::GetILToNativeMapping2 (Método)</span><span class="sxs-lookup"><span data-stu-id="1bb6e-103">ICorProfilerInfo4::GetILToNativeMapping2 Method</span></span>

<span data-ttu-id="1bb6e-104">Obtiene una asignación de desplazamientos del lenguaje intermedio de Microsoft (MSIL) a los desplazamientos nativos para el código incluido en la versión recompilada con JIT de la función especificada.</span><span class="sxs-lookup"><span data-stu-id="1bb6e-104">Gets a map from Microsoft intermediate language (MSIL) offsets to native offsets for the code contained in the JIT-recompiled version of the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1bb6e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1bb6e-105">Syntax</span></span>  
  
```cpp  
HRESULT GetILToNativeMapping(  
    [in] FunctionID functionId,  
    [in] ReJITID reJitId,  
    [in] ULONG32 cMap,  
    [out] ULONG32 *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        COR_DEBUG_IL_TO_NATIVE_MAP map[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1bb6e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1bb6e-106">Parameters</span></span>  

 `functionId`  
 <span data-ttu-id="1bb6e-107">[in] Identificador de la función que contiene el código.</span><span class="sxs-lookup"><span data-stu-id="1bb6e-107">[in] The ID of the function that contains the code.</span></span>  
  
 `pReJitId`  
 <span data-ttu-id="1bb6e-108">[in] Identidad de la función recompilada con JIT.</span><span class="sxs-lookup"><span data-stu-id="1bb6e-108">[in] The identity of the JIT-recompiled function.</span></span> <span data-ttu-id="1bb6e-109">La identidad debe ser cero en el .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="1bb6e-109">The identity must be zero in the .NET Framework 4.5.</span></span>  
  
 `cMap`  
 <span data-ttu-id="1bb6e-110">[in] Tamaño máximo de la matriz `map`.</span><span class="sxs-lookup"><span data-stu-id="1bb6e-110">[in] The maximum size of the `map` array.</span></span>  
  
 `pcMap`  
 <span data-ttu-id="1bb6e-111">[out] Número total de estructuras COR_DEBUG_IL_TO_NATIVE_MAP disponibles.</span><span class="sxs-lookup"><span data-stu-id="1bb6e-111">[out] The total number of available COR_DEBUG_IL_TO_NATIVE_MAP structures.</span></span>  
  
 `map`  
 <span data-ttu-id="1bb6e-112">[out] Matriz de estructuras `COR_DEBUG_IL_TO_NATIVE_MAP`, cada una de las cuales especifica los desplazamientos.</span><span class="sxs-lookup"><span data-stu-id="1bb6e-112">[out] An array of `COR_DEBUG_IL_TO_NATIVE_MAP` structures, each of which specifies the offsets.</span></span> <span data-ttu-id="1bb6e-113">Después de que el método `GetILToNativeMapping2` vuelva, `map` contendrá algunas o todas las estructuras `COR_DEBUG_IL_TO_NATIVE_MAP`.</span><span class="sxs-lookup"><span data-stu-id="1bb6e-113">After the `GetILToNativeMapping2` method returns, `map` will contain some or all of the `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1bb6e-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1bb6e-114">Remarks</span></span>  

 <span data-ttu-id="1bb6e-115">`GetILToNativeMapping2` es similar al método [ICorProfilerInfo:: GetILToNativeMapping](icorprofilerinfo-getiltonativemapping-method.md) , salvo que permitirá al generador de perfiles especificar el identificador de la función recompilada en versiones futuras.</span><span class="sxs-lookup"><span data-stu-id="1bb6e-115">`GetILToNativeMapping2` is similar to the [ICorProfilerInfo::GetILToNativeMapping](icorprofilerinfo-getiltonativemapping-method.md) method, except that it will allow the profiler to specify the ID of the recompiled function in future releases.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1bb6e-116">El método [ICorProfilerFunctionControl:: SetILInstrumentedCodeMap (](icorprofilerfunctioncontrol-setilinstrumentedcodemap-method.md) no está implementado en la .NET Framework 4,5, por lo que las funciones que se han vuelto a compilar JIT no pueden tener una asignación de Il a nativo que difiere de la función compilada originalmente.</span><span class="sxs-lookup"><span data-stu-id="1bb6e-116">The [ICorProfilerFunctionControl::SetILInstrumentedCodeMap](icorprofilerfunctioncontrol-setilinstrumentedcodemap-method.md) method is not implemented in the .NET Framework 4.5, so functions that have been JIT-recompiled cannot have an IL-to-native mapping that differs from the originally compiled function.</span></span> <span data-ttu-id="1bb6e-117">Como tal, `GetILToNativeMapping2` no se puede llamar con un identificador de recompilación JIT distinto de cero en el .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="1bb6e-117">As such, `GetILToNativeMapping2` cannot be called with a nonzero JIT-recompiled ID in the .NET Framework 4.5.</span></span>  
  
 <span data-ttu-id="1bb6e-118">El método `GetILToNativeMapping2` devuelve una matriz de estructuras `COR_DEBUG_IL_TO_NATIVE_MAP`.</span><span class="sxs-lookup"><span data-stu-id="1bb6e-118">The `GetILToNativeMapping2` method returns an array of `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span> <span data-ttu-id="1bb6e-119">Para transmitir que ciertos intervalos de instrucciones nativas se corresponden con regiones especiales de código (por ejemplo, el prólogo), una entrada de la matriz puede tener su `ilOffset` campo establecido en un valor de la enumeración [CorDebugIlToNativeMappingTypes (](../debugging/cordebugiltonativemappingtypes-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="1bb6e-119">To convey that certain ranges of native instructions correspond to special regions of code (for example, the prolog), an entry in the array can have its `ilOffset` field set to a value of the [CorDebugIlToNativeMappingTypes](../debugging/cordebugiltonativemappingtypes-enumeration.md) enumeration.</span></span>  
  
 <span data-ttu-id="1bb6e-120">Después de la devolución de `GetILToNativeMapping2`, debe comprobar que el búfer `map` era lo suficientemente grande como para contener todas las estructuras `COR_DEBUG_IL_TO_NATIVE_MAP`.</span><span class="sxs-lookup"><span data-stu-id="1bb6e-120">After `GetILToNativeMapping2` returns, you must verify that the `map` buffer was large enough to contain all the `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span> <span data-ttu-id="1bb6e-121">Para ello, compare el valor de `cMap` con el valor del parámetro `pcMap`.</span><span class="sxs-lookup"><span data-stu-id="1bb6e-121">To do this, compare the value of `cMap` with the value of the `pcMap` parameter.</span></span> <span data-ttu-id="1bb6e-122">Si el valor de `pcMap`, al multiplicarlo por el tamaño de una estructura `COR_DEBUG_IL_TO_NATIVE_MAP`, es mayor que `cMap`, asigne un búfer `map` mayor, actualice `cMap` con el nuevo tamaño de mayores dimensiones y vuelva a llamar a `GetILToNativeMapping2`.</span><span class="sxs-lookup"><span data-stu-id="1bb6e-122">If the `pcMap` value, when it is multiplied by the size of a `COR_DEBUG_IL_TO_NATIVE_MAP` structure, is larger than `cMap`, allocate a larger `map` buffer, update `cMap` with the new, larger size, and call `GetILToNativeMapping2` again.</span></span>  
  
 <span data-ttu-id="1bb6e-123">También tiene la opción de llamar primero a `GetILToNativeMapping2` con un búfer `map` de longitud de cero para obtener el tamaño de búfer correcto.</span><span class="sxs-lookup"><span data-stu-id="1bb6e-123">Alternatively, you can first call `GetILToNativeMapping2` with a zero-length `map` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="1bb6e-124">Después, puede establecer el tamaño del búfer en el valor devuelto en `pcMap` y volver a llamar a `GetILToNativeMapping2`.</span><span class="sxs-lookup"><span data-stu-id="1bb6e-124">You can then set the buffer size to the value returned in `pcMap` and call `GetILToNativeMapping2` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1bb6e-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1bb6e-125">Requirements</span></span>  

 <span data-ttu-id="1bb6e-126">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1bb6e-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1bb6e-127">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1bb6e-127">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1bb6e-128">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1bb6e-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1bb6e-129">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1bb6e-129">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bb6e-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="1bb6e-130">See also</span></span>

- [<span data-ttu-id="1bb6e-131">Método GetILToNativeMapping</span><span class="sxs-lookup"><span data-stu-id="1bb6e-131">GetILToNativeMapping Method</span></span>](icorprofilerinfo-getiltonativemapping-method.md)
- [<span data-ttu-id="1bb6e-132">ICorProfilerInfo4 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1bb6e-132">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)
- [<span data-ttu-id="1bb6e-133">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="1bb6e-133">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="1bb6e-134">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="1bb6e-134">Profiling</span></span>](index.md)
