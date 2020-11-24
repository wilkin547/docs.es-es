---
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
ms.openlocfilehash: 5a29507ca56cac4ab800845e3a88706dc7a25379
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683997"
---
# <a name="icorprofilercallbackmoduleloadfinished-method"></a><span data-ttu-id="384af-102">ICorProfilerCallback::ModuleLoadFinished (Método)</span><span class="sxs-lookup"><span data-stu-id="384af-102">ICorProfilerCallback::ModuleLoadFinished Method</span></span>

<span data-ttu-id="384af-103">Notifica al generador de perfiles que un módulo ha terminado de cargarse.</span><span class="sxs-lookup"><span data-stu-id="384af-103">Notifies the profiler that a module has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="384af-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="384af-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleLoadFinished(  
    [in] ModuleID moduleId,  
    [in] HRESULT  hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="384af-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="384af-105">Parameters</span></span>  

 `moduleId`  
 <span data-ttu-id="384af-106">de IDENTIFICADOR del módulo que ha terminado de cargarse.</span><span class="sxs-lookup"><span data-stu-id="384af-106">[in] The ID of the module that has finished loading.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="384af-107">de HRESULT que indica si el módulo se cargó correctamente.</span><span class="sxs-lookup"><span data-stu-id="384af-107">[in] An HRESULT that indicates whether the module was loaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="384af-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="384af-108">Remarks</span></span>  

 <span data-ttu-id="384af-109">El valor de `moduleId` no es válido para una solicitud de información hasta que `ModuleLoadFinished` se llama al método.</span><span class="sxs-lookup"><span data-stu-id="384af-109">The value of `moduleId` is not valid for an information request until the `ModuleLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="384af-110">Algunas partes de la carga del módulo pueden continuar después de la `ModuleLoadFinished` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="384af-110">Some parts of loading the module might continue after the `ModuleLoadFinished` callback.</span></span> <span data-ttu-id="384af-111">Un valor HRESULT de error en `hrStatus` indica un error.</span><span class="sxs-lookup"><span data-stu-id="384af-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="384af-112">Sin embargo, un valor HRESULT correcto en `hrStatus` indica solo que la primera parte de la carga del módulo se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="384af-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the module has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="384af-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="384af-113">Requirements</span></span>  

 <span data-ttu-id="384af-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="384af-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="384af-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="384af-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="384af-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="384af-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="384af-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="384af-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="384af-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="384af-118">See also</span></span>

- [<span data-ttu-id="384af-119">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="384af-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="384af-120">Método ModuleLoadStarted</span><span class="sxs-lookup"><span data-stu-id="384af-120">ModuleLoadStarted Method</span></span>](icorprofilercallback-moduleloadstarted-method.md)
