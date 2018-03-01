---
title: "ICorProfilerCallback3::ProfilerDetachSucceeded (Método)"
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
- ICorProfilerCallback3.ProfilerDetachSucceeded Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback3::ProfilerDetachSucceeded
helpviewer_keywords:
- ProfilerDetachSucceeded method [.NET Framework profiling]
- ICorProfilerCallback3::ProfilerDetachSucceeded method [.NET Framework profiling]
ms.assetid: 05164966-16ce-4cc9-a530-43a640c00711
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d06671917094752287836800ebc492d5f0a5b595
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallback3profilerdetachsucceeded-method"></a><span data-ttu-id="a4d81-102">ICorProfilerCallback3::ProfilerDetachSucceeded (Método)</span><span class="sxs-lookup"><span data-stu-id="a4d81-102">ICorProfilerCallback3::ProfilerDetachSucceeded Method</span></span>
<span data-ttu-id="a4d81-103">Notifica al generador de perfiles que Common Language Runtime (CLR) está a punto de descargar el archivo DLL del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="a4d81-103">Notifies the profiler that the common language runtime (CLR) is about to unload the profiler DLL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4d81-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a4d81-104">Syntax</span></span>  
  
```  
HRESULT ProfilerDetachSucceeded();  
```  
  
## <a name="return-value"></a><span data-ttu-id="a4d81-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a4d81-105">Return Value</span></span>  
 <span data-ttu-id="a4d81-106">Se omite el valor devuelto por esta devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="a4d81-106">The return value from this callback is ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a4d81-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a4d81-107">Remarks</span></span>  
 <span data-ttu-id="a4d81-108">La devolución de llamada `ProfilerDetachSucceeded` se emite después de que todos los subprocesos han salido del código del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="a4d81-108">The `ProfilerDetachSucceeded` callback is issued after all threads have exited the profiler's code.</span></span> <span data-ttu-id="a4d81-109">Cuando se llama a este método, el generador de perfiles debe realizar tareas de última hora que no son adecuadas para su destructor, tales como notificar a su interfaz de usuario o registrar componentes.</span><span class="sxs-lookup"><span data-stu-id="a4d81-109">When this method is called, the profiler should perform any last-minute tasks that are not appropriate for its destructor, such as notifying its UI or logging component.</span></span> <span data-ttu-id="a4d81-110">Sin embargo, el generador de perfiles no debe llamar a funciones en las interfaces que se proporcionan con el CLR durante esta devolución de llamada (como el [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) o `IMetaData*` interfaces).</span><span class="sxs-lookup"><span data-stu-id="a4d81-110">However, the profiler must not call functions on interfaces that are provided by the CLR during this callback (such as the [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) or `IMetaData*` interfaces).</span></span>  
  
 <span data-ttu-id="a4d81-111">El CLR crea una entrada en el registro de eventos de aplicación de Windows para indicar que la operación de desasociación ha sido correcta.</span><span class="sxs-lookup"><span data-stu-id="a4d81-111">The CLR creates an entry in the Windows Application event log to indicate that the detach operation is successful.</span></span>  
  
 <span data-ttu-id="a4d81-112">Después de que el generador de perfiles vuelva de esta devolución de llamada, el CLR libera el objeto de generador de perfiles y descarga el archivo DLL del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="a4d81-112">After the profiler returns from this callback, the CLR releases the profiler object and unloads the profiler DLL.</span></span> <span data-ttu-id="a4d81-113">Por lo tanto, el generador de perfiles no debe realizar acciones que puedan hacer que la ejecución se realice dentro del archivo DLL del generador de perfiles después de que vuelva de esta devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="a4d81-113">Therefore, the profiler must not perform any actions that would cause execution to occur inside the profiler DLL after it returns from this callback.</span></span> <span data-ttu-id="a4d81-114">Por ejemplo, no debe crear subprocesos ni registrar devoluciones de llamada de temporizador.</span><span class="sxs-lookup"><span data-stu-id="a4d81-114">For example, it must not create threads or register timer callbacks.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4d81-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a4d81-115">Requirements</span></span>  
 <span data-ttu-id="a4d81-116">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a4d81-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4d81-117">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a4d81-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a4d81-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a4d81-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a4d81-119">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4d81-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4d81-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="a4d81-120">See Also</span></span>  
 [<span data-ttu-id="a4d81-121">Interfaces de metadatos</span><span class="sxs-lookup"><span data-stu-id="a4d81-121">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [<span data-ttu-id="a4d81-122">ICorProfilerInfo3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a4d81-122">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [<span data-ttu-id="a4d81-123">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="a4d81-123">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="a4d81-124">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="a4d81-124">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
