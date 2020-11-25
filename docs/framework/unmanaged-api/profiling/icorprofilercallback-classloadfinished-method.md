---
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
ms.openlocfilehash: 3be00d278a92398ad282a071f3e313e5de0e65a6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700293"
---
# <a name="icorprofilercallbackclassloadfinished-method"></a><span data-ttu-id="b0afe-102">ICorProfilerCallback::ClassLoadFinished (Método)</span><span class="sxs-lookup"><span data-stu-id="b0afe-102">ICorProfilerCallback::ClassLoadFinished Method</span></span>

<span data-ttu-id="b0afe-103">Notifica al generador de perfiles que se ha terminado de cargar una clase.</span><span class="sxs-lookup"><span data-stu-id="b0afe-103">Notifies the profiler that a class has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0afe-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b0afe-104">Syntax</span></span>  
  
```cpp  
HRESULT ClassLoadFinished(  
    [in] ClassID classId,  
    [in] HRESULT hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b0afe-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b0afe-105">Parameters</span></span>

- `classId`

  <span data-ttu-id="b0afe-106">\[in] identifica la clase que se cargó.</span><span class="sxs-lookup"><span data-stu-id="b0afe-106">\[in] Identifies the class that was loaded.</span></span>

- `hrStatus`

  <span data-ttu-id="b0afe-107">\[in] un valor HRESULT que indica si la clase se cargó correctamente.</span><span class="sxs-lookup"><span data-stu-id="b0afe-107">\[in] An HRESULT that indicates whether the class loaded successfully.</span></span>

## <a name="remarks"></a><span data-ttu-id="b0afe-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b0afe-108">Remarks</span></span>  

 <span data-ttu-id="b0afe-109">El valor de `classId` no es válido para una solicitud de información hasta que `ClassLoadFinished` se llama al método.</span><span class="sxs-lookup"><span data-stu-id="b0afe-109">The value of `classId` is not valid for an information request until the `ClassLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="b0afe-110">Algunas partes de la carga de la clase podrían continuar después de la `ClassLoadFinished` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="b0afe-110">Some parts of loading the class might continue after the `ClassLoadFinished` callback.</span></span> <span data-ttu-id="b0afe-111">Un valor HRESULT de error en `hrStatus` indica un error.</span><span class="sxs-lookup"><span data-stu-id="b0afe-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="b0afe-112">Sin embargo, un valor HRESULT correcto en `hrStatus` indica solo que la primera parte de la carga de la clase se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="b0afe-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the class has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0afe-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b0afe-113">Requirements</span></span>  

 <span data-ttu-id="b0afe-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0afe-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0afe-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b0afe-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b0afe-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b0afe-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b0afe-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0afe-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0afe-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b0afe-118">See also</span></span>

- [<span data-ttu-id="b0afe-119">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b0afe-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="b0afe-120">Método ClassLoadStarted</span><span class="sxs-lookup"><span data-stu-id="b0afe-120">ClassLoadStarted Method</span></span>](icorprofilercallback-classloadstarted-method.md)
