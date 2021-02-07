---
description: 'Más información sobre: ICorProfilerCallback:: Classloadstarted ((método)'
title: ICorProfilerCallback::ClassLoadStarted (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ClassLoadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ClassLoadStarted
helpviewer_keywords:
- ICorProfilerCallback::ClassLoadStarted method [.NET Framework profiling]
- ClassLoadStarted method [.NET Framework profiling]
ms.assetid: 9f728de8-45c2-45a5-ac4a-45660bd36ecf
topic_type:
- apiref
ms.openlocfilehash: 2474f8041b0858cbcb81d3f4042f1748cb99df3e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99706479"
---
# <a name="icorprofilercallbackclassloadstarted-method"></a><span data-ttu-id="ad542-103">ICorProfilerCallback::ClassLoadStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="ad542-103">ICorProfilerCallback::ClassLoadStarted Method</span></span>

<span data-ttu-id="ad542-104">Notifica al generador de perfiles que se está cargando una clase.</span><span class="sxs-lookup"><span data-stu-id="ad542-104">Notifies the profiler that a class is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad542-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ad542-105">Syntax</span></span>  
  
```cpp  
HRESULT ClassLoadStarted(  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ad542-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ad542-106">Parameters</span></span>

- `classId`

  <span data-ttu-id="ad542-107">\[in] identifica la clase que se está cargando.</span><span class="sxs-lookup"><span data-stu-id="ad542-107">\[in] Identifies the class that is being loaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="ad542-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ad542-108">Remarks</span></span>  

 <span data-ttu-id="ad542-109">El valor de `classId` no es válido para una solicitud de información hasta que se llama al método [ICorProfilerCallback:: classloadfinished (](icorprofilercallback-classloadfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="ad542-109">The value of `classId` is not valid for an information request until the [ICorProfilerCallback::ClassLoadFinished](icorprofilercallback-classloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad542-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ad542-110">Requirements</span></span>  

 <span data-ttu-id="ad542-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ad542-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad542-112">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ad542-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ad542-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ad542-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ad542-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad542-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad542-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="ad542-115">See also</span></span>

- [<span data-ttu-id="ad542-116">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad542-116">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
