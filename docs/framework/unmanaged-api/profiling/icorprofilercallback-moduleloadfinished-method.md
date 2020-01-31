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
ms.openlocfilehash: 661229e5fbd5d106662f0e823a1753bd76c33311
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866174"
---
# <a name="icorprofilercallbackmoduleloadfinished-method"></a><span data-ttu-id="37ec8-102">ICorProfilerCallback::ModuleLoadFinished (Método)</span><span class="sxs-lookup"><span data-stu-id="37ec8-102">ICorProfilerCallback::ModuleLoadFinished Method</span></span>
<span data-ttu-id="37ec8-103">Notifica al generador de perfiles que un módulo ha terminado de cargarse.</span><span class="sxs-lookup"><span data-stu-id="37ec8-103">Notifies the profiler that a module has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37ec8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="37ec8-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleLoadFinished(  
    [in] ModuleID moduleId,  
    [in] HRESULT  hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="37ec8-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="37ec8-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="37ec8-106">de IDENTIFICADOR del módulo que ha terminado de cargarse.</span><span class="sxs-lookup"><span data-stu-id="37ec8-106">[in] The ID of the module that has finished loading.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="37ec8-107">de HRESULT que indica si el módulo se cargó correctamente.</span><span class="sxs-lookup"><span data-stu-id="37ec8-107">[in] An HRESULT that indicates whether the module was loaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="37ec8-108">Notas</span><span class="sxs-lookup"><span data-stu-id="37ec8-108">Remarks</span></span>  
 <span data-ttu-id="37ec8-109">El valor de `moduleId` no es válido para una solicitud de información hasta que se llama al método `ModuleLoadFinished`.</span><span class="sxs-lookup"><span data-stu-id="37ec8-109">The value of `moduleId` is not valid for an information request until the `ModuleLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="37ec8-110">Algunas partes de la carga del módulo pueden continuar después de la devolución de llamada de `ModuleLoadFinished`.</span><span class="sxs-lookup"><span data-stu-id="37ec8-110">Some parts of loading the module might continue after the `ModuleLoadFinished` callback.</span></span> <span data-ttu-id="37ec8-111">Un valor HRESULT de error en `hrStatus` indica un error.</span><span class="sxs-lookup"><span data-stu-id="37ec8-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="37ec8-112">Sin embargo, un valor HRESULT correcto en `hrStatus` solo indica que la primera parte de la carga del módulo se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="37ec8-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the module has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37ec8-113">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="37ec8-113">Requirements</span></span>  
 <span data-ttu-id="37ec8-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="37ec8-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37ec8-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="37ec8-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="37ec8-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="37ec8-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="37ec8-117">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37ec8-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37ec8-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="37ec8-118">See also</span></span>

- [<span data-ttu-id="37ec8-119">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="37ec8-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="37ec8-120">ModuleLoadStarted (método)</span><span class="sxs-lookup"><span data-stu-id="37ec8-120">ModuleLoadStarted Method</span></span>](icorprofilercallback-moduleloadstarted-method.md)
