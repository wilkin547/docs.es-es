---
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
ms.openlocfilehash: 9a9fdc80c8f63dd5b004953266a5d7399655bc71
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500371"
---
# <a name="icorprofilercallbackclassloadstarted-method"></a><span data-ttu-id="f929b-102">ICorProfilerCallback::ClassLoadStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="f929b-102">ICorProfilerCallback::ClassLoadStarted Method</span></span>
<span data-ttu-id="f929b-103">Notifica al generador de perfiles que se está cargando una clase.</span><span class="sxs-lookup"><span data-stu-id="f929b-103">Notifies the profiler that a class is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f929b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f929b-104">Syntax</span></span>  
  
```cpp  
HRESULT ClassLoadStarted(  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f929b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f929b-105">Parameters</span></span>

- `classId`

  <span data-ttu-id="f929b-106">\[in] identifica la clase que se está cargando.</span><span class="sxs-lookup"><span data-stu-id="f929b-106">\[in] Identifies the class that is being loaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="f929b-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f929b-107">Remarks</span></span>  
 <span data-ttu-id="f929b-108">El valor de `classId` no es válido para una solicitud de información hasta que se llama al método [ICorProfilerCallback:: classloadfinished (](icorprofilercallback-classloadfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="f929b-108">The value of `classId` is not valid for an information request until the [ICorProfilerCallback::ClassLoadFinished](icorprofilercallback-classloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f929b-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f929b-109">Requirements</span></span>  
 <span data-ttu-id="f929b-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f929b-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f929b-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f929b-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f929b-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f929b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f929b-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f929b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f929b-114">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="f929b-114">See also</span></span>

- [<span data-ttu-id="f929b-115">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f929b-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
