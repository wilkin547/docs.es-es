---
description: 'Más información acerca de: ICorProfilerCallback:: Shutdown (método)'
title: ICorProfilerCallback::Shutdown (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.Shutdown
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::Shutdown
helpviewer_keywords:
- ICorProfilerCallback::Shutdown method [.NET Framework profiling]
- Shutdown method [.NET Framework profiling]
ms.assetid: 1ea194f0-a331-4855-a2ce-37393b8e5f84
topic_type:
- apiref
ms.openlocfilehash: 7afc274579f248ee190e379160f2709b5cb9881a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99657325"
---
# <a name="icorprofilercallbackshutdown-method"></a><span data-ttu-id="437fd-103">ICorProfilerCallback::Shutdown (Método)</span><span class="sxs-lookup"><span data-stu-id="437fd-103">ICorProfilerCallback::Shutdown Method</span></span>

<span data-ttu-id="437fd-104">Notifica al generador de perfiles que la aplicación se está cerrando.</span><span class="sxs-lookup"><span data-stu-id="437fd-104">Notifies the profiler that the application is shutting down.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="437fd-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="437fd-105">Syntax</span></span>  
  
```cpp  
HRESULT Shutdown();  
```  
  
## <a name="remarks"></a><span data-ttu-id="437fd-106">Observaciones</span><span class="sxs-lookup"><span data-stu-id="437fd-106">Remarks</span></span>  

 <span data-ttu-id="437fd-107">El código del generador de perfiles no puede llamar de forma segura a los métodos de la interfaz [ICorProfilerInfo](icorprofilerinfo-interface.md) después de `Shutdown` llamar al método.</span><span class="sxs-lookup"><span data-stu-id="437fd-107">The profiler code cannot safely call methods of the [ICorProfilerInfo](icorprofilerinfo-interface.md) interface after the `Shutdown` method is called.</span></span> <span data-ttu-id="437fd-108">Cualquier llamada a `ICorProfilerInfo` métodos produce un comportamiento indefinido después de que el `Shutdown` método devuelva un resultado.</span><span class="sxs-lookup"><span data-stu-id="437fd-108">Any calls to `ICorProfilerInfo` methods result in undefined behavior after the `Shutdown` method returns.</span></span> <span data-ttu-id="437fd-109">Es posible que se sigan produciendo ciertos eventos inmutables después del apagado; el generador de perfiles debe tener cuidado de volver inmediatamente cuando esto suceda.</span><span class="sxs-lookup"><span data-stu-id="437fd-109">Certain immutable events may still occur after shutdown; the profiler should take care to return immediately when this occurs.</span></span>  
  
 <span data-ttu-id="437fd-110">`Shutdown`Solo se llamará al método si la aplicación administrada en la que se va a crear el perfiles se inicia como código administrado (es decir, el marco inicial en la pila de procesos está administrado).</span><span class="sxs-lookup"><span data-stu-id="437fd-110">The `Shutdown` method will be called only if the managed application that is being profiled started as managed code (that is, the initial frame on the process stack is managed).</span></span> <span data-ttu-id="437fd-111">Si la aplicación se inició como código no administrado, pero posteriormente se saltó a código administrado, con lo que se crea una instancia del Common Language Runtime (CLR), entonces `Shutdown` no se llamará a.</span><span class="sxs-lookup"><span data-stu-id="437fd-111">If the application started as unmanaged code but later jumped into managed code, thereby creating an instance of the common language runtime (CLR), then `Shutdown` will not be called.</span></span> <span data-ttu-id="437fd-112">En estos casos, el generador de perfiles debe incluir en su biblioteca una `DllMain` rutina que use el valor DLL_PROCESS_DETACH para liberar los recursos y realizar el procesamiento de limpieza de sus datos, como el vaciado de seguimientos en el disco, etc.</span><span class="sxs-lookup"><span data-stu-id="437fd-112">For these cases, the profiler should include in its library a `DllMain` routine that uses the DLL_PROCESS_DETACH value to free any resources and perform clean-up processing of its data, such as flushing traces to disk and so on.</span></span>  
  
 <span data-ttu-id="437fd-113">En general, el generador de perfiles debe hacer frente a apagados inesperados.</span><span class="sxs-lookup"><span data-stu-id="437fd-113">In general, the profiler must cope with unexpected shutdowns.</span></span> <span data-ttu-id="437fd-114">Por ejemplo, un proceso podría detenerse mediante el `TerminateProcess` método Win32 (declarado en Winbase. h).</span><span class="sxs-lookup"><span data-stu-id="437fd-114">For example, a process might be halted by Win32's `TerminateProcess` method (declared in Winbase.h).</span></span> <span data-ttu-id="437fd-115">En otros casos, CLR detendrá determinados subprocesos administrados (subprocesos en segundo plano) sin proporcionar mensajes de destrucción ordenada para ellos.</span><span class="sxs-lookup"><span data-stu-id="437fd-115">In other cases, the CLR will halt certain managed threads (background threads) without delivering orderly destruction messages for them.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="437fd-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="437fd-116">Requirements</span></span>  

 <span data-ttu-id="437fd-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="437fd-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="437fd-118">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="437fd-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="437fd-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="437fd-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="437fd-120">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="437fd-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="437fd-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="437fd-121">See also</span></span>

- [<span data-ttu-id="437fd-122">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="437fd-122">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="437fd-123">Método Initialize</span><span class="sxs-lookup"><span data-stu-id="437fd-123">Initialize Method</span></span>](icorprofilercallback-initialize-method.md)
