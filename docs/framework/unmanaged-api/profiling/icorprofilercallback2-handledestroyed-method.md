---
title: ICorProfilerCallback2::HandleDestroyed (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.HandleDestroyed
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::HandleDestroyed
helpviewer_keywords:
- ICorProfilerCallback2::HandleDestroyed method [.NET Framework profiling]
- HandleDestroyed method [.NET Framework profiling]
ms.assetid: ab4f4bbd-40c7-4667-bfde-60cd73803110
topic_type:
- apiref
ms.openlocfilehash: b2618da708a1c4351b56a15af9156a68392a0d59
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865758"
---
# <a name="icorprofilercallback2handledestroyed-method"></a><span data-ttu-id="08b96-102">ICorProfilerCallback2::HandleDestroyed (Método)</span><span class="sxs-lookup"><span data-stu-id="08b96-102">ICorProfilerCallback2::HandleDestroyed Method</span></span>
<span data-ttu-id="08b96-103">Notifica al generador de perfiles de código que se ha destruido un identificador de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="08b96-103">Notifies the code profiler that a garbage collection handle has been destroyed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08b96-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="08b96-104">Syntax</span></span>  
  
```cpp  
HRESULT HandleDestroyed(  
    [in] GCHandleID handleId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="08b96-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="08b96-105">Parameters</span></span>  
 `handleId`  
 <span data-ttu-id="08b96-106">de IDENTIFICADOR del identificador para la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="08b96-106">[in] The ID of the handle for the garbage collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08b96-107">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="08b96-107">Requirements</span></span>  
 <span data-ttu-id="08b96-108">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08b96-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08b96-109">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="08b96-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="08b96-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="08b96-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="08b96-111">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08b96-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08b96-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="08b96-112">See also</span></span>

- [<span data-ttu-id="08b96-113">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="08b96-113">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="08b96-114">ICorProfilerCallback2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="08b96-114">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
