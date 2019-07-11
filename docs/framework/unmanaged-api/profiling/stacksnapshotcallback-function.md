---
title: StackSnapshotCallback (Función)
ms.date: 03/30/2017
api_name:
- StackSnapshotCallback
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- StackSnapshotCallback
helpviewer_keywords:
- StackSnapshotCallback function [.NET Framework profiling]
ms.assetid: d0f235b2-91fe-4f82-b7d5-e5c64186eea8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6140ecda1d12c26e1936daee4eaad11cbd9b6ba4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781230"
---
# <a name="stacksnapshotcallback-function"></a><span data-ttu-id="473d9-102">StackSnapshotCallback (Función)</span><span class="sxs-lookup"><span data-stu-id="473d9-102">StackSnapshotCallback Function</span></span>
<span data-ttu-id="473d9-103">Proporciona el generador de perfiles con información sobre cada marco administrado y cada ejecución de los marcos no administrados en la pila durante un recorrido de pila, que se inicia mediante la [ICorProfilerInfo2:: DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="473d9-103">Provides the profiler with information about each managed frame and each run of unmanaged frames on the stack during a stack walk, which is initiated by the [ICorProfilerInfo2::DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="473d9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="473d9-104">Syntax</span></span>  
  
```cpp  
HRESULT __stdcall StackSnapshotCallback (  
    [in] FunctionID funcId,  
    [in] UINT_PTR ip,  
    [in] COR_PRF_FRAME_INFO frameInfo,  
    [in] ULONG32 contextSize,  
    [in] BYTE context[],  
    [in] void *clientData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="473d9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="473d9-105">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="473d9-106">[in] Si este valor es cero, esta devolución de llamada es para una ejecución de marcos no administrados; en caso contrario, es el identificador de una función administrada y esta devolución de llamada es para un marco administrado.</span><span class="sxs-lookup"><span data-stu-id="473d9-106">[in] If this value is zero, this callback is for a run of unmanaged frames; otherwise, it is the identifier of a managed function and this callback is for a managed frame.</span></span>  
  
 `ip`  
 <span data-ttu-id="473d9-107">[in] El valor de puntero de instrucción de código nativo en el marco.</span><span class="sxs-lookup"><span data-stu-id="473d9-107">[in] The value of the native code instruction pointer in the frame.</span></span>  
  
 `frameInfo`  
 <span data-ttu-id="473d9-108">[in] Un `COR_PRF_FRAME_INFO` valor al que hace referencia a información sobre el marco de pila.</span><span class="sxs-lookup"><span data-stu-id="473d9-108">[in] A `COR_PRF_FRAME_INFO` value that references information about the stack frame.</span></span> <span data-ttu-id="473d9-109">Este valor es válido para su uso solo durante esta devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="473d9-109">This value is valid for use only during this callback.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="473d9-110">[in] El tamaño de la `CONTEXT` estructura, que hace referencia el `context` parámetro.</span><span class="sxs-lookup"><span data-stu-id="473d9-110">[in] The size of the `CONTEXT` structure, which is referenced by the `context` parameter.</span></span>  
  
 `context`  
 <span data-ttu-id="473d9-111">[in] Un puntero a Win32 `CONTEXT` estructura que representa el estado de la CPU para este marco.</span><span class="sxs-lookup"><span data-stu-id="473d9-111">[in] A pointer to a Win32 `CONTEXT` structure that represents the state of the CPU for this frame.</span></span>  
  
 <span data-ttu-id="473d9-112">El `context` parámetro sólo es válido si se pasó el marcador COR_PRF_SNAPSHOT_CONTEXT `ICorProfilerInfo2::DoStackSnapshot`.</span><span class="sxs-lookup"><span data-stu-id="473d9-112">The `context` parameter is valid only if the COR_PRF_SNAPSHOT_CONTEXT flag was passed in `ICorProfilerInfo2::DoStackSnapshot`.</span></span>  
  
 `clientData`  
 <span data-ttu-id="473d9-113">[in] Un puntero a los datos de cliente, que se pasan directamente a través de `ICorProfilerInfo2::DoStackSnapshot`.</span><span class="sxs-lookup"><span data-stu-id="473d9-113">[in] A pointer to the client data, which is passed straight through from `ICorProfilerInfo2::DoStackSnapshot`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="473d9-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="473d9-114">Remarks</span></span>  
 <span data-ttu-id="473d9-115">El `StackSnapshotCallback` función se implementa el sistema de escritura del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="473d9-115">The `StackSnapshotCallback` function is implemented by the profiler writer.</span></span> <span data-ttu-id="473d9-116">Debe limitar la complejidad del trabajo realizado `StackSnapshotCallback`.</span><span class="sxs-lookup"><span data-stu-id="473d9-116">You must limit the complexity of work done in `StackSnapshotCallback`.</span></span> <span data-ttu-id="473d9-117">Por ejemplo, al usar `ICorProfilerInfo2::DoStackSnapshot` de forma asincrónica, el subproceso de destino puede mantener bloqueos.</span><span class="sxs-lookup"><span data-stu-id="473d9-117">For example, when using `ICorProfilerInfo2::DoStackSnapshot` in an asynchronous manner, the target thread may be holding locks.</span></span> <span data-ttu-id="473d9-118">Si el código dentro de `StackSnapshotCallback` requiere los mismos bloqueos, puede producirse un interbloqueo.</span><span class="sxs-lookup"><span data-stu-id="473d9-118">If code within `StackSnapshotCallback` requires the same locks, a deadlock could ensue.</span></span>  
  
 <span data-ttu-id="473d9-119">El `ICorProfilerInfo2::DoStackSnapshot` llamadas al método el `StackSnapshotCallback` función una vez por cada marco administrado o una vez por cada ejecución de marcos no administrados.</span><span class="sxs-lookup"><span data-stu-id="473d9-119">The `ICorProfilerInfo2::DoStackSnapshot` method calls the `StackSnapshotCallback` function once per managed frame or once per run of unmanaged frames.</span></span> <span data-ttu-id="473d9-120">Si `StackSnapshotCallback` se llama para una ejecución de marcos no administrados, el generador de perfiles puede utilizar el contexto del registro (que se hace referencia mediante el `context` parámetro) para realizar su propio recorrido de pila no administrado.</span><span class="sxs-lookup"><span data-stu-id="473d9-120">If `StackSnapshotCallback` is called for a run of unmanaged frames, the profiler may use the register context (referenced by the `context` parameter) to perform its own unmanaged stack walk.</span></span> <span data-ttu-id="473d9-121">En este caso, Win32 `CONTEXT` estructura representa el estado de la CPU para el marco insertado más recientemente en la ejecución de los marcos no administrados.</span><span class="sxs-lookup"><span data-stu-id="473d9-121">In this case, the Win32 `CONTEXT` structure represents the CPU state for the most recently pushed frame within the run of unmanaged frames.</span></span> <span data-ttu-id="473d9-122">Aunque Win32 `CONTEXT` estructura incluye valores para todos los registros, debe confiar sólo en los valores de registro de puntero de marco, el registro de puntero de pila, registro de puntero de instrucción y la no volátil (es decir, conservada) registros de enteros.</span><span class="sxs-lookup"><span data-stu-id="473d9-122">Although the Win32 `CONTEXT` structure includes values for all registers, you should rely only on the values of the stack pointer register, frame pointer register, instruction pointer register, and the nonvolatile (that is, preserved) integer registers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="473d9-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="473d9-123">Requirements</span></span>  
 <span data-ttu-id="473d9-124">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="473d9-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="473d9-125">**Encabezado**: CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="473d9-125">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="473d9-126">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="473d9-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="473d9-127">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="473d9-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="473d9-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="473d9-128">See also</span></span>

- [<span data-ttu-id="473d9-129">DoStackSnapshot (método)</span><span class="sxs-lookup"><span data-stu-id="473d9-129">DoStackSnapshot Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)
- [<span data-ttu-id="473d9-130">Funciones estáticas globales para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="473d9-130">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
