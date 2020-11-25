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
ms.openlocfilehash: 06064d82e5f572de08e56fd83923134a94d5e77b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731935"
---
# <a name="icorprofilercallback2handledestroyed-method"></a><span data-ttu-id="f14e8-102">ICorProfilerCallback2::HandleDestroyed (Método)</span><span class="sxs-lookup"><span data-stu-id="f14e8-102">ICorProfilerCallback2::HandleDestroyed Method</span></span>

<span data-ttu-id="f14e8-103">Notifica al generador de perfiles de código que se ha destruido un identificador de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="f14e8-103">Notifies the code profiler that a garbage collection handle has been destroyed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f14e8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f14e8-104">Syntax</span></span>  
  
```cpp  
HRESULT HandleDestroyed(  
    [in] GCHandleID handleId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f14e8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f14e8-105">Parameters</span></span>  

 `handleId`  
 <span data-ttu-id="f14e8-106">de IDENTIFICADOR del identificador para la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="f14e8-106">[in] The ID of the handle for the garbage collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f14e8-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f14e8-107">Requirements</span></span>  

 <span data-ttu-id="f14e8-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f14e8-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f14e8-109">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f14e8-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f14e8-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f14e8-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f14e8-111">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f14e8-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f14e8-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f14e8-112">See also</span></span>

- [<span data-ttu-id="f14e8-113">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f14e8-113">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="f14e8-114">ICorProfilerCallback2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f14e8-114">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
