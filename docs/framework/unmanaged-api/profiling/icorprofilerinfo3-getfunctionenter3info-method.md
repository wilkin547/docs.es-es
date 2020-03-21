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
ms.openlocfilehash: 50d16b8036144d6ede349149fa4ae37344064d8b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177025"
---
# <a name="icorprofilerinfo3getfunctionenter3info-method"></a><span data-ttu-id="71c17-102">ICorProfilerInfo3::GetFunctionEnter3Info (Método)</span><span class="sxs-lookup"><span data-stu-id="71c17-102">ICorProfilerInfo3::GetFunctionEnter3Info Method</span></span>
<span data-ttu-id="71c17-103">Proporciona la información de marco y argumento de pila de la función que se notifica al generador de perfiles mediante la [función FunctionEnter3WithInfo.](functionenter3withinfo-function.md)</span><span class="sxs-lookup"><span data-stu-id="71c17-103">Provides the stack frame and argument information of the function that is being reported to the profiler by the [FunctionEnter3WithInfo](functionenter3withinfo-function.md) function.</span></span> <span data-ttu-id="71c17-104">Solo se puede llamar a este método durante la devolución de llamada `FunctionEnter3WithInfo`.</span><span class="sxs-lookup"><span data-stu-id="71c17-104">This method can be called only during the `FunctionEnter3WithInfo` callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71c17-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="71c17-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionEnter3Info(  
            [in]  FunctionID functionId,
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo,  
            [in, out] ULONG *pcbArgumentInfo,  
            [out, size_is(*pcbArgumentInfo)]  
                  COR_PRF_FUNCTION_ARGUMENT_INFO *pArgumentInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="71c17-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="71c17-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="71c17-107">[in] `FunctionID` de la función que se está especificando.</span><span class="sxs-lookup"><span data-stu-id="71c17-107">[in] The `FunctionID` of the function that is being entered.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="71c17-108">[in] Controlador opaco que representa información sobre un marco de pila determinado.</span><span class="sxs-lookup"><span data-stu-id="71c17-108">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="71c17-109">El generador de perfiles debe proporcionar lo mismo `eltInfo` que lo proporcionó la función [FunctionEnter3WithInfo.](functionenter3withinfo-function.md)</span><span class="sxs-lookup"><span data-stu-id="71c17-109">The profiler should provide the same `eltInfo` that it was given by the [FunctionEnter3WithInfo](functionenter3withinfo-function.md) function.</span></span>  
  
 `pFrameInfo`  
 <span data-ttu-id="71c17-110">[out] Controlador opaco que representa información genérica sobre un marco de pila determinado.</span><span class="sxs-lookup"><span data-stu-id="71c17-110">[out] An opaque handle that represents generics information about a given stack frame.</span></span> <span data-ttu-id="71c17-111">Este identificador es válido solo durante la devolución de llamada `FunctionEnter3WithInfo` en la que el generador de perfiles llamó al método `GetFunctionEnter3Info`.</span><span class="sxs-lookup"><span data-stu-id="71c17-111">This handle is valid only during the `FunctionEnter3WithInfo` callback in which the profiler called the `GetFunctionEnter3Info` method.</span></span>  
  
 `pcbArgumentInfo`  
 <span data-ttu-id="71c17-112">[adentro, fuera] Un puntero al tamaño total, en bytes, de la estructura [COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md) (además `pArgumentInfo`de cualquier estructura [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) adicional para los intervalos de argumentos a los que apunta ).</span><span class="sxs-lookup"><span data-stu-id="71c17-112">[in, out] A pointer to the total size, in bytes, of the [COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md) structure (plus any additional [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) structures for the argument ranges pointed to by `pArgumentInfo`).</span></span> <span data-ttu-id="71c17-113">Si el tamaño especificado no es suficiente, se devuelve ERROR_INSUFFICIENT_BUFFER y el tamaño esperado se almacena en `pcbArgumentInfo`.</span><span class="sxs-lookup"><span data-stu-id="71c17-113">If the specified size is not enough, ERROR_INSUFFICIENT_BUFFER is returned and the expected size is stored in `pcbArgumentInfo`.</span></span> <span data-ttu-id="71c17-114">Para llamar a `GetFunctionEnter3Info` para recuperar el valor de `*pcbArgumentInfo` esperado, establezca `*pcbArgumentInfo`=0 y `pArgumentInfo`=NULL.</span><span class="sxs-lookup"><span data-stu-id="71c17-114">To call `GetFunctionEnter3Info` just to retrieve the expected value for `*pcbArgumentInfo`, set `*pcbArgumentInfo`=0 and `pArgumentInfo`=NULL.</span></span>  
  
 `pArgumentInfo`  
 <span data-ttu-id="71c17-115">[fuera] Puntero a una estructura [de COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md) que describe las ubicaciones de los argumentos de la función en la memoria, en orden de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="71c17-115">[out] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md) structure that describes the locations of the function's arguments in memory, in left-to-right order.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="71c17-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="71c17-116">Remarks</span></span>  
 <span data-ttu-id="71c17-117">El generador de perfiles debe asignar espacio suficiente para la estructura `COR_PRF_FUNCTION_ARGUMENT_INFO` de la función que se está inspeccionando y debe indicar el tamaño del parámetro `pcbArgumentInfo`.</span><span class="sxs-lookup"><span data-stu-id="71c17-117">The profiler must allocate sufficient space for the `COR_PRF_FUNCTION_ARGUMENT_INFO` structure of the function that is being inspected, and must indicate the size in the `pcbArgumentInfo` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71c17-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="71c17-118">Requirements</span></span>  
 <span data-ttu-id="71c17-119">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71c17-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71c17-120">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="71c17-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="71c17-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="71c17-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="71c17-122">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71c17-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71c17-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="71c17-123">See also</span></span>

- [<span data-ttu-id="71c17-124">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="71c17-124">FunctionEnter3WithInfo</span></span>](functionenter3withinfo-function.md)
- [<span data-ttu-id="71c17-125">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="71c17-125">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="71c17-126">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="71c17-126">FunctionTailcall3WithInfo</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="71c17-127">ICorProfilerInfo3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="71c17-127">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="71c17-128">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="71c17-128">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="71c17-129">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="71c17-129">Profiling</span></span>](index.md)
