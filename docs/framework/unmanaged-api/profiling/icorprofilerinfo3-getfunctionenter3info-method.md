---
title: "ICorProfilerInfo3::GetFunctionEnter3Info (Método)"
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
- ICorProfilerInfo3.GetFunctionEnter3Info Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetFunctionEnter3Info
helpviewer_keywords:
- GetFunctionEnter3Info method [.NET Framework profiling]
- ICorProfilerInfo3::GetFunctionEnter3Info method [.NET Framework profiling]
ms.assetid: 542c7c65-dd56-4651-b76f-5db2465e4a15
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6b7053f526d415dbaef872e37d139d25ae5ac462
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo3getfunctionenter3info-method"></a><span data-ttu-id="e299b-102">ICorProfilerInfo3::GetFunctionEnter3Info (Método)</span><span class="sxs-lookup"><span data-stu-id="e299b-102">ICorProfilerInfo3::GetFunctionEnter3Info Method</span></span>
<span data-ttu-id="e299b-103">Proporciona la información de pila de marco y los argumentos de la función que se va a notificar al generador de perfiles la [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md) función.</span><span class="sxs-lookup"><span data-stu-id="e299b-103">Provides the stack frame and argument information of the function that is being reported to the profiler by the [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md) function.</span></span> <span data-ttu-id="e299b-104">Solo se puede llamar a este método durante la devolución de llamada `FunctionEnter3WithInfo`.</span><span class="sxs-lookup"><span data-stu-id="e299b-104">This method can be called only during the `FunctionEnter3WithInfo` callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e299b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e299b-105">Syntax</span></span>  
  
```  
HRESULT GetFunctionEnter3Info(  
            [in]  FunctionID functionId,   
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo,  
            [in, out] ULONG *pcbArgumentInfo,  
            [out, size_is(*pcbArgumentInfo)]  
                  COR_PRF_FUNCTION_ARGUMENT_INFO *pArgumentInfo);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e299b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e299b-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="e299b-107">[in] `FunctionID` de la función que se está especificando.</span><span class="sxs-lookup"><span data-stu-id="e299b-107">[in] The `FunctionID` of the function that is being entered.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="e299b-108">[in] Controlador opaco que representa información sobre un marco de pila determinado.</span><span class="sxs-lookup"><span data-stu-id="e299b-108">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="e299b-109">El generador de perfiles debe proporcionar el mismo `eltInfo` entregado por el [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md) función.</span><span class="sxs-lookup"><span data-stu-id="e299b-109">The profiler should provide the same `eltInfo` that it was given by the [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md) function.</span></span>  
  
 `pFrameInfo`  
 <span data-ttu-id="e299b-110">[out] Controlador opaco que representa información genérica sobre un marco de pila determinado.</span><span class="sxs-lookup"><span data-stu-id="e299b-110">[out] An opaque handle that represents generics information about a given stack frame.</span></span> <span data-ttu-id="e299b-111">Este identificador es válido solo durante la devolución de llamada `FunctionEnter3WithInfo` en la que el generador de perfiles llamó al método `GetFunctionEnter3Info`.</span><span class="sxs-lookup"><span data-stu-id="e299b-111">This handle is valid only during the `FunctionEnter3WithInfo` callback in which the profiler called the `GetFunctionEnter3Info` method.</span></span>  
  
 `pcbArgumentInfo`  
 <span data-ttu-id="e299b-112">[entrada, salida] Un puntero al tamaño total, en bytes, de la [COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md) estructura (más cualquier adicionales [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) las estructuras de los intervalos de argumentos que señala `pArgumentInfo`).</span><span class="sxs-lookup"><span data-stu-id="e299b-112">[in, out] A pointer to the total size, in bytes, of the [COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md) structure (plus any additional [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) structures for the argument ranges pointed to by `pArgumentInfo`).</span></span> <span data-ttu-id="e299b-113">Si el tamaño especificado no es suficiente, se devuelve ERROR_INSUFFICIENT_BUFFER y el tamaño esperado se almacena en `pcbArgumentInfo`.</span><span class="sxs-lookup"><span data-stu-id="e299b-113">If the specified size is not enough, ERROR_INSUFFICIENT_BUFFER is returned and the expected size is stored in `pcbArgumentInfo`.</span></span> <span data-ttu-id="e299b-114">Para llamar a `GetFunctionEnter3Info` para recuperar el valor de `*pcbArgumentInfo` esperado, establezca `*pcbArgumentInfo`=0 y `pArgumentInfo`=NULL.</span><span class="sxs-lookup"><span data-stu-id="e299b-114">To call `GetFunctionEnter3Info` just to retrieve the expected value for `*pcbArgumentInfo`, set `*pcbArgumentInfo`=0 and `pArgumentInfo`=NULL.</span></span>  
  
 `pArgumentInfo`  
 <span data-ttu-id="e299b-115">[out] Un puntero a un [COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md) estructura que describe las ubicaciones de los argumentos de la función de memoria, ordenados de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="e299b-115">[out] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md) structure that describes the locations of the function's arguments in memory, in left-to-right order.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e299b-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e299b-116">Remarks</span></span>  
 <span data-ttu-id="e299b-117">El generador de perfiles debe asignar espacio suficiente para la estructura `COR_PRF_FUNCTION_ARGUMENT_INFO` de la función que se está inspeccionando y debe indicar el tamaño del parámetro `pcbArgumentInfo`.</span><span class="sxs-lookup"><span data-stu-id="e299b-117">The profiler must allocate sufficient space for the `COR_PRF_FUNCTION_ARGUMENT_INFO` structure of the function that is being inspected, and must indicate the size in the `pcbArgumentInfo` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e299b-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e299b-118">Requirements</span></span>  
 <span data-ttu-id="e299b-119">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e299b-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e299b-120">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e299b-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e299b-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e299b-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e299b-122">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e299b-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e299b-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="e299b-123">See Also</span></span>  
 [<span data-ttu-id="e299b-124">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="e299b-124">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)  
 [<span data-ttu-id="e299b-125">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="e299b-125">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)  
 [<span data-ttu-id="e299b-126">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="e299b-126">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)  
 [<span data-ttu-id="e299b-127">ICorProfilerInfo3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e299b-127">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [<span data-ttu-id="e299b-128">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="e299b-128">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="e299b-129">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="e299b-129">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
