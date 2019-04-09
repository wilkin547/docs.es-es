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
ms.openlocfilehash: 9d01f3d7485b19c076d9cd3e83aeccbcf5e728f4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59160711"
---
# <a name="icorprofilercallbackclassunloadfinished-method"></a><span data-ttu-id="2f363-102">ICorProfilerCallback::ClassUnloadFinished (Método)</span><span class="sxs-lookup"><span data-stu-id="2f363-102">ICorProfilerCallback::ClassUnloadFinished Method</span></span>
<span data-ttu-id="2f363-103">Notifica al generador de perfiles que una clase ha terminado de descargarse.</span><span class="sxs-lookup"><span data-stu-id="2f363-103">Notifies the profiler that a class has finished unloading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f363-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2f363-104">Syntax</span></span>  
  
```  
HRESULT ClassUnloadFinished(  
    [in] ClassID classId,  
    [in] HRESULT hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2f363-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2f363-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="2f363-106">[in] Identifica la clase que se ha descargado.</span><span class="sxs-lookup"><span data-stu-id="2f363-106">[in] Identifies the class that was unloaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="2f363-107">[in] Un HRESULT que indica si la clase se descargó correctamente.</span><span class="sxs-lookup"><span data-stu-id="2f363-107">[in] An HRESULT that indicates whether the class was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2f363-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2f363-108">Remarks</span></span>  
 <span data-ttu-id="2f363-109">Algunas partes de la descarga de la clase podrían continuar después de la `ClassUnloadFinished` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="2f363-109">Some parts of unloading the class might continue after the `ClassUnloadFinished` callback.</span></span> <span data-ttu-id="2f363-110">Un error HRESULT en `hrStatus` indica un error.</span><span class="sxs-lookup"><span data-stu-id="2f363-110">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="2f363-111">Sin embargo, un valor HRESULT correcto en `hrStatus` sólo indica que la primera parte de la descarga de la clase se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="2f363-111">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the class has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f363-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2f363-112">Requirements</span></span>  
 <span data-ttu-id="2f363-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2f363-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f363-114">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2f363-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2f363-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2f363-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="2f363-116">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="2f363-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2f363-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="2f363-117">See also</span></span>

- [<span data-ttu-id="2f363-118">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2f363-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="2f363-119">Método ClassUnloadStarted</span><span class="sxs-lookup"><span data-stu-id="2f363-119">ClassUnloadStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classunloadstarted-method.md)
