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
ms.openlocfilehash: e0ff90f99c1127b5a4626f47514ba7099b5d48af
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866603"
---
# <a name="icorprofilercallbackclassloadfinished-method"></a><span data-ttu-id="6df3b-102">ICorProfilerCallback::ClassLoadFinished (Método)</span><span class="sxs-lookup"><span data-stu-id="6df3b-102">ICorProfilerCallback::ClassLoadFinished Method</span></span>
<span data-ttu-id="6df3b-103">Notifica al generador de perfiles que se ha terminado de cargar una clase.</span><span class="sxs-lookup"><span data-stu-id="6df3b-103">Notifies the profiler that a class has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6df3b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6df3b-104">Syntax</span></span>  
  
```cpp  
HRESULT ClassLoadFinished(  
    [in] ClassID classId,  
    [in] HRESULT hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6df3b-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="6df3b-105">Parameters</span></span>

- `classId`

  <span data-ttu-id="6df3b-106">\[en] identifica la clase que se cargó.</span><span class="sxs-lookup"><span data-stu-id="6df3b-106">\[in] Identifies the class that was loaded.</span></span>

- `hrStatus`

  <span data-ttu-id="6df3b-107">\[in] un valor HRESULT que indica si la clase se cargó correctamente.</span><span class="sxs-lookup"><span data-stu-id="6df3b-107">\[in] An HRESULT that indicates whether the class loaded successfully.</span></span>

## <a name="remarks"></a><span data-ttu-id="6df3b-108">Notas</span><span class="sxs-lookup"><span data-stu-id="6df3b-108">Remarks</span></span>  
 <span data-ttu-id="6df3b-109">El valor de `classId` no es válido para una solicitud de información hasta que se llama al método `ClassLoadFinished`.</span><span class="sxs-lookup"><span data-stu-id="6df3b-109">The value of `classId` is not valid for an information request until the `ClassLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="6df3b-110">Algunas partes de la carga de la clase podrían continuar después de la devolución de llamada de `ClassLoadFinished`.</span><span class="sxs-lookup"><span data-stu-id="6df3b-110">Some parts of loading the class might continue after the `ClassLoadFinished` callback.</span></span> <span data-ttu-id="6df3b-111">Un valor HRESULT de error en `hrStatus` indica un error.</span><span class="sxs-lookup"><span data-stu-id="6df3b-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="6df3b-112">Sin embargo, un valor HRESULT correcto en `hrStatus` solo indica que la primera parte de la carga de la clase se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="6df3b-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the class has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6df3b-113">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="6df3b-113">Requirements</span></span>  
 <span data-ttu-id="6df3b-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6df3b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6df3b-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6df3b-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6df3b-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6df3b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6df3b-117">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6df3b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6df3b-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="6df3b-118">See also</span></span>

- [<span data-ttu-id="6df3b-119">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6df3b-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="6df3b-120">ClassLoadStarted (método)</span><span class="sxs-lookup"><span data-stu-id="6df3b-120">ClassLoadStarted Method</span></span>](icorprofilercallback-classloadstarted-method.md)
