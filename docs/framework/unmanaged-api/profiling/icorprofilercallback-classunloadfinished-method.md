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
ms.openlocfilehash: 5d9474f78dd8b999a37f60e0698cfd04240b897a
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866577"
---
# <a name="icorprofilercallbackclassunloadfinished-method"></a><span data-ttu-id="4ec4a-102">ICorProfilerCallback::ClassUnloadFinished (Método)</span><span class="sxs-lookup"><span data-stu-id="4ec4a-102">ICorProfilerCallback::ClassUnloadFinished Method</span></span>
<span data-ttu-id="4ec4a-103">Notifica al generador de perfiles que una clase ha terminado de descargarse.</span><span class="sxs-lookup"><span data-stu-id="4ec4a-103">Notifies the profiler that a class has finished unloading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ec4a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4ec4a-104">Syntax</span></span>  
  
```cpp  
HRESULT ClassUnloadFinished(  
    [in] ClassID classId,  
    [in] HRESULT hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4ec4a-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="4ec4a-105">Parameters</span></span>

- `classId`

  <span data-ttu-id="4ec4a-106">\[en] identifica la clase que se ha descargado.</span><span class="sxs-lookup"><span data-stu-id="4ec4a-106">\[in] Identifies the class that was unloaded.</span></span>

- `hrStatus`

  <span data-ttu-id="4ec4a-107">\[in] un valor HRESULT que indica si la clase se ha descargado correctamente.</span><span class="sxs-lookup"><span data-stu-id="4ec4a-107">\[in] An HRESULT that indicates whether the class was unloaded successfully.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="4ec4a-108">Notas</span><span class="sxs-lookup"><span data-stu-id="4ec4a-108">Remarks</span></span>  
 <span data-ttu-id="4ec4a-109">Algunas partes de la descarga de la clase podrían continuar después de la devolución de llamada de `ClassUnloadFinished`.</span><span class="sxs-lookup"><span data-stu-id="4ec4a-109">Some parts of unloading the class might continue after the `ClassUnloadFinished` callback.</span></span> <span data-ttu-id="4ec4a-110">Un valor HRESULT de error en `hrStatus` indica un error.</span><span class="sxs-lookup"><span data-stu-id="4ec4a-110">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="4ec4a-111">Sin embargo, un valor HRESULT correcto en `hrStatus` solo indica que la primera parte de la descarga de la clase se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="4ec4a-111">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the class has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ec4a-112">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="4ec4a-112">Requirements</span></span>  
 <span data-ttu-id="4ec4a-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4ec4a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ec4a-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4ec4a-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4ec4a-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4ec4a-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4ec4a-116">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ec4a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ec4a-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="4ec4a-117">See also</span></span>

- [<span data-ttu-id="4ec4a-118">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4ec4a-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="4ec4a-119">ClassUnloadStarted (método)</span><span class="sxs-lookup"><span data-stu-id="4ec4a-119">ClassUnloadStarted Method</span></span>](icorprofilercallback-classunloadstarted-method.md)
