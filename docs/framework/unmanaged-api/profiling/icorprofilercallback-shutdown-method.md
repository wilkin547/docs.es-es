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
ms.openlocfilehash: 490f9dd5446a51bd07881cdb9825d737e380a63e
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865862"
---
# <a name="icorprofilercallbackshutdown-method"></a><span data-ttu-id="741bb-102">ICorProfilerCallback::Shutdown (Método)</span><span class="sxs-lookup"><span data-stu-id="741bb-102">ICorProfilerCallback::Shutdown Method</span></span>
<span data-ttu-id="741bb-103">Notifica al generador de perfiles que la aplicación se está cerrando.</span><span class="sxs-lookup"><span data-stu-id="741bb-103">Notifies the profiler that the application is shutting down.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="741bb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="741bb-104">Syntax</span></span>  
  
```cpp  
HRESULT Shutdown();  
```  
  
## <a name="remarks"></a><span data-ttu-id="741bb-105">Notas</span><span class="sxs-lookup"><span data-stu-id="741bb-105">Remarks</span></span>  
 <span data-ttu-id="741bb-106">El código del generador de perfiles no puede llamar a los métodos de la interfaz [ICorProfilerInfo](icorprofilerinfo-interface.md) de forma segura después de llamar al método `Shutdown`.</span><span class="sxs-lookup"><span data-stu-id="741bb-106">The profiler code cannot safely call methods of the [ICorProfilerInfo](icorprofilerinfo-interface.md) interface after the `Shutdown` method is called.</span></span> <span data-ttu-id="741bb-107">Cualquier llamada a métodos `ICorProfilerInfo` produce un comportamiento indefinido después de que el método `Shutdown` devuelva.</span><span class="sxs-lookup"><span data-stu-id="741bb-107">Any calls to `ICorProfilerInfo` methods result in undefined behavior after the `Shutdown` method returns.</span></span> <span data-ttu-id="741bb-108">Es posible que se sigan produciendo ciertos eventos inmutables después del apagado; el generador de perfiles debe tener cuidado de volver inmediatamente cuando esto suceda.</span><span class="sxs-lookup"><span data-stu-id="741bb-108">Certain immutable events may still occur after shutdown; the profiler should take care to return immediately when this occurs.</span></span>  
  
 <span data-ttu-id="741bb-109">Solo se llamará al método `Shutdown` si la aplicación administrada en la que se va a crear el perfiles se inicia como código administrado (es decir, el marco inicial en la pila de procesos se administra).</span><span class="sxs-lookup"><span data-stu-id="741bb-109">The `Shutdown` method will be called only if the managed application that is being profiled started as managed code (that is, the initial frame on the process stack is managed).</span></span> <span data-ttu-id="741bb-110">Si la aplicación se inició como código no administrado, pero posteriormente salta a código administrado, con lo que se crea una instancia del Common Language Runtime (CLR), no se llamará a `Shutdown`.</span><span class="sxs-lookup"><span data-stu-id="741bb-110">If the application started as unmanaged code but later jumped into managed code, thereby creating an instance of the common language runtime (CLR), then `Shutdown` will not be called.</span></span> <span data-ttu-id="741bb-111">En estos casos, el generador de perfiles debe incluir en su biblioteca una rutina `DllMain` que use el valor DLL_PROCESS_DETACH para liberar los recursos y realizar el procesamiento de la limpieza de sus datos, como el vaciado de seguimientos en el disco, etc.</span><span class="sxs-lookup"><span data-stu-id="741bb-111">For these cases, the profiler should include in its library a `DllMain` routine that uses the DLL_PROCESS_DETACH value to free any resources and perform clean-up processing of its data, such as flushing traces to disk and so on.</span></span>  
  
 <span data-ttu-id="741bb-112">En general, el generador de perfiles debe hacer frente a apagados inesperados.</span><span class="sxs-lookup"><span data-stu-id="741bb-112">In general, the profiler must cope with unexpected shutdowns.</span></span> <span data-ttu-id="741bb-113">Por ejemplo, un proceso podría detenerse mediante Win32 `TerminateProcess` método (declarado en Winbase. h).</span><span class="sxs-lookup"><span data-stu-id="741bb-113">For example, a process might be halted by Win32's `TerminateProcess` method (declared in Winbase.h).</span></span> <span data-ttu-id="741bb-114">En otros casos, CLR detendrá determinados subprocesos administrados (subprocesos en segundo plano) sin proporcionar mensajes de destrucción ordenada para ellos.</span><span class="sxs-lookup"><span data-stu-id="741bb-114">In other cases, the CLR will halt certain managed threads (background threads) without delivering orderly destruction messages for them.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="741bb-115">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="741bb-115">Requirements</span></span>  
 <span data-ttu-id="741bb-116">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="741bb-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="741bb-117">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="741bb-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="741bb-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="741bb-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="741bb-119">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="741bb-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="741bb-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="741bb-120">See also</span></span>

- [<span data-ttu-id="741bb-121">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="741bb-121">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="741bb-122">Initialize (método)</span><span class="sxs-lookup"><span data-stu-id="741bb-122">Initialize Method</span></span>](icorprofilercallback-initialize-method.md)
