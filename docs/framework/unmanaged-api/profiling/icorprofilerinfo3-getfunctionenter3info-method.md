---
title: ICorProfilerInfo3::GetFunctionEnter3Info (Método)
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0a8dd1f92dc36dcda58bdecbdb18e8d3509f7c6e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782161"
---
# <a name="icorprofilerinfo3getfunctionenter3info-method"></a><span data-ttu-id="5ee1b-102">ICorProfilerInfo3::GetFunctionEnter3Info (Método)</span><span class="sxs-lookup"><span data-stu-id="5ee1b-102">ICorProfilerInfo3::GetFunctionEnter3Info Method</span></span>
<span data-ttu-id="5ee1b-103">Proporciona la información de marco y el argumento de pila de la función que se va a notificar al generador de perfiles la [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md) función.</span><span class="sxs-lookup"><span data-stu-id="5ee1b-103">Provides the stack frame and argument information of the function that is being reported to the profiler by the [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md) function.</span></span> <span data-ttu-id="5ee1b-104">Solo se puede llamar a este método durante la devolución de llamada `FunctionEnter3WithInfo`.</span><span class="sxs-lookup"><span data-stu-id="5ee1b-104">This method can be called only during the `FunctionEnter3WithInfo` callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ee1b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5ee1b-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionEnter3Info(  
            [in]  FunctionID functionId,   
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo,  
            [in, out] ULONG *pcbArgumentInfo,  
            [out, size_is(*pcbArgumentInfo)]  
                  COR_PRF_FUNCTION_ARGUMENT_INFO *pArgumentInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5ee1b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5ee1b-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="5ee1b-107">[in] `FunctionID` de la función que se está especificando.</span><span class="sxs-lookup"><span data-stu-id="5ee1b-107">[in] The `FunctionID` of the function that is being entered.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="5ee1b-108">[in] Controlador opaco que representa información sobre un marco de pila determinado.</span><span class="sxs-lookup"><span data-stu-id="5ee1b-108">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="5ee1b-109">El generador de perfiles debe proporcionar el mismo `eltInfo` dado por la [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md) función.</span><span class="sxs-lookup"><span data-stu-id="5ee1b-109">The profiler should provide the same `eltInfo` that it was given by the [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md) function.</span></span>  
  
 `pFrameInfo`  
 <span data-ttu-id="5ee1b-110">[out] Controlador opaco que representa información genérica sobre un marco de pila determinado.</span><span class="sxs-lookup"><span data-stu-id="5ee1b-110">[out] An opaque handle that represents generics information about a given stack frame.</span></span> <span data-ttu-id="5ee1b-111">Este identificador es válido solo durante la devolución de llamada `FunctionEnter3WithInfo` en la que el generador de perfiles llamó al método `GetFunctionEnter3Info`.</span><span class="sxs-lookup"><span data-stu-id="5ee1b-111">This handle is valid only during the `FunctionEnter3WithInfo` callback in which the profiler called the `GetFunctionEnter3Info` method.</span></span>  
  
 `pcbArgumentInfo`  
 <span data-ttu-id="5ee1b-112">[in, out] Un puntero al tamaño total, en bytes, de la [COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md) estructura (más cualquier adicionales [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) estructuras de los intervalos de argumento apuntados `pArgumentInfo`).</span><span class="sxs-lookup"><span data-stu-id="5ee1b-112">[in, out] A pointer to the total size, in bytes, of the [COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md) structure (plus any additional [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) structures for the argument ranges pointed to by `pArgumentInfo`).</span></span> <span data-ttu-id="5ee1b-113">Si el tamaño especificado no es suficiente, se devuelve ERROR_INSUFFICIENT_BUFFER y el tamaño esperado se almacena en `pcbArgumentInfo`.</span><span class="sxs-lookup"><span data-stu-id="5ee1b-113">If the specified size is not enough, ERROR_INSUFFICIENT_BUFFER is returned and the expected size is stored in `pcbArgumentInfo`.</span></span> <span data-ttu-id="5ee1b-114">Para llamar a `GetFunctionEnter3Info` para recuperar el valor de `*pcbArgumentInfo` esperado, establezca `*pcbArgumentInfo`=0 y `pArgumentInfo`=NULL.</span><span class="sxs-lookup"><span data-stu-id="5ee1b-114">To call `GetFunctionEnter3Info` just to retrieve the expected value for `*pcbArgumentInfo`, set `*pcbArgumentInfo`=0 and `pArgumentInfo`=NULL.</span></span>  
  
 `pArgumentInfo`  
 <span data-ttu-id="5ee1b-115">[out] Un puntero a un [COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md) estructura que describe las ubicaciones de los argumentos de función en la memoria, en orden de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="5ee1b-115">[out] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md) structure that describes the locations of the function's arguments in memory, in left-to-right order.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5ee1b-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5ee1b-116">Remarks</span></span>  
 <span data-ttu-id="5ee1b-117">El generador de perfiles debe asignar espacio suficiente para la estructura `COR_PRF_FUNCTION_ARGUMENT_INFO` de la función que se está inspeccionando y debe indicar el tamaño del parámetro `pcbArgumentInfo`.</span><span class="sxs-lookup"><span data-stu-id="5ee1b-117">The profiler must allocate sufficient space for the `COR_PRF_FUNCTION_ARGUMENT_INFO` structure of the function that is being inspected, and must indicate the size in the `pcbArgumentInfo` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ee1b-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5ee1b-118">Requirements</span></span>  
 <span data-ttu-id="5ee1b-119">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ee1b-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ee1b-120">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5ee1b-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5ee1b-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5ee1b-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5ee1b-122">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ee1b-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ee1b-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="5ee1b-123">See also</span></span>

- [<span data-ttu-id="5ee1b-124">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="5ee1b-124">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)
- [<span data-ttu-id="5ee1b-125">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="5ee1b-125">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [<span data-ttu-id="5ee1b-126">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="5ee1b-126">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [<span data-ttu-id="5ee1b-127">ICorProfilerInfo3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5ee1b-127">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="5ee1b-128">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="5ee1b-128">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="5ee1b-129">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="5ee1b-129">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
