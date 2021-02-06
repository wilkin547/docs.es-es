---
description: 'Más información sobre: ICorProfilerCallback:: Threadassignedtoosthread ((método)'
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
ms.openlocfilehash: 04fba4cabb0ac58b3afeaae1fd579865335a9e14
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99647991"
---
# <a name="icorprofilercallbackthreadassignedtoosthread-method"></a><span data-ttu-id="c90cc-103">ICorProfilerCallback::ThreadAssignedToOSThread (Método)</span><span class="sxs-lookup"><span data-stu-id="c90cc-103">ICorProfilerCallback::ThreadAssignedToOSThread Method</span></span>

<span data-ttu-id="c90cc-104">Notifica al generador de perfiles que un subproceso administrado se está implementando utilizando un subproceso del sistema operativo determinado.</span><span class="sxs-lookup"><span data-stu-id="c90cc-104">Notifies the profiler that a managed thread is being implemented using a particular operating system thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c90cc-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c90cc-105">Syntax</span></span>  
  
```cpp  
HRESULT ThreadAssignedToOSThread(  
    [in] ThreadID managedThreadId,  
    [in] DWORD    osThreadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c90cc-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c90cc-106">Parameters</span></span>  

 `managedThreadId`  
 <span data-ttu-id="c90cc-107">de Identificador del subproceso administrado.</span><span class="sxs-lookup"><span data-stu-id="c90cc-107">[in] The identifier of the managed thread.</span></span>  
  
 `osThreadId`  
 <span data-ttu-id="c90cc-108">de Identificador del subproceso del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="c90cc-108">[in] The identifier of the operating system thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c90cc-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c90cc-109">Remarks</span></span>  

 <span data-ttu-id="c90cc-110">La `ThreadAssignedToOSThread` devolución de llamada existe para que el generador de perfiles pueda mantener una asignación precisa entre fibras de subprocesos del sistema operativo y subprocesos administrados.</span><span class="sxs-lookup"><span data-stu-id="c90cc-110">The `ThreadAssignedToOSThread` callback exists so that the profiler can maintain an accurate mapping across fibers of operating system threads to managed threads.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c90cc-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c90cc-111">Requirements</span></span>  

 <span data-ttu-id="c90cc-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c90cc-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c90cc-113">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c90cc-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c90cc-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c90cc-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c90cc-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c90cc-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c90cc-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="c90cc-116">See also</span></span>

- [<span data-ttu-id="c90cc-117">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c90cc-117">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
