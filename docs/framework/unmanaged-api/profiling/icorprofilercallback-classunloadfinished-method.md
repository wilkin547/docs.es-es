---
title: ICorProfilerCallback::ClassUnloadFinished (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ClassUnloadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ClassUnloadFinished
helpviewer_keywords:
- ICorProfilerCallback::ClassUnloadFinished method [.NET Framework profiling]
- ClassUnloadFinished method [.NET Framework profiling]
ms.assetid: 55674b68-678a-4747-ae06-4e91519c7305
topic_type:
- apiref
ms.openlocfilehash: 114d5d58d0d9098944299aefd0cb99a70c5da09d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700268"
---
# <a name="icorprofilercallbackclassunloadfinished-method"></a><span data-ttu-id="3a2c7-102">ICorProfilerCallback::ClassUnloadFinished (Método)</span><span class="sxs-lookup"><span data-stu-id="3a2c7-102">ICorProfilerCallback::ClassUnloadFinished Method</span></span>

<span data-ttu-id="3a2c7-103">Notifica al generador de perfiles que una clase ha terminado de descargarse.</span><span class="sxs-lookup"><span data-stu-id="3a2c7-103">Notifies the profiler that a class has finished unloading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a2c7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3a2c7-104">Syntax</span></span>  
  
```cpp  
HRESULT ClassUnloadFinished(  
    [in] ClassID classId,  
    [in] HRESULT hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3a2c7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3a2c7-105">Parameters</span></span>

- `classId`

  <span data-ttu-id="3a2c7-106">\[in] identifica la clase que se ha descargado.</span><span class="sxs-lookup"><span data-stu-id="3a2c7-106">\[in] Identifies the class that was unloaded.</span></span>

- `hrStatus`

  <span data-ttu-id="3a2c7-107">\[in] un valor HRESULT que indica si la clase se ha descargado correctamente.</span><span class="sxs-lookup"><span data-stu-id="3a2c7-107">\[in] An HRESULT that indicates whether the class was unloaded successfully.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="3a2c7-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3a2c7-108">Remarks</span></span>  

 <span data-ttu-id="3a2c7-109">Algunas partes de la descarga de la clase podrían continuar después de la `ClassUnloadFinished` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="3a2c7-109">Some parts of unloading the class might continue after the `ClassUnloadFinished` callback.</span></span> <span data-ttu-id="3a2c7-110">Un valor HRESULT de error en `hrStatus` indica un error.</span><span class="sxs-lookup"><span data-stu-id="3a2c7-110">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="3a2c7-111">Sin embargo, un valor HRESULT correcto en `hrStatus` indica solo que la primera parte de la descarga de la clase se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="3a2c7-111">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the class has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a2c7-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3a2c7-112">Requirements</span></span>  

 <span data-ttu-id="3a2c7-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3a2c7-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a2c7-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3a2c7-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3a2c7-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3a2c7-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3a2c7-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a2c7-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a2c7-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3a2c7-117">See also</span></span>

- [<span data-ttu-id="3a2c7-118">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3a2c7-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="3a2c7-119">Método ClassUnloadStarted</span><span class="sxs-lookup"><span data-stu-id="3a2c7-119">ClassUnloadStarted Method</span></span>](icorprofilercallback-classunloadstarted-method.md)
