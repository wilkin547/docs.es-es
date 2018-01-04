---
title: "ICorProfilerCallback::ModuleLoadFinished (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ModuleLoadFinished
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ModuleLoadFinished
helpviewer_keywords:
- ModuleLoadFinished method [.NET Framework profiling]
- ICorProfilerCallback::ModuleLoadFinished method [.NET Framework profiling]
ms.assetid: 050649e5-ffc0-4458-a0a4-d9ee128a219e
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 360c14ccdd67cb7609ffe2f9c49914fdda163389
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackmoduleloadfinished-method"></a><span data-ttu-id="a61b7-102">ICorProfilerCallback::ModuleLoadFinished (Método)</span><span class="sxs-lookup"><span data-stu-id="a61b7-102">ICorProfilerCallback::ModuleLoadFinished Method</span></span>
<span data-ttu-id="a61b7-103">Notifica al generador de perfiles que un módulo ha terminado de cargarse.</span><span class="sxs-lookup"><span data-stu-id="a61b7-103">Notifies the profiler that a module has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a61b7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a61b7-104">Syntax</span></span>  
  
```  
HRESULT ModuleLoadFinished(  
    [in] ModuleID moduleId,  
    [in] HRESULT  hrStatus);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a61b7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a61b7-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="a61b7-106">[in] El identificador del módulo que ha terminado de cargarse.</span><span class="sxs-lookup"><span data-stu-id="a61b7-106">[in] The ID of the module that has finished loading.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="a61b7-107">[in] Un valor HRESULT que indica si el módulo se cargó correctamente.</span><span class="sxs-lookup"><span data-stu-id="a61b7-107">[in] An HRESULT that indicates whether the module was loaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a61b7-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a61b7-108">Remarks</span></span>  
 <span data-ttu-id="a61b7-109">El valor de `moduleId` no es válido para una solicitud de información hasta que el `ModuleLoadFinished` se llama al método.</span><span class="sxs-lookup"><span data-stu-id="a61b7-109">The value of `moduleId` is not valid for an information request until the `ModuleLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="a61b7-110">Algunas partes de la carga del módulo podrían continuar después de la `ModuleLoadFinished` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="a61b7-110">Some parts of loading the module might continue after the `ModuleLoadFinished` callback.</span></span> <span data-ttu-id="a61b7-111">Un valor HRESULT de error en `hrStatus` indica un error.</span><span class="sxs-lookup"><span data-stu-id="a61b7-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="a61b7-112">Sin embargo, un valor HRESULT correcto en `hrStatus` sólo indica que la primera parte de la carga del módulo se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="a61b7-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the module has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a61b7-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a61b7-113">Requirements</span></span>  
 <span data-ttu-id="a61b7-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a61b7-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a61b7-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a61b7-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a61b7-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a61b7-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a61b7-117">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a61b7-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a61b7-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="a61b7-118">See Also</span></span>  
 [<span data-ttu-id="a61b7-119">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a61b7-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="a61b7-120">ModuleLoadStarted (método)</span><span class="sxs-lookup"><span data-stu-id="a61b7-120">ModuleLoadStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadstarted-method.md)
