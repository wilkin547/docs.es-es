---
description: 'Más información sobre: método ICorProfilerCallback2:: Finalizeableobjectqueued ('
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
ms.openlocfilehash: 62424ea60f72cee2328a143e4e50acd7af33e221
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99647926"
---
# <a name="icorprofilercallback2finalizeableobjectqueued-method"></a><span data-ttu-id="6fa26-103">ICorProfilerCallback2::FinalizeableObjectQueued (Método)</span><span class="sxs-lookup"><span data-stu-id="6fa26-103">ICorProfilerCallback2::FinalizeableObjectQueued Method</span></span>

<span data-ttu-id="6fa26-104">Notifica al generador de perfiles de código que un objeto con un finalizador se ha puesto en cola en el subproceso finalizador para la ejecución de su `Finalize` método.</span><span class="sxs-lookup"><span data-stu-id="6fa26-104">Notifies the code profiler that an object with a finalizer has been queued to the finalizer thread for execution of its `Finalize` method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fa26-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6fa26-105">Syntax</span></span>  
  
```cpp  
HRESULT FinalizeableObjectQueued(  
    [in] DWORD finalizerFlags,  
    [in] ObjectID objectID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6fa26-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6fa26-106">Parameters</span></span>  

 `finalizerFlags`  
 <span data-ttu-id="6fa26-107">de Un valor de la enumeración [COR_PRF_FINALIZER_FLAGS](cor-prf-finalizer-flags-enumeration.md) que describe aspectos del finalizador.</span><span class="sxs-lookup"><span data-stu-id="6fa26-107">[in] A value of the [COR_PRF_FINALIZER_FLAGS](cor-prf-finalizer-flags-enumeration.md) enumeration that describes aspects of the finalizer.</span></span>  
  
 `objectID`  
 <span data-ttu-id="6fa26-108">de IDENTIFICADOR del objeto que se ha puesto en la cola.</span><span class="sxs-lookup"><span data-stu-id="6fa26-108">[in] The ID of the object that has been queued.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6fa26-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6fa26-109">Requirements</span></span>  

 <span data-ttu-id="6fa26-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6fa26-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6fa26-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6fa26-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6fa26-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6fa26-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6fa26-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6fa26-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fa26-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="6fa26-114">See also</span></span>

- [<span data-ttu-id="6fa26-115">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6fa26-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="6fa26-116">ICorProfilerCallback2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6fa26-116">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
