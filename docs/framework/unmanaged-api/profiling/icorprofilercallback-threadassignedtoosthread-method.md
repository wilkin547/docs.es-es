---
title: ICorProfilerCallback::ThreadAssignedToOSThread (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ThreadAssignedToOSThread
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ThreadAssignedToOSThread
helpviewer_keywords:
- ThreadAssignedToOSThread method [.NET Framework profiling]
- ICorProfilerCallback::ThreadAssignedToOSThread method [.NET Framework profiling]
ms.assetid: f9671e5a-7b14-4f5b-8404-58136422c8b2
topic_type:
- apiref
ms.openlocfilehash: 1b69c0522c47d4e675180af67adab166626da4d7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440025"
---
# <a name="icorprofilercallbackthreadassignedtoosthread-method"></a><span data-ttu-id="27dfc-102">ICorProfilerCallback::ThreadAssignedToOSThread (Método)</span><span class="sxs-lookup"><span data-stu-id="27dfc-102">ICorProfilerCallback::ThreadAssignedToOSThread Method</span></span>
<span data-ttu-id="27dfc-103">Notifica al generador de perfiles que un subproceso administrado se está implementando utilizando un subproceso del sistema operativo determinado.</span><span class="sxs-lookup"><span data-stu-id="27dfc-103">Notifies the profiler that a managed thread is being implemented using a particular operating system thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27dfc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="27dfc-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadAssignedToOSThread(  
    [in] ThreadID managedThreadId,  
    [in] DWORD    osThreadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="27dfc-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="27dfc-105">Parameters</span></span>  
 `managedThreadId`  
 <span data-ttu-id="27dfc-106">de Identificador del subproceso administrado.</span><span class="sxs-lookup"><span data-stu-id="27dfc-106">[in] The identifier of the managed thread.</span></span>  
  
 `osThreadId`  
 <span data-ttu-id="27dfc-107">de Identificador del subproceso del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="27dfc-107">[in] The identifier of the operating system thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="27dfc-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="27dfc-108">Remarks</span></span>  
 <span data-ttu-id="27dfc-109">La devolución de llamada de `ThreadAssignedToOSThread` existe para que el generador de perfiles pueda mantener una asignación precisa entre fibras de subprocesos del sistema operativo y subprocesos administrados.</span><span class="sxs-lookup"><span data-stu-id="27dfc-109">The `ThreadAssignedToOSThread` callback exists so that the profiler can maintain an accurate mapping across fibers of operating system threads to managed threads.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27dfc-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="27dfc-110">Requirements</span></span>  
 <span data-ttu-id="27dfc-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="27dfc-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27dfc-112">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="27dfc-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="27dfc-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="27dfc-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="27dfc-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27dfc-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27dfc-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="27dfc-115">See also</span></span>

- [<span data-ttu-id="27dfc-116">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="27dfc-116">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
