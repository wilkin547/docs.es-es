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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d15656079c087026a905d9268edf4966d8ef4034
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54503565"
---
# <a name="icorprofilercallbackmoduleloadfinished-method"></a><span data-ttu-id="bf76a-102">ICorProfilerCallback::ModuleLoadFinished (Método)</span><span class="sxs-lookup"><span data-stu-id="bf76a-102">ICorProfilerCallback::ModuleLoadFinished Method</span></span>
<span data-ttu-id="bf76a-103">Notifica al generador de perfiles que un módulo ha terminado de cargarse.</span><span class="sxs-lookup"><span data-stu-id="bf76a-103">Notifies the profiler that a module has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf76a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bf76a-104">Syntax</span></span>  
  
```  
HRESULT ModuleLoadFinished(  
    [in] ModuleID moduleId,  
    [in] HRESULT  hrStatus);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bf76a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bf76a-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="bf76a-106">[in] El identificador del módulo que ha terminado de cargarse.</span><span class="sxs-lookup"><span data-stu-id="bf76a-106">[in] The ID of the module that has finished loading.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="bf76a-107">[in] Un HRESULT que indica si el módulo se cargó correctamente.</span><span class="sxs-lookup"><span data-stu-id="bf76a-107">[in] An HRESULT that indicates whether the module was loaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bf76a-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bf76a-108">Remarks</span></span>  
 <span data-ttu-id="bf76a-109">El valor de `moduleId` no es válido para una solicitud de información hasta que el `ModuleLoadFinished` se llama al método.</span><span class="sxs-lookup"><span data-stu-id="bf76a-109">The value of `moduleId` is not valid for an information request until the `ModuleLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="bf76a-110">Algunas partes de la carga del módulo podrían continuar después de la `ModuleLoadFinished` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="bf76a-110">Some parts of loading the module might continue after the `ModuleLoadFinished` callback.</span></span> <span data-ttu-id="bf76a-111">Un error HRESULT en `hrStatus` indica un error.</span><span class="sxs-lookup"><span data-stu-id="bf76a-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="bf76a-112">Sin embargo, un valor HRESULT correcto en `hrStatus` sólo indica que la primera parte de la carga del módulo se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="bf76a-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the module has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf76a-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bf76a-113">Requirements</span></span>  
 <span data-ttu-id="bf76a-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf76a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf76a-115">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bf76a-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bf76a-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bf76a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bf76a-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf76a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf76a-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="bf76a-118">See also</span></span>
- [<span data-ttu-id="bf76a-119">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="bf76a-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="bf76a-120">ModuleLoadStarted (método)</span><span class="sxs-lookup"><span data-stu-id="bf76a-120">ModuleLoadStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadstarted-method.md)
