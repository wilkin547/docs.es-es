---
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6462fe44459228a377f4e583a8a5a1cd93d939bb
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57480369"
---
# <a name="icorprofilercallbackmoduleunloadfinished-method"></a><span data-ttu-id="0da3a-102">ICorProfilerCallback::ModuleUnloadFinished (Método)</span><span class="sxs-lookup"><span data-stu-id="0da3a-102">ICorProfilerCallback::ModuleUnloadFinished Method</span></span>
<span data-ttu-id="0da3a-103">Notifica al generador de perfiles que un módulo ha terminado de descargarse.</span><span class="sxs-lookup"><span data-stu-id="0da3a-103">Notifies the profiler that a module has finished unloading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0da3a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0da3a-104">Syntax</span></span>  
  
```  
HRESULT ModuleUnloadFinished(  
    [in] ModuleID moduleId,  
    [in] HRESULT  hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0da3a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0da3a-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="0da3a-106">[in] El identificador del módulo que se ha descargado.</span><span class="sxs-lookup"><span data-stu-id="0da3a-106">[in] The ID of the module that was unloaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="0da3a-107">[in] Un HRESULT que indica si el módulo se descargó correctamente.</span><span class="sxs-lookup"><span data-stu-id="0da3a-107">[in] An HRESULT that indicates whether the module was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0da3a-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0da3a-108">Remarks</span></span>  
 <span data-ttu-id="0da3a-109">El valor de `moduleId` no es válido para una solicitud de información después de la [ModuleUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadstarted-method.md) devuelve del método.</span><span class="sxs-lookup"><span data-stu-id="0da3a-109">The value of `moduleId` is not valid for an information request after the [ICorProfilerCallback::ModuleUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="0da3a-110">Algunas partes de la descarga de la clase podrían continuar después de la `ModuleUnloadFinished` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="0da3a-110">Some parts of unloading the class might continue after the `ModuleUnloadFinished` callback.</span></span> <span data-ttu-id="0da3a-111">Un error HRESULT en `hrStatus` indica un error.</span><span class="sxs-lookup"><span data-stu-id="0da3a-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="0da3a-112">Sin embargo, un valor HRESULT correcto en `hrStatus` sólo indica que la primera parte de la descarga del módulo se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="0da3a-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the module has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0da3a-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0da3a-113">Requirements</span></span>  
 <span data-ttu-id="0da3a-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0da3a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0da3a-115">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0da3a-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0da3a-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0da3a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0da3a-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0da3a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0da3a-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="0da3a-118">See also</span></span>
- [<span data-ttu-id="0da3a-119">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0da3a-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
