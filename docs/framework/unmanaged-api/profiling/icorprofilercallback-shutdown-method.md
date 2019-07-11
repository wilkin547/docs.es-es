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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9d63dd911a5f674a3ce0b02ec78de443c7aebf84
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67747174"
---
# <a name="icorprofilercallbackshutdown-method"></a><span data-ttu-id="c09c8-102">ICorProfilerCallback::Shutdown (Método)</span><span class="sxs-lookup"><span data-stu-id="c09c8-102">ICorProfilerCallback::Shutdown Method</span></span>
<span data-ttu-id="c09c8-103">Notifica al generador de perfiles que se va a cerrar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c09c8-103">Notifies the profiler that the application is shutting down.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c09c8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c09c8-104">Syntax</span></span>  
  
```cpp  
HRESULT Shutdown();  
```  
  
## <a name="remarks"></a><span data-ttu-id="c09c8-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c09c8-105">Remarks</span></span>  
 <span data-ttu-id="c09c8-106">El código del generador de perfiles no puede llamar con seguridad a los métodos de la [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) después de la interfaz del `Shutdown` se llama al método.</span><span class="sxs-lookup"><span data-stu-id="c09c8-106">The profiler code cannot safely call methods of the [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) interface after the `Shutdown` method is called.</span></span> <span data-ttu-id="c09c8-107">Las llamadas a `ICorProfilerInfo` métodos como resultado un comportamiento indefinido después el `Shutdown` devuelve del método.</span><span class="sxs-lookup"><span data-stu-id="c09c8-107">Any calls to `ICorProfilerInfo` methods result in undefined behavior after the `Shutdown` method returns.</span></span> <span data-ttu-id="c09c8-108">Algunos eventos inmutables aún pueden producirse tras el apagado; el generador de perfiles debe tener cuidado para devolver inmediatamente cuando esto ocurre.</span><span class="sxs-lookup"><span data-stu-id="c09c8-108">Certain immutable events may still occur after shutdown; the profiler should take care to return immediately when this occurs.</span></span>  
  
 <span data-ttu-id="c09c8-109">El `Shutdown` se llamará al método únicamente si ha iniciado la aplicación administrada que se está generando el perfil como código administrado (es decir, se administra el marco inicial de la pila de proceso).</span><span class="sxs-lookup"><span data-stu-id="c09c8-109">The `Shutdown` method will be called only if the managed application that is being profiled started as managed code (that is, the initial frame on the process stack is managed).</span></span> <span data-ttu-id="c09c8-110">Si la aplicación se inicia como código no administrado pero posteriormente pasa a código administrado, con lo que se crea una instancia de common language runtime (CLR), a continuación, `Shutdown` no se llamará.</span><span class="sxs-lookup"><span data-stu-id="c09c8-110">If the application started as unmanaged code but later jumped into managed code, thereby creating an instance of the common language runtime (CLR), then `Shutdown` will not be called.</span></span> <span data-ttu-id="c09c8-111">Para estos casos, el generador de perfiles debe incluir en su biblioteca un `DllMain` rutina que usa el DLL_PROCESS_DETACH valor para liberar los recursos y realizar el procesamiento de limpieza de sus datos, como vaciar los seguimientos en el disco y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="c09c8-111">For these cases, the profiler should include in its library a `DllMain` routine that uses the DLL_PROCESS_DETACH value to free any resources and perform clean-up processing of its data, such as flushing traces to disk and so on.</span></span>  
  
 <span data-ttu-id="c09c8-112">En general, el generador de perfiles debe hacer frente a los apagados inesperados.</span><span class="sxs-lookup"><span data-stu-id="c09c8-112">In general, the profiler must cope with unexpected shutdowns.</span></span> <span data-ttu-id="c09c8-113">Por ejemplo, podría detener un proceso de Win32 `TerminateProcess` método (declarado en Winbase.h).</span><span class="sxs-lookup"><span data-stu-id="c09c8-113">For example, a process might be halted by Win32's `TerminateProcess` method (declared in Winbase.h).</span></span> <span data-ttu-id="c09c8-114">En otros casos, CLR detendrá determinados subprocesos administrados (subprocesos en segundo plano) sin entregar los mensajes de destrucción ordenada para ellos.</span><span class="sxs-lookup"><span data-stu-id="c09c8-114">In other cases, the CLR will halt certain managed threads (background threads) without delivering orderly destruction messages for them.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c09c8-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c09c8-115">Requirements</span></span>  
 <span data-ttu-id="c09c8-116">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c09c8-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c09c8-117">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c09c8-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c09c8-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c09c8-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c09c8-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c09c8-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c09c8-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="c09c8-120">See also</span></span>

- [<span data-ttu-id="c09c8-121">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c09c8-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="c09c8-122">Initialize (método)</span><span class="sxs-lookup"><span data-stu-id="c09c8-122">Initialize Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)
