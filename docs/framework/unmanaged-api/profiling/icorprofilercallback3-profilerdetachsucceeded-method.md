---
title: ICorProfilerCallback3::ProfilerDetachSucceeded (Método)
ms.date: 03/30/2017
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
ms.openlocfilehash: 93406dddf7babd8cf61032666737b993c2f721f4
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499602"
---
# <a name="icorprofilercallback3profilerdetachsucceeded-method"></a><span data-ttu-id="9a426-102">ICorProfilerCallback3::ProfilerDetachSucceeded (Método)</span><span class="sxs-lookup"><span data-stu-id="9a426-102">ICorProfilerCallback3::ProfilerDetachSucceeded Method</span></span>
<span data-ttu-id="9a426-103">Notifica al generador de perfiles que Common Language Runtime (CLR) está a punto de descargar el archivo DLL del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="9a426-103">Notifies the profiler that the common language runtime (CLR) is about to unload the profiler DLL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a426-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9a426-104">Syntax</span></span>  
  
```cpp  
HRESULT ProfilerDetachSucceeded();  
```  
  
## <a name="return-value"></a><span data-ttu-id="9a426-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9a426-105">Return Value</span></span>  
 <span data-ttu-id="9a426-106">Se omite el valor devuelto por esta devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="9a426-106">The return value from this callback is ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9a426-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9a426-107">Remarks</span></span>  
 <span data-ttu-id="9a426-108">La devolución de llamada `ProfilerDetachSucceeded` se emite después de que todos los subprocesos han salido del código del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="9a426-108">The `ProfilerDetachSucceeded` callback is issued after all threads have exited the profiler's code.</span></span> <span data-ttu-id="9a426-109">Cuando se llama a este método, el generador de perfiles debe realizar tareas de última hora que no son adecuadas para su destructor, tales como notificar a su interfaz de usuario o registrar componentes.</span><span class="sxs-lookup"><span data-stu-id="9a426-109">When this method is called, the profiler should perform any last-minute tasks that are not appropriate for its destructor, such as notifying its UI or logging component.</span></span> <span data-ttu-id="9a426-110">Sin embargo, el generador de perfiles no debe llamar a las funciones de las interfaces proporcionadas por el CLR durante esta devolución de llamada (como la [ICorProfilerInfo](icorprofilerinfo-interface.md) o las `IMetaData*` interfaces).</span><span class="sxs-lookup"><span data-stu-id="9a426-110">However, the profiler must not call functions on interfaces that are provided by the CLR during this callback (such as the [ICorProfilerInfo](icorprofilerinfo-interface.md) or `IMetaData*` interfaces).</span></span>  
  
 <span data-ttu-id="9a426-111">El CLR crea una entrada en el registro de eventos de aplicación de Windows para indicar que la operación de desasociación ha sido correcta.</span><span class="sxs-lookup"><span data-stu-id="9a426-111">The CLR creates an entry in the Windows Application event log to indicate that the detach operation is successful.</span></span>  
  
 <span data-ttu-id="9a426-112">Después de que el generador de perfiles vuelva de esta devolución de llamada, el CLR libera el objeto de generador de perfiles y descarga el archivo DLL del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="9a426-112">After the profiler returns from this callback, the CLR releases the profiler object and unloads the profiler DLL.</span></span> <span data-ttu-id="9a426-113">Por lo tanto, el generador de perfiles no debe realizar acciones que puedan hacer que la ejecución se realice dentro del archivo DLL del generador de perfiles después de que vuelva de esta devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="9a426-113">Therefore, the profiler must not perform any actions that would cause execution to occur inside the profiler DLL after it returns from this callback.</span></span> <span data-ttu-id="9a426-114">Por ejemplo, no debe crear subprocesos ni registrar devoluciones de llamada de temporizador.</span><span class="sxs-lookup"><span data-stu-id="9a426-114">For example, it must not create threads or register timer callbacks.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a426-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9a426-115">Requirements</span></span>  
 <span data-ttu-id="9a426-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a426-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a426-117">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9a426-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9a426-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9a426-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9a426-119">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a426-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a426-120">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="9a426-120">See also</span></span>

- [<span data-ttu-id="9a426-121">Interfaces de metadatos</span><span class="sxs-lookup"><span data-stu-id="9a426-121">Metadata Interfaces</span></span>](../metadata/metadata-interfaces.md)
- [<span data-ttu-id="9a426-122">ICorProfilerInfo3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9a426-122">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="9a426-123">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="9a426-123">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="9a426-124">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="9a426-124">Profiling</span></span>](index.md)
