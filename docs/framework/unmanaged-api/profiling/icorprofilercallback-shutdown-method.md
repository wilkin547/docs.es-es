---
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
ms.openlocfilehash: f6873de1a864489d144a671b1a9e1349eaf77d15
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503190"
---
# <a name="icorprofilercallbackshutdown-method"></a><span data-ttu-id="9158d-102">ICorProfilerCallback::Shutdown (Método)</span><span class="sxs-lookup"><span data-stu-id="9158d-102">ICorProfilerCallback::Shutdown Method</span></span>
<span data-ttu-id="9158d-103">Notifica al generador de perfiles que la aplicación se está cerrando.</span><span class="sxs-lookup"><span data-stu-id="9158d-103">Notifies the profiler that the application is shutting down.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9158d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9158d-104">Syntax</span></span>  
  
```cpp  
HRESULT Shutdown();  
```  
  
## <a name="remarks"></a><span data-ttu-id="9158d-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9158d-105">Remarks</span></span>  
 <span data-ttu-id="9158d-106">El código del generador de perfiles no puede llamar de forma segura a los métodos de la interfaz [ICorProfilerInfo](icorprofilerinfo-interface.md) después de `Shutdown` llamar al método.</span><span class="sxs-lookup"><span data-stu-id="9158d-106">The profiler code cannot safely call methods of the [ICorProfilerInfo](icorprofilerinfo-interface.md) interface after the `Shutdown` method is called.</span></span> <span data-ttu-id="9158d-107">Cualquier llamada a `ICorProfilerInfo` métodos produce un comportamiento indefinido después de que el `Shutdown` método devuelva un resultado.</span><span class="sxs-lookup"><span data-stu-id="9158d-107">Any calls to `ICorProfilerInfo` methods result in undefined behavior after the `Shutdown` method returns.</span></span> <span data-ttu-id="9158d-108">Es posible que se sigan produciendo ciertos eventos inmutables después del apagado; el generador de perfiles debe tener cuidado de volver inmediatamente cuando esto suceda.</span><span class="sxs-lookup"><span data-stu-id="9158d-108">Certain immutable events may still occur after shutdown; the profiler should take care to return immediately when this occurs.</span></span>  
  
 <span data-ttu-id="9158d-109">`Shutdown`Solo se llamará al método si la aplicación administrada en la que se va a crear el perfiles se inicia como código administrado (es decir, el marco inicial en la pila de procesos está administrado).</span><span class="sxs-lookup"><span data-stu-id="9158d-109">The `Shutdown` method will be called only if the managed application that is being profiled started as managed code (that is, the initial frame on the process stack is managed).</span></span> <span data-ttu-id="9158d-110">Si la aplicación se inició como código no administrado, pero posteriormente se saltó a código administrado, con lo que se crea una instancia del Common Language Runtime (CLR), entonces `Shutdown` no se llamará a.</span><span class="sxs-lookup"><span data-stu-id="9158d-110">If the application started as unmanaged code but later jumped into managed code, thereby creating an instance of the common language runtime (CLR), then `Shutdown` will not be called.</span></span> <span data-ttu-id="9158d-111">En estos casos, el generador de perfiles debe incluir en su biblioteca una `DllMain` rutina que use el valor DLL_PROCESS_DETACH para liberar los recursos y realizar el procesamiento de limpieza de sus datos, como el vaciado de seguimientos en el disco, etc.</span><span class="sxs-lookup"><span data-stu-id="9158d-111">For these cases, the profiler should include in its library a `DllMain` routine that uses the DLL_PROCESS_DETACH value to free any resources and perform clean-up processing of its data, such as flushing traces to disk and so on.</span></span>  
  
 <span data-ttu-id="9158d-112">En general, el generador de perfiles debe hacer frente a apagados inesperados.</span><span class="sxs-lookup"><span data-stu-id="9158d-112">In general, the profiler must cope with unexpected shutdowns.</span></span> <span data-ttu-id="9158d-113">Por ejemplo, un proceso podría detenerse mediante el `TerminateProcess` método Win32 (declarado en Winbase. h).</span><span class="sxs-lookup"><span data-stu-id="9158d-113">For example, a process might be halted by Win32's `TerminateProcess` method (declared in Winbase.h).</span></span> <span data-ttu-id="9158d-114">En otros casos, CLR detendrá determinados subprocesos administrados (subprocesos en segundo plano) sin proporcionar mensajes de destrucción ordenada para ellos.</span><span class="sxs-lookup"><span data-stu-id="9158d-114">In other cases, the CLR will halt certain managed threads (background threads) without delivering orderly destruction messages for them.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9158d-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9158d-115">Requirements</span></span>  
 <span data-ttu-id="9158d-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9158d-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9158d-117">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9158d-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9158d-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9158d-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9158d-119">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9158d-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9158d-120">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="9158d-120">See also</span></span>

- [<span data-ttu-id="9158d-121">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9158d-121">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="9158d-122">Método Initialize</span><span class="sxs-lookup"><span data-stu-id="9158d-122">Initialize Method</span></span>](icorprofilercallback-initialize-method.md)
