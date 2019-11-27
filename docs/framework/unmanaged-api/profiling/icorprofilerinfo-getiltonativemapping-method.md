---
title: ICorProfilerInfo::GetILToNativeMapping (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetILToNativeMapping
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetILToNativeMapping
helpviewer_keywords:
- GetILToNativeMapping method, ICorProfilerInfo interface [.NET Framework profiling]
- ICorProfilerInfo::GetILToNativeMapping method [.NET Framework profiling]
ms.assetid: 6a5431ef-22fb-4e53-bac5-703986297eb1
topic_type:
- apiref
ms.openlocfilehash: 8dc551b2b1e29aba371e56eecfd981f16b4b1e3e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439037"
---
# <a name="icorprofilerinfogetiltonativemapping-method"></a><span data-ttu-id="81b51-102">ICorProfilerInfo::GetILToNativeMapping (Método)</span><span class="sxs-lookup"><span data-stu-id="81b51-102">ICorProfilerInfo::GetILToNativeMapping Method</span></span>
<span data-ttu-id="81b51-103">Obtiene una asignación de desplazamientos del lenguaje intermedio de Microsoft (MSIL) a los desplazamientos nativos para el código incluido en la función especificada.</span><span class="sxs-lookup"><span data-stu-id="81b51-103">Gets a map from Microsoft intermediate language (MSIL) offsets to native offsets for the code contained in the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81b51-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="81b51-104">Syntax</span></span>  
  
```cpp  
HRESULT GetILToNativeMapping(  
    [in] FunctionID functionId,  
    [in] ULONG32 cMap,  
    [out] ULONG32 *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        COR_DEBUG_IL_TO_NATIVE_MAP map[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="81b51-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="81b51-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="81b51-106">[in] Identificador de la función que contiene el código.</span><span class="sxs-lookup"><span data-stu-id="81b51-106">[in] The ID of the function that contains the code.</span></span>  
  
 `cMap`  
 <span data-ttu-id="81b51-107">[in] Tamaño máximo de la matriz `map`.</span><span class="sxs-lookup"><span data-stu-id="81b51-107">[in] The maximum size of the `map` array.</span></span>  
  
 `pcMap`  
 <span data-ttu-id="81b51-108">[out] Número total de estructuras COR_DEBUG_IL_TO_NATIVE_MAP disponibles.</span><span class="sxs-lookup"><span data-stu-id="81b51-108">[out] The total number of available COR_DEBUG_IL_TO_NATIVE_MAP structures.</span></span>  
  
 `map`  
 <span data-ttu-id="81b51-109">[out] Matriz de estructuras `COR_DEBUG_IL_TO_NATIVE_MAP`, cada una de las cuales especifica los desplazamientos.</span><span class="sxs-lookup"><span data-stu-id="81b51-109">[out] An array of `COR_DEBUG_IL_TO_NATIVE_MAP` structures, each of which specifies the offsets.</span></span> <span data-ttu-id="81b51-110">Después de que el método `GetILToNativeMapping` vuelva, `map` contendrá algunas o todas las estructuras `COR_DEBUG_IL_TO_NATIVE_MAP`.</span><span class="sxs-lookup"><span data-stu-id="81b51-110">After the `GetILToNativeMapping` method returns, `map` will contain some or all of the `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="81b51-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="81b51-111">Remarks</span></span>  
 <span data-ttu-id="81b51-112">El método `GetILToNativeMapping` devuelve una matriz de estructuras `COR_DEBUG_IL_TO_NATIVE_MAP`.</span><span class="sxs-lookup"><span data-stu-id="81b51-112">The `GetILToNativeMapping` method returns an array of `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span> <span data-ttu-id="81b51-113">Para transmitir que ciertos intervalos de instrucciones nativas corresponden a regiones especiales de código (por ejemplo, el prólogo), una entrada de la matriz puede tener su `ilOffset` campo establecido en un valor de la enumeración [CorDebugIlToNativeMappingTypes (](../../../../docs/framework/unmanaged-api/debugging/cordebugiltonativemappingtypes-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="81b51-113">To convey that certain ranges of native instructions correspond to special regions of code (for example, the prolog), an entry in the array can have its `ilOffset` field set to a value of the [CorDebugIlToNativeMappingTypes](../../../../docs/framework/unmanaged-api/debugging/cordebugiltonativemappingtypes-enumeration.md) enumeration.</span></span>  
  
 <span data-ttu-id="81b51-114">Después de la devolución de `GetILToNativeMapping`, debe comprobar que el búfer `map` era lo suficientemente grande como para contener todas las estructuras `COR_DEBUG_IL_TO_NATIVE_MAP`.</span><span class="sxs-lookup"><span data-stu-id="81b51-114">After `GetILToNativeMapping` returns, you must verify that the `map` buffer was large enough to contain all the `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span> <span data-ttu-id="81b51-115">Para ello, compare el valor de `cMap` con el valor del parámetro `pcMap`.</span><span class="sxs-lookup"><span data-stu-id="81b51-115">To do this, compare the value of `cMap` with the value of the `pcMap` parameter.</span></span> <span data-ttu-id="81b51-116">Si el valor de `pcMap`, al multiplicarlo por el tamaño de una estructura `COR_DEBUG_IL_TO_NATIVE_MAP`, es mayor que `cMap`, asigne un búfer `map` mayor, actualice `cMap` con el nuevo tamaño de mayores dimensiones y vuelva a llamar a `GetILToNativeMapping`.</span><span class="sxs-lookup"><span data-stu-id="81b51-116">If the `pcMap` value, when it is multiplied by the size of a `COR_DEBUG_IL_TO_NATIVE_MAP` structure, is larger than `cMap`, allocate a larger `map` buffer, update `cMap` with the new, larger size, and call `GetILToNativeMapping` again.</span></span>  
  
 <span data-ttu-id="81b51-117">También tiene la opción de llamar primero a `GetILToNativeMapping` con un búfer `map` de longitud de cero para obtener el tamaño de búfer correcto.</span><span class="sxs-lookup"><span data-stu-id="81b51-117">Alternatively, you can first call `GetILToNativeMapping` with a zero-length `map` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="81b51-118">Después, puede establecer el tamaño del búfer en el valor devuelto en `pcMap` y volver a llamar a `GetILToNativeMapping`.</span><span class="sxs-lookup"><span data-stu-id="81b51-118">You can then set the buffer size to the value returned in `pcMap` and call `GetILToNativeMapping` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81b51-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="81b51-119">Requirements</span></span>  
 <span data-ttu-id="81b51-120">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81b51-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81b51-121">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="81b51-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="81b51-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="81b51-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="81b51-123">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81b51-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81b51-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="81b51-124">See also</span></span>

- [<span data-ttu-id="81b51-125">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="81b51-125">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="81b51-126">GetILToNativeMapping2 (método)</span><span class="sxs-lookup"><span data-stu-id="81b51-126">GetILToNativeMapping2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getiltonativemapping2-method.md)
- [<span data-ttu-id="81b51-127">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="81b51-127">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="81b51-128">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="81b51-128">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
