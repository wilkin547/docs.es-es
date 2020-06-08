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
ms.openlocfilehash: d7a4f7d08e6d8698dbb58c4c2d111a47d0ccc8db
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499784"
---
# <a name="icorprofilercallback2handledestroyed-method"></a><span data-ttu-id="00fae-102">ICorProfilerCallback2::HandleDestroyed (Método)</span><span class="sxs-lookup"><span data-stu-id="00fae-102">ICorProfilerCallback2::HandleDestroyed Method</span></span>
<span data-ttu-id="00fae-103">Notifica al generador de perfiles de código que se ha destruido un identificador de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="00fae-103">Notifies the code profiler that a garbage collection handle has been destroyed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00fae-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="00fae-104">Syntax</span></span>  
  
```cpp  
HRESULT HandleDestroyed(  
    [in] GCHandleID handleId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="00fae-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="00fae-105">Parameters</span></span>  
 `handleId`  
 <span data-ttu-id="00fae-106">de IDENTIFICADOR del identificador para la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="00fae-106">[in] The ID of the handle for the garbage collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00fae-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="00fae-107">Requirements</span></span>  
 <span data-ttu-id="00fae-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="00fae-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00fae-109">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="00fae-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="00fae-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="00fae-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="00fae-111">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00fae-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00fae-112">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="00fae-112">See also</span></span>

- [<span data-ttu-id="00fae-113">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="00fae-113">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="00fae-114">ICorProfilerCallback2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="00fae-114">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
