---
description: 'Más información sobre: método ICorProfilerCallback2:: Handledestroyed ('
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
ms.openlocfilehash: d583a2170efbb4ebe72d7eacdd60af1a089a518f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99705604"
---
# <a name="icorprofilercallback2handledestroyed-method"></a><span data-ttu-id="eeae8-103">ICorProfilerCallback2::HandleDestroyed (Método)</span><span class="sxs-lookup"><span data-stu-id="eeae8-103">ICorProfilerCallback2::HandleDestroyed Method</span></span>

<span data-ttu-id="eeae8-104">Notifica al generador de perfiles de código que se ha destruido un identificador de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="eeae8-104">Notifies the code profiler that a garbage collection handle has been destroyed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eeae8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="eeae8-105">Syntax</span></span>  
  
```cpp  
HRESULT HandleDestroyed(  
    [in] GCHandleID handleId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eeae8-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="eeae8-106">Parameters</span></span>  

 `handleId`  
 <span data-ttu-id="eeae8-107">de IDENTIFICADOR del identificador para la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="eeae8-107">[in] The ID of the handle for the garbage collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eeae8-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="eeae8-108">Requirements</span></span>  

 <span data-ttu-id="eeae8-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eeae8-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eeae8-110">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="eeae8-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="eeae8-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eeae8-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eeae8-112">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eeae8-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eeae8-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="eeae8-113">See also</span></span>

- [<span data-ttu-id="eeae8-114">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="eeae8-114">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="eeae8-115">ICorProfilerCallback2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="eeae8-115">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
