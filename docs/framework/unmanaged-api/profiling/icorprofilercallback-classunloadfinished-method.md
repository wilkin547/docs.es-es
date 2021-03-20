---
description: 'Más información sobre: ICorProfilerCallback:: Classunloadfinished ((método)'
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
ms.openlocfilehash: 7d4fd1c85d496b7adea0096b03520a14c2fab11c
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2021
ms.locfileid: "104759265"
---
# <a name="icorprofilercallbackclassunloadfinished-method"></a><span data-ttu-id="7317b-103">ICorProfilerCallback::ClassUnloadFinished (Método)</span><span class="sxs-lookup"><span data-stu-id="7317b-103">ICorProfilerCallback::ClassUnloadFinished Method</span></span>

<span data-ttu-id="7317b-104">Notifica al generador de perfiles que una clase ha terminado de descargarse.</span><span class="sxs-lookup"><span data-stu-id="7317b-104">Notifies the profiler that a class has finished unloading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7317b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7317b-105">Syntax</span></span>  
  
```cpp  
HRESULT ClassUnloadFinished(  
    [in] ClassID classId,  
    [in] HRESULT hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7317b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7317b-106">Parameters</span></span>

<span data-ttu-id="7317b-107">`classId` de Identifica la clase que se ha descargado.</span><span class="sxs-lookup"><span data-stu-id="7317b-107">`classId` [in] Identifies the class that was unloaded.</span></span>

<span data-ttu-id="7317b-108">`hrStatus` de HRESULT que indica si la clase se ha descargado correctamente.</span><span class="sxs-lookup"><span data-stu-id="7317b-108">`hrStatus` [in] An HRESULT that indicates whether the class was unloaded successfully.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="7317b-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="7317b-109">Remarks</span></span>  

 <span data-ttu-id="7317b-110">Algunas partes de la descarga de la clase podrían continuar después de la `ClassUnloadFinished` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="7317b-110">Some parts of unloading the class might continue after the `ClassUnloadFinished` callback.</span></span> <span data-ttu-id="7317b-111">Un valor HRESULT de error en `hrStatus` indica un error.</span><span class="sxs-lookup"><span data-stu-id="7317b-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="7317b-112">Sin embargo, un valor HRESULT correcto en `hrStatus` indica solo que la primera parte de la descarga de la clase se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="7317b-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the class has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7317b-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7317b-113">Requirements</span></span>  

 <span data-ttu-id="7317b-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7317b-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7317b-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7317b-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7317b-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7317b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7317b-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7317b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7317b-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7317b-118">See also</span></span>

- [<span data-ttu-id="7317b-119">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7317b-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="7317b-120">Método ClassUnloadStarted</span><span class="sxs-lookup"><span data-stu-id="7317b-120">ClassUnloadStarted Method</span></span>](icorprofilercallback-classunloadstarted-method.md)
