---
description: 'Más información acerca de: StackSnapshotCallback (función)'
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
ms.openlocfilehash: a49588bc3277956acad612afd0fcab3fa7edffbd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99736861"
---
# <a name="stacksnapshotcallback-function"></a><span data-ttu-id="510fa-103">StackSnapshotCallback (Función)</span><span class="sxs-lookup"><span data-stu-id="510fa-103">StackSnapshotCallback Function</span></span>

<span data-ttu-id="510fa-104">Proporciona al generador de perfiles información sobre cada marco administrado y cada ejecución de marcos no administrados en la pila durante un recorrido de pila, iniciado por el método [ICorProfilerInfo2::D ostacksnapshot](icorprofilerinfo2-dostacksnapshot-method.md) .</span><span class="sxs-lookup"><span data-stu-id="510fa-104">Provides the profiler with information about each managed frame and each run of unmanaged frames on the stack during a stack walk, which is initiated by the [ICorProfilerInfo2::DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="510fa-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="510fa-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="510fa-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="510fa-106">Parameters</span></span>  

 `funcId`  
 <span data-ttu-id="510fa-107">de Si este valor es cero, esta devolución de llamada es para una ejecución de marcos no administrados; de lo contrario, es el identificador de una función administrada y esta devolución de llamada es para un marco administrado.</span><span class="sxs-lookup"><span data-stu-id="510fa-107">[in] If this value is zero, this callback is for a run of unmanaged frames; otherwise, it is the identifier of a managed function and this callback is for a managed frame.</span></span>  
  
 `ip`  
 <span data-ttu-id="510fa-108">de El valor del puntero de instrucción de código nativo en el marco.</span><span class="sxs-lookup"><span data-stu-id="510fa-108">[in] The value of the native code instruction pointer in the frame.</span></span>  
  
 `frameInfo`  
 <span data-ttu-id="510fa-109">de `COR_PRF_FRAME_INFO` Valor que hace referencia a información sobre el marco de pila.</span><span class="sxs-lookup"><span data-stu-id="510fa-109">[in] A `COR_PRF_FRAME_INFO` value that references information about the stack frame.</span></span> <span data-ttu-id="510fa-110">Este valor solo es válido para su uso durante esta devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="510fa-110">This value is valid for use only during this callback.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="510fa-111">de Tamaño de la `CONTEXT` estructura, al que hace referencia el `context` parámetro.</span><span class="sxs-lookup"><span data-stu-id="510fa-111">[in] The size of the `CONTEXT` structure, which is referenced by the `context` parameter.</span></span>  
  
 `context`  
 <span data-ttu-id="510fa-112">de Puntero a una `CONTEXT` estructura de Win32 que representa el estado de la CPU para este marco.</span><span class="sxs-lookup"><span data-stu-id="510fa-112">[in] A pointer to a Win32 `CONTEXT` structure that represents the state of the CPU for this frame.</span></span>  
  
 <span data-ttu-id="510fa-113">El `context` parámetro solo es válido si se ha pasado la marca COR_PRF_SNAPSHOT_CONTEXT `ICorProfilerInfo2::DoStackSnapshot` .</span><span class="sxs-lookup"><span data-stu-id="510fa-113">The `context` parameter is valid only if the COR_PRF_SNAPSHOT_CONTEXT flag was passed in `ICorProfilerInfo2::DoStackSnapshot`.</span></span>  
  
 `clientData`  
 <span data-ttu-id="510fa-114">de Puntero a los datos del cliente, que se pasa directamente a partir de `ICorProfilerInfo2::DoStackSnapshot` .</span><span class="sxs-lookup"><span data-stu-id="510fa-114">[in] A pointer to the client data, which is passed straight through from `ICorProfilerInfo2::DoStackSnapshot`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="510fa-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="510fa-115">Remarks</span></span>  

 <span data-ttu-id="510fa-116">El `StackSnapshotCallback` escritor del generador de perfiles implementa la función.</span><span class="sxs-lookup"><span data-stu-id="510fa-116">The `StackSnapshotCallback` function is implemented by the profiler writer.</span></span> <span data-ttu-id="510fa-117">Debe limitar la complejidad del trabajo realizado en `StackSnapshotCallback` .</span><span class="sxs-lookup"><span data-stu-id="510fa-117">You must limit the complexity of work done in `StackSnapshotCallback`.</span></span> <span data-ttu-id="510fa-118">Por ejemplo, cuando `ICorProfilerInfo2::DoStackSnapshot` se usa de forma asincrónica, el subproceso de destino puede estar manteniendo bloqueos.</span><span class="sxs-lookup"><span data-stu-id="510fa-118">For example, when using `ICorProfilerInfo2::DoStackSnapshot` in an asynchronous manner, the target thread may be holding locks.</span></span> <span data-ttu-id="510fa-119">Si el código dentro de `StackSnapshotCallback` requiere los mismos bloqueos, podría producirse un interbloqueo.</span><span class="sxs-lookup"><span data-stu-id="510fa-119">If code within `StackSnapshotCallback` requires the same locks, a deadlock could ensue.</span></span>  
  
 <span data-ttu-id="510fa-120">El `ICorProfilerInfo2::DoStackSnapshot` método llama a la `StackSnapshotCallback` función una vez por cada marco administrado o una vez por cada ejecución de fotogramas no administrados.</span><span class="sxs-lookup"><span data-stu-id="510fa-120">The `ICorProfilerInfo2::DoStackSnapshot` method calls the `StackSnapshotCallback` function once per managed frame or once per run of unmanaged frames.</span></span> <span data-ttu-id="510fa-121">Si `StackSnapshotCallback` se llama a para una ejecución de marcos no administrados, el generador de perfiles puede usar el contexto de registro (al que hace referencia el `context` parámetro) para realizar su propio recorrido de pila no administrado.</span><span class="sxs-lookup"><span data-stu-id="510fa-121">If `StackSnapshotCallback` is called for a run of unmanaged frames, the profiler may use the register context (referenced by the `context` parameter) to perform its own unmanaged stack walk.</span></span> <span data-ttu-id="510fa-122">En este caso, la estructura de Win32 `CONTEXT` representa el estado de la CPU para el marco insertado más recientemente en la ejecución de fotogramas no administrados.</span><span class="sxs-lookup"><span data-stu-id="510fa-122">In this case, the Win32 `CONTEXT` structure represents the CPU state for the most recently pushed frame within the run of unmanaged frames.</span></span> <span data-ttu-id="510fa-123">Aunque la `CONTEXT` estructura Win32 incluye valores para todos los registros, solo debe confiar en los valores del registro de puntero de pila, el registro de puntero de marco, el registro de puntero de instrucción y los registros de entero no volátiles (es decir, conservados).</span><span class="sxs-lookup"><span data-stu-id="510fa-123">Although the Win32 `CONTEXT` structure includes values for all registers, you should rely only on the values of the stack pointer register, frame pointer register, instruction pointer register, and the nonvolatile (that is, preserved) integer registers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="510fa-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="510fa-124">Requirements</span></span>  

 <span data-ttu-id="510fa-125">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="510fa-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="510fa-126">**Encabezado:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="510fa-126">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="510fa-127">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="510fa-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="510fa-128">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="510fa-128">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="510fa-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="510fa-129">See also</span></span>

- [<span data-ttu-id="510fa-130">Método DoStackSnapshot</span><span class="sxs-lookup"><span data-stu-id="510fa-130">DoStackSnapshot Method</span></span>](icorprofilerinfo2-dostacksnapshot-method.md)
- [<span data-ttu-id="510fa-131">Funciones estáticas globales para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="510fa-131">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
