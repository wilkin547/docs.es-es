---
description: 'Más información sobre: ICorProfilerCallback:: Moduleunloadfinished ((método)'
title: ICorProfilerCallback::ModuleUnloadFinished (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleUnloadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleUnloadFinished
helpviewer_keywords:
- ModuleUnloadFinished method [.NET Framework profiling]
- ICorProfilerCallback::ModuleUnloadFinished method [.NET Framework profiling]
ms.assetid: 185e3327-9f9c-44bc-8a5c-febea9a6bb5b
topic_type:
- apiref
ms.openlocfilehash: 32182beb879813a4e60f69494bd93799c0f66e1d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99745263"
---
# <a name="icorprofilercallbackmoduleunloadfinished-method"></a><span data-ttu-id="d3f5d-103">ICorProfilerCallback::ModuleUnloadFinished (Método)</span><span class="sxs-lookup"><span data-stu-id="d3f5d-103">ICorProfilerCallback::ModuleUnloadFinished Method</span></span>

<span data-ttu-id="d3f5d-104">Notifica al generador de perfiles que un módulo ha terminado de descargarse.</span><span class="sxs-lookup"><span data-stu-id="d3f5d-104">Notifies the profiler that a module has finished unloading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3f5d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d3f5d-105">Syntax</span></span>  
  
```cpp  
HRESULT ModuleUnloadFinished(  
    [in] ModuleID moduleId,  
    [in] HRESULT  hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d3f5d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d3f5d-106">Parameters</span></span>  

 `moduleId`  
 <span data-ttu-id="d3f5d-107">de IDENTIFICADOR del módulo que se ha descargado.</span><span class="sxs-lookup"><span data-stu-id="d3f5d-107">[in] The ID of the module that was unloaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="d3f5d-108">de HRESULT que indica si el módulo se ha descargado correctamente.</span><span class="sxs-lookup"><span data-stu-id="d3f5d-108">[in] An HRESULT that indicates whether the module was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d3f5d-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d3f5d-109">Remarks</span></span>  

 <span data-ttu-id="d3f5d-110">El valor de `moduleId` no es válido para una solicitud de información después de que el método [ICorProfilerCallback:: ModuleUnloadStarted (](icorprofilercallback-moduleunloadstarted-method.md) devuelva.</span><span class="sxs-lookup"><span data-stu-id="d3f5d-110">The value of `moduleId` is not valid for an information request after the [ICorProfilerCallback::ModuleUnloadStarted](icorprofilercallback-moduleunloadstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="d3f5d-111">Algunas partes de la descarga de la clase podrían continuar después de la `ModuleUnloadFinished` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="d3f5d-111">Some parts of unloading the class might continue after the `ModuleUnloadFinished` callback.</span></span> <span data-ttu-id="d3f5d-112">Un valor HRESULT de error en `hrStatus` indica un error.</span><span class="sxs-lookup"><span data-stu-id="d3f5d-112">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="d3f5d-113">Sin embargo, un valor HRESULT correcto en `hrStatus` indica solo que la primera parte de la descarga del módulo se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="d3f5d-113">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the module has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3f5d-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d3f5d-114">Requirements</span></span>  

 <span data-ttu-id="d3f5d-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d3f5d-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3f5d-116">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d3f5d-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d3f5d-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d3f5d-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d3f5d-118">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3f5d-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3f5d-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="d3f5d-119">See also</span></span>

- [<span data-ttu-id="d3f5d-120">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d3f5d-120">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
