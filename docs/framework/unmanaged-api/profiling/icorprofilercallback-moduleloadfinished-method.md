---
description: 'Más información sobre: ICorProfilerCallback:: ModuleLoadFinished (método)'
title: ICorProfilerCallback::ModuleLoadFinished (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleLoadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleLoadFinished
helpviewer_keywords:
- ModuleLoadFinished method [.NET Framework profiling]
- ICorProfilerCallback::ModuleLoadFinished method [.NET Framework profiling]
ms.assetid: 050649e5-ffc0-4458-a0a4-d9ee128a219e
topic_type:
- apiref
ms.openlocfilehash: 960eb9edd036055069ef3f9ab3a93602ce4ef9bf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99745351"
---
# <a name="icorprofilercallbackmoduleloadfinished-method"></a><span data-ttu-id="9276d-103">ICorProfilerCallback::ModuleLoadFinished (Método)</span><span class="sxs-lookup"><span data-stu-id="9276d-103">ICorProfilerCallback::ModuleLoadFinished Method</span></span>

<span data-ttu-id="9276d-104">Notifica al generador de perfiles que un módulo ha terminado de cargarse.</span><span class="sxs-lookup"><span data-stu-id="9276d-104">Notifies the profiler that a module has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9276d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9276d-105">Syntax</span></span>  
  
```cpp  
HRESULT ModuleLoadFinished(  
    [in] ModuleID moduleId,  
    [in] HRESULT  hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9276d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9276d-106">Parameters</span></span>  

 `moduleId`  
 <span data-ttu-id="9276d-107">de IDENTIFICADOR del módulo que ha terminado de cargarse.</span><span class="sxs-lookup"><span data-stu-id="9276d-107">[in] The ID of the module that has finished loading.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="9276d-108">de HRESULT que indica si el módulo se cargó correctamente.</span><span class="sxs-lookup"><span data-stu-id="9276d-108">[in] An HRESULT that indicates whether the module was loaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9276d-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="9276d-109">Remarks</span></span>  

 <span data-ttu-id="9276d-110">El valor de `moduleId` no es válido para una solicitud de información hasta que `ModuleLoadFinished` se llama al método.</span><span class="sxs-lookup"><span data-stu-id="9276d-110">The value of `moduleId` is not valid for an information request until the `ModuleLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="9276d-111">Algunas partes de la carga del módulo pueden continuar después de la `ModuleLoadFinished` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="9276d-111">Some parts of loading the module might continue after the `ModuleLoadFinished` callback.</span></span> <span data-ttu-id="9276d-112">Un valor HRESULT de error en `hrStatus` indica un error.</span><span class="sxs-lookup"><span data-stu-id="9276d-112">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="9276d-113">Sin embargo, un valor HRESULT correcto en `hrStatus` indica solo que la primera parte de la carga del módulo se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="9276d-113">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the module has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9276d-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9276d-114">Requirements</span></span>  

 <span data-ttu-id="9276d-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9276d-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9276d-116">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9276d-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9276d-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9276d-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9276d-118">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9276d-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9276d-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="9276d-119">See also</span></span>

- [<span data-ttu-id="9276d-120">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9276d-120">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="9276d-121">Método ModuleLoadStarted</span><span class="sxs-lookup"><span data-stu-id="9276d-121">ModuleLoadStarted Method</span></span>](icorprofilercallback-moduleloadstarted-method.md)
