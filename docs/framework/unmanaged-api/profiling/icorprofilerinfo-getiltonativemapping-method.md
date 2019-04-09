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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d7bbf0e03fc69332f77f3ac34a399a96f638da3f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59206725"
---
# <a name="icorprofilerinfogetiltonativemapping-method"></a><span data-ttu-id="74b7a-102">ICorProfilerInfo::GetILToNativeMapping (Método)</span><span class="sxs-lookup"><span data-stu-id="74b7a-102">ICorProfilerInfo::GetILToNativeMapping Method</span></span>
<span data-ttu-id="74b7a-103">Obtiene una asignación de desplazamientos del lenguaje intermedio de Microsoft (MSIL) a los desplazamientos nativos para el código incluido en la función especificada.</span><span class="sxs-lookup"><span data-stu-id="74b7a-103">Gets a map from Microsoft intermediate language (MSIL) offsets to native offsets for the code contained in the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74b7a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="74b7a-104">Syntax</span></span>  
  
```  
HRESULT GetILToNativeMapping(  
    [in] FunctionID functionId,  
    [in] ULONG32 cMap,  
    [out] ULONG32 *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        COR_DEBUG_IL_TO_NATIVE_MAP map[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="74b7a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="74b7a-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="74b7a-106">[in] Identificador de la función que contiene el código.</span><span class="sxs-lookup"><span data-stu-id="74b7a-106">[in] The ID of the function that contains the code.</span></span>  
  
 `cMap`  
 <span data-ttu-id="74b7a-107">[in] Tamaño máximo de la matriz `map`.</span><span class="sxs-lookup"><span data-stu-id="74b7a-107">[in] The maximum size of the `map` array.</span></span>  
  
 `pcMap`  
 <span data-ttu-id="74b7a-108">[out] El número total de estructuras COR_DEBUG_IL_TO_NATIVE_MAP disponibles.</span><span class="sxs-lookup"><span data-stu-id="74b7a-108">[out] The total number of available COR_DEBUG_IL_TO_NATIVE_MAP structures.</span></span>  
  
 `map`  
 <span data-ttu-id="74b7a-109">[out] Matriz de estructuras `COR_DEBUG_IL_TO_NATIVE_MAP`, cada una de las cuales especifica los desplazamientos.</span><span class="sxs-lookup"><span data-stu-id="74b7a-109">[out] An array of `COR_DEBUG_IL_TO_NATIVE_MAP` structures, each of which specifies the offsets.</span></span> <span data-ttu-id="74b7a-110">Después de que el método `GetILToNativeMapping` vuelva, `map` contendrá algunas o todas las estructuras `COR_DEBUG_IL_TO_NATIVE_MAP`.</span><span class="sxs-lookup"><span data-stu-id="74b7a-110">After the `GetILToNativeMapping` method returns, `map` will contain some or all of the `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="74b7a-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="74b7a-111">Remarks</span></span>  
 <span data-ttu-id="74b7a-112">El método `GetILToNativeMapping` devuelve una matriz de estructuras `COR_DEBUG_IL_TO_NATIVE_MAP`.</span><span class="sxs-lookup"><span data-stu-id="74b7a-112">The `GetILToNativeMapping` method returns an array of `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span> <span data-ttu-id="74b7a-113">Para transmitir que determinados intervalos de instrucciones nativas se corresponden con regiones de código (por ejemplo, el prólogo) especiales, puede tener una entrada de la matriz su `ilOffset` campo establecido en un valor de la [CorDebugIlToNativeMappingTypes](../../../../docs/framework/unmanaged-api/debugging/cordebugiltonativemappingtypes-enumeration.md) enumeración.</span><span class="sxs-lookup"><span data-stu-id="74b7a-113">To convey that certain ranges of native instructions correspond to special regions of code (for example, the prolog), an entry in the array can have its `ilOffset` field set to a value of the [CorDebugIlToNativeMappingTypes](../../../../docs/framework/unmanaged-api/debugging/cordebugiltonativemappingtypes-enumeration.md) enumeration.</span></span>  
  
 <span data-ttu-id="74b7a-114">Después de la devolución de `GetILToNativeMapping`, debe comprobar que el búfer `map` era lo suficientemente grande como para contener todas las estructuras `COR_DEBUG_IL_TO_NATIVE_MAP`.</span><span class="sxs-lookup"><span data-stu-id="74b7a-114">After `GetILToNativeMapping` returns, you must verify that the `map` buffer was large enough to contain all the `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span> <span data-ttu-id="74b7a-115">Para ello, compare el valor de `cMap` con el valor del parámetro `pcMap`.</span><span class="sxs-lookup"><span data-stu-id="74b7a-115">To do this, compare the value of `cMap` with the value of the `pcMap` parameter.</span></span> <span data-ttu-id="74b7a-116">Si el valor de `pcMap`, al multiplicarlo por el tamaño de una estructura `COR_DEBUG_IL_TO_NATIVE_MAP`, es mayor que `cMap`, asigne un búfer `map` mayor, actualice `cMap` con el nuevo tamaño de mayores dimensiones y vuelva a llamar a `GetILToNativeMapping`.</span><span class="sxs-lookup"><span data-stu-id="74b7a-116">If the `pcMap` value, when it is multiplied by the size of a `COR_DEBUG_IL_TO_NATIVE_MAP` structure, is larger than `cMap`, allocate a larger `map` buffer, update `cMap` with the new, larger size, and call `GetILToNativeMapping` again.</span></span>  
  
 <span data-ttu-id="74b7a-117">También tiene la opción de llamar primero a `GetILToNativeMapping` con un búfer `map` de longitud de cero para obtener el tamaño de búfer correcto.</span><span class="sxs-lookup"><span data-stu-id="74b7a-117">Alternatively, you can first call `GetILToNativeMapping` with a zero-length `map` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="74b7a-118">Después, puede establecer el tamaño del búfer en el valor devuelto en `pcMap` y volver a llamar a `GetILToNativeMapping`.</span><span class="sxs-lookup"><span data-stu-id="74b7a-118">You can then set the buffer size to the value returned in `pcMap` and call `GetILToNativeMapping` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74b7a-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="74b7a-119">Requirements</span></span>  
 <span data-ttu-id="74b7a-120">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74b7a-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74b7a-121">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="74b7a-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="74b7a-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="74b7a-122">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="74b7a-123">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="74b7a-123">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="74b7a-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="74b7a-124">See also</span></span>

- [<span data-ttu-id="74b7a-125">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="74b7a-125">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="74b7a-126">Método GetILToNativeMapping2</span><span class="sxs-lookup"><span data-stu-id="74b7a-126">GetILToNativeMapping2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getiltonativemapping2-method.md)
- [<span data-ttu-id="74b7a-127">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="74b7a-127">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="74b7a-128">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="74b7a-128">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
