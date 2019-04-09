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
ms.openlocfilehash: f096c1f3898348141e13da44f39f2768417acd1c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59152248"
---
# <a name="icorprofilercallbackmoduleunloadfinished-method"></a><span data-ttu-id="3788b-102">ICorProfilerCallback::ModuleUnloadFinished (Método)</span><span class="sxs-lookup"><span data-stu-id="3788b-102">ICorProfilerCallback::ModuleUnloadFinished Method</span></span>
<span data-ttu-id="3788b-103">Notifica al generador de perfiles que un módulo ha terminado de descargarse.</span><span class="sxs-lookup"><span data-stu-id="3788b-103">Notifies the profiler that a module has finished unloading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3788b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3788b-104">Syntax</span></span>  
  
```  
HRESULT ModuleUnloadFinished(  
    [in] ModuleID moduleId,  
    [in] HRESULT  hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3788b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3788b-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="3788b-106">[in] El identificador del módulo que se ha descargado.</span><span class="sxs-lookup"><span data-stu-id="3788b-106">[in] The ID of the module that was unloaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="3788b-107">[in] Un HRESULT que indica si el módulo se descargó correctamente.</span><span class="sxs-lookup"><span data-stu-id="3788b-107">[in] An HRESULT that indicates whether the module was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3788b-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3788b-108">Remarks</span></span>  
 <span data-ttu-id="3788b-109">El valor de `moduleId` no es válido para una solicitud de información después de la [ModuleUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadstarted-method.md) devuelve del método.</span><span class="sxs-lookup"><span data-stu-id="3788b-109">The value of `moduleId` is not valid for an information request after the [ICorProfilerCallback::ModuleUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="3788b-110">Algunas partes de la descarga de la clase podrían continuar después de la `ModuleUnloadFinished` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="3788b-110">Some parts of unloading the class might continue after the `ModuleUnloadFinished` callback.</span></span> <span data-ttu-id="3788b-111">Un error HRESULT en `hrStatus` indica un error.</span><span class="sxs-lookup"><span data-stu-id="3788b-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="3788b-112">Sin embargo, un valor HRESULT correcto en `hrStatus` sólo indica que la primera parte de la descarga del módulo se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="3788b-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the module has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3788b-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3788b-113">Requirements</span></span>  
 <span data-ttu-id="3788b-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3788b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3788b-115">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3788b-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3788b-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3788b-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="3788b-117">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="3788b-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3788b-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="3788b-118">See also</span></span>

- [<span data-ttu-id="3788b-119">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3788b-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
