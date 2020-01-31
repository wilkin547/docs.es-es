---
title: ICorProfilerCallback2::FinalizeableObjectQueued (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.FinalizeableObjectQueued
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::FinalizeableObjectQueued
helpviewer_keywords:
- FinalizeableObjectQueued method [.NET Framework profiling]
- ICorProfilerCallback2::FinalizeableObjectQueued method [.NET Framework profiling]
ms.assetid: 92d76893-683c-475d-9996-5bff03cdb10f
topic_type:
- apiref
ms.openlocfilehash: b9093f920a8c14247bc51471da3682c7e500afa4
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865810"
---
# <a name="icorprofilercallback2finalizeableobjectqueued-method"></a><span data-ttu-id="16381-102">ICorProfilerCallback2::FinalizeableObjectQueued (Método)</span><span class="sxs-lookup"><span data-stu-id="16381-102">ICorProfilerCallback2::FinalizeableObjectQueued Method</span></span>
<span data-ttu-id="16381-103">Notifica al generador de perfiles de código que un objeto con un finalizador se ha puesto en cola en el subproceso finalizador para la ejecución de su método `Finalize`.</span><span class="sxs-lookup"><span data-stu-id="16381-103">Notifies the code profiler that an object with a finalizer has been queued to the finalizer thread for execution of its `Finalize` method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16381-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="16381-104">Syntax</span></span>  
  
```cpp  
HRESULT FinalizeableObjectQueued(  
    [in] DWORD finalizerFlags,  
    [in] ObjectID objectID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="16381-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="16381-105">Parameters</span></span>  
 `finalizerFlags`  
 <span data-ttu-id="16381-106">de Un valor de la enumeración [COR_PRF_FINALIZER_FLAGS](cor-prf-finalizer-flags-enumeration.md) que describe aspectos del finalizador.</span><span class="sxs-lookup"><span data-stu-id="16381-106">[in] A value of the [COR_PRF_FINALIZER_FLAGS](cor-prf-finalizer-flags-enumeration.md) enumeration that describes aspects of the finalizer.</span></span>  
  
 `objectID`  
 <span data-ttu-id="16381-107">de IDENTIFICADOR del objeto que se ha puesto en la cola.</span><span class="sxs-lookup"><span data-stu-id="16381-107">[in] The ID of the object that has been queued.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16381-108">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="16381-108">Requirements</span></span>  
 <span data-ttu-id="16381-109">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="16381-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16381-110">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="16381-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="16381-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="16381-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="16381-112">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16381-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16381-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="16381-113">See also</span></span>

- [<span data-ttu-id="16381-114">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="16381-114">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="16381-115">ICorProfilerCallback2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="16381-115">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
