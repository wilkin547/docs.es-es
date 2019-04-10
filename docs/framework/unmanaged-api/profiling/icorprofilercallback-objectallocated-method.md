---
title: ICorProfilerCallback::ObjectAllocated (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ObjectAllocated
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ObjectAllocated
helpviewer_keywords:
- ObjectAllocated method [.NET Framework profiling]
- ICorProfilerCallback::ObjectAllocated method [.NET Framework profiling]
ms.assetid: eb412622-77cc-4abd-a2cd-c910fe8edd54
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c07b37e58141f7aff747bd3772be265ae0da42ac
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59222021"
---
# <a name="icorprofilercallbackobjectallocated-method"></a><span data-ttu-id="328b6-102">ICorProfilerCallback::ObjectAllocated (Método)</span><span class="sxs-lookup"><span data-stu-id="328b6-102">ICorProfilerCallback::ObjectAllocated Method</span></span>
<span data-ttu-id="328b6-103">Notifica al generador de perfiles que se ha asignado la memoria del montón de un objeto.</span><span class="sxs-lookup"><span data-stu-id="328b6-103">Notifies the profiler that memory within the heap has been allocated for an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="328b6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="328b6-104">Syntax</span></span>  
  
```  
HRESULT ObjectAllocated(  
    [in] ObjectID objectId,  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="328b6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="328b6-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="328b6-106">[in] El identificador del objeto para el que se asignó la memoria.</span><span class="sxs-lookup"><span data-stu-id="328b6-106">[in] The ID of the object for which memory was allocated.</span></span>  
  
 `classId`  
 <span data-ttu-id="328b6-107">[in] El identificador de la clase que el objeto es una instancia.</span><span class="sxs-lookup"><span data-stu-id="328b6-107">[in] The ID of the class of which the object is an instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="328b6-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="328b6-108">Remarks</span></span>  
 <span data-ttu-id="328b6-109">El `ObjectedAllocated` no se llama al método para las asignaciones en la pila o memoria no administrada.</span><span class="sxs-lookup"><span data-stu-id="328b6-109">The `ObjectedAllocated` method is not called for allocations from either the stack or unmanaged memory.</span></span> <span data-ttu-id="328b6-110">El `classId` parámetro puede hacer referencia a una clase en código administrado que no se ha cargado aún.</span><span class="sxs-lookup"><span data-stu-id="328b6-110">The `classId` parameter can refer to a class in managed code that has not been loaded yet.</span></span> <span data-ttu-id="328b6-111">El generador de perfiles recibirá una devolución de llamada de carga de clase para esa clase inmediatamente después de la `ObjectAllocated` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="328b6-111">The profiler will receive a class load callback for that class immediately after the `ObjectAllocated` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="328b6-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="328b6-112">Requirements</span></span>  
 <span data-ttu-id="328b6-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="328b6-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="328b6-114">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="328b6-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="328b6-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="328b6-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="328b6-116">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="328b6-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="328b6-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="328b6-117">See also</span></span>

- [<span data-ttu-id="328b6-118">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="328b6-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="328b6-119">Método ClassLoadStarted</span><span class="sxs-lookup"><span data-stu-id="328b6-119">ClassLoadStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadstarted-method.md)
- [<span data-ttu-id="328b6-120">Método ClassLoadFinished</span><span class="sxs-lookup"><span data-stu-id="328b6-120">ClassLoadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md)
