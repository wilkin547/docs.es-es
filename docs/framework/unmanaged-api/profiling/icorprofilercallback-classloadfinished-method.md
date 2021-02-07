---
description: 'Más información sobre: ICorProfilerCallback:: Classloadfinished ((método)'
title: ICorProfilerCallback::ClassLoadFinished (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ClassLoadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ClassLoadFinished
helpviewer_keywords:
- ClassLoadFinished method [.NET Framework profiling]
- ICorProfilerCallback::ClassLoadFinished method [.NET Framework profiling]
ms.assetid: 3dd80fbe-d62d-4d4d-acf8-5b7d0efe607e
topic_type:
- apiref
ms.openlocfilehash: ba0a6a643ab49a4e7a0ed10dda0dadff5741234d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99706428"
---
# <a name="icorprofilercallbackclassloadfinished-method"></a><span data-ttu-id="e5392-103">ICorProfilerCallback::ClassLoadFinished (Método)</span><span class="sxs-lookup"><span data-stu-id="e5392-103">ICorProfilerCallback::ClassLoadFinished Method</span></span>

<span data-ttu-id="e5392-104">Notifica al generador de perfiles que se ha terminado de cargar una clase.</span><span class="sxs-lookup"><span data-stu-id="e5392-104">Notifies the profiler that a class has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5392-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e5392-105">Syntax</span></span>  
  
```cpp  
HRESULT ClassLoadFinished(  
    [in] ClassID classId,  
    [in] HRESULT hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5392-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e5392-106">Parameters</span></span>

- `classId`

  <span data-ttu-id="e5392-107">\[in] identifica la clase que se cargó.</span><span class="sxs-lookup"><span data-stu-id="e5392-107">\[in] Identifies the class that was loaded.</span></span>

- `hrStatus`

  <span data-ttu-id="e5392-108">\[in] un valor HRESULT que indica si la clase se cargó correctamente.</span><span class="sxs-lookup"><span data-stu-id="e5392-108">\[in] An HRESULT that indicates whether the class loaded successfully.</span></span>

## <a name="remarks"></a><span data-ttu-id="e5392-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e5392-109">Remarks</span></span>  

 <span data-ttu-id="e5392-110">El valor de `classId` no es válido para una solicitud de información hasta que `ClassLoadFinished` se llama al método.</span><span class="sxs-lookup"><span data-stu-id="e5392-110">The value of `classId` is not valid for an information request until the `ClassLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="e5392-111">Algunas partes de la carga de la clase podrían continuar después de la `ClassLoadFinished` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="e5392-111">Some parts of loading the class might continue after the `ClassLoadFinished` callback.</span></span> <span data-ttu-id="e5392-112">Un valor HRESULT de error en `hrStatus` indica un error.</span><span class="sxs-lookup"><span data-stu-id="e5392-112">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="e5392-113">Sin embargo, un valor HRESULT correcto en `hrStatus` indica solo que la primera parte de la carga de la clase se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="e5392-113">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the class has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5392-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e5392-114">Requirements</span></span>  

 <span data-ttu-id="e5392-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5392-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5392-116">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e5392-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e5392-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e5392-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e5392-118">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5392-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5392-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="e5392-119">See also</span></span>

- [<span data-ttu-id="e5392-120">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e5392-120">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="e5392-121">Método ClassLoadStarted</span><span class="sxs-lookup"><span data-stu-id="e5392-121">ClassLoadStarted Method</span></span>](icorprofilercallback-classloadstarted-method.md)
