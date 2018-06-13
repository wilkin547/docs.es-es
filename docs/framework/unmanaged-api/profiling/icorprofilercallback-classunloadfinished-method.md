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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ebf72fe4f9fae5b3d791e6eed2e9421b9f4e3296
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33450822"
---
# <a name="icorprofilercallbackclassunloadfinished-method"></a><span data-ttu-id="ca70e-102">ICorProfilerCallback::ClassUnloadFinished (Método)</span><span class="sxs-lookup"><span data-stu-id="ca70e-102">ICorProfilerCallback::ClassUnloadFinished Method</span></span>
<span data-ttu-id="ca70e-103">Notifica al generador de perfiles que una clase ha terminado de descargarse.</span><span class="sxs-lookup"><span data-stu-id="ca70e-103">Notifies the profiler that a class has finished unloading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca70e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ca70e-104">Syntax</span></span>  
  
```  
HRESULT ClassUnloadFinished(  
    [in] ClassID classId,  
    [in] HRESULT hrStatus);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ca70e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ca70e-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="ca70e-106">[in] Identifica la clase que se descargó.</span><span class="sxs-lookup"><span data-stu-id="ca70e-106">[in] Identifies the class that was unloaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="ca70e-107">[in] Un valor HRESULT que indica si la clase se descargó correctamente.</span><span class="sxs-lookup"><span data-stu-id="ca70e-107">[in] An HRESULT that indicates whether the class was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ca70e-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ca70e-108">Remarks</span></span>  
 <span data-ttu-id="ca70e-109">Algunas partes de la descarga de la clase podrían continuar después de la `ClassUnloadFinished` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="ca70e-109">Some parts of unloading the class might continue after the `ClassUnloadFinished` callback.</span></span> <span data-ttu-id="ca70e-110">Un valor HRESULT de error en `hrStatus` indica un error.</span><span class="sxs-lookup"><span data-stu-id="ca70e-110">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="ca70e-111">Sin embargo, un valor HRESULT correcto en `hrStatus` sólo indica que la primera parte de la descarga de la clase se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="ca70e-111">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the class has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca70e-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ca70e-112">Requirements</span></span>  
 <span data-ttu-id="ca70e-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca70e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca70e-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ca70e-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ca70e-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ca70e-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ca70e-116">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca70e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca70e-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="ca70e-117">See Also</span></span>  
 [<span data-ttu-id="ca70e-118">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ca70e-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="ca70e-119">ClassUnloadStarted (método)</span><span class="sxs-lookup"><span data-stu-id="ca70e-119">ClassUnloadStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classunloadstarted-method.md)
